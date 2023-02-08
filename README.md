# Ajustes Hiperparametros

O objetivo deste tutorial é apresentar métodos de ajustes finos (tunning), em suma, ajustes de hiperparâmetros é um meio de refinar nosso melhor modelo em busca de uma melhor predição.

Quando escolhemos o modelo "vencedor", até o momento não nos preocupamos muito com os parâmetros, ou seja, usamos os ajustes de "fábrica" e esses ajustes são feitos automaticamnente e sem nossa intervenção quando treinamos o modelo em busca do melhor ajuste que se adequa ao nosso propósito, quando passamos desta fase de escolha do melhor modelo ai vem a etapa de ajustes dos hiperparâmetros, nesta etapa, para nos auxiliar existem algumas ferramentas de otimização, iremos apresentar 3 delas que são:

## Grid search
O Grid Search testa todas as combinações possíveis (este é o problema desse método), pois dependendo do modelo são milhares de combinações possíveis demandando muito tempo e processamento de máquina o que pode tornar o projeto inviável, num mundo hipotético onde tempo e processamento não fosse um problema esse seria de longe o melhor modelo de ajustes de hiperparâmetros, e como ele testa "todas" as combinações possíveis então uma hora ele acha a melhor combinação, por este motivo é considerado o melhor método de ajuste. o GS já faz parte do pacote scikit learn.

## Random search
Diferentemente do Grid search o Random não testa todos os parâmetros, mas como proprio nome sugere, ele faz testes randômicos entre os hiperparâmetros e sugere o melhor ajuste com base em testes. o RS também faz parte so pacote scikit learning.

## Bayesian search
Este método tem um "modelo preditivo interno" que testa vários ajustes de hiperparâmetros porém sempre observando quais destes ajustes mais impactam no resultado do modelo. O BS precisa do pacote scikit optimize.


## Qual método escolher e como aplicar?
Essa é uma pergunta muito difícil de responder, vai de projeto pra projeto, por exemplo, um projeto com poucas features, em que você pretende ajustar poucos hiperparâmetros e em que tempo e processamento não irá impactar no seu resultado com certeza o Grid search é a melhor opção, já projetos muito robustos o Grid search não é o mais indicado.<br>
Para fazer o tunning de hiperparâmetros sempre use a validação (cross validation) nos dados de treino, os dados de teste "SEMPRE" devem ser deixados de fora e por último, quando tudo tiver ajustado e pronto pro teste final.

## Mas o que são hiperparâmetros?
Hiperparâmetros são ajustes feitos a posteriori ao treinamento afim de "tunnar" nosso modelo.

Aqui estão alguns exemplos comuns de hiperparâmetros,  Kizito (2020):

  - Taxa de divisão de teste de treinamento;
  - Taxa de aprendizado em algoritmos de otimização (por exemplo, gradiente descendente);
  - Escolha do algoritmo de otimização (por exemplo, descida de gradiente, descida de gradiente estocástico ou otimizador de Adam);
  - Escolha da função de ativação em uma camada de rede neural (nn) (por exemplo, Sigmoid, ReLU, Tanh);
  - A escolha da função de custo ou perda que o modelo usará;
  - Número de camadas ocultas em um nn;
  - Número de unidades de ativação em cada camada;
  - A taxa de abandono em nn (probabilidade de abandono);
  - Número de iterações (épocas) no treinamento a nn;
  - Número de clusters em uma tarefa de clustering;
  - Kernel ou tamanho do filtro em camadas convolucionais;
  - Tamanho do pool;
  - Tamanho do batch.


## Referências
NYUYTIYMBIY, Kizito. Parâmetros e Hiperparâmetros em Machine Learning e Deep Learning. Website 30 de dezembro de 2020, disponível em <https://towardsdatascience.com/parameters-and-hyperparameters-aa609601a9ac>. Acesso em 08 de fevereiro de 2023.
