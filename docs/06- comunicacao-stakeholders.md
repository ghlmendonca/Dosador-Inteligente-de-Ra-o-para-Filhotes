# 👥 Gestão de Stakeholders e Plano de Comunicação — Projeto Petdose

> **Documento de Mapeamento, Matriz de Engajamento e Plano de Comunicação (Aula 6)**

---

## 1. Conceito e Identificação de Stakeholders

### Definição
Stakeholders são todas as partes interessadas (internas ou externas) que podem influenciar, ser diretamente afetadas ou demonstrar interesse nos resultados e no andamento do projeto **Petdose**.

### Importância no Projeto
A gestão de stakeholders garante que as expectativas sejam alinhadas desde o início. No caso do Petdose, a validação vai além dos desenvolvedores: inclui usuários finais (tutores de cães filhotes) que ditam a usabilidade do PWA, médicos veterinários que validam a segurança e eficácia nutricional do algoritmo, e professores/avaliadores que definem os critérios de aprovação acadêmica.

---

## 2. Identificação e Classificação dos Stakeholders (Petdose)

| Stakeholder | Tipo | Função / Papel no Projeto |
| :--- | :--- | :--- |
| **Gilmar Vieira Garcia** | Interno | Gerente do Projeto e Líder de Planejamento |
| **Davi Rodriguez Medeiros** | Interno | Desenvolvedor Lead (Software PWA & Integração IoT) |
| **Gustavo Heitor** | Interno | Desenvolvedor Lead (Hardware & Embarcados ESP32) |
| **Professores / Evaluadores** | Externo/Interno | Avaliação acadêmica, bancas e orientação metodológica |
| **Tutores de Pets Filhotes** | Externo | Usuários finais (operadores do PWA e alimentador físico) |
| **Médicos Veterinários** | Externo | Consultores especialistas (validação do cálculo calórico/nutricional) |
| **Fornecedores de Componentes** | Externo | Provedores de placas (ESP32), sensores (HX711) e atuadores |

---

## 3. Matriz Poder / Influência $\times$ Interesse

A classificação a seguir organiza os stakeholders de acordo com seu grau de poder sobre as decisões e nível de interesse nos resultados do Petdose:

```
                  EIXO PODER / INFLUÊNCIA
           Baixo                            Alto
      +-------------------------------+-------------------------------+
      | MANTER INFORMADO              | GERENCIAR DE PERTO            |
 A    |                               |                               |
 L    | • Tutores de Pets (Usuários)  | • Equipe Dev / GP (Integrantes|
 T    | • Médicos Veterinários        |   Gilmar, Davi, Gustavo)      |
 O    |                               | • Professores / Orientadores  |
I     +-------------------------------+-------------------------------+
N     | MONITORAR                     | MANTER SATISFEITO             |
T     |                               |                               |
E     | • Fornecedores de Componentes | • Coordenação do Curso /      |
R     |   Eletrônicos                 |   Instituição de Ensino       |
E     |                               |                               |
S     +-------------------------------+-------------------------------+
S
E          Baixo                            Alto
```

### Detalhamento dos Quadrantes:

1. **Alto Poder e Alto Interesse (Gerenciar de Perto):**
   * **Integrantes da Equipe (Gilmar, Davi, Gustavo):** Responsáveis diretos pela execução e tomada de decisão. Comunicação diária e contínua.
   * **Professores / Orientadores:** Decidem a aprovação do projeto e direcionam requisitos técnicos e acadêmicos.

2. **Alto Poder e Baixo Interesse (Manter Satisfeito):**
   * **Coordenação do Curso / Faculdade:** Define regras gerais, prazos de entrega e infraestrutura de laboratórios sem interferir na rotina diária.

3. **Baixo Poder e Alto Interesse (Manter Informado):**
   * **Tutores de Cães Filhotes:** Têm alto interesse na facilidade de uso e na precisão da ração, mas baixo poder de alteração na arquitetura do projeto.
   * **Médicos Veterinários:** Interessados na saúde do pet e na precisão do algoritmo calórico.

4. **Baixo Poder e Baixo Interesse (Monitorar):**
   * **Fornecedores de Componentes:** Impactam apenas em prazos de entrega de peças (ex: ESP32, célula de carga), demandando acompanhamento preventivo.

---

## 4. Plano de Comunicação e Estratégias de Engajamento

O plano abaixo estabelece os canais, frequências e fluxos bilaterais de informação, além dos gatilhos para eventos críticos.

### Tabela do Plano de Comunicação

| Receptor (Quem) | Conteúdo da Comunicação | Frequência | Canal / Meio | Responsável | Ação em Eventos Críticos (Gatilho) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Equipe Interna (Devs/GP)** | Daily, alinhamento de tarefas, código e prototipagem | Diária / Contínua | WhatsApp / Discord / GitHub | Gilmar V. Garcia | Reunião de emergência em caso de falha de hardware ou atraso no Caminho Crítico > 2 dias. |
| **Professores / Orientadores** | Relatório de status, validação de etapas da EAP e protótipo | Semanal / Quinzenal | Reuniões Presenciais / Google Classroom | Gilmar V. Garcia | Envio imediato de e-mail e pedido de mentoria caso ocorra mudança de escopo. |
| **Tutores (Usuários)** | Testes de usabilidade PWA, feedback da interface e operação | Pontual (Fases de Teste) | Formulários Google / Testes Guiados | Davi R. Medeiros | Reorganização do layout do PWA se a taxa de erro de uso for $> 20\%$. |
| **Médicos Veterinários** | Validação das curvas nutricionais e limites de dosagem | Pontual (Fase de Algoritmo) | Entrevista / E-mail técnico | Davi / Gustavo | Ajuste imediato dos coeficientes da fórmula calórica ($NEM/NECD$). |
| **Fornecedores** | Cotação, rastreio e confirmação de entrega de peças | Sob demanda | Marketplace / WhatsApp Store | Gustavo Heitor | Acionar fornecedor reserva local se o prazo de entrega exceder 5 dias úteis. |

---

## 5. Uso de IA e Validação Humana

### Registro do Prompt Utilizado para Apoio

> *"Atue como um Gerente de Projetos especialista em PMBOK. Com base no projeto Petdose (dosador inteligente IoT para filhotes com ESP32 e PWA), crie uma Matriz de Poder x Interesse de Stakeholders e um Plano de Comunicação. Sugira uma classificação inicial e os canais de engajamento."*

### Validação Critica pela Equipe
A análise gerada pela Inteligência Artificial foi revisada e adaptada pelo grupo considerando a realidade do projeto:
* **Ajuste Realizado:** A IA havia classificado os *Médicos Veterinários* no quadrante de "Alto Poder". A equipe reclassificou para "Baixo Poder / Alto Interesse", pois a consultoria veterinária serve como parâmetro técnico de validação, mas não possui poder de veto ou gerenciamento sobre o desenvolvimento do hardware/software.
* **Ajuste de Comunicação:** A inclusão de um gatilho crítico específico para atrasos na entrega de componentes foi adicionada manualmente pela equipe devido ao impacto direto no **Caminho Crítico** (Atividades A3 e A5).
