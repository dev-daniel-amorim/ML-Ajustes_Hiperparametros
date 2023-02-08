# Ajustes Hiperparametros

O objetivo deste tutorial é apresentar métodos de ajustes finos (tunning), em suma, ajustes de hiperparâmetros é um meio de refinar nosso melhor modelo em busca de uma melhor predição.

Quando escolhemos o modelo "vencedor", até o momento não nos preocupamos muito com os parâmetros, ou seja, usamos os ajustes de "fabrica" em busca do melhor modelo que se adequa ao nosso propósito, quando passamos desta fase de escolha do melhor modelo ai vem a etapa de ajustes, para nos auxiliar existem algumas ferramentas de otimização, iresmos apresentar 3 delas que são:

## Grid search
O Grid Search testa todas as combinações possíveis (este é o problema desse método), pois dependendo do modelo são milhares de combinações possíveis demandando muito tempo e processamento de máquina o que pode tornar o projeto inviável, num mundo hipotético onde tempo e processamento não fosse um problema esse seria de longe o melhor modelo de ajustes de hiperparâmetros, e como ele testa "todas" as combinações possíveis então uma hora ele acha a melhor combinação, por este motivo é considerado o melhor método de ajuste. o GS já faz parte do pacote scikit learn.

## Random search
Diferentemente do Grid search o Random não testa todos os parâmetros, mas como proprio nome sugere, ele faz testes randômicos entre os hiperparâmetros e sugere o melhor ajuste com base em testes. o RS também faz parte so pacote scikit learning.

## Bayesian search
Este método tem um "modelo preditivo interno" que testa vários ajustes de hiperparâmetros porém sempre observando quais destes ajustes mais impactam no resultado do modelo. O BS precisa do pacote scikit optimize.

## Qual escolher e como aplicar?
Essa é uma pergunta muito difícil de responder, vai de projeto pra projeto, por exemplo, um projeto com poucas features, em que você pretende ajustar poucos hiperparâmetros e em que tempo e processamento não irá impactar no seu resultado com certeza o Grid search é a melhor opção, já projetos muito robustos o Grid search não é o mais indicado.<br>
Para fazer o tunning de hiperparâmetros sempre use a validação (cross validation), os dados de teste "SEMPRE" devem ser deixados por último, quando tudo tiver ajustado e pronto pro teste final.
