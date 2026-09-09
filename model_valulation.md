## Avaliação de Modelos

> **Status:** rascunho / estrutura — artigo em elaboração.

**Resumo:** Avaliar se o modelo é realmente útil é, talvez, um dos principais passos antes de iniciar seu desenvolvimento. Para saber se um modelo é bom, precisamos ter com o que comparar, ou seja uma baseline. Este artigo reúne as principais métricas e técnicas para avaliar modelos de *Machine Learning*, organizadas por tipo de problema — Classificação, Regressão, Clustering, Séries Temporais. Além de considerações que se aplicam a qualquer modelo, independentemente da categoria. Assim buscaremos apresentar métricas em que seja possivel decidir estatisticamente se o modelo é viavel em cenários diversificados.

---

### 1. Introdução

**Avaliação de modelos** é o processo de medir o desempenho e a qualidade preditiva de um algoritmo de Aprendizagem de Máquina (*Machine Learning*) usando dados de teste independentes.

- Por que avaliar modelos vai além da acurácia
- Overfitting vs. underfitting: o papel da avaliação na detecção
- Divisão dos dados: treino, validação e teste
- Validação cruzada (k-fold, stratified k-fold, time series split)

---

### 2. Classificação

- Matriz de confusão (verdadeiro/falso positivo e negativo)

    |                   | Predito Positivo | Predito Negativo |
    | ----------------- | ---------------- | ---------------- |
    | **Real Positivo** | VP               | FN               |
    | **Real Negativo** | FP               | VN               |


- Acurácia (*accuracy*) — Mede a porcentagem total de previsões corretas do modelo.

$$ 
\text{Acurácia} = \frac{TP + TN}{TP + TN + FP + FN} 
$$

- Precisão (*precision*) - Indica a proporção de verdadeiros positivos entre todas a previsões positivas feitas.

$$ 
\text{Precisão} = \frac{VP}{VP + FP} 
$$

- Revocação(*recall*) - Mede a capacidade do modelo de encontrar todos os casos positivos reais.

$$ 
\text{Revocação} = \frac{VP}{VP + FN} 
$$

- F1-score - É a medida harmônica entre a precisão e revocação.

$$ 
\text{F1-Score} = 2 \times \frac{\text{Precisão} \times \text{Recall}}{\text{Precisão} + \text{Recall}} 
$$

- Curva ROC e AUC - Avaliam a separação entre as classes em diferentes limites de decisão.
- Curva Precision-Recall
- Log loss
- Matthews Correlation Coefficient
- Estratégias para classes desbalanceadas (SMOTE, class weights, threshold tuning)

---

### 3. Regressão

- MAE (*Mean Absolute Error* - Erro Absoluto Médio) - Média da soma dos valores absolutos dos erros.

$$ 
\text{MAE} = \frac{1}{n}\sum_{i=1}^{n}|y_i - \hat{y}_i| 
$$

Analogia: Pense que uma casa pode ser vendida por R$ 500.000,00, mas é vendida por R$ 525.000,00 e na próxima semana pensa que pode ser vendida por R$ 400.000,00, mas é vendida por R$ 390.000,00, seu MAE é R$ 17.500,00, ou seja, (R$ 25.000,00 + R$ 10.000,00, divido por 2). O MAE ignora se um modelo está consistentemente superestimando ou subestimando suas previsões. Ele simplismente analisa a distância média em relação à verdade.

- RSE (Relative Squared Error)

$$ 
\text{RSE} = \frac{\sum_{i=1}^{n}(y_i - \hat{y}_i)^2}
{\sum_{i=1}^{n}(y_i - \bar{y})^2} 
$$

- RMSE (*Root Mean Squared Error* - Raiz do Erro Quadrático Médio) - 

$$ 
\text{RMSE} = \sqrt{\frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2} 
$$

- MSE e RMSE (Erro Quadrático Médio)
- MAPE (Erro Percentual Absoluto Médio)
- RMSLE
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
