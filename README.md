# Deep Retrieval Recommendation utilizando a base de dados do MyAnimeList
Modelo de recomendação utilizando Tensorflow Recommenders e a base de dados do myanimelist.

- Problem Statement
- Retrieval Method
- Data Exploration and Data Visualization
- Data Preprocessing
- Modeling
- Model Evaluation and Validation
- Test
- What Can Be Improved?

# Problem Statement
Dado um usuario, precisamos recomenda-lo conteúdos com base em outros conteúdos que o usuario viu e gostou, mas excluindo conteúdos que o usuario ja viu.
Para treino, nós utilizaremos o Tensorflow-Recommenders, que contém um conjunto de metrics e loss voltadas para diversos tipos de recomendação e por isso atende bem o nosso contexto.
# Retrieval Method
Sistemas de recomendação o mundo real são compostos de duas fases:

1 - O estagio de "Recuperação"(Retrieval) é responsavel por selecionar de conteúdos iniciais, dentre todas as possibilidades, que o usuario possa estar interessado. O objetivo principal é eliminar todas as possibilidades que o usuario não tenha interesse. Como podemos estar lidando com milhões de possibilidades, isso deve ser computacionalmente eficiente.

2 - Dentre todas as possibilidades escolhidas, ranquear quais o usuario tenha mais interesse, isso filtra ainda mais os resultados e retorna somente as recomendações que o usuario possa ter interesse.

No entanto a abordagem que nós usamos utiliza somente o metodo de recuperação(retrieval), devido à nossa base de dados.

# Data Exploration and Data Visualization

(Não irei me aprofundar muito nessa parte ja que não é nossa base real)
Utilizamos a base de dados [Anime Recommendation Database 2020](https://www.kaggle.com/hernan4444/anime-recommendation-database-2020)

Dessa base utilizaremos os arquivos:

*anime_with_synopsis.csv* - Lista de animes com seu nome, genero e synopses.

*animelist.csv* - contém 100 milhões de interações de usuarios.

# Data Preprocessing
# Modeling
# Model Evaluation and Validation
# Test 
# What Can Be Improved?

![embeddings_3](https://user-images.githubusercontent.com/71555983/155336541-8dec7647-07ba-43eb-8a12-7d229645bbbc.png)

