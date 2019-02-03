# Cognitivo-teste

[Link para o Colab](https://colab.research.google.com/drive/1rX4XxTcEcyRIfVgTSw5XnnyNbwje-gct)

Perguntas do teste Vinho Verde
#5 Perguntas extras do questionário

Aqui serão respondidas as perguntas extras do questionário. Os mesmo estarão em um arquivo README.md em um repoistório git.

## 5.a Como foi a definição da sua estratégia de modelagem?

Eu tentei não limitar minha estratégia entre modelos classificatórios e modelos regressionais. Pelo enunciado do problema e explicação das variáveis, vi que ambos os modelos poderiam dar certo. Se fosse um modelo classificatório, eu teria 10 classes, e se fosse um modelo regressional, eu teria uma variávei contínua que se limitasse em 0 e 10, e a partir daí eu poderia arredondar e apresentar um número inteiro para o usuário/cliente.

Durante o EDA (análise exploratória) eu vi como algumas variáveis interagiam entre si, e isso foi limitando, por experiência, o tipo de modelos que dariam mais certo com essa base de dados: Árvore, Floresta, KNN e MLP. Em um ambiente real, é legal ir além disso, ou até usar algoritmos de teste de vários modelos ao mesmo tempo, mas como eu tinha tempo limitado, já fui setando a estratégia para esses modelos. Além do mais, eu não tinha uma equipe para debater e me mostrar outros pontos de vista (ou dividirmos a tarefa e testamos mais modelos diferentes). Em certo momento, inclusive, minha estratégia era gerar um modelo para vinhos brancos e outro para vinhos tintos, utilizando a estratégia dos modelos especialistas.

Ainda durante o EDA, me deparei com o fato de que, além de termos ruído na base (porém pouco), a base estava totalmente desbalanceada, então eu teria que me preocupar em métricas que apontassem que o modelo estaria bem generalizado para dados extras. Ou seja, jogar métricas como acurácia fora e focar em F1-score ou R2-score adaptado. F1-Score pois eu não sabia, pelo enunciado do problema, o que traria mais danos ao cliente: falsos negativos ou falsos positivois, então foquei em uma balanceamento entre os dois. R2-score adaptado pois eu gostaria que meu modelo se adequasse bem para dados no qual ele não foi treinado.

Obviamente eu me preocupei também com underfitting e overfitting, mas esses são mais fáceis de lidar. Uma boa divisão da base de dados em treino e teste com alguns k-folds (ou validação cruzada) já ajudam a avitar esses dois problemas.

## 5.b Como foi definida a função de custo utilizada?

Eu queria que grandes disparidades de erros gritassem bem alto, por isso escolhi MSE.

## 5.c Qual foi o critério utilizado na seleção do modelo final?

Explicado no ponto a.

Classificação: F1-score - Balanceamento entre precisão e recall
Regressão: Baixo MSE e Alto R2 Score adaptador - Um menor número de erros gritantes e um indicador de que esse modelo consegue se adaptar a uma base no qual não foi treinado (generalização)

## 5.d Qual foi o critério utilizado para validação do modelo? Por que escolheu utilizar este método?

Explicado n oponto a e c

Classificação: F1-score - Balanceamento entre precisão e recall
Regressão: Baixo MSE e Alto R2 Score adaptador - Um menor número de erros gritantes e um indicador de que esse modelo consegue se adaptar a uma base no qual não foi treinado (generalização)

## 5.e Quais evidências você possui de que seu modelo é suficientemente bom?

Não considero esse um bom modelo ( ainda mais levando em consideração que eu conheço a base de dados original da vinho verde ), mas tendo em vista as limitações que tinhámos ( e é isso que acontece no mundo real ), eu acredito que esse modelo é suficientemente bom pelo F1-Score a R2-score adaptado explicado nas perguntas passadas, mas também pq ele conseguiu se concentrar (tanto em classificação quanto em regressão ) nos scores que são mais prevalentes, evitando os grandes extremos.

No caso da classificação, isso ficou ainda mais evidante no plot da matriz de confusão e na matriz de classificações erradas. Os modelos 24 e 25 possuiam as mesmas métricas, porém o modelo 24 possuia menos erros extremos, e eu acredito que isso o faz o melhor.
