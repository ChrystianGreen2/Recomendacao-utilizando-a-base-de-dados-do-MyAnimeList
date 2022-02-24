# Deep Retrieval Recommendation utilizando a base de dados do MyAnimeList - Under Construction 
Modelo de recomendação utilizando Tensorflow Recommenders e a base de dados do myanimelist.

Não irei me aprofundar muito nas partes de exploração,visualização e preprocessamento ja que não são nossos dados reais, então o foco é na Modelagem e resultados.

- Problem Statement
- Retrieval Method
- Data Exploration and Data Visualization
- Data Preprocessing
- Modeling
- Model Evaluation and Validation
- Using the Model
- What Can Be Improved?

# Problem Statement
Dado um usuario, precisamos recomenda-lo conteúdos com base em outros conteúdos que o usuario viu e gostou, mas excluindo conteúdos que o usuario ja viu.
Para treino, nós utilizaremos o Tensorflow-Recommenders, que contém um conjunto de metrics e loss voltadas para diversos tipos de recomendação e por isso atende bem o nosso contexto.
# Retrieval Method
Sistemas de recomendação o mundo real são compostos de duas fases:

1 - O estagio de "Recuperação"(Retrieval) é responsavel por selecionar de conteúdos iniciais, dentre todas as possibilidades, que o usuario possa estar interessado. O objetivo principal é eliminar todas as possibilidades que o usuario não tenha interesse. Como podemos estar lidando com milhões de possibilidades, isso deve ser computacionalmente eficiente.

2 - Dentre todas as possibilidades escolhidas, ranquear quais o usuario tenha mais interesse, isso filtra ainda mais os resultados e retorna somente as recomendações que o usuario possa ter interesse.

No entanto a abordagem que nós usamos utiliza somente o metodo de recuperação(retrieval), devido à nossa base de dados.

# Data Exploration, Data Visualization and Data Preprocessing
Utilizamos a base de dados [Anime Recommendation Database 2020](https://www.kaggle.com/hernan4444/anime-recommendation-database-2020)

Dessa base utilizaremos os arquivos:

*anime_with_synopsis.csv* - Lista de animes com seu nome, genero e synopses.

*animelist.csv* - contém 100 milhões de interações de usuarios.

![image](https://user-images.githubusercontent.com/71555983/155591932-1ca7165e-3008-465a-ba84-17f439b849b4.png)

# Modeling

O nosso modelo é composto de dois submodelos:

QueryModel - Computa a representação da busca, no nosso caso usamos o Id do usuário para realizar a busca.

CandidateModel - Computa a representação dos conteúdos, utilizamos as informaçoes do conteúdo como nome,titulo e sinopse.

# Model Evaluation and Validation
O modelo desempenha bem mal nessa base de dados,em todas suas metricas intrissicas, no entanto a metrica mais importante é o engajamento do usuario e isso será medido através de A/B test.

![image](https://user-images.githubusercontent.com/71555983/155594853-b68f137e-c16e-4562-9e06-fbd8d709db37.png)

# Using the Model
Para fazer a recomendação existem 3 metódos, scann, bruteforce e streaming, a diferença entre eles é a velocidade que trazem recomendações, nesse exemplo utilizaremos o BruteForce.

Para realizar as recomendações, fornecemos o ID do usuario e é nos retornado a lista de recomendações ranqueada pelo modelo.
![image](https://user-images.githubusercontent.com/71555983/155600874-124e6414-a5a9-4625-8690-88e52f642eac.png)
Em 0.5 segundos foram feitas 50 recomendações para o usuario 2997.

#### Recomendações:
![image](https://user-images.githubusercontent.com/71555983/155601155-dbab3d30-4138-4604-9e6c-763e97730509.png)

# What Can Be Improved?
Muitas coisas podem ser melhoradas, aqui nós só pegamos as interações do usuario sem se preocupar com o tipo, poderiamos ter retirado animes que ele desistiu de ver, classificou com nota baixa, assistiu somente 1 episódio e etc...
Muitos filtros poderiam ter sido aplicados com o objetivo de treinar somente em conteúdos que o usuario realmente gostou.

O preprocessamento dos dados é outra opção, nós apenas vectorizamos todo o texto e treinamos para obter suas representações numericas.

O tempo de treino e a profundidade da rede neural, ja que a rede só tem uma camada e usamos somente 20 epochs.

A utilização de mais um target explicito como o rating que o usuario deu naquele anime.

# Conclusion
Existem diversos fatores que irão ajudar a melhorar a recomendação a ideia é que o modelo real vá contendo todas essas melhorias, a ideia aqui é mostrar a base do modelo e que abordagem que estamos usando para gerar as recomendações e como será feita as recomendações.

Esse "artigo" tambem é uma tentativa minha de deixar mais claro como são feitos os produtos que usam ML e não deixar uma caixa preta que somente o desenvolvedor pode entender.
# Anime Embeddings
![embeddings_3](https://user-images.githubusercontent.com/71555983/155336541-8dec7647-07ba-43eb-8a12-7d229645bbbc.png)

