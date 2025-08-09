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
