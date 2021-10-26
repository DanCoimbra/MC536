# Aluno
* 155077: Daniel Credico de Coimbra

# Base de dados
Apresentaremos como nosso banco de dados em formato tabular será enriquecido por um banco de dados em formato de grafo de conhecimento. O banco de dados escolhido será o [MindReader](https://mindreader.tech/dataset/), que armazena conhecimento sobre como filmes, livros, atores, diretores, gêneros, estúdios, anos, e outras coisas se conectam. A título de exemplo, nós transformaremos parte desse grafo de conhecimento em tabelas, que então enriquecerá nosso modelo tabular e nos permitirá responder algumas perguntas adicionais. Nosso exemplo consiste de duas tabelas. Note que cada entidade em MindReader possui um código único. Por exemplo, Q222939 designa o filme Jumanji. Chamaremos isso de Q-ID.

* Tabela #1: [IMDb ID, Q-ID]. Em duas colunas, essa tabela relaciona o IMDb ID de cada filme com seu correspondente Q-ID. Dada a unicidade de cada um dos dois IDs, podemos tomar qualquer uma das duas colunas como chave primária. Ambas as colunas são chaves estrangeiras.

* Tabela #2: [Q-ID1, Q-ID2]. Em duas colunas, essa tabela expressa em formato tabular parte do grafo de conhecimento MindReader. Em específico, expressa quais atores participaram de quais filmes. Q-ID1 designa um ator e Q-ID2 designa um filme. Grafos de conhecimento podem ser expressos como uma lista de triplas ordenadas; neste caso, suprimimos um dos elementos da tripla—a coluna correspondente à relação—pois em todos os casos se trata da mesma relação, a saber, aquela que MindReader chama de "STARRING".

Assim, nosso dataset adquirá duas novas colunas e agora terá informações sobre todos os atores que participaram de cada um dos 75 filmes de maior bilheteria (nominal ou real, ainda a decidir) dos últimos 70 anos.


## Perguntas de Pesquisa/análise
* Qual o ator mais comum dentre filmes de alta bilheteria?
* Qual a dupla de atores mais comum dentre filmes de alta bilheteria?
* Qual o maior número de atores que já participou, todos juntos, de dois filmes?