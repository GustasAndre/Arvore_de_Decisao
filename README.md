Previsão de Empréstimos Pessoais usando Árvores de Decisão e Random Forest
Este projeto visa prever se um cliente aceitará uma oferta de empréstimo pessoal utilizando modelos de Árvore de Decisão e Random Forest. O conjunto de dados contém informações demográficas e comportamentais dos clientes que são usadas para construir e avaliar os modelos.

Conjunto de Dados
O dataset utilizado neste projeto é o Bank Personal Loan Modelling, que contém as seguintes variáveis:

Age: Idade do cliente
Experience: Anos de experiência profissional
Income: Renda anual do cliente
Family: Tamanho da família
CCAvg: Média de gastos mensais no cartão de crédito
Education: Nível educacional (1: Graduação, 2: Pós-graduação, 3: Profissional)
Mortgage: Valor da hipoteca
Securities Account: Possui conta de valores mobiliários? (0: Não, 1: Sim)
CD Account: Possui conta de depósito (CD)? (0: Não, 1: Sim)
Online: Usa internet banking? (0: Não, 1: Sim)
CreditCard: Possui cartão de crédito no banco? (0: Não, 1: Sim)
Personal_Loan (Alvo): O cliente aceitou o empréstimo pessoal oferecido? (0: Não, 1: Sim)
Etapas do Projeto
Carregamento dos Dados: O dataset é carregado a partir de um arquivo Excel.
Pré-processamento: Limpeza dos dados (remoção de valores nulos) e separação em variáveis independentes e dependentes.
Divisão em Treino e Teste: Os dados são divididos em conjunto de treino e teste usando uma proporção de 80-20.
Treinamento dos Modelos: O modelo inicial é uma Árvore de Decisão, e depois usamos Random Forest com ajuste de hiperparâmetros via Grid Search.
Avaliação: O modelo é avaliado usando métricas como acurácia, precisão, recall, F1-score e ROC-AUC.
Bibliotecas Utilizadas
Pandas: Para manipulação e análise dos dados.
NumPy: Para computação numérica.
Scikit-learn: Para modelos de machine learning e métricas.
Matplotlib & Seaborn: Para visualização de dados.
Modelos
Árvore de Decisão
Inicialmente, utilizamos o DecisionTreeClassifier da biblioteca Scikit-learn. Ao treinar o modelo, notamos que ele apresentava underfitting, com uma acurácia de 1.0 no conjunto de treino e 0.98 no conjunto de teste, indicando que o modelo estava muito simples.

Para melhorar o desempenho, foi realizada uma busca em grade (Grid Search) para otimizar a profundidade máxima da árvore (max_depth). O modelo ajustado apresentou um desempenho melhor, equilibrando a complexidade do modelo e sua capacidade de generalização.

Random Forest
Após a árvore de decisão, implementamos um modelo de Random Forest. Novamente, foi usada a busca em grade para otimizar os hiperparâmetros, como o número de estimadores (n_estimators) e a profundidade máxima (max_depth).

Desempenho dos Modelos
Árvore de Decisão (Após Tuning):

Acurácia no Treino: ~1.0
Acurácia no Teste: ~0.98
Observou-se underfitting no modelo inicial, que foi corrigido após o ajuste de hiperparâmetros.

Random Forest (Após Tuning):

Acurácia no Treino: ~0.99
Acurácia no Teste: ~0.98
Como Executar
Clone o repositório:
bash
Copiar código
git clone https://github.com/seu-usuario/seu-repositorio.git
Instale as bibliotecas necessárias:
bash
Copiar código
pip install -r requirements.txt
Execute o script:
bash
Copiar código
python loan_model.py
Melhorias Futuras
Tuning adicional de hiperparâmetros para melhorar a generalização.
Testar outros modelos, como Gradient Boosting ou XGBoost.
Implementar validação cruzada para uma avaliação mais robusta.
Contato
Para dúvidas ou sugestões, entre em contato com Gustavo André em [dev.gustavoandre@gmail.com].
