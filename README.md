# Ajustes Hiperparametros

O objetivo deste tutorial é apresentar métodos de ajustes finos (tunning). Ajustes de hiperparâmetros é um meio de refinar nosso melhor modelo em busca de uma melhor desempenho.

Quando escolhemos o modelo "vencedor", até o momento não nos preocupamos muito com os parâmetros dele, ou seja, usamos os ajustes "padrões" e esses ajustes são feitos automaticamnente quando treinamos o modelo, passado esta fase de escolha do melhor modelo ai vem a etapa de ajustes dos hiperparâmetros ou ajuste fino deste modelo "vencedor", e para nos auxiliar existem algumas ferramentas de otimização que testam automaticamente hiperparâmetros que desejarmos dentro de um range que passamos. Iremos apresentar 3 destas ferramentas:

## Grid search
O Grid Search testa todas as combinações possíveis (este é o problema desse método), pois dependendo do modelo são milhares de combinações possíveis demandando muito tempo e processamento de máquina o que pode tornar o projeto inviável, num mundo hipotético onde tempo e processamento não fosse um problema esse seria de longe o melhor modelo de ajustes de hiperparâmetros, e como ele testa "todas" as combinações possíveis então uma hora ele acha a melhor combinação, por este motivo é considerado o melhor método de ajuste, porém não indicado pela lentidão. O GS já faz parte do pacote scikit learn (Veja exemplo de utilização no notebook).

## Random search
Diferentemente do Grid search o Random não testa todos os parâmetros, mas como próprio nome sugere, ele faz testes randômicos entre os hiperparâmetros que passamos e sugere o melhor ajuste com base nesses testes. O RS também faz parte do pacote scikit learning (Veja exemplo de utilização no notebook).

## Bayesian search
Este método difere dos outros pois tem um "modelo preditivo interno" que testa vários ajustes de hiperparâmetros porém sempre observando quais destes ajustes mais impactuam no resultado do modelo. Ele não testa todos os hiperparâmetros passados, mas faz testes "entre" os valores sugeridos por nós. O BS precisa do pacote scikit optimize (Veja exemplo de utilização no notebook).

## Configurações básicas
Todos os métodos acima tem suas configurações bem parecidas com o exemplo abaixo (consulte o notebook para mais):

    # INFORMAMOS OS PARAMETROS QUE QUEREMOS TESTAR (ABAIXO SÓ UM MERO EXEMPLO)
    params = {'bootstrap': [True], 
             'max_depth': [8, 10, 12], # tamanho da arvore
             'max_features': ['auto', 'sqrt', 'log2'], # features auto ou raiz ou log
             'min_samples_leaf': [2, 3, 4], # numero de folhas das arvores
             'min_samples_split': [2, 3, 4], #splits de 4 ou 6 divisões
             'n_estimators' : [200, 300, 400, 500, 600, 700] # numero de estimadores
            }
    # PASSAMOS PRO OTIMIZADOR, O MODELO VENCEDOR, OS HIPERPARAMETROS PRA TESTAR E ALGUNS PARAMETROS ADICIONAIS
    randomForest_RandomizedSearchCV = RandomizedSearchCV(RandomForestClass, params, cv=5, scoring="accuracy", 
                           n_iter=32, verbose=True, n_jobs=1)
    
    # TREINAMOS O MODELO
    randomForest_RandomizedSearchCV.fit(X_treino, y_treino)


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


## Notebook
[Clique aqui para visualizar o notebook deste tutorial](https://github.com/dev-daniel-amorim/ML-Ajustes_Hiperparametros/blob/main/ML%20-%20Ajustes%20Hiperpar%C3%A2metros.ipynb)

## Referências
NYUYTIYMBIY, Kizito. Parâmetros e Hiperparâmetros em Machine Learning e Deep Learning. Website 30 de dezembro de 2020, disponível em <https://towardsdatascience.com/parameters-and-hyperparameters-aa609601a9ac>. Acesso em 08 de fevereiro de 2023.


<br>
<hr>

[<< Voltar para página inicial](https://github.com/dev-daniel-amorim)
