# Prova – Regressão Logística

## Parte A – Análise Exploratória, Validação Cruzada, Lasso e Ridge

### Dataset
Utilize o dataset [Gender Recognition by Voice and Speech Analysis](https://raw.githubusercontent.com/primaryobjects/voice-gender/master/voice.csv).

### 1. Preparação e Análise Exploratória
- Carregue o dataset e crie um DataFrame com todas as features e a variável alvo.
- Verifique a proporção das classes para avaliar o balanceamento do alvo.
- Analise a distribuição de cada feature utilizando histogramas ou gráficos de densidade.
- Calcule a matriz de correlação entre as features e discuta possíveis problemas de multicolinearidade.
- Discuta as diferentes escalas das features e justifique a necessidade de padronização.

### 2. Grid Search com Validação Cruzada
- Padronize os dados com `StandardScaler`.
- Configure um modelo `LogisticRegression` e utilize `GridSearchCV` com validação cruzada k-fold (k=5) para testar:
    - Penalização L1 (Lasso) e L2 (Ridge)
    - Diferentes valores de C: `[0.01, 0.1, 1, 10, 100]`
- Reporte a combinação de parâmetros com melhor desempenho médio de validação.

### 3. Modelo Final
- Reajuste o modelo nos dados de treino usando os melhores hiperparâmetros.
- Reporte acurácia, precisão, recall, F1-score e matriz de confusão no conjunto de teste.

### 4. Discussão
- Compare os coeficientes obtidos para L1 e L2.
- Indique quais variáveis foram eliminadas no caso do Lasso.
- Discuta os efeitos práticos da regularização no desempenho e na interpretabilidade do modelo.

---

## Parte B – Alterando a Função de Perda

### 1. Experimento
- Implemente um modelo de regressão logística alternativo que utilize RMSE (Root Mean Squared Error) como função de perda (pode ser manual ou adaptando o scikit-learn).
- Treine o modelo e reporte acurácia e curva ROC no conjunto de teste.

### 2. Comparação
- Compare os resultados do modelo com RMSE com os resultados do modelo logístico padrão (log-loss).
- Plote a curva de decisão para verificar se o modelo treinado com RMSE produz probabilidades bem calibradas.

### 3. Discussão Crítica
- Explique por que RMSE é uma péssima ideia para regressão logística:
    - A regressão logística produz probabilidades, não valores contínuos.
    - RMSE não penaliza adequadamente previsões de alta confiança incorretas.
    - Log-loss é mais sensível a erros em probabilidades extremas.
- Conclua: o que acontece com a interpretação e qualidade das probabilidades quando trocamos log-loss por RMSE?

---

**Referência do dataset:**  
https://raw.githubusercontent.com/primaryobjects/voice-gender/master/voice.csv