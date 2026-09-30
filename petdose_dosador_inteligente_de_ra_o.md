# 🐾 Petdose — Dosador Inteligente de Ração para Filhotes

> **Protótipo funcional de um dosador de ração automatizado, conectado via IoT (ESP32) e integrado a uma interface digital (PWA), focado na precisão nutricional e saúde de filhotes.**

---

## 📌 Sumário
- [Sobre o Projeto](#-sobre-o-projeto)
- [Justificativa](#-justificativa)
- [Objetivos](#-objetivos)
- [Escopo do Projeto](#-escopo-do-projeto)
- [Arquitetura e Componentes](#-arquitetura-e-componentes)
- [Estrutura Analítica do Projeto (EAP)](#-estrutura-analítica-do-projeto-eap)
- [Equipe e Stakeholders](#-equipe-e-stakeholders)
- [Matriz de Riscos](#-matriz-de-riscos)
- [Visão do Produto e Futuro](#-visão-do-produto-e-futuro)
- [Aviso Legal (Disclaimer)](#-aviso-legal-disclaimer)

---

## 📖 Sobre o Projeto

O **Petdose** é uma solução que une **Internet das Coisas (IoT)**, **Automação** e **Engenharia de Software** para automatizar e otimizar a alimentação de cães em fase de crescimento. 

A partir do cadastro de informações como peso, idade, raça e porte, o sistema estima a necessidade calórica diária, realiza o fracionamento adequado das refeições e efetua o disparo automático das porções nos horários programados, acompanhado do monitoramento de telemetria e peso em tempo real.

---

## 💡 Justificativa

A alimentação inadequada na fase de filhote — seja por superalimentação ou subalimentação — causa impactos diretos na saúde do animal a curto e longo prazo. Como as necessidades nutricionais mudam rapidamente durante o crescimento, a medição e o fracionamento manuais tornam-se suscetíveis a erros humanos ou à falta de rotina por parte dos tutores.

O **Petdose** resolve esse problema ao automatizar a dispensação com precisão baseada em pesagem contínua via **célula de carga**, permitindo ainda que o tutor acompanhe o histórico e métricas pelo aplicativo móvel/PWA.

---

## 🎯 Objetivos

### Objetivo Geral
Desenvolver e validar um protótipo funcional de dosador inteligente de ração conectado por IoT, controlado por um **ESP32**, capaz de calcular, fracionar, agendar e dispensar porções de ração com margem de erro reduzida.

### Critérios de Sucesso
* **Precisão na Dosagem:** Margem de erro de no máximo **$\pm 5\%$** em condições controladas (ex: para $100\,\text{g}$, dispensar entre $95\,\text{g}$ e $105\,\text{g}$).
* **Confiabilidade:** Execução dos agendamentos programados sem falhas operacionais significativas.
* **Usabilidade:** Interface PWA intuitiva permitindo cadastro do pet, acompanhamento e configuração de horários por qualquer perfil de usuário.
* **Segurança Mecânica e Elétrica:** Proteção física contra acesso do animal às partes eletrônicas e ao reservatório.

---

## 📋 Escopo do Projeto

### 🟢 Dentro do Escopo
* Cadastro do animal (nome, idade, peso, porte, características).
* Algoritmo de estimativa de necessidade calórica diária e conversão para gramas.
* Configuração e execução de agendamentos para dispensação.
* Sistema mecânico de dispensação com controle de fluxo.
* Medição de porções via célula de carga (módulo HX711) e controle pelo ESP32.
* Registro de histórico de alimentação dos últimos 3 dias.
* Interface PWA / Dashboard web conectada via protocolo IoT (MQTT/REST).
* Arquitetura preparada para integração futura de Inteligência Artificial.

### 🔴 Fora do Escopo Inicial
* Comercialização em larga escala ou fabricação industrial.
* Certificações definitivas de produtos eletrônicos (ex: ANATEL, Inmetro).
* Diagnósticos ou prescrições médicas veterinárias definitivas.
* Aplicação para animais adultos, silvestres ou de pecuária nesta primeira fase.

---

## 🛠️ Arquitetura e Componentes

### Diagrama do Fluxo de Integração
$$\text{PWA (App)} \longleftrightarrow \text{Broker IoT / Nuvem} \longleftrightarrow \text{ESP32} \longrightarrow \text{Sensores/Atuadores} \longrightarrow \text{Dispensação}$$

### Principais Componentes
* **Microcontrolador:** ESP32 (Wi-Fi + Bluetooth).
* **Sensores:** Célula de carga com módulo conversor A/D **HX711**.
* **Atuadores:** Servomotor ou Motor DC para controle de abertura/trava da calha.
* **Software / Front-End:** PWA (Progressive Web App) responsivo.
* **Comunicação:** REST API / WebSockets / MQTT.

---

## 📂 Estrutura Analítica do Projeto (EAP)

```text
EAP — PETDOSE
│
├── 1.0 GERENCIAMENTO DO PROJETO
│   ├── 1.1 Elaboração e Aprovação do Project Charter
│   ├── 1.2 Estruturação da EAP e Dicionário
│   ├── 1.3 Cronograma e Matriz de Riscos
│   ├── 1.4 Planejamento Orçamentário e Aquisição de Componentes
│   └── 1.5 Reuniões de Acompanhamento e Relatórios
│
├── 2.0 INTERFACE DA APLICAÇÃO (PWA)
│   ├── 2.1 Módulo de Autenticação / Perfil
│   ├── 2.2 Módulo de Cadastro do Animal
│   ├── 2.3 Dashboard e Histórico (3 dias)
│   ├── 2.4 Painel de Agendamento e Horários
│   └── 2.5 Notificações e Status de Conexão
│
├── 3.0 HARDWARE E SISTEMA MECÂNICO
│   ├── 3.1 Firmware da Unidade de Controle (ESP32)
│   ├── 3.2 Sistema de Pesagem (Célula de Carga + HX711)
│   ├── 3.3 Mecanismo de Dispensação e Controle de Fluxo
│   ├── 3.4 Dimensionamento do Circuito Eletrônico e Alimentação
│   └── 3.5 Estrutura Física e Reservatório Protegido
│
├── 4.0 ALGORITMO NUTRICIONAL
│   ├── 4.1 Cálculo de Gasto Energético (NEM/NECD)
│   ├── 4.2 Módulo de Conversão Calórica → Gramas
│   ├── 4.3 Sistema de Planejamento de Curva de Crescimento
│   └── 4.4 Lógica de Fracionamento Diário
│
├── 5.0 INTEGRAÇÃO IOT E IA
│   ├── 5.1 Protocolo de Comunicação ESP32 ↔ PWA
│   ├── 5.2 Banco de Dados em Nuvem (Telemetria)
│   ├── 5.3 Módulo de Operação Local e Contingência (Failover)
│   └── 5.4 Modelo de IA para Calibração de Dose
│
├── 6.0 TESTES, QUALIDADE E VALIDAÇÃO
│   ├── 6.1 Teste de Precisão da Dosagem (Margem ±5%)
│   ├── 6.2 Testes Mecânicos e Antientupimento
│   ├── 6.3 Teste de Comunicação IoT e Latência
│   ├── 6.4 Teste de Segurança Elétrica e Estrutural
│   └── 6.5 Validação dos Cálculos Nutricionais
│
└── 7.0 DOCUMENTAÇÃO E ENCERRAMENTO
    ├── 7.1 Documentação Técnica da Arquitetura
    ├── 7.2 Manual do Usuário e Guia do PWA
    ├── 7.3 Relatório Final de Testes
    └── 7.4 Apresentação e Demonstração Final
```

---

## 👥 Equipe e Stakeholders

### Equipe de Gerenciamento e Desenvolvimento
* **Gilmar Vieira Garcia** — Gerente do Projeto (`gilmargarcia186@gmail.com`)
* **Davi** — Desenvolvedor / Integrador (`davirodmedeiros1@gmail.com`)
* **Gustavo** — Desenvolvedor / Hardware

### Principais Stakeholders
| Stakeholder | Papel / Interesse | Nível de Influência |
| :--- | :--- | :---: |
| **Gerente de Projeto** | Planejamento, controle e execução | Alta |
| **Equipe Dev** | Construção de Hardware, Firmware e PWA | Alta |
| **Tutores / Usuários** | Operação intuitiva e confiabilidade na alimentação | Alta |
| **Veterinários** | Validação técnica das diretrizes nutricionais | Alta |
| **Orientadores / Professores** | Avaliação acadêmica e técnica | Média |

---

## ⚠️ Matriz de Riscos

| Risco | Probabilidade | Impacto | Plano de Mitigação |
| :--- | :---: | :---: | :--- |
| **Dosagem imprecisa** | Média | Alto | Calibração constante do HX711 e repetibilidade de testes |
| **Entupimento de ração no reservatório** | Média | Alto | Validação do design mecânico da calha e testes de fluxo |
| **Falha na conexão IoT** | Média | Médio | Implementação de rotina local no ESP32 (*failover*) |
| **Acesso do pet à eletrônica/reservatório** | Média | Alto | Blindagem mecânica da estrutura e cabos protegidos |
| **Divergência nutricional** | Baixa | Alto | Validação de fórmulas baseadas em literatura veterinária |

---

## 🚀 Visão do Produto e Futuro

A visão de longo prazo do **Petdose** é evoluir de um dispositivo individual para uma **plataforma completa de monitoramento preventivo da saúde animal**:

1. **Fase 1:** Dosador automático com temporizador local.
2. **Fase 2:** Dosador conectado via PWA e telemetria básica.
3. **Fase 3:** Análise de curvas de crescimento e histórico nutricional.
4. **Fase 4:** Integração com Inteligência Artificial para ajuste dinâmico do consumo alimentar baseado em taxas de ganho de peso.

---

## 🚨 Aviso Legal (Disclaimer)

> **Aviso Importante:** O algoritmo nutricional integrado a este sistema serve exclusivamente como uma **ferramenta de estimativa e automação**. Ele **não** substitui a consulta, diagnóstico ou prescrição de um médico veterinário qualificado.
```

---

O arquivo `README.md` foi gerado para documentar o repositório do seu projeto. Ele atende aos requisitos técnicos e às apresentações acadêmicas do trabalho. Se precisar de ajustes nos links, imagens ou diagramas adicionais, basta avisar!