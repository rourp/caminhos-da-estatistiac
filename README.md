# caminhos-da-estatistica

**Objetivo do estudo: Apresentação da Empresa**

A empresa escolhida é a multinacional de tecnologia estadunidense Amazon, com o
estudo se restringindo aos dados extraídos do site da mesma.
A Amazon foi fundada em 1994 e começou como uma livraria online, sendo uma das
pioneiras neste setor. Hoje, é uma das maiores empresas do mundo por valor de
mercado, com um leque de atuação extremamente diverso, composto por livros (tanto
físico quanto digital), varejo, eletrônicos (como a assistente virtual Alexa e o leitor de
livros Kindle), entretenimento por streaming (Prime Video e Twitch), video-games (Luna
Cloud Gaming), serviços de cloud (AWS), entre outros.
Por se tratar de uma das maiores empresas de tecnologia do mundo e ter um vasto ramo
de atuação, seus negócios possuem quantidades massivas de dados e algoritmos
complexos para que a experiência do consumidor seja otimizada da melhor maneira
possível.

**Objetivo do estudo: Problema de Pesquisa**

A Amazon, inicialmente uma modesta livraria online, transformou-se em uma gigante do
varejo global, muito graças a sua capacidade de conquistar a confiança dos
consumidores. No final dos anos 90 e início dos anos 2000, quando a internet ainda era
vista com desconfiança — exacerbada pela bolha da internet —, a Amazon é um dos
exemplos de superação de adversidade, pois, mesmo perdendo 90% do seu valor de
mercado no início dos anos 2000, conseguiu sobreviver e se tornar referência no ramo da
tecnologia.
Um aspecto central do crescimento da Amazon foi sua aposta em expandir seus produtos
ofertados, trazendo para si parceiros externos, ou seja, tornando-se um market place.
Para isso, o sistema de reviews foi essencial, junto com o nome da Amazon, foi essencial
para que houvesse confiança dos consumidores. Afinal, é mais provável que um cliente
opte por um produto avaliado e testado por outros usuários ou um produto sem
avaliações? Além do mais, essa estratégia permitiu que a Amazon não apenas vendesse
produtos, mas também oferecesse recomendações relevantes com base nos gostos e
nas experiências dos clientes. Isso foi essencial para fortalecer ainda mais a confiança do
consumidor e criar um ciclo de feedback contínuo que ajudou a empresa a se adaptar
rapidamente às demandas dos clientes.
Esse sistema de avaliações será o foco desta pesquisa, especialmente no contexto do
mercado de materiais de escritório, um setor que passou por grandes transformações
durante a pandemia da COVID-19. A necessidade de adaptação ao home office fez com
que muitas empresas e trabalhadores buscassem novos produtos para estruturar seus
espaços de trabalho em casa. Nesse cenário, o papel das avaliações de produtos
tornou-se ainda mais crucial, pois os consumidores, baseiam-se nas opiniões de outros
usuários para escolher os melhores itens ou na sugestão dos departamentos de TI da
empresa, que podem ter se baseado em opiniões dos usuários também. Produtos como
cadeiras ergonômicas, mesas, equipamentos eletrônicos e material de escritório
ganharam destaque nas avaliações, e a Amazon teve que ajustar sua oferta para atender
a essa nova demanda – algo que ela conseguiu, tendo em vista que seu lucro subiu
220% com o crescimento das compras online durante a pandemia.
Portanto, o foco deste estudo está em analisar, por meio de modelos e medidas, como a
Amazon, através de seu sistema de reviews, contribuiu para a adaptação de
consumidores ao home office e como as avaliações de materiais de escritório ajudaram a
guiar as decisões de compra durante esse período, além do impacto que a pandemia
pode ter tido na procura por materiais de escritório. A pesquisa se divide nas seguintes
etapas:
Coleta e pré-processamento de dados: utilizamos a base de dados "Amazon Reviews
2023”, com foco em produtos do segmento de materiais de escritório (“Office_Products”).
Desenvolvimento de um modelo de NLP: para classificar o sentimento das avaliações
como positivo, negativo ou neutro, utilizamos modelos e/ou medidas como SVM, BERT,
TF-IDF, entre outros.
Validação e teste: avaliar o desempenho do modelo em termos de precisão de recall
usando um conjunto de dados de validação e ajustes conforme o necessário.
Implementação de um painel de controle: criar uma visualização que mostre a distribuição
de sentimentos ao longo do tempo e oferecer insights sobre as mudanças nas
preferências dos consumidores de materiais de escritório durante a pandemia.
Ao longo do estudo, será investigado como essas avaliações ajudaram os consumidores
a encontrar produtos de qualidade e a superar as dificuldades impostas pela rápida
transição para o home office, com foco no impacto desse sistema de reviews para a
confiança e satisfação dos clientes no setor de materiais de escritório, utilizando
metodologias escaláveis para estudo de outros tipos de produtos, o que pode ajudar varejistas a entenderem o impacto de um bom sistema de avaliações, para que possam
aprimorar ou criar o seu próprio, além de ajudar os comerciantes a priorizarem produtos,
melhorar atendimento, e também guiar melhor o consumidor.

**Apresentação dos metadados e Análise Exploratória de
Dados**

Os dados foram obtidos através do link
https://huggingface.co/datasets/McAuley-Lab/Amazon-Reviews-2023 e serão utilizadas as
bases em “Office_Products”. Abaixo, as colunas que serão analisadas, seus tipos e uma
explicação de cada uma delas, conforme a fonte dos dados:

User Reviews

| Field             | Type   | Explanation                                                                                                                                      |
|-------------------|--------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `rating`          | float  | Rating of the product (from 1.0 to 5.0).                                                                                                         |
| `title`           | str    | Title of the user review.                                                                                                                        |
| `text`            | str    | Text body of the user review.                                                                                                                    |
| `images`          | list   | Images that users post after receiving the product. Each image has different sizes (small, medium, large), represented by the small_image_url, medium_image_url, and large_image_url respectively. |
| `asin`            | str    | ID of the product.                                                                                                                               |
| `parent_asin`     | str    | Parent ID of the product. Products with different colors, styles, sizes usually belong to the same parent ID. The “asin” in previous Amazon datasets is actually the parent ID. Use parent ID to find product meta. |
| `user_id`         | str    | ID of the reviewer.                                                                                                                              |
| `timestamp`       | int    | Time of the review (in Unix time).                                                                                                               |
| `verified_purchase`| bool   | User purchase verification.                                                                                                                     |
| `helpful_vote`    | int    | Number of helpful votes the review received.                                                                                                     |

Item Metadata

| Field              | Type   | Explanation                                                                                                                                      |
|--------------------|--------|--------------------------------------------------------------------------------------------------------------------------------------------------|
| `main_category`     | str    | Main category (i.e., domain) of the product.                                                                                                     |
| `title`            | str    | Name of the product.                                                                                                                             |
| `average_rating`    | float  | Rating of the product shown on the product page.                                                                                                 |
| `rating_number`     | int    | Number of ratings for the product.                                                                                                               |
| `features`          | list   | Bullet-point format features of the product.                                                                                                     |
| `description`       | list   | Description of the product.                                                                                                                      |
| `price`             | float  | Price in US dollars (at time of crawling).                                                                                                       |
| `images`            | list   | Images of the product. Each image has different sizes (thumb, large, hi_res). The "variant" field shows the position of the image.                |
| `videos`            | list   | Videos of the product, including title and URL.                                                                                                  |
| `store`             | str    | Store name of the product.                                                                                                                       |
| `categories`        | list   | Hierarchical categories of the product.                                                                                                          |
| `details`           | dict   | Product details, including materials, brand, sizes, etc.                                                                                         |
| `parent_asin`       | str    | Parent ID of the product.                                                                                                                        |
| `bought_together`   | list   | Recommended bundles from the website.                                                                                                            |

Análise Exploratória de Dados

A análise exploratória é fundamental para entender a estrutura e as características dos
dados. Nesta seção, utilizaremos gráficos e estatísticas descritivas para compreender
melhor os dados para que o modelo seja aplicado posteriormente e seja possível.

Gráficos:
● Histogramas para as distribuições das notas.
● Gráficos de dispersão para correlação entre notas e sentimentos.
● Boxplots para identificar outliers nas notas.

Estatísticas Descritivas:
● Média, mediana, e moda das notas.
● Frequência de categorias de sentimentos em relação às notas.

Análise:
● Identificação de padrões e tendências nos dados.

**Bibliotecas**

Vamos utilizar as seguintes bibliotecas e suas funções específicas:
nltk: Utilizada para o processamento de linguagem natural, incluindo a tokenização, stemming,
lematização e remoção de stopwords.
plotly : Excelente para criar gráficos interativos e visualizações dinâmicas.
pandas: Essencial para a manipulação e análise de dados, facilitando a limpeza, transformação e
exploração de datasets.
seaborn: Complementa o matplotlib, fornecendo gráficos estatísticos e estéticos aprimorados.
watermark: Usada para adicionar informações de rodapé como versão de biblioteca e data nos
notebooks Jupyter.
numpy: Oferece suporte para arrays multidimensionais e funções matemáticas de alto
desempenho.
re: Biblioteca para manipulação e operação de expressões regulares, essencial para encontrar
padrões e substituir textos.
matplotlib: Ferramenta para criação de gráficos estáticos, animados e interativos,
frequentemente utilizada em conjunto com pandas e numpy.
Com estas bibliotecas, abordaremos de forma eficiente todas as etapas necessárias para nossa
análise.

**Tratamento da Base**

Limpeza de Dados:
- Remoção de dados duplicados.
- Tratamento de valores ausentes (imputação ou exclusão).
- Remoção de comentários não relevantes ou spam.

Transformação de Dados:
- Conversão de notas em categorias (positivo, neutro, negativo).
- Pré-processamento de texto (remoção de stopwords, stemming ou
lemmatization)
- Criação de variáveis dummy, se necessário.

Divisão dos Dados: 
- Separação dos dados em conjuntos de treino e teste

**Definição e Descrição das Bases Teóricas dos Métodos**

O estudo irá abordar a problemática por meio de três modelos/técnicas: Support Vector
Machines (SVM), Bidirectional Encoder Representations from Transformers (BERT) e
Term Frequency-Inverse Document Frequency (TF-IDF).

Support Vector Machines (SVM)

O SVM (Support Vector Machine ou Máquina de Vetores de Suporte) é um algoritmo de
aprendizado de máquina voltado para a classificação, que procura identificar o hiperplano
ideal que maximiza a distância entre classes distintas. Esse hiperplano divide os dados
em um espaço de n dimensões, enquanto as linhas adjacentes a ele, conhecidas como
vetores de suporte, são os pontos mais próximos que determinam essa distância. Ao
maximizar essa margem, o SVM consegue generalizar de forma mais eficaz,
proporcionando previsões de classificação mais precisas em novos conjuntos de dados.

Bidirectional Encoder Representations from Transformers (BERT)

O BERT (Bidirectional Encoder Representations from Transformers) é um algoritmo de
aprendizado profundo que serve como um “tradutor” da linguagem dos seres humanos
para a máquina. Ele utiliza a arquitetura Transformer, um mecanismo de atenção que
aprende as relações contextuais entre palavras (ou subpalavras) em um texto. Ao
contrário de modelos direcionais que leem o texto sequencialmente, o encoder do
Transformer lê toda a sequência de palavras de uma vez, permitindo que o modelo
aprenda o contexto de uma palavra com base em seu entorno, tanto à esquerda quanto à
direita. Para treinar o modelo de linguagem, o BERT emprega duas estratégias de
treinamento: a previsão de tokens mascarados e a previsão de próxima frase, superando
assim as limitações de modelos que apenas preveem a próxima palavra em uma
sequência.

Term Frequency-Inverse Document Frequency (TF-IDF)

O TF-IDF (Term Frequency-Inverse Document Frequency) é uma medida utilizada para
quantificar a importância ou relevância de textos em um documento em relação a uma
coleção de documentos.
O TF significa a frequência dos termos, seja ela a quantidade bruta que esses termos
aparecem no documento, ou pela frequência com base no tamanho do documento ou
mesmo de forma booleana, considerando 1 para o termo que aparece e 0 se não
aparece.
O IDF mostra a raridade dos termos em relação à coleção de documentos. Ele pega o
total de documentos na coleção e analisa quantos possuem os termos procurados,
fazendo uma divisão de forma logarítmica do número total de documentos na coleção
pelo número de documentos que possuem os termos.
O resultado final, TF-IDF, é a multiplicação de ambos os termos, portanto, quanto mais
próximo de 0 for o resultado, menos relevante será o termo.

**Definição e Descrição da Acurácia**

A acurácia é uma medida crucial na avaliação de modelos de análise de sentimentos,
especialmente quando se busca entender a relação entre as avaliações numéricas (notas
de 0 a 5) e os comentários textuais dos usuários. Neste contexto, a acurácia pode ser
definida como a proporção de previsões corretas sobre o total de previsões feitas. Para
avaliar a correspondência entre a nota atribuída e a análise de sentimento dos
comentários, consideramos os seguintes pontos:
Categorização das Notas
As notas podem ser categorizadas como positivas (4 e 5), neutras (3) e negativas (0 a 2).
Essa categorização nos permite comparar a polaridade dos comentários com a nota
fornecida.
Análise de Sentimentos
Utilizamos um modelo de análise de sentimentos para classificar os comentários em
categorias semelhantes: positivo, neutro ou negativo. O modelo é treinado com dados
rotulados, onde os sentimentos são previamente definidos.
Métricas de Avaliação
Para avaliar a eficácia do modelo, utilizamos a matriz de confusão, que nos permite
visualizar o desempenho do modelo em termos de previsões corretas e incorretas. As
métricas que analisamos incluem:
True Positives (TP): Comentários positivos que correspondem a notas de 4 ou 5.
True Negatives (TN): Comentários negativos que correspondem a notas de 0 a 2.
False Positives (FP): Comentários positivos que, na realidade, correspondem a notas de
0 a 2.
False Negatives (FN): Comentários negativos que correspondem a notas de 4 ou 5.
Acurácia do Modelo
A acurácia do modelo é calculada com a fórmula:

--

**Análises de Sentimentos com Vader**

Neste script, aplicamos a ferramenta de análise de sentimentos VADER (Valence Aware Dictionary and sEntiment Reasoner) para classificar o sentimento de avaliações textuais. VADER é um modelo popular baseado em regras usado para analisar o sentimento expresso em texto, projetado especificamente para lidar com mídias sociais, mas aplicável a qualquer tipo de dado textual.

Análise de sentimentos com VADER: Começamos inicializando uma instância do SentimentIntensityAnalyzer, que calcula a polaridade de um determinado texto. VADER calcula quatro pontuações de sentimentos para cada avaliação: positiva, negativa, neutra e uma pontuação composta. A pontuação composta representa um sentimento geral, normalizado entre -1 (extremamente negativo) a +1 (extremamente positivo).

Extração da pontuação composta: Depois de aplicar VADER a cada avaliação na coluna Cleaned_Review, armazenamos os resultados em uma nova coluna vader_scores. Deste dicionário, extraímos especificamente a pontuação composta, o que simplifica a tarefa de classificar o sentimento geral em "Positivo", "Negativo" ou "Neutro" com base em limites definidos.

Classificando sentimentos: A função classify_sentiment usa a pontuação composta para categorizar o sentimento. Uma pontuação maior ou igual a 0,05 indica um sentimento positivo, uma pontuação menor ou igual a -0,05 indica um sentimento negativo e qualquer coisa entre os dois é considerada neutra. Essa classificação ajuda a entender o tom emocional transmitido no texto da revisão.

Saída final: Após aplicar a classificação de sentimento, o DataFrame agora contém colunas para o texto original da revisão limpa, a pontuação composta e o rótulo do sentimento final. Isso permite uma interpretação fácil das pontuações numéricas de sentimento e suas respectivas categorias (Positivo, Neutro ou Negativo). Em seguida, exibimos as primeiras entradas para visualizar os resultados.

No geral, este script demonstra uma maneira simples e eficaz de realizar análise de sentimentos em dados de texto usando o VADER, permitindo a categorização automatizada do tom emocional em avaliações de clientes, feedback ou qualquer outra forma de texto escrito."

**Análise**

Dominância de sentimento positivo: - A esmagadora maioria das avaliações é classificada como positiva (525.365 contagens). Isso sugere que os clientes estão geralmente satisfeitos ou expressando opiniões favoráveis ​​nas avaliações.

Sentimento neutro: - Há um número significativamente menor de avaliações classificadas como neutras (77.025 contagens). Isso significa que poucas avaliações não são nem fortemente positivas nem negativas, mostrando uma falta de feedback intermediário.

Sentimento negativo: - Uma pequena parte das avaliações é classificada como negativa (99.138 contagens). Embora menos do que avaliações positivas, isso indica que alguns clientes estão compartilhando insatisfação ou experiências negativas.

*Representação visual: *- O gráfico de barras destaca claramente a distribuição desproporcional de sentimentos, onde as avaliações positivas superam em muito os sentimentos negativos e neutros.

A rotulagem é bem feita, com os números de contagem exatos anotados no topo de cada barra, permitindo fácil compreensão dos dados. Melhorias no equilíbrio: - Se o conjunto de dados visa representar uma análise de sentimento equilibrada, pode ser necessário reunir ou equilibrar mais avaliações negativas ou neutras para evitar o domínio do sentimento positivo. Alternativamente, tal desequilíbrio pode ser um reflexo de uma experiência do cliente geralmente positiva.













