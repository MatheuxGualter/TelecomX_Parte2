# TelecomX_Parte2

# Projeto de Análise de Churn da Telecom X - Parte 2: Modelagem Preditiva

## 🚀 Propósito da Análise

O objetivo principal deste projeto é desenvolver e avaliar modelos de Machine Learning capazes de prever a evasão de clientes (churn) da empresa de telecomunicações Telecom X. A análise visa identificar os clientes com maior probabilidade de cancelar seus serviços, permitindo à empresa agir proativamente com estratégias de retenção, minimizando assim as perdas financeiras.

-----

## 📂 Estrutura do Projeto

O projeto está organizado na seguinte estrutura de arquivos:

  - `README.md`: Este arquivo, que descreve o projeto e suas etapas.
  - `projeto_telecom_churn.ipynb`: O notebook principal que contém todo o código para preparação dos dados, modelagem e análise.
  - `dados_tratados.csv`: O dataset original, já limpo e padronizado, proveniente da primeira parte do desafio.
  - `dados_preparados_para_modelagem.csv`: O dataset após as etapas de pré-processamento (codificação, etc.), pronto para ser usado nos modelos.
  - `visualizations/`: Diretório para armazenar os gráficos gerados, como matrizes de correlação e gráficos de importância das variáveis.

-----

## 🔧 Preparação dos Dados para Modelagem

Antes de construir os modelos preditivos, o dataset passou pelas seguintes etapas de preparação:

1.  **Classificação e Tratamento de Variáveis**:

      - As variáveis categóricas, como `Servico_Internet` e `Tipo_Contrato`, foram identificadas e transformadas em formato numérico usando a técnica de **One-Hot Encoding**.
      - Variáveis irrelevantes para a análise preditiva, como `ID_Cliente`, foram removidas.

2.  **Normalização dos Dados**:

      - As variáveis numéricas foram normalizadas usando `StandardScaler` para garantir que todas estivessem na mesma escala. Essa etapa é crucial para modelos como a Regressão Logística, que são sensíveis à magnitude dos dados.

3.  **Separação dos Dados**:

      - O dataset foi dividido em dois conjuntos: **treino (80%)** e **teste (20%)**. A separação foi feita com estratificação (`stratify`), garantindo que a proporção de clientes que evadiram (`Evasao = 1`) seja a mesma em ambos os conjuntos, o que é fundamental para a avaliação precisa dos modelos.

-----

## 🤖 Modelagem Preditiva e Avaliação

Dois modelos de classificação foram criados e comparados para prever a evasão de clientes.

### **Modelos Escolhidos**

  - **Regressão Logística**:

      - **Justificativa**: É um modelo linear, simples e altamente interpretável. Foi treinado dentro de um pipeline que inclui a etapa de normalização (`StandardScaler`) para otimizar seu desempenho.
      - **Avaliação**: Apresentou uma acurácia de **80,10%** e um `recall` para a classe de evasão de **53%**, mostrando um bom desempenho geral.

  - **Random Forest**:

      - **Justificativa**: É um modelo de ensemble baseado em árvores de decisão que não requer normalização dos dados. É robusto e geralmente tem um bom desempenho em problemas de classificação.
      - **Avaliação**: Obteve uma acurácia de **77,97%** e um `recall` para a classe de evasão de **46%**, um desempenho ligeiramente inferior ao da Regressão Logística.

### **Métricas de Avaliação**

Os modelos foram avaliados com as seguintes métricas, que são essenciais para problemas de classificação desbalanceados:

  - **Acurácia**: Medida geral de acerto.
  - **Precisão**: Proporção de acertos para a classe positiva (evasão).
  - **Recall**: Capacidade do modelo de encontrar todos os casos positivos (evasão).
  - **F1-score**: Média harmônica entre precisão e recall.
  - **Matriz de Confusão**: Visualização que mostra o número de acertos e erros de cada classe.

-----

## 📊 Análise e Principais Insights

A análise da importância das variáveis, por meio dos coeficientes da Regressão Logística e da importância de recursos do Random Forest, revelou os seguintes insights:

  - **Principais Fatores que Levam à Evasão**:

      - **Serviço de Internet (Fibra Óptica)**: Clientes que utilizam fibra óptica são mais propensos a cancelar.
      - **Método de Pagamento (Cheque Eletrônico)**: O uso de pagamentos eletrônicos está associado a uma maior taxa de churn.

  - **Principais Fatores de Retenção**:

      - **Meses de Contrato**: O tempo de contrato é o fator mais crucial para a retenção. Clientes com contratos mais longos têm menor probabilidade de evadir.
      - **Tipo de Contrato (Dois Anos)**: Contratos de longo prazo são um forte indicador de retenção.
4.  **Execute as Células**:

      - Execute as células do notebook `projeto_telecom_churn.ipynb` em sequência para replicar todo o processo de análise e modelagem.
