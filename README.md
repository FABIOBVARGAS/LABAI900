# LABAI900
itens do treinamento da DIO AI900

O machine learning automatizado permite que você experimente vários algoritmos e parâmetros para treinar vários modelos e identificar o melhor para seus dados. Neste exercício, você usará um conjunto de dados de detalhes históricos de aluguel de bicicletas para treinar um modelo que prevê o número de aluguéis de bicicletas que devem ser esperados em um determinado dia, com base em características sazonais e meteorológicas.

No Azure Machine Learning Studio , visualize a página ML automatizado (em Criação ).

Crie um novo trabalho de ML automatizado com as seguintes configurações, usando Avançar conforme necessário para avançar pela interface do usuário:

Configurações básicas :

Nome do trabalho : O campo Nome do trabalho já deve estar preenchido previamente com um nome exclusivo. Mantenha-o como está.
Novo nome do experimento :mslearn-bike-rental
Descrição : Aprendizado de máquina automatizado para previsão de aluguel de bicicletas
Tags : nenhuma
Tipo de tarefa e dados :

Selecione o tipo de tarefa : Regressão
Selecionar conjunto de dados : Crie um novo conjunto de dados com as seguintes configurações:
Tipo de dados :
Nome :bike-rentals
Descrição :Historic bike rental data
Tipo : Tabela (mltable)
Fonte de dados :
Selecione De arquivos locais
Tipo de armazenamento de destino :
Tipo de armazenamento de dados : Azure Blob Storage
Nome : workspaceblobstore
Seleção de MLtable :
Pasta de upload : Baixe e descompacte a pasta que contém os dois arquivos que você precisa enviar https://aka.ms/bike-rentals
Selecione Criar . Após a criação do conjunto de dados, selecione o conjunto de dados bike-rentals para continuar a enviar o trabalho de ML automatizado.

Configurações da tarefa :

Tipo de tarefa : Regressão
Conjunto de dados : aluguel de bicicletas
Coluna de destino : aluguéis (inteiro)
Configurações adicionais :
Métrica primária : NormalizedRootMeanSquaredError
Explique o melhor modelo : Não selecionado
Habilitar empilhamento de conjunto : Não selecionado
Usar todos os modelos suportados : Não selecionado. Você restringirá o trabalho para tentar apenas alguns algoritmos específicos.
Modelos permitidos : Selecione apenas RandomForest e LightGBM — normalmente você tentaria o máximo possível, mas cada modelo adicionado aumenta o tempo necessário para executar o trabalho.
Limites : Expandir esta seção
Máximo de ensaios :3
Máximo de ensaios simultâneos :3
Máximo de nós :3
Limite de pontuação métrica : 0.085( para que se um modelo atingir uma pontuação métrica de erro quadrático médio normalizado de 0,085 ou menos, o trabalho termine. )
Tempo limite do experimento :15
Tempo limite de iteração :15
Habilitar rescisão antecipada : Selecionado
Validação e teste :
Tipo de validação : Divisão de validação de trem
Porcentagem de dados de validação : 10
Conjunto de dados de teste : Nenhum
Calcular :

Selecione o tipo de computação : Sem servidor
Tipo de máquina virtual : CPU
Camada de máquina virtual : Dedicada
Tamanho da máquina virtual : Standard_DS3_V2*
Número de instâncias : 1


Envie o trabalho de treinamento. Ele inicia automaticamente.

Espere o trabalho terminar. Pode levar um tempo — agora pode ser uma boa hora para um coffee break!
