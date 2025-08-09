 # 📡 Telecom X — Previsão de Evasão de Clientes (Churn)

Este projeto tem como objetivo prever a evasão de clientes de uma operadora de telecomunicações (Telecom X) utilizando técnicas de ciência de dados e aprendizado de máquina. A partir de dados históricos de clientes, foram desenvolvidos modelos preditivos capazes de identificar perfis com maior risco de cancelamento, contribuindo para estratégias de retenção mais eficazes.

## 📁 Estrutura do Projeto

- `data/` — Conjunto de dados tratados e codificados.
- `notebooks/` — Análises exploratórias, modelagem e visualizações.
- `models/` — Modelos treinados e métricas de avaliação.
- `reports/` — Relatórios e gráficos gerados.
- `README.md` — Documentação do projeto.

## 🧪 Metodologia

1. **Análise Exploratória de Dados (EDA)**
   - Verificação da proporção de churn
   - Análise de correlação entre variáveis
   - Visualizações com boxplots e scatter plots

2. **Pré-processamento**
   - One-Hot Encoding para variáveis categóricas
   - Balanceamento das classes com SMOTE
   - Padronização dos dados com Z-score
   - Separação em treino e teste com estratificação

3. **Modelagem**
   - Regressão Logística
   - Random Forest Classifier
   - K-Nearest Neighbors (KNN)

4. **Avaliação**
   - Métricas: Precisão, Recall, F1-score, AUC
   - Curvas ROC
   - Matriz de confusão
   - Análise de importância das variáveis

## 🧹 Preparação dos Dados

### 🔢 Classificação das Variáveis

- **Numéricas**: `tenure`, `monthly_charges`, `total_charges`
- **Categóricas**: `contract`, `payment_method`, `internet_service`, `gender`, `partner`, `dependents`, entre outras

### ⚙️ Etapas de Pré-processamento

- **Codificação**: Aplicado One-Hot Encoding para variáveis categóricas
- **Normalização**: Padronização das variáveis numéricas com Z-score
- **Balanceamento**: Utilizado SMOTE para equilibrar as classes (churn vs não churn)
- **Separação dos dados**: Dividido em treino (80%) e teste (20%) com estratificação para manter a proporção de churn

#### Distribuição CHURN
<img width="580" height="455" alt="Distribuição CHURN" src="https://github.com/user-attachments/assets/6482bdec-cf33-4f41-8fc8-5861a88c86ce" />

### 🧠 Justificativas das Escolhas

- **One-Hot Encoding**: Evita ordens artificiais em variáveis categóricas
- **Z-score**: Essencial para algoritmos sensíveis à escala como KNN e Regressão Logística
- **SMOTE**: Corrige o desbalanceamento da variável alvo, melhorando o recall
- **Estratificação**: Garante representatividade da classe minoritária no conjunto de teste

---

## 📊 Análise Exploratória de Dados (EDA)

Durante a EDA, foram gerados diversos gráficos para entender o comportamento dos clientes:

- **Boxplots**: Comparação de `monthly_charges` entre clientes que saíram e os que permaneceram
- **Histograma de Tenure**: Clientes com menos tempo de contrato têm maior propensão ao churn
- **Gráfico de barras**: Contratos mensais apresentam maior taxa de evasão
- **Heatmap de correlação**: Identificação de relações entre variáveis numéricas

#### Matriz de Correlação
<img width="881" height="787" alt="matriz correlacao telecom x 2" src="https://github.com/user-attachments/assets/5ae92a1d-0485-407f-acfa-275ae2103ac5" />

#### Distribuição Tempo Contrato vs. CHURN
<img width="841" height="701" alt="distribuição tempo contrato vs churn" src="https://github.com/user-attachments/assets/c403e1d9-ab01-4916-afe9-5814f605c160" />


#### Distribuição Total Gasto vs. CHURN
<img width="859" height="701" alt="Distribuição total gasto vs churn" src="https://github.com/user-attachments/assets/ffc7dc8d-cd75-4b91-8c9f-bde0bb409da6" />


#### Scatter Plot Tempo Contrato vs. Gasto Total (com Churn)
<img width="889" height="590" alt="scatter plot tempo contrato vs gasto total com Churn" src="https://github.com/user-attachments/assets/3838ea58-271d-4243-b8ab-53ebaa9247b3" />


### 🔍 Insights Relevantes

- Clientes com contrato `Month-to-month` e pagamento via `Electronic check` têm maior risco de churn
- O tempo de contrato (`tenure`) é inversamente proporcional à probabilidade de evasão
- Serviços como `Fiber optic` estão associados a maior taxa de cancelamento

---

## 🤖 Modelagem Preditiva

Modelos testados:

- **Regressão Logística** — melhor desempenho geral
- **Random Forest** — bom para interpretação de variáveis
- **KNN** — sensível à escala, usado como comparação

#### Modelo Regresão Logistica
<img width="584" height="432" alt="modelo reg log" src="https://github.com/user-attachments/assets/7520ca21-1863-473f-bad1-b6efac7a6172" />

#### Modelo Random Forest Classifier
<img width="584" height="432" alt="Modelo random forest" src="https://github.com/user-attachments/assets/117204ad-4510-473f-b61a-86d3d9e6a8b0" />

#### Modelo KNN
<img width="584" height="432" alt="Modelo KNN" src="https://github.com/user-attachments/assets/082615ef-5391-4760-a72e-93774a24a620" />

#### Matriz de Confusão Lado a Lado
<img width="1176" height="590" alt="matriz confusão lado a lado" src="https://github.com/user-attachments/assets/280792ac-1784-44b3-bae9-99caf4d3b558" />


### 📈 Métricas do Modelo Final (Regressão Logística)

| Métrica        | Valor   |
|----------------|---------|
| AUC            | 0.8443  |
| Recall (Churn) | 0.80    |
| F1-score       | 0.63    |


## 📊 Principais Resultados

- **Regressão Logística** apresentou o melhor desempenho geral:
  - AUC: 0.8443
  - Recall (Churn): 0.80
  - F1-score (Churn): 0.63

- **Variáveis mais influentes**:
  - Tipo de contrato (`Month-to-month`)
  - Método de pagamento (`Electronic check`)
  - Tempo de contrato (`tenure`)
  - Total gasto (`total_charges`)
  - Tipo de serviço de internet (`Fiber optic`)


#### Principais Fatores CHURN (Regressão Logística)
<img width="992" height="590" alt="importancia var reg log" src="https://github.com/user-attachments/assets/663a4f0a-1676-4302-b83d-14faf349f5f7" />


## 🎯 Estratégias de Retenção Recomendadas

- Foco em clientes com contratos mensais
- Incentivo a métodos de pagamento automáticos
- Ações preventivas nos primeiros meses de contrato
- Oferta de serviços adicionais (suporte técnico, segurança online)
- Ajuste do limiar de decisão para otimizar ações de retenção

## ✅ Conclusão

O projeto demonstra como a aplicação de modelos preditivos pode antecipar comportamentos críticos e orientar decisões estratégicas. A Regressão Logística se mostrou eficaz na identificação de clientes em risco, e a análise das variáveis fornece insights valiosos para ações direcionadas.

## 🚀 Próximos Passos

- Implantação do modelo em ambiente produtivo
- Monitoramento contínuo da performance
- Integração com sistemas de CRM e campanhas de retenção

- ▶️ Executando o Notebook
- Clone o repositório:
git clone https://github.com/Krurosu/Telecom_X_2_Challenge.git
cd Telecom-X-Churn

- Abra o notebook principal:
jupyter notebook notebooks/churn_analysis.ipynb
- Certifique-se de que o arquivo telecom_churn_clean.csv está na pasta data/.
- Execute as células sequencialmente para reproduzir toda a análise.

- ## 🛠️ Instruções de Execução

### 📦 Bibliotecas Necessárias

Certifique-se de instalar as seguintes bibliotecas:

pandas | numpy | matplotlib | seaborn | scikit-learn | imbalanced-learn

