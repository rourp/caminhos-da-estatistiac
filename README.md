# Grupo caminhos-da-estatistica

Este repositório contém todos os arquivos relacionados ao projeto TextInsight. Abaixo está a lista de arquivos incluídos:

**caminhos_da_estatistica.ipynb:**   
Este notebook Jupyter contém o código e as análises estatísticas realizadas durante o projeto.

**Apresentação do projeto - TextInsight.pdf:**   
Um documento PDF que apresenta uma visão geral do projeto, incluindo objetivos, metodologia e resultados principais.

**Relatório Técnico TextInsight.pdf:**   
Um relatório técnico detalhado que descreve todas as etapas do projeto, incluindo a coleta de dados, análise e conclusões.

**Proposta do Projeto - TextInsight.pdf:**   
A proposta inicial do projeto, detalhando o escopo, objetivos e plano de ação.

**Link repositório GitHub.pdf:**   
Um documento contendo o link para acessar este repositório no GitHub.



**Objetivo do Estudo: Apresentação da Empresa**  
A empresa escolhida é a Amazon, uma multinacional de tecnologia dos EUA, fundada em 1994 como uma livraria online. Hoje, é uma das maiores empresas do mundo, atuando em diversas áreas como livros, varejo, eletrônicos, streaming, videogames, serviços de cloud (AWS), entre outros. A Amazon utiliza grandes quantidades de dados e algoritmos complexos para otimizar a experiência do consumidor.

**Objetivo do Estudo: Problema de Pesquisa**  
A Amazon transformou-se de uma livraria online em uma gigante do varejo global, superando adversidades como a bolha da internet. Um fator crucial para seu crescimento foi a expansão de produtos e a criação de um marketplace, onde o sistema de avaliações desempenhou um papel essencial para ganhar a confiança dos consumidores.

**Foco da Pesquisa**  
O estudo foca no sistema de avaliações da Amazon, especialmente no mercado de materiais de escritório, que passou por grandes mudanças durante a pandemia da COVID-19. A pesquisa analisará como as avaliações ajudaram os consumidores a se adaptarem ao home office e a escolherem os melhores produtos, como cadeiras ergonômicas e equipamentos eletrônicos.

**Metodologia**  
Coleta e Pré-processamento de Dados: Utilização da base de dados "Amazon Reviews 2023" focada em materiais de escritório.
Desenvolvimento de Modelo de NLP: Classificação do sentimento das avaliações (positivo, negativo ou neutro) usando modelos como SVM, BERT, TF-IDF.
Validação e Teste: Avaliação do desempenho do modelo em termos de precisão e recall.
Implementação de Painel de Controle: Visualização da distribuição de sentimentos ao longo do tempo e insights sobre mudanças nas preferências dos consumidores.
Objetivo Final
Investigar como as avaliações ajudaram os consumidores a encontrar produtos de qualidade e a superar a transição para o home office, além de entender o impacto desse sistema de reviews na confiança e satisfação dos clientes no setor de materiais de escritório.
Análise Exploratória de Dados  

A análise exploratória é fundamental para entender a estrutura e as características dos
dados. Nesta seção, utilizaremos gráficos e estatísticas descritivas para compreender
melhor os dados para que o modelo seja aplicado posteriormente e seja possível.

**Gráficos:**  
● Histogramas para as distribuições das notas.
● Gráficos de dispersão para correlação entre notas e sentimentos.
● Boxplots para identificar outliers nas notas.

**Estatísticas Descritivas:**  
● Média, mediana, e moda das notas.
● Frequência de categorias de sentimentos em relação às notas.

**Análise:**  
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













