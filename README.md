# Previsão do Diagnóstico de Diabetes.

![Alt Text](URL da imagem)

## Descrição do Projeto

O objetivo deste projeto é desenvolver um modelo de aprendizado de máquina capaz de prever diagnosticamente se um paciente possui ou não diabetes. A base de dados utilizada é originária do National Institute of Diabetes and Digestive and Kidney Diseases e foi fornecida pelo Kaggle. A seleção dessas instâncias envolveu restrições específicas, sendo todas as pacientes mulheres com pelo menos 21 anos e de herança Pima Indian.

## Motivação

O problema central abordado neste projeto é a previsão do diagnóstico de diabetes em pacientes com base em medidas diagnósticas específicas. A importância dessa previsão reside na capacidade de antecipar e identificar pacientes em risco, permitindo intervenções médicas precoces e personalizadas.

## Conjunto de Dados

### Contexto

Os conjuntos de dados consistem em várias variáveis preditoras médicas e uma variável de destino, "Outcome". As variáveis preditoras incluem o número de gestações que a paciente teve, seu índice de massa corporal (BMI), nível de insulina, idade, entre outras.

### Fonte dos Dados

Os dados foram originalmente fornecidos pelo National Institute of Diabetes and Digestive and Kidney Diseases, e a seleção específica de instâncias foi realizada com base em determinadas restrições. A pesquisa original que resultou neste conjunto de dados foi conduzida por Smith, Everhart, Dickson, Knowler e Johannes em 1988, utilizando o algoritmo de aprendizado ADAP para prever o início do diabetes mellitus.

### Inspiração

O projeto é inspirado no desafio de construir um modelo de aprendizado de máquina que seja capaz de prever com precisão se os pacientes no conjunto de dados possuem ou não diabetes. A inspiração para esse desafio é a busca por métodos eficazes de identificação e prevenção de condições médicas críticas.

### Dados no Kaggle

Os dados utilizados neste projeto podem ser encontrados no Kaggle. [Clique aqui para acessar os dados no Kaggle](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database).

## Principais Técnicas/Algoritmos Utilizados

O desenvolvimento do modelo foi feito usando o pandas. Foi aplicada uma seleção de variáveis para selecionar as melhores variáveis para o modelo – foi utilizado feature importance com Random forest. Os modelos estatísticos treinados e testados foram árvore de decisão, regressão logística, Random forest e regressão logística. Esses modelos foram importados do scikit-learn.

A avaliação do modelo será realizada utilizando métricas apropriadas para problemas de classificação binária, como precisão, recall, F1-score e a área sob a curva ROC (AUC-ROC). O objetivo é desenvolver um modelo que alcance alto desempenho na previsão de casos positivos e negativos de diabetes, proporcionando uma base sólida para decisões médicas.

## Estrutura do Projeto

### 1 – Data prep. 
[Acesse o código de etapa aqui](https://github.com/Rafael-Salomao/Predicao-de-Diabetes/blob/fec5f2b4528976be8d7eccaafc687b1c49e47651/01%20Data%20Prep/Predi%C3%A7%C3%A3o_de_Diabetes_01_DataPrep.ipynb)

- Introdução
- Entendimento do Problema
- Entendimento dos Dados
- Preparação dos Dados
- Bibliotecas que serão utilizadas no projeto
- Lendo os dados disponibilizados
- Separando dados para garantir validação cruzada Holdout 70/30
- Metadados
- Tratamento de Nulos
- Padronização
- Salvando tabelas de treino e teste pós preparação dos dados

### 2 - Feature Selection 
[Acesse o código de etapa aqui](https://github.com/Rafael-Salomao/Predicao-de-Diabetes/blob/c0827ea4ee5b8ddbdb086b3844553f4424be34b0/02%20Feature%20Selection/Predi%C3%A7%C3%A3o_de_Diabetes_02_FeatureSelection.ipynb)

- Lendo dados pós processo de data prep
- Obter importância das variáveis
- Salvando abt para treinamento dos modelos

### 3 - Treinamento e Avaliação dos Modelos
[Acesse o código de etapa aqui](https://github.com/Rafael-Salomao/Predicao-de-Diabetes/blob/c0827ea4ee5b8ddbdb086b3844553f4424be34b0/03%20Modelos/Predi%C3%A7%C3%A3o_de_Diabetes_03_Modelos.ipynb)

- Importar bibliotecas
- Funções que serão utilizadas
- Importar base de dados com as principais variáveis
- Verificar distribuição da taxa de evento
- Separando as variáveis de entrada (features) e de saída (target)
- Treinamento dos modelos
  - Árvore de Decisão
  - Regressão Logística
  - Random Forest
  - LightGBM
- Escolha Modelo Campeão
- Salvando artefatos dos modelos

### 4 - Código de Escoragem
[Acesse o código de etapa aqui](https://github.com/Rafael-Salomao/Predicao-de-Diabetes/blob/c0827ea4ee5b8ddbdb086b3844553f4424be34b0/04%20Escoragem/Predi%C3%A7%C3%A3o_de_Diabetes_04_Escoragem.ipynb)

- Leitura dos dados a serem escorados
- Separar 70% dos dados para treino e 30% para validação
- Carregar os encoders e a lista de colunas
- Carregar a padronização
- Carregar lista de variáveis que passaram pelo Feature Selection (utilizadas no treinamento do modelo)
- Carregando modelo campeão
- Escorando base de treino e teste
- Salvando como arquivo csv

### Conclusão

#### Resultados:

O modelo escolhido é o Random Forest, destaca-se pela ordenação eficaz das taxas de score, proporcionando uma identificação eficiente de pacientes propensos ou menos propensos a desenvolver diabetes. Seu bom desempenho na métrica AUC reforça a confiabilidade na capacidade do modelo de distinguir entre casos positivos e negativos. Além disso, a consistência nas métricas de KS, Gini e AUC para as bases de treinamento e teste sugere que o modelo não tenha overfitting, garantindo robustez e generalização para novos dados. Essa escolha é respaldada por sua eficácia e confiabilidade na predição de casos de diabetes.

#### Discussão

Ao finalizar o projeto, o modelo desenvolvido revela a capacidade de prever a probabilidade de um indivíduo desenvolver diabetes. Essa informação permite a implementação de medidas preventivas antecipadas para mitigar os impactos da doença ou adiar sua manifestação. O modelo demonstra uma sólida capacidade de predição, sendo eficaz na identificação de indivíduos mais ou menos propensos à condição. Nesse sentido, é recomendado que aqueles com pontuações intermediárias busquem uma avaliação mais detalhada por profissionais de saúde. Assim, o modelo serve como uma ferramenta valiosa para auxiliar na tomada de decisão desses profissionais.

### Próximos Passos

O desenvolvimento subsequente do projeto envolverá a implementação em produção, possibilitando a criação de um aplicativo para entrada de informações dos pacientes e obtenção de resultados em tempo real. Isso permitirá identificar rapidamente se uma pessoa é propensa, não é propensa ou requer uma análise mais detalhada.

## Contato

Quer falar comigo? Conecte-se comigo no [LinkedIn](https://www.linkedin.com/in/rafaelsdomingos/) ou se preferir, escreva um e-mail para rafael.salomaod96@gmail.com. Também estou presente no [Medium](https://medium.com/@rafael.salomaod), compartilhando aprendizados ao longo dos meus estudos em Big Data & Analytics.
