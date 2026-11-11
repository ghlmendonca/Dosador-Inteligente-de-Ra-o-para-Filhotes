# Plano da Qualidade — Projeto Petdose

**Projeto:** Petdose — Dosador Inteligente de Ração para Filhotes  
**Arquivo de Referência:** `docs/07-plano-da-qualidade.md`  
**Equipe:** Davi, Gilmar e Gustavo  
**Data:** Setembro de 2026  
**Versão:** 1.0  

---

## 1. Introdução e Objetivos da Qualidade

O objetivo deste Plano de Qualidade é estabelecer critérios objetivos, métricas verificáveis e processos formais de teste e inspeção para garantir que o protótipo do **Petdose** atinja altos padrões de exatidão, confiabilidade e segurança.

O plano abrange dois pilares essenciais:
* **Qualidade do Produto:** Garante o correto funcionamento do hardware, firmware, interface PWA, precisão da balança e algoritmos nutricionais.
* **Qualidade do Processo:** Garante a padronização no desenvolvimento, reprodutibilidade dos testes, controle de versões de código/esquemáticos e documentação técnica robusta.

---

## 2. Métricas Principais da Qualidade

As entregas do projeto serão avaliadas com base nas quatro métricas centrais de sistemas embarcados e IoT:

1. **Exatidão (Precisão de Dosagem):** Margem de erro na medição do peso e dispensa da porção programada.
2. **Latência (Tempo de Resposta):** Tempo transcorrido entre o comando emitido na interface PWA/Nuvem e a execução física pelo ESP32.
3. **Disponibilidade & Resiliência:** Capacidade de operação do sistema (especialmente execução de agendamentos salvos localmente mesmo sem sinal de Wi-Fi).
4. **Conformidade Nutricional:** Acurácia das recomendações calóricas e fracionamento de ração frente às normas veterinárias padrão (NRC/FEDIAF).

---

## 3. Tabela de Planejamento da Qualidade (Qualidade do Produto e Controle)

A tabela a seguir relaciona os pacotes de trabalho da EAP do Petdose aos seus respectivos requisitos verificáveis, critérios de aceitação numéricos, métodos de ensaio, responsáveis e evidências geradas.

| ID/EAP | Requisito | Critério de Aceitação | Teste / Inspeção | Responsável | Evidência Gerada |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **2.1 / 2.2** | Autenticação e Cadastro do Pet (PWA) | Tempo de resposta na gravação do cadastro $< 2,0\text{s}$; validação obrigatória de campos numéricos (peso $> 0\text{kg}$). | Teste de interface (UI) digitando valores limites e dados inválidos. | Davi | Logs do Firebase/Banco de Dados e Capturas de Tela. |
| **2.4** | Agendamento Remoto de Porções | Interface deve permitir programar até 6 refeições diárias sem perda de dados ao atualizar a página. | Ensaio funcional no PWA com recarga de página e verificação de persistência. | Davi | Relatório de testes de Usabilidade e PWA storage log. |
| **3.1 / 5.3** | Operação Offline do ESP32 | Execução pontual da dosagem agendada mesmo com Wi-Fi desconectado (tolerância temporal de $\pm 5\text{s}$). | Desligamento forçado do roteador Wi-Fi durante o horário programado de alimentação. | Gilmar | Log serial do ESP32 via monitor de depuração (NVS flash log). |
| **3.2** | Exatidão da Pesagem (HX711) | Erro absoluto de medição de peso $\le \pm 2\text{g}$ na faixa de $10\text{g}$ a $500\text{g}$. | Ensaio de calibração com pesos de aferição padrão ($50\text{g}$, $100\text{g}$, $200\text{g}$). | Gilmar | Tabela de calibração e curvas de erro em planilha eletrônica. |
| **3.3 / 6.1** | Precisão na Dispensação da Ração | Margem de erro total da porção dispensada $\le \pm 5\%$ da quantidade programada (ex: $100\text{g} \rightarrow 95\text{g}$ a $105\text{g}$). | Bateria de 50 dispensações consecutivas com medição em balança analítica externa. | Gilmar / Todos | Relatório estatístico de dosagem (desvio padrão e histograma de massa). |
| **3.5** | Segurança Mecânica e Proteção Física | Zero acesso do animal aos componentes eletrônicos e cabos; resistência do reservatório a tombamento. | Inspeção visual e teste mecânico de impacto leve/estresse físico no protótipo montado. | Gilmar / Davi | Checklists de inspeção física assinado e registros fotográficos. |
| **4.1 / 4.2** | Cálculo da Necessidade Energética (NEM/NECD) | Variação $< 1\%$ entre o valor calculado pelo algoritmo e o valor de controle manual via fórmula NRC/FEDIAF. | Teste unitário automatizado cobrindo 20 cenários de raças, idades e pesos de filhotes. | Gustavo | Script de teste em Python/Jest e planilha comparativa de referência. |
| **5.1 / 6.3** | Latência de Comunicação IoT (PWA $\leftrightarrow$ ESP32) | Tempo de resposta para o comando "Dispensar Agora" ser acionado na placa $\le 3,0\text{s}$ em rede $4\text{G}/2.4\text{GHz}$. | Medição de carimbo de data/hora (*timestamp*) entre a emissão do comando no app e recepção no ESP32. | Davi / Gilmar | Logs de comunicação MQTT/WebSocket com marcação de tempo. |

---

## 4. Gestão de Não Conformidades (Garantia do Processo)

Caso qualquer teste de inspeção ou ensaio técnico falhe ou apresente resultados fora dos critérios de aceitação definidos na tabela acima, a equipe adotará estritamente o fluxo padronizado de **Gestão de Não Conformidades**:

```text
  ┌────────────┐     ┌────────────┐     ┌──────────────────────┐     ┌───────────┐     ┌──────────┐
  │ 1. DETECTAR│ ──> │ 2. REGISTRAR│ ──> │ 3. INVESTIGAR CAUSA  │ ──> │ 4. CORRIGIR│ ──> │5. RETESTAR│
  └────────────┘     └────────────┘     └──────────────────────┘     └───────────┘     └──────────┘
```

1. **Detectar:** Identificação da falha durante a execução dos procedimentos de teste (ex: desvio de dosagem em $8\%$).
2. **Registrar:** Abertura formal de uma *Issue* no repositório GitHub com a *label* `bug` / `não-conformidade`, contendo a descrição da falha, logs e condições do ambiente.
3. **Investigar Causa Raiz:** Reunião técnica entre os responsáveis pelo módulo (ex: verificar se a falha na dosagem é mecânica, de travamento por tamanho do grão de ração ou rampa de desaceleração do motor).
4. **Corrigir:** Aplicação da Ação Corretiva (ex: ajuste no algoritmo de tara/desaceleração do firmware ou alteração na geometria da calha).
5. **Retestar:** Repetição completa do protocolo de teste original. A não conformidade só será dada como encerrada após a emissão de uma nova evidência que atenda ao critério de aceitação.

---

## 5. Registro do Uso de Inteligência Artificial

Em conformidade com as diretrizes do projeto, o uso de ferramentas de Inteligência Artificial no planejamento e estruturação da qualidade foi devidamente registrado e auditado pela equipe técnica.

### 5.1 Prompt Estruturado Utilizado
> *"Atue como um Engenheiro de Garantia da Qualidade (QA) de Sistemas Embarcados e IoT. Com base na EAP do projeto Petdose (dosador inteligente de ração com ESP32, célula de carga HX711 e PWA), sugira uma tabela de planejamento da qualidade. Inclua critérios de aceitação numéricos objetivos (ex: tolerância de massa em gramas, latência em segundos, precisão nutricional), métodos de teste e evidências para as entregas das fases de hardware, software, algoritmo e integração. Garanta que a margem de erro da dosagem seja de até $\pm 5\%$."*

### 5.2 Análise Crítica e Revisão Humana
* **Sugestões da IA Aprovadas:** A estrutura dos critérios de aceitação numéricos, a inclusão do ensaio estatístico de 50 dispensações para validação da célula de carga e os limites de latência IoT foram mantidos na íntegra por estarem perfeitamente alinhados ao escopo do Project Charter.
* **Ajustes e Revisões Feitas pela Equipe:**
  1. A IA havia sugerido uma tolerância de pesagem do HX711 de $\pm 0,1\text{g}$, o que foi considerado inviável na revisão técnica devido à vibração gerada pelo motor do dosador. O critério foi ajustado pragmaticamente para $\le \pm 2\text{g}$.
  2. A IA não havia previsto a perda de sinal Wi-Fi no teste de operação local do ESP32. A equipe adicionou explicitamente o teste de desligamento forçado do roteador para validar o requisito de resiliência (operação offline).

---

## 6. Publicação e Controle de Versões

Este documento está publicado no repositório oficial do projeto no caminho `docs/07-plano-da-qualidade.md` e devidamente vinculado na seção de documentação do arquivo `README.md`. Qualquer alteração nas métricas de qualidade exige a aprovação do Gerente do Projeto (Gilmar Garcia) e revisão dos responsáveis técnicos.