# Controle Integrado de Mudanças – Petdose

## 1. Identificação da solicitação

- **ID:** CR-001
- **Título:** Otimização do mecanismo de dispensação de ração.
- **Solicitante:** Equipe de desenvolvimento do Petdose.
- **Data:** 16/11/2026.
- **Status:** Pendente de aprovação.

## 2. Motivação

O planejamento original do projeto Petdose prevê a utilização de um servomotor para realizar a abertura e o fechamento da comporta responsável pela liberação da ração.

Durante a avaliação dos componentes, a equipe identificou a possibilidade de substituir o servomotor por um motor de passo, visando reduzir os custos de aquisição e adequar o acionamento às necessidades funcionais do mecanismo.

O sistema necessita basicamente de duas condições de operação: comporta aberta e comporta fechada, não exigindo um posicionamento angular de alta precisão.

Entretanto, ao avaliar a substituição do motor, foram identificadas outras questões relacionadas ao funcionamento e à segurança do mecanismo, principalmente quanto ao esforço exercido pela ração sobre a comporta e à necessidade de garantir seu fechamento mesmo em situações de interrupção da alimentação elétrica.

Essas questões também seriam relevantes caso o servomotor original fosse mantido, pois a perda de alimentação pode comprometer a capacidade de retenção da posição da comporta.

Diante disso, a equipe propõe uma otimização mais abrangente do mecanismo de dispensação, envolvendo alterações no acionamento e no layout mecânico.

## 3. Alterações propostas

A solicitação contempla três alterações principais:

### 3.1 Substituição do servomotor por motor de passo

Substituir o servomotor originalmente planejado por um motor de passo, considerando seu potencial de redução de custos e sua adequação ao movimento de abertura e fechamento da comporta.

A escolha deverá considerar o torque necessário para movimentar o mecanismo, a compatibilidade com o ESP32, a necessidade de um driver e o consumo de energia.

### 3.2 Alteração do layout de descida da ração

Modificar o percurso de descida da ração, prevendo a utilização de um duto com uma curva de 90° antes da comporta.

No layout original, a comporta fica posicionada diretamente abaixo do reservatório, podendo receber parte significativa da pressão exercida pela coluna de ração.

Com a alteração proposta, pretende-se fazer com que parte desse esforço seja suportada pelas paredes do duto, reduzindo potencialmente a força aplicada diretamente sobre a comporta e, consequentemente, o torque necessário para seu acionamento.

Essa alteração deverá ser validada por meio de testes, considerando também a possibilidade de acúmulo ou obstrução de ração na região da curva.

### 3.3 Adição de uma trava mecânica de segurança

Prever a instalação de um mecanismo de travamento que mantenha a comporta fechada mesmo quando houver interrupção da alimentação elétrica.

A finalidade é evitar que a comporta se abra involuntariamente devido à pressão exercida pela ração armazenada, impedindo a liberação não programada do alimento.

A trava deverá permitir o destravamento durante o acionamento normal do mecanismo e retornar à condição de segurança após o fechamento.

Essa medida é importante independentemente do tipo de motor utilizado, pois tanto o servomotor quanto o motor de passo podem perder a capacidade de manter ativamente a posição quando desenergizados.

## 4. Análise integrada dos impactos

| Dimensão | Impactos da mudança |
|---|---|
| Escopo | Substituição do motor, alteração do percurso da ração e inclusão de uma trava mecânica. |
| EAP | Inclusão de atividades de adaptação mecânica, instalação da trava, montagem e testes. |
| Cronograma | Necessidade de tempo adicional para desenvolvimento, fabricação, integração e validação das alterações. |
| Custos | Possibilidade de redução do custo do motor, com custos adicionais de driver, duto, trava e adaptações. |
| Qualidade | Necessidade de garantir abertura, fechamento, retenção da comporta e fluxo adequado da ração. |
| Riscos | Travamento da ração na curva, torque insuficiente, perda de passos e falha no mecanismo de trava. |
| Recursos | Necessidade de componentes eletrônicos, materiais mecânicos e equipamentos para realização dos testes. |
| Comunicação | Integração entre os responsáveis pelo hardware, firmware e desenvolvimento mecânico. |

## 5. Alternativas avaliadas

| Alternativa | Descrição |
|---|---|
| A | Manter o servomotor e o layout original, acrescentando uma trava de segurança. |
| B | Substituir o servomotor por motor de passo, mantendo o layout original e acrescentando a trava. |
| C | Manter o servomotor, modificar o layout com a curva de 90° e adicionar a trava. |
| D | Substituir o servomotor por motor de passo, modificar o layout com a curva de 90° e adicionar a trava. |

A alternativa D representa a proposta mais abrangente de otimização, pois busca reduzir os custos de acionamento e o esforço mecânico sobre a comporta, além de acrescentar uma medida de segurança contra abertura involuntária.

Entretanto, as alternativas deverão ser comparadas considerando os custos totais, a viabilidade mecânica e os resultados dos testes.

## 6. Recomendação da equipe

A equipe recomenda avaliar a alternativa D, considerando a substituição do servomotor por um motor de passo, a alteração do percurso da ração por meio de um duto com curva de 90° e a instalação de uma trava mecânica de segurança.

A proposta busca otimizar o funcionamento do mecanismo, reduzir os custos de aquisição e diminuir o esforço necessário para movimentar a comporta.

A inclusão da trava é considerada uma medida de segurança necessária independentemente da escolha do motor, garantindo que a comporta permaneça fechada mesmo em situações de interrupção da alimentação elétrica.

A aprovação fica condicionada à verificação do torque necessário, dimensionamento do motor, funcionamento da trava, compatibilidade elétrica e realização de testes com o reservatório abastecido.

## 7. Decisão simulada

**Status: Pendente de aprovação.**

A equipe recomenda a implementação das alterações propostas, mas considera necessária a realização de testes para comprovar a viabilidade técnica e econômica da solução.

A decisão final deverá ser submetida ao professor responsável pelo projeto, que atuará como instância de aprovação na atividade didática.

## 8. Plano de implementação

Caso aprovada, deverão ser realizadas as seguintes ações:

1. Comparar os custos e as especificações do servomotor e do motor de passo.
2. Dimensionar o motor considerando os esforços mecânicos da comporta.
3. Desenvolver o novo layout do duto com curva de 90°.
4. Projetar e instalar a trava mecânica de segurança.
5. Adaptar o circuito de acionamento e a programação do ESP32.
6. Realizar testes de abertura e fechamento com o reservatório abastecido.
7. Verificar a capacidade de retenção da comporta sem alimentação elétrica.
8. Avaliar o fluxo de ração e a possibilidade de obstruções na curva.
9. Atualizar os documentos de escopo, EAP, cronograma, custos e riscos.

## 9. Documentos afetados no GitHub

| Documento | Atualização necessária |
|---|---|
| `02-escopo-e-eap.md` | Atualizar as entregas e atividades relacionadas ao mecanismo de dispensação. |
| `03-cronograma.md` | Incluir atividades de desenvolvimento, fabricação e testes. |
| `04-custos/` | Atualizar os custos dos componentes e materiais adicionais. |
| `05-risk-register/` | Incluir riscos relacionados ao acionamento, fluxo de ração e mecanismo de trava. |
| `07-plano-da-qualidade.md` | Incluir critérios de aceitação para abertura, fechamento e retenção da comporta. |
| `08-recursos-e-responsabilidades.md` | Atualizar as responsabilidades relacionadas às alterações mecânicas e eletrônicas. |
| `README.md` | Adicionar referência ao documento de controle de mudanças. |

## 10. Registro do uso da IA

A inteligência artificial foi utilizada como ferramenta de apoio na análise da solicitação de mudança, auxiliando na identificação dos impactos técnicos, econômicos e operacionais.

Foram avaliadas possibilidades de substituição do servomotor por motor de passo, alteração do percurso de descida da ração e inclusão de uma trava mecânica para garantir o fechamento da comporta em situações de interrupção da alimentação elétrica.

As sugestões foram analisadas pela equipe, que permanece responsável pela validação técnica, realização dos testes e decisão final.

## 11. Conclusão

A solicitação de mudança surgiu a partir da avaliação da possibilidade de substituição do servomotor por um motor de passo, inicialmente motivada pela redução de custos e pela adequação do acionamento às necessidades do projeto.

Durante essa análise, foram identificadas oportunidades adicionais de melhoria no mecanismo de dispensação, principalmente relacionadas à redução do esforço mecânico sobre a comporta e à segurança de funcionamento em situações de falta de energia.

Dessa forma, a proposta passou a contemplar não apenas a substituição do motor, mas também a previsão de um novo layout para a descida da ração, utilizando uma curva de 90°, e a inclusão de uma trava mecânica de segurança.

As alterações buscam melhorar a eficiência, reduzir custos e aumentar a confiabilidade do Petdose, mantendo sua funcionalidade principal.

A implementação deverá ocorrer somente após a análise dos impactos e a validação das soluções propostas.
