!pip install plotly
!pip install pandas

import pandas as pd
#importar base de dados
tabela = pd.read_csv("telecom_users.csv")
#Visualizar base de dados
#Tratar base de dados
tabela = tabela.drop("Unnamed: 0",axis=1)
display(tabela)

tabela["TotalGasto"] = pd.to_numeric(tabela["TotalGasto"], errors="coerce")

tabela = tabela.dropna(how="all", axis=1)
tabela = tabela.dropna(how="any", axis=0)
display(tabela.info())

print(tabela["Churn"].value_counts(normalize=True))

#Analise detalhada dos clientes
import plotly.express as px
#Gráficos:
for coluna in tabela.columns:
    grafico = px.histogram(tabela,x=coluna,color="Churn")
    grafico.show()