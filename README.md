# desafio-01-python-dio
Projeto de Detecção de Anomalias em Transações com Python - curso Santander - Dados com Python e IA

A partir de um dataset carregado via API, temos um conjunto de dados que representam transações reais com cartão de crédito e queremos treinar modelos para detectar fraudes. A quantidade de transações fraudulentas frente ao número de transações normais é muito baixa, gerando um desbalanceamento dos dados. Se isso não for observado no treinamento do modelo, ele poderá simplesmente aprender que tudo está normal e não detectar as fraudes.

Assim, foram utilizadas algumas técnicas para melhorar o dataset para treinamento dos modelo.

Inicialmente, observando a coluna de valor (Amount), percebe-se uma distinção grande entre os números. Foi utilizada a função logP1 da biblioteca numPy para criar uma nova coluna Amount_log e aplicar a fórmula: Amount_log = ln (Amount + 1).

A seguir, foram padronizados os dados com o StandardScaler, criando uma coluna Amount_scaled para distribuir melhor os pesos das vairáveis e ajudar no aprendizado dos modelos.

Testou-se três modelos:
1) Logistic Regression
2) Random Forest
3) XGBoost

Diferentemente da Expert, o limiar de decisão utilizado foi o padrão, de 50% e não 30%. Observamos que ao final, com o modelo XGBoost que apresentou melhores resultados, o valor da precisão ficou em 0.94, contra 0.93 da Expert, permanecendo o recall e o f1-score com os mesmos valores que ela obteve.

Ainda foram feitos testes usando Oversampling e Undersampling, porém os resultados obtidos foram piores.

