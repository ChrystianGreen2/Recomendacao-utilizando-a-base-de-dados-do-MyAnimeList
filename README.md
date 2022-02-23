# Deep Retrieval Recommendation utilizando a base de dados do MyAnimeList
Modelo de recomendação utilizando Tensorflow Recommenders e a base de dados do myanimelist.

- Problem Statement
- Metrics
- Data Exploration and Data Visualization
- Data Preprocessing
- Modeling
- Model Evaluation and Validation
- Justification
- Reflection
- What Can Be Improved?

# Problem Statement
Dado um usuario, precisamos recomenda-lo conteúdos com base em outros conteúdos que o usuario viu e gostou, mas excluindo conteúdos que o usuario ja viu.
Para treino, nós utilizaremos o Tensorflow-Recommenders, que contém um conjunto de metrics e loss voltadas para diversos tipos de recomendação e por isso atende bem o nosso contexto.
# Metrics

![embeddings_3](https://user-images.githubusercontent.com/71555983/155336541-8dec7647-07ba-43eb-8a12-7d229645bbbc.png)

