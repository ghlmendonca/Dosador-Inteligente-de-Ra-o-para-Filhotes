# 📋 Project Charter — Petdose

> **Dosador Inteligente de Ração para Filhotes**

---

| Informação | Detalhes |
| :--- | :--- |
| **Nome do Projeto** | Petdose — Dosador Inteligente de Ração para Filhotes |
| **Patrocinador** | A definir |
| **Gerente do Projeto** | Gilmar Vieira Garcia — `gilmargarcia186@gmail.com` — (64) 9 9668-5112 |
| **Equipe de Desenvolvimento** | Davi — `davirodmedeiros1@gmail.com`<br>Gustavo — `gustavoheitorlm17@gmail.com` |
| **Data de Emissão** | 26/08/2026 |
| **Versão** | 1.0 |

---

## 1. Objetivo do Projeto

Desenvolver um protótipo funcional de um dosador inteligente de ração conectado por IoT, capaz de:
* Monitorar o perfil do animal (peso, idade e fase de crescimento);
* Calcular a quantidade recomendada de alimento com base em algoritmos nutricionais;
* Realizar o fracionamento e dispensar automaticamente as porções em horários programados.

O sistema utilizará um microcontrolador **ESP32**, **sensor de peso (célula de carga com módulo HX711)** e uma **interface digital (PWA/Dashboard)** para permitir o acompanhamento do histórico de alimentação e o ajuste dinâmico das porções. 

Como evolução futura, o projeto prevê a incorporação de recursos de Inteligência Artificial para análise contínua de crescimento e identificação de padrões alimentares.

---

## 2. Justificativa

A alimentação inadequada de filhotes — por superalimentação ou subalimentação — traz prejuízos ao seu desenvolvimento físico e saúde de longo prazo. O cálculo manual e a rotina diária de dosagem frequentemente geram inconsistências na quantidade e nos horários das refeições.

O projeto **Petdose** une IoT, automação mecânica, sensores de precisão, software responsivo e inteligência de dados para otimizar a rotina dos tutores e garantir maior precisão nutricional. Além do uso doméstico, a solução possui potencial de adaptação futura para criadores, clínicas veterinárias, abrigos e aplicações agropecuárias.

---

## 3. Escopo do Projeto

### 🟢 Dentro do Escopo (In-Scope)

* Cadastro do animal (idade, peso e características básicas);
* Estimativa da necessidade diária de alimentação e conversão em gramas de ração;
* Configuração manual ou automática de horários e frequências de dispensação;
* Dispensação automática e medição da quantidade efetivamente dispensada via sensor de peso;
* Armazenamento e exibição do histórico de alimentação dos últimos 3 dias;
* Interface de acompanhamento (PWA / Dashboard web);
* Unidade de controle central utilizando **ESP32** com comunicação IoT;
* Integração do mecanismo de dispensação e sensores em uma estrutura física segura;
* Arquitetura preparada para integração futura de modelos de IA.

### 🔴 Fora do Escopo Inicial (Out-of-Scope)

* Comercialização em larga escala ou fabricação industrial;
* Obtenção de certificações definitivas do produto (ex.: ANATEL, Inmetro);
* Diagnósticos médicos ou prescrições nutricionais veterinárias definitivas;
* Aplicação inicial para animais adultos, silvestres ou pecuária.

> ⚠️ **Nota legal:** O algoritmo nutricional integrado é estritamente uma ferramenta de estimativa e automação, **não** substituindo o diagnóstico ou prescrição veterinária profissional.

---

## 4. Principais Stakeholders

| Stakeholder | Papel / Interesse | Nível de Influência |
| :--- | :--- | :---: |
| **Gerente do Projeto** | Planejamento, controle de escopo, riscos e execução geral | Alta |
| **Equipe Dev** | Desenvolvimento de Hardware, Firmware, PWA e Algoritmos | Alta |
| **Tutores / Usuários** | Operação simplificada, confiabilidade e precisão na alimentação | Alta |
| **Veterinários** | Validação técnica das diretrizes e fórmulas nutricionais | Alta |
| **Orientadores / Professores** | Avaliação acadêmica, técnica e institucional | Média |
| **Fornecedores** | Disponibilidade e entrega dos componentes eletrônicos e mecânicos | Alta |

---

## 5. Premissas

1. O **ESP32** terá capacidade de processamento suficiente para controlar os atuadores, sensores e rotinas IoT.
2. A célula de carga com módulo **HX711** apresentará precisão e repetibilidade adequadas para dosagem de ração.
3. Será possível desenvolver um mecanismo mecânico eficiente que evite travamentos ou entupimentos.
4. O aplicativo PWA se comunicará de forma estável com o ESP32 via Wi-Fi/Protocólos IoT (REST/MQTT).
5. As tabelas e fórmulas de cálculo nutricional para filhotes estarão disponíveis e validadas.
6. Haverá disponibilidade de mercado para os componentes eletroeletrônicos necessários.
7. O protótipo será testado e validado prioritariamente em ambiente controlado.

---

## 6. Restrições

1. **Orçamento:** Limitação financeira para aquisição de componentes e estrutura física.
2. **Tempo:** Prazo estrito para desenvolvimento simultâneo de hardware, firmware e software.
3. **Mecânica:** Limitações no fluxo físico de ração dependendo do tamanho e formato do grão.
4. **Segurança:** Necessidade de isolar e proteger os componentes elétricos contra o acesso do animal.
5. **Acurácia Nutricional:** Recomendações restritas a diretrizes de literatura, necessitando de validação profissional.

---

## 7. Principais Entregas

1. **Entrega 1 — Planejamento do Projeto:** Project Charter, Levantamento de Requisitos, EAP, Cronograma e Matriz de Riscos.
2. **Entrega 2 — Projeto Eletrônico:** Esquema elétrico, ESP32, sensor de peso (HX711), atuadores e circuito de alimentação.
3. **Entrega 3 — Sistema Mecânico:** Reservatório, mecanismo de dosagem/trava, suporte físico e proteção de componentes.
4. **Entrega 4 — Algoritmo Nutricional:** Lógica de estimativa energética (NEM/NECD), conversão em gramas e fracionamento diário.
5. **Entrega 5 — Interface do Usuário (PWA):** Cadastro do pet, painel de agendamento, dashboard e histórico.
6. **Entrega 6 — Integração IoT:** Comunicação ESP32 $\leftrightarrow$ PWA, sincronização de dados e modo de contingência (*failover*).
7. **Entrega 7 — Módulo de Inteligência Artificial:** Estruturação da base de dados e modelos iniciais para análise de crescimento.
8. **Entrega 8 — Protótipo Funcional Integrado:** Unificação do PWA, IoT, ESP32, sensores e estrutura física.
9. **Entrega 9 — Testes e Validação:** Testes de dosagem (margem de erro), repetibilidade, conectividade e segurança.
10. **Entrega 10 — Documentação Final:** Manual do usuário, relatório técnico, resultados e recomendações de evolução.

---

## 8. Critérios de Sucesso

* **Funcionalidade:** Dispensação automática executada conforme agendamento, com registro em histórico e controle via PWA.
* **Precisão de Dosagem:** Margem de erro de no máximo $\pm 5\%$ em condições controladas (ex.: para uma porção de $100\,\text{g}$, dispensar entre $95\,\text{g}$ e $105\,\text{g}$).
* **Confiabilidade:** Execução continuada de agendamentos sem falhas críticas ou perda de conexão.
* **Usabilidade:** Configuração e cadastro efetuados de forma simples por usuários leigos.
* **Segurança:** Isolamento mecânico e elétrico eficiente prevenindo acidentes ou danos causados pelo pet.

---

## 9. Papel e Autoridade do Gerente do Projeto

**Gerente:** Gilmar Vieira Garcia

**Responsabilidades:**
* Planejamento e controle de escopo, prazo, custo e qualidade;
* Gestão da matriz de riscos e acompanhamento das entregas;
* Coordenação técnica e operacional da equipe de desenvolvimento;
* Gestão da comunicação com patrocinadores, professores e stakeholders.

**Autoridade:** O gerente tem autoridade para priorizar tarefas, alocar recursos e propor adequações técnicas, respeitando as restrições de orçamento e prazo aprovadas.

---

## 10. Matriz de Riscos Iniciais

| Risco | Probabilidade | Impacto | Plano de Mitigação / Resposta |
| :--- | :---: | :---: | :--- |
| **Dosagem imprecisa** | Média | Alto | Calibração contínua do HX711 e testes repetitivos com amostras de peso |
| **Entupimento de ração** | Média | Alto | Testar geometrias de calha e mecanismos de vibração/agitação |
| **Falha do sensor de peso** | Média | Alto | Rotinas de tara automática e testes com sensores reservas |
| **Falha na conexão IoT** | Média | Médio | Criar lógica de agendamento local persistida na EEPROM/Flash do ESP32 |
| **Divergência nutricional** | Baixa/Média | Alto | Validar fórmulas com literatura veterinária e especialistas |
| **Danos causados pelo animal** | Média | Alto | Blindagem da eletrônica e fios com proteção física |

---

## 11. Visão do Produto & Declaração de Sucesso

### Evolução em Fases
$$
\text{Dosador Automático} \longrightarrow \text{Conexão IoT} \longrightarrow \text{App/PWA} \longrightarrow \text{Monitoramento de Crescimento} \longrightarrow \text{IA Integrada}
$$

### Declaração de Sucesso
> Desenvolver e validar um protótipo de dosador inteligente capaz de determinar, controlar e dispensar automaticamente porções de ração para filhotes, utilizando sensores, ESP32, comunicação IoT e uma interface digital PWA, proporcionando maior precisão, praticidade e segurança na nutrição do animal.