## **Análise qualitativa**

Depois de identificar os riscos do Petdose, precisamos definir quais merecem maior atenção. Para isso, vamos avaliar duas dimensões: a probabilidade de ocorrência e o impacto sobre o projeto.

**Probabilidade (P)**

Qual é a chance de o risco ocorrer durante o desenvolvimento ou funcionamento do protótipo?

**Impacto (I)**

Se o risco ocorrer, qual será a consequência para o funcionamento, o prazo, o orçamento ou a segurança do projeto?

### **Escala de avaliação — 1 a 5**

| Valor | Probabilidade | Impacto |
| :---: | :---: | :---: |
| 1 | Muito baixa | Muito baixo |
| 2 | Baixa | Baixo |
| 3 | Média | Moderado |
| 4 | Alta | Alto |
| 5 | Muito alta | Muito alto |

**Pontuação do risco \= Probabilidade × Impacto**

A pontuação permite priorizar os riscos, mas não representa uma medida exata. As classificações devem ser justificadas pela equipe, considerando as características reais do Petdose.

**Classificação dos riscos** 

| Pontuação | Classificação | Ação recomendada |
| :---: | ----- | ----- |
| 1–4 | Baixo | Monitorar |
| 5–9 | Moderado | Planejar ações preventivas |
| 10–16 | Alto | Priorizar medidas de prevenção e resposta |
| 17–25 | Crítico | Priorizar o tratamento e avaliar a necessidade de mudanças no projeto |

| ID | Risco | P | I | P × I | Classificação |
| :---: | :---: | :---: | :---: | :---: | :---: |
| **R01** | Sensor de peso apresentar medições imprecisas | 4 | 5 | **20** | Crítico |
| **R02** | Mecanismo de dispensação apresentar entupimento | 4 | 4 | **16** | Alto |
| **R03** | Atraso na aquisição de componentes | 3 | 4 | **12** | Alto |
| **R04** | Integração entre ESP32 e aplicativo apresentar falhas | 4 | 4 | **16** | Alto |
| **R05** | Custos dos componentes superarem o orçamento | 3 | 4 | **12** | Alto |
| **R06** | Algoritmo nutricional apresentar parâmetros inadequados | 3 | 5 | **15** | Alto |
| **R07** | Animal conseguir acessar partes perigosas do equipamento | 1 | 5 | **5** | Moderado |
| **R08** | Integrante responsável por uma atividade ficar indisponível | 3 | 4 | **12** | Alto |

## **Prevenção e contingência**

O plano de prevenção busca reduzir a probabilidade de um risco acontecer. O plano de contingência estabelece o que a equipe fará caso ele ocorra.

### **Registro de prevenção e contingência**

| ID | Risco | Ação preventiva | Plano de contingência |
| :---: | :---: | :---: | :---: |
| **R01** | Sensor de peso impreciso | Calibrar a célula de carga e realizar testes com massas conhecidas. | Recalibrar ou substituir o sensor e repetir os testes de precisão. |
| **R02** | Entupimento da ração | Testar a geometria da calha, a abertura da comporta e diferentes tipos de ração. | Interromper a dispensação automática, desobstruir o mecanismo e ajustar a estrutura. |
| **R03** | Atraso na aquisição de componentes | Comprar os itens críticos antecipadamente e pesquisar fornecedores alternativos. | Adquirir um componente equivalente, após verificar sua compatibilidade. |
| **R04** | Falha na integração entre ESP32 e aplicativo | Realizar provas de conceito e testes de comunicação antes da integração final. | Corrigir a interface ou adotar uma arquitetura alternativa previamente testada. |
| **R05** | Custos acima do previsto | Solicitar cotações e manter uma reserva para contingências. | Utilizar a reserva disponível e reavaliar os itens não essenciais. |
| **R06** | Algoritmo nutricional inadequado | Pesquisar referências técnicas e buscar validação por profissional qualificado. | Suspender recomendações automáticas não validadas e utilizar parâmetros previamente revisados. |
| **R07** | Animal acessar partes perigosas | Projetar uma estrutura que proteja a eletrônica e as partes móveis. | Retirar o equipamento de uso até corrigir a falha de proteção. |
| **R08** | Indisponibilidade de integrante | Documentar atividades e compartilhar conhecimentos entre os integrantes. | Redistribuir as tarefas e reorganizar o cronograma. |

**Registro de Riscos** 

| ID | Categoria | Risco | EAP | P | I | P × I | Estratégia | Responsável | Status |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | ----- | :---: |
| **R01** | Técnico | Medição imprecisa do sensor de peso | 3.2 | 4 | 5 | 20 | Mitigar | Responsável pela instrumentação | Aberto |
| **R02** | Técnico | Entupimento do mecanismo de dispensação | 3.3 | 4 | 4 | 16 | Mitigar | Responsável pela mecânica | Aberto |
| **R03** | Cronograma | Atraso na entrega de componentes | 1\. 4 | 3 | 4 | 12 | Mitigar | Responsável pelas aquisições | Aberto |
| **R04** | Técnico | Falha de comunicação entre ESP32 e aplicativo | 5.1 | 4 | 4 | 16 | Mitigar | Responsável pela integração IoT | Aberto |
| **R05** | Financeiro | Custos superiores ao orçamento | 1.4 | 3 | 4 | 12 | Mitigar | Gerente do projeto | Aberto |
| **R06** | Técnico  | Algoritmo nutricional apresentar parâmetros inadequados  | 4.0 | 3 | 5 | 15 |  Mitigar  | Responsável pelo algoritmo nutricional  | Aberto  |
| **R07** | Operacional  | Animal conseguir acessar partes perigosas do equipamento  | 3.5  | 1 | 5 | 5 | Evitar/Mitigar   |  Responsável pela mecânica  | Aberto  |
| **R08** | Recursos humanos  | Indisponibilidade de integrante responsável por uma atividade  | 1.0 | 3 | 4 | 12 | Mitigar  | Gerente do projeto  | Aberto  |

