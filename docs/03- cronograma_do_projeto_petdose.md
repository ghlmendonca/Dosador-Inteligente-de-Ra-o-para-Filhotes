# Cronograma de Execução do Projeto — Petdose
**Projeto:** Dosador Inteligente de Ração para Filhotes  
**Prazo Final:** Novembro de 2026  
**Equipe:** Davi, Gilmar e Gustavo  

---

## Mês 1: Setembro de 2026 — Planejamento, Especificação e Aquisições

### Semana 1 (01/09 a 07/09)
* **[1.1]** Redação e alinhamento inicial do Project Charter (*Gilmar / Todos*)
* **[1.2]** Estruturação da EAP e Dicionário da EAP (*Gilmar*)
* **[4.1.1]** Pesquisa bibliográfica sobre fórmulas nutricionais (NRC/FEDIAF) (*Gustavo*)

### Semana 2 (08/09 a 14/09)
* **[1.1.3]** Aprovação formal do Project Charter (*Gilmar*)
* **[1.3]** Elaboração do Cronograma final e Matriz de Riscos (*Gilmar / Todos*)
* **[1.4.1]** Cotação de componentes eletrônicos e impressão 3D (*Davi*)

### Semana 3 (15/09 a 21/09)
* **[1.4.2]** Aquisição e recebimento dos componentes (ESP32, HX711, Motores) (*Davi*)
* **[2.1.1]** Modelagem de dados e layout das telas de autenticação (*Davi*)
* **[3.1.1]** Configuração do ambiente de desenvolvimento ESP32 (PlatformIO/Arduino) (*Gilmar*)

### Semana 4 (22/09 a 30/09)
* **[1.5]** Consolidação do relatório de status do Mês 1 (*Gilmar*)
* **[2.1.2]** Implementação do fluxo de autenticação e sessão de usuário no PWA (*Davi*)
* **[4.1.2]** Codificação das equações de Gasto Energético (NEM/NECD) (*Gustavo*)

---

## Mês 2: Outubro de 2026 — Desenvolvimento Paralelo e Integração

### Semana 5 (01/10 a 07/10)
* **[2.2]** Módulo de Cadastro do Animal no PWA (*Davi*)
* **[3.2]** Integração do módulo HX711 e célula de carga ao ESP32 (*Gilmar*)
* **[4.2]** Módulo de conversão calórica e cálculo de gramas de ração (*Gustavo*)
* **[3.5.1]** Modelagem CAD 3D do chassi e reservatório (*Gilmar / Davi*)

### Semana 6 (08/10 a 14/10)
* **[2.3]** Desenvolvimento do Dashboard e histórico de 3 dias no PWA (*Davi*)
* **[3.3]** Testes e controle PWM do atuador/mecanismo de dispensação (*Gilmar*)
* **[4.3]** Implementação da curva de crescimento de filhotes por porte (*Gustavo*)
* **[3.5.2]** Impressão/Fabricação das partes físicas do protótipo (*Gilmar / Davi*)

### Semana 7 (15/10 a 21/10)
* **[2.4 & 2.5]** Painel de agendamento e notificações no PWA (*Davi*)
* **[3.4 & 3.5.3]** Montagem do circuito final, fonte de alimentação e estrutura física (*Gilmar / Todos*)
* **[4.4]** Lógica de fracionamento diário e limites de segurança (*Gustavo*)
* **[5.1.1]** Definição e configuração do broker/protocolo de comunicação IoT (*Davi / Gilmar*)

### Semana 8 (22/10 a 31/10)
* **[5.1.2 & 5.1.3]** Integração de envio/recebimento de telemetria ESP32 ↔ PWA (*Gilmar / Davi*)
* **[5.2]** Configuração do Banco de Dados em Nuvem e salvamento de logs (*Davi / Gustavo*)
* **[5.3]** Programação da rotina de operação offline no ESP32 (*Gilmar*)
* **[5.4]** Estruturação do modelo/regras de IA para ajuste automático (*Gustavo*)

---

## Mês 3: Novembro de 2026 — Testes, Validação e Encerramento

### Semana 9 (01/11 a 07/11)
* **[6.1]** Bateria de testes de precisão da dosagem (Meta: erro ≤ ±5%) (*Todos*)
* **[6.2]** Testes mecânicos de entupimento, travamento e repetibilidade (*Gilmar*)
* **[6.3]** Testes de latência de comunicação e reconexão Wi-Fi (*Davi / Gilmar*)

### Semana 10 (08/11 a 15/11)
* **[6.4]** Testes de segurança física/elétrica contra acesso do animal (*Gilmar / Todos*)
* **[6.5]** Validação do algoritmo nutricional junto a tabelas/profissionais (*Gustavo*)
* **[7.1]** Início da compilação da documentação técnica da arquitetura (*Gilmar / Davi*)

### Semana 11 (16/11 a 22/11)
* **[7.2]** Elaboração do Manual do Usuário e Guia do PWA (*Davi / Gilmar*)
* **[7.3]** Consolidação do Relatório Final de Testes e Desempenho (*Gustavo / Gilmar*)
* **[7.4.2]** Gravação de vídeos de demonstração prática do protótipo em funcionamento (*Todos*)

### Semana 12 (23/11 a 30/11)
* **[7.4.1]** Finalização dos slides e ensaio da apresentação final (*Todos*)
* **[7.4]** Entrega da documentação final e apresentação para a banca/stakeholders (*Todos*)

---

## Resumo dos Marcos de Conclusão

| Marco  | Descrição | Data Limite | Responsável Principal |
| :---   | :----                                           | :---      | :--- |
| **M1** | Project Charter & EAP Aprovados                 | 14/09/2026 | Gilmar |
| **M2** | Componentes Adquiridos e Firmware Base Pronto   | 30/09/2026 | Davi / Gilmar |
| **M3** | PWA Funcional (Telas, Cadastro e Agendamento)   | 15/10/2026 | Davi |
| **M4** | Estrutura Física e Circuito Eletrônico Montados | 20/10/2026 | Gilmar |
| **M5** | Algoritmo Nutricional Codificado                | 21/10/2026 | Gustavo |
| **M6** | Integração Completa IoT (ESP32 + Nuvem + PWA)   | 31/10/2026 | Davi / Gilmar |
| **M7** | Testes de Dosagem e Precisão Concluídos (±5%)   | 07/11/2026 | Todos |
| **M8** | Documentação Técnica e Manual do Usuário        | 22/11/2026 | Davi / Gilmar |
| **M9** | Apresentação Final e Encerramento do Projeto    | 30/11/2026 | Todos |
