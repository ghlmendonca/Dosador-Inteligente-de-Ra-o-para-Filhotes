# Plano de Recursos e Responsabilidades — Projeto Petdose

**Projeto:** Petdose — Dosador Inteligente de Ração para Filhotes  
**Arquivo de Referência:** `docs/08-recursos-e-responsabilidades.md`  
**Equipe:** Gilmar Garcia, Davi Medeiros e Gustavo  
**Data:** Setembro de 2026  
**Versão:** 1.0  

---

## 1. Levantamento de Recursos por Entrega da EAP

A tabela abaixo relaciona as entregas da Estrutura Analítica do Projeto (EAP) aos recursos humanos, materiais, tecnológicos e de infraestrutura necessários, identificando suas principais restrições de uso.

| Entrega da EAP | Recursos Humanos | Recursos Materiais | Recursos Tecnológicos | Infraestrutura e Restrições |
| :--- | :--- | :--- | :--- | :--- |
| **1.0 Gerenciamento do Projeto** | Gerente de Projeto (Gilmar) + Equipe | Caderno de notas, documentos impressos | GitHub, Google Docs/Sheets, Mermaid/Draw.io | Acesso à internet; alinhamento de agenda entre os 3 integrantes. |
| **2.0 Interface da Aplicação (PWA)** | Desenvolvedor Frontend/Mobile (Davi) | Computador pessoal / Smartphone para testes | React/Vue/HTML5, Firebase Auth, Service Workers, VS Code | Conta gratuita no Firebase/Vercel; tempo de desenvolvimento de UI/UX. |
| **3.0 Hardware e Sistema Mecânico** | Eng. de Sistemas Embarcados (Gilmar) + Apoio (Davi) | ESP32, Célula de carga + HX711, Motor de passo/Servo, Fonte 5V/12V, Filamento 3D/Acrílico | PlatformIO / Arduino IDE, FreeRTOS, KiCAD/EasyEDA, Software CAD (Fusion 360/SolidWorks) | Acesso à impressora 3D e bancada de eletrônica (multímetro, ferro de solda); prazo de entrega dos componentes. |
| **4.0 Algoritmo Nutricional e IA** | Especialista em Dados/Algoritmos (Gustavo) | Computador pessoal, tabelas nutricionais NRC/FEDIAF | Python, Pandas/Scikit-learn (prototipação), Node.js/API | Validação externa com médico veterinário; disponibilidade de base de dados de crescimento. |
| **5.0 Integração IoT e Nuvem** | Dev IoT (Davi & Gilmar) + Dados (Gustavo) | Placa ESP32 montada, roteador Wi-Fi | Broker MQTT / WebSockets, Firebase Realtime DB / Firestore, REST API | Estabilidade da rede Wi-Fi de 2.4GHz durante os ensaios de comunicação. |
| **6.0 Testes, Qualidade e Validação** | Toda a equipe (Liderança: Gilmar) | Balança analítica de precisão, pesos padrão ($50\text{g}$ a $200\text{g}$), 3 tipos de ração | Monitor Serial, Scripts de teste automatizado, Planilhas de análise estatística | Disponibilidade de bancada de laboratório e balança aferida; ambiente controlado sem vibrações externas. |
| **7.0 Documentação e Encerramento** | Toda a equipe | Protótipo físico finalizado, câmera/smartphone para gravação | Markdown, GitHub, PowerPoint/Canva | Prazo final improrrogável até 30/11/2026. |

---

## 2. Equipe, Competências e Lacunas de Conhecimento

Para evitar gargalos técnicos e o **risco de pessoa-chave**, mapeamos o nível de proficiência atual de cada integrante (escala: *Básico*, *Intermediário*, *Avançado*).

### 2.1 Matriz de Competências da Equipe

| Competência Técnica / Gerencial | Gilmar (GP / Hardware) | Davi (PWA / IoT) | Gustavo (Dados / Nutrição) | Nível Crítico Necessário |
| :--- | :---: | :---: | :---: | :---: |
| **Gestão de Projetos, EAP e Cronograma** | Avançado | Intermediário | Intermediário | Avançado |
| **Eletrônica, ESP32 e Sensores (HX711)** | Avançado | Básico | Básico | Avançado |
| **Modelagem 3D e Prototipagem Mecânica** | Intermediário | Intermediário | Básico | Intermediário |
| **Desenvolvimento Web / PWA e Bancos em Nuvem** | Básico | Avançado | Intermediário | Avançado |
| **Protocolos IoT (MQTT / APIs REST)** | Intermediário | Avançado | Básico | Avançado |
| **Modelagem Matemática, Nutrição Animal e IA** | Básico | Básico | Avançado | Avançado |
| **Testes de Qualidade e Documentação Técnica** | Intermediário | Intermediário | Intermediário | Intermediário |

### 2.2 Análise de Lacunas e Risco de Pessoa-Chave

* **Lacuna 1 — Modelagem Mecânica e Impressão 3D (Nível Intermediário):** Nenhum integrante possui nível avançado em CAD 3D para mecanismos de rosca sem-fim/calha.
  * *Mitigação:* Gilmar e Davi trabalharão em dupla (pair design) utilizando modelos paramétricos abertos como base e realizarão testes rápidos de impressão antes da montagem final.
* **Lacuna 2 — Risco de Pessoa-Chave em Domínios Específicos:** Gilmar concentra o conhecimento de firmware/hardware, Davi concentra o frontend/PWA e Gustavo concentra o algoritmo nutricional.
  * *Mitigação:* Todo código, esquema elétrico e modelagem matemática deve ser documentado no GitHub com `README` explicativo e revisado por pelo menos um colega antes do *merge* (revisão cruzada).

---

## 3. Matriz de Responsabilidades (RACI)

A matriz RACI define os papéis para os principais pacotes de trabalho da EAP. **Regra adotada:** Apenas um único **A** (*Accountable*) por atividade para garantir clareza na tomada de decisão.

* **R** = *Responsible* (Executa a atividade)
* **A** = *Accountable* (Responde pelo resultado final e aprova)
* **C** = *Consulted* (Consultado antes da execução — comunicação bidirecional)
* **I** = *Informed* (Informado sobre o progresso — comunicação unidirecional)

| ID EAP | Pacote de Trabalho / Entrega | Gilmar (GP / Hard.) | Davi (Soft. / PWA) | Gustavo (Alg. / IA) | Orientador / Vet. (Externo) |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **1.1 / 1.2** | Project Charter, EAP e Cronograma | **A / R** | R | R | C |
| **1.4** | Cotação e Aquisição de Componentes | **A** | **R** | I | I |
| **2.1 / 2.2** | Autenticação e Cadastro do Pet (PWA) | I | **A / R** | C | I |
| **2.3 / 2.4** | Dashboard, Histórico e Agendamentos | I | **A / R** | C | I |
| **3.1 / 3.2** | Firmware ESP32 e Calibração HX711 | **A / R** | C | I | I |
| **3.3 / 3.5** | Mecanismo Dispensador e Chassi 3D | **A / R** | R | I | I |
| **4.1 / 4.2** | Cálculo Energético e Conversão Calórica | I | C | **A / R** | C |
| **4.3 / 4.4** | Curva de Crescimento e Fracionamento | I | C | **A / R** | C |
| **5.1 / 5.2** | Comunicação IoT (ESP32 $\leftrightarrow$ PWA) e Nuvem | R | **A / R** | C | I |
| **5.3** | Operação Offline e Contingência (NVS) | **A / R** | C | I | I |
| **5.4** | Modelo de IA para Ajuste de Dose | I | C | **A / R** | I |
| **6.1 / 6.2** | Testes de Precisão ($\pm 5\%$) e Mecânica | **A / R** | R | R | I |
| **6.5** | Validação Nutricional do Algoritmo | I | I | **A / R** | C |
| **7.1 / 7.3** | Documentação Técnica e Relatório Final | **A** | R | R | I |
| **7.4** | Apresentação Final e Demonstração | **A / R** | R | R | I |

---

## 4. Capacidade, Disponibilidade e Análise de Sobrecarga

Considerando que os integrantes são estudantes com outras disciplinas acadêmicas, estabeleceu-se a **capacidade semanal disponível** de cada membro entre Setembro e Novembro de 2026:

* **Gilmar:** $10\text{ horas/semana}$
* **Davi:** $10\text{ horas/semana}$
* **Gustavo:** $8\text{ horas/semana}$
* **Capacidade Total da Equipe:** $28\text{ horas/semana}$

### 4.1 Estimativa de Esforço vs. Capacidade (Período Crítico: Outubro/2026)

Na **Semana 7 e Semana 8 (15/10 a 31/10)** ocorre o pico de integração do projeto. Abaixo está a análise de carga de trabalho semanal média nesse período:

| Integrante | Atividades Alocadas no Período | Esforço Planejado (h/sem) | Capacidade Disponível (h/sem) | Taxa de Alocação (%) | Status |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **Gilmar** | Montagem circuito (4h) + Chassi 3D (4h) + Integração IoT (4h) + Reuniões (1h) | $13\text{ h}$ | $10\text{ h}$ | $130\%$ | **Sobrecarga (+30%)** |
| **Davi** | Painel Agendamento/Push (4h) + Integração IoT (4h) + Banco Nuvem (2h) | $10\text{ h}$ | $10\text{ h}$ | $100\%$ | Adequado (Limite) |
| **Gustavo** | Fracionamento (2h) + Base de dados IA (3h) + Apoio Banco Nuvem (2h) | $7\text{ h}$ | $8\text{ h}$ | $87,5\%$ | Com folga ($1\text{h}$) |

$$\text{Taxa de Alocação} = \left( \frac{\text{Esforço Planejado}}{\text{Capacidade Disponível}} \right) \times 100$$

---

## 5. Ações de Nivelamento, Mitigação de Conflitos e Liderança

### 5.1 Resolução da Sobrecarga e Conflitos Identificados

1. **Suavização de Recursos (Gilmar — $130\% \rightarrow 100\%$):**
   * *Ação:* Antecipar a impressão 3D e acabamento do chassi (**A3.5.2**) para a Semana 6 (usando folga de horário do laboratório) e delegar a montagem mecânica auxiliar e organização da fiação para **Davi** e **Gustavo** durante o encontro presencial de sábado. Isso reduz $3\text{h}$ semanais de Gilmar na Semana 7 sem alterar o prazo final.
2. **Conflito de Equipamento Compartilhado (Protótipo Físico Único):**
   * *Problema:* Gilmar precisa do ESP32 para testar o motor/balança enquanto Davi precisa testar o recebimento de comandos MQTT.
   * *Ação:* Utilizar um **segundo ESP32 de bancada** (apenas a placa, sem sensores acoplados) para Davi validar o protocolo MQTT/WebSocket paralelamente aos testes mecânicos de Gilmar.
3. **Semanas de Provas Acadêmicas:**
   * *Ação:* O cronograma prevê uma margem de segurança (buffer) de 5 dias entre o fim dos testes (15/11) e a entrega final (30/11) para absorver eventuais quedas de produtividade em semanas de avaliação.

### 5.2 Protocolo de Resolução de Conflitos e Decisões Técnicas

* **Divergências Técnicas (ex: escolha de broker MQTT ou motor):** Serão decididas com base em 3 critérios objetivos: *custo, tempo de implementação e confiabilidade*. A decisão final cabe ao **A** da atividade na RACI e deve ser registrada em uma *Issue* ou *Discussion* no GitHub.
* **Atrasos nas Entregas:** Tratados nas reuniões semanais de 15 minutos (*Daily/Weekly Sync*). Se uma tarefa do caminho crítico atrasar mais de 48h, o Gerente de Projeto (Gilmar) realoca esforços imediatamente.

---

## 6. Registro do Uso de Inteligência Artificial

Em conformidade com as boas práticas de engenharia e transparência acadêmica, registra-se abaixo o uso de IA como ferramenta de apoio ao planejamento de recursos.

### 6.1 Prompt Estruturado Utilizado

> *"Atue como gerente de projetos tecnológicos com experiência em Engenharia Elétrica e Automação. Com base na EAP do projeto Petdose (dosador de ração com ESP32, HX711, PWA e algoritmo nutricional) e uma equipe de 3 integrantes (Gilmar: Hardware/GP, Davi: PWA/IoT, Gustavo: Dados/Nutrição) com disponibilidade de 10h, 10h e 8h semanais respectivamente: 1) Relacione recursos humanos, materiais e tecnológicos por entrega; 2) Crie uma matriz de competências e identifique riscos de pessoa-chave; 3) Elabore uma matriz RACI com um único A por linha; 4) Calcule a taxa de alocação na fase de integração (Outubro) e sugira ações de suavização de sobrecarga."*

### 6.2 Avaliação Crítica e Ajustes Realizados pela Equipe

* **O que foi aproveitado:** A estruturação da tabela de recursos por entrega da EAP, a identificação do risco de pessoa-chave nos domínios isolados e a ideia de utilizar um segundo ESP32 para desacoplar os testes de rede dos testes mecânicos.
* **O que foi corrigido/validado manualmente:**
  1. **Unicidade do A na RACI:** A IA inicialmente atribuiu `A/R` duplo (para Gilmar e Davi) na atividade de *Integração IoT (5.1)*. A equipe corrigiu a matriz definindo **Davi** como único **A** da integração de software/nuvem e **Gilmar** como **R** pelo lado do firmware, evitando ambiguidade de decisão.
  2. **Realismo na Disponibilidade:** A IA estimou inicialmente 15 horas semanais por integrante. A equipe ajustou os valores reais para $10\text{h}$, $10\text{h}$ e $8\text{h}$ considerando a carga horária das disciplinas do semestre letivo.
  3. **Orçamento:** Validou-se que a inclusão de um segundo ESP32 para testes paralelos cabe na reserva de contingência da planilha de custos (`docs/04-custos/`).

---

## 7. Checklist de Verificação e Publicação

- [x] Recursos humanos, materiais, tecnológicos e de infraestrutura relacionados à EAP.
- [x] Matriz de competências e lacunas de conhecimento registradas.
- [x] Matriz RACI elaborada com exatamente um **A** por pacote de trabalho.
- [x] Disponibilidade semanal, esforço e sobrecargas calculados matematicamente.
- [x] Ações de suavização e resolução de conflitos documentadas.
- [x] Uso de IA registrado e auditado pela equipe.
- [ ] Arquivo publicado em `docs/08-recursos-e-responsabilidades.md` e linkado no `README.md`.