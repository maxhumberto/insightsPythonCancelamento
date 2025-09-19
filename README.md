# 📊 Projeto de Análise de Cancelamentos

Este projeto tem como objetivo analisar uma base de dados de cancelamentos de clientes e identificar os principais fatores que impactam nas desistências.  

---

## 🚀 Passo a passo do projeto

### **Passo 1: Importar a base de dados**
```python
import pandas as pd

tabela = pd.read_csv("cancelamentos_sample.csv")
# Excluir coluna CustomerID, pois não agrega valor
tabela = tabela.drop(columns="CustomerID")
display(tabela)
Passo 2: Visualizar a base de dados

Visualização inicial da tabela.

Exclusão de colunas inúteis que não ajudam na análise.
Passo 3: Tratar inconsistências da base
# Verificação de valores nulos
display(tabela.info())

# Exclusão de linhas com valores vazios
tabela = tabela.dropna()
display(tabela.info())
Passo 4: Análise inicial dos cancelamentos
# Quantidade de clientes que cancelaram ou não
display(tabela["cancelou"].value_counts())

# Percentual de cancelamentos
display(tabela["cancelou"].value_counts(normalize=True))
Passo 5: Análise das causas do cancelamento
import plotly.express as px
import plotly.io as pio

# Configuração para exibição no notebook
pio.renderers.default = "notebook_connected"

# Gráficos de cada coluna em relação ao cancelamento
for coluna in tabela.columns:
    grafico = px.histogram(tabela, x=coluna, color="cancelou")
    grafico.show()
Tecnologias utilizadas

Python

Pandas → manipulação de dados

Plotly → visualização interativa

Jupyter Notebook (ou execução em browser)

📈 Resultados esperados

Identificação dos fatores que levam ao cancelamento.

Criação de insights acionáveis para reduzir a taxa de churn.

Base para futuros modelos de Machine Learning preditivo.
