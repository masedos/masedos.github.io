## Avaliação de Modelos

> **Status:** rascunho / estrutura — artigo em elaboração.

**Resumo:** este artigo reúne as principais métricas e técnicas para avaliar modelos de Machine Learning, organizadas por tipo de problema — Classificação, Regressão, Clustering, Séries Temporais — além de considerações que se aplicam a qualquer modelo, independentemente da categoria.

---

### 1. Introdução

- Por que avaliar modelos vai além da acurácia
- Overfitting vs. underfitting: o papel da avaliação na detecção
- Divisão dos dados: treino, validação e teste
- Validação cruzada (k-fold, stratified k-fold, time series split)

---

### 2. Classificação

- Matriz de confusão (verdadeiro/falso positivo e negativo)
- Acurácia — quando ela engana (dados desbalanceados)
- Precision, Recall e F1-score
- Curva ROC e AUC
- Curva Precision-Recall
- Log loss
- Estratégias para classes desbalanceadas (SMOTE, class weights, threshold tuning)

---

### 3. Regressão

- MAE (Erro Absoluto Médio)
- MSE e RMSE (Erro Quadrático Médio)
- MAPE (Erro Percentual Absoluto Médio)
- R² e R² ajustado
- Análise de resíduos
- Quando usar cada métrica (sensibilidade a outliers, interpretabilidade)

---

### 4. Clustering

- Métricas internas: Silhouette Score, Índice de Davies-Bouldin, Índice de Calinski-Harabasz
- Métricas externas (quando há rótulos de referência): Rand Index, Adjusted Rand Index, Mutual Information
- Método do cotovelo (Elbow Method) para escolha do número de clusters
- Limitações da avaliação em aprendizado não supervisionado

---

### 5. Séries Temporais

- Divisão temporal dos dados (evitar vazamento de informação do futuro)
- MAE, RMSE e MAPE aplicados a forecasting
- Backtesting e validação com janelas deslizantes (rolling/expanding window)
- Comparação com baselines (naive forecast, média móvel)

---

### 6. Sistemas de Recomendação

- Precision@K e Recall@K
- MAP (Mean Average Precision) e NDCG
- Coverage e diversidade das recomendações

---

### 7. Considerações Gerais

- Trade-off entre viés e variância
- Custo computacional e latência como critério de avaliação
- Interpretabilidade e explicabilidade (SHAP, feature importance)
- Monitoramento de modelos em produção (drift de dados e de conceito)

---

### 8. Conclusão

_(a escrever)_

### Referências

_(a escrever)_
