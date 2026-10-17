# 🎯 Declaração de Escopo e EAP — Petdose

> **Gerenciamento de Escopo e Estrutura Analítica do Projeto (EAP / WBS)**

---

## 📐 1. Contexto e Complexidade do Projeto

Projetos como o **Petdose** possuem alta complexidade porque envolvem múltiplos domínios técnicos simultaneamente:
- **Hardware & Mecânica:** Estrutura física, reservatório e mecânica de dispensação.
- **Firmware / Sistema Embarcado:** Programação do ESP32, leitura de sensores e acionamento de atuadores.
- **Software Web/Mobile (PWA):** Interface para tutor, cadastro do pet, agendamentos e visualização de telemetria.
- **Algoritmos Científicos (Nutrição):** Lógica matemática para estimativa nutricional (NEM/NECD) e conversão em gramas.
- **Inteligência Artificial & IoT:** Tratamento de dados de telemetria, conectividade em nuvem e modelo preditivo/corretivo de dosagem.

A **Estrutura Analítica do Projeto (EAP)** ajuda a organizar e dividir etapas, tarefas e partes do projeto em pacotes de trabalho gerenciáveis, garantindo execução eficiente e minimizando riscos de falhas de comunicação ou perda de progresso entre as áreas.

---

## 📌 2. Declaração do Escopo

### 🟢 O que FAZ PARTE do Projeto (In-Scope)
- Desenvolvimento do protótipo físico com reservatório, mecanismo de fluxo e proteção para componentes.
- Integração da unidade de controle (ESP32) com célula de carga (módulo HX711) e dispensador.
- Desenvolvimento de PWA para cadastro do animal, configuração de porções e horários de alimentação.
- Implementação da lógica de cálculo nutricional para filhotes e conversão calórica em massa de ração ($g$).
- Comunicação bidirecional IoT (ESP32 $\longleftrightarrow$ Nuvem $\longleftrightarrow$ PWA).
- Mecanismo de operação em modo offline (*failover*) no ESP32 caso haja queda de conexão.
- Histórico de dispensação e telemetria dos últimos 3 dias.
- Bateria de testes de precisão ($\pm 5\%$), repetibilidade, segurança e validação dos cálculos.

### 🔴 O que NÃO FAZ PARTE do Projeto (Out-of-Scope)
- Fabricação industrial ou produção em larga escala.
- Certificação formal junto a órgãos reguladores (ANATEL, Inmetro, etc.).
- Diagnósticos ou prescrições médicas veterinárias definitivas.
- Alimentação de animais adultos, animais silvestres ou de pecuária.
- Desenvolvimento de app nativo em lojas (iOS/Android) — o foco inicial é PWA.

---

## 🌳 3. Estrutura Analítica do Projeto (EAP / WBS)

```
EAP PETDOSE — DOSADOR INTELIGENTE DE RAÇÃO
│
├── 1.0 GERENCIAMENTO DO PROJETO
│   ├── 1.1 Elaboração e Aprovação do Project Charter
│   ├── 1.2 Estruturação da EAP e Dicionário da EAP
│   ├── 1.3 Elaboração do Cronograma e Matriz de Riscos
│   ├── 1.4 Planejamento Orçamentário e Aquisição de Componentes
│   └── 1.5 Reuniões de Acompanhamento e Relatórios de Status
│
├── 2.0 INTERFACE DA APLICAÇÃO (PWA) E SISTEMA DE USUÁRIO
│   ├── 2.1 Módulo de Autenticação e Perfil de Usuário (Login/Cadastro do Tutor)
│   ├── 2.2 Módulo de Cadastro do Animal (Nome, Raça, Idade, Peso Inicial, Porte)
│   ├── 2.3 Dashboard Principal e Visualização de Histórico (Últimos 3 dias)
│   ├── 2.4 Painel de Configuração de Agendamentos (Horários e Frequência)
│   └── 2.5 Sistema de Notificações, Alertas e Status de Conexão
│
├── 3.0 HARDWARE E SISTEMA MECÂNICO (EMBARCADO)
│   ├── 3.1 Unidade de Controle Principal (Programação e Configuração do ESP32)
│   ├── 3.2 Sistema de Pesagem (Célula de Carga + Módulo HX711 e Calibração)
│   ├── 3.3 Mecanismo de Dispensação e Controle de Fluxo (Motor/Servo e Calha)
│   ├── 3.4 Dimensionamento Eletrônico e Circuito de Alimentação (Fonte/Proteção)
│   └── 3.5 Estrutura Física e Reservatório (Modelagem e Proteção Contra Acesso do Pet)
│
├── 4.0 ALGORITMO NUTRICIONAL E PLANEJAMENTO DE CRESCIMENTO
│   ├── 4.1 Lógica de Cálculo do Gasto Energético (NEM/NECD para Filhotes)
│   ├── 4.2 Módulo de Conversão Calórica (Necessidade Calórica -> Gramas de Ração)
│   ├── 4.3 Sistema de Planejamento de Crescimento (Tabelas de Curva de Crescimento)
│   └── 4.4 Lógica de Fracionamento e Divisão Diária de Porções
│
├── 5.0 INTEGRAÇÃO IOT E RECURSOS DE INTELIGÊNCIA ARTIFICIAL
│   ├── 5.1 Protocolo de Comunicação ESP32 ↔ PWA (MQTT / WebSockets / REST API)
│   ├── 5.2 Banco de Dados em Nuvem (Armazenamento de Telemetria e Registros)
│   ├── 5.3 Módulo de Operação Local e Contingência (Failover sem Internet)
│   └── 5.4 Modelo de IA para Correção da Dose (Ajuste Fino com Base na Medição/Evolução)
│
├── 6.0 TESTES, QUALIDADE E VALIDAÇÃO
│   ├── 6.1 Testes de Precisão da Dosagem (Metas de Margem de Erro ±5%)
│   ├── 6.2 Testes de Repetibilidade, Entupimento e Disparo Mecânico
│   ├── 6.3 Testes de Comunicação IoT e Latência da Interface PWA
│   ├── 6.4 Testes de Segurança Elétrica e Resistência Física do Protótipo
│   └── 6.5 Validação dos Cálculos Nutricionais com Literatura/Veterinários
│
└── 7.0 DOCUMENTAÇÃO, IMPLEMENTAÇÃO E ENCERRAMENTO
    ├── 7.1 Documentação Técnica da Arquitetura (Hardware, Firmware e Software)
    ├── 7.2 Manual do Usuário e Guia de Instalação do PWA
    ├── 7.3 Relatório Final de Testes e Desempenho do Protótipo
    └── 7.4 Apresentação Final e Demonstração do Projeto
```

---

## 📖 4. Dicionário Sucinto da EAP

| Nível 1 | Descrição do Nível | Foco Principal de Entrega |
| :--- | :--- | :--- |
| **1.0 Gerenciamento do Projeto** | Governança, acompanhamento de riscos, planejamento financeiro e cronograma. | Documentação de gestão e relatórios de progresso. |
| **2.0 Interface PWA** | Desenvolvimento da aplicação frontend progressiva e responsiva. | Telas de cadastro, dashboard, histórico e agendamento. |
| **3.0 Hardware e Mecânica** | Modelagem da estrutura física, integração de sensores e circuito de alimentação. | Protótipo físico montado com ESP32 e célula de carga. |
| **4.0 Algoritmo Nutricional** | Codificação das fórmulas e tabelas nutricionais para filhotes. | Módulo lógico de cálculo de porções em gramas. |
| **5.0 Conectividade & IA** | Integração em nuvem, persistência de dados, tolerância a falhas e IA preditiva. | Sistema de mensageria IoT e modelo de ajuste de dose. |
| **6.0 Testes & Validação** | Testes integrados de dosagem, repetibilidade, segurança física e elétrica. | Relatório de homologação do protótipo. |
| **7.0 Documentação & Fechamento** | Consolidação técnica, manuais de operação e apresentação acadêmica/executiva. | Entregáveis finais do projeto. |