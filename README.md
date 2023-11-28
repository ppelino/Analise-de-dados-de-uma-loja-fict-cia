# Analise_de_dados_loja_fictícia

Vamos criar um projeto de análise de vendas usando Pandas, uma biblioteca poderosa para manipulação e análise de dados, e Matplotlib para visualizações. Este projeto pode ajudar a demonstrar suas habilidades em análise de dados e programação Python.

Passo a Passo:
1. Preparação do Ambiente:
Certifique-se de ter Python instalado. Recomendo utilizar ambientes virtuais para o projeto.
Instale as bibliotecas necessárias:

pip install pandas matplotlib

2. Obtenção dos Dados:
Use um conjunto de dados de vendas fictício ou real (por exemplo, CSV ou Excel) e coloque-o na pasta do projeto.
3. Criando o Código:
a. Importe as bibliotecas:

import pandas as pd
import matplotlib.pyplot as plt

b. Carregue os dados:

# Suponha que o arquivo CSV seja 'dados_vendas.csv'
df = pd.read_excel('vendas.xlsx')

c. Explore os dados:

Verifique as primeiras linhas do DataFrame:

print(df.head())

Informações sobre as colunas e tipos de dados:

print(df.info())

d. Análise dos dados:

Exemplo: Total de vendas por mês

df['Data'] = pd.to_datetime(df['Data'])  # Converter para tipo data se necessário
df['Mês'] = df['Data'].dt.month  # Criar coluna 'Mês'

vendas_por_mes = df.groupby('Mês')['Valor'].sum()
print(vendas_por_mes)

e. Visualização dos dados:

Gráfico de barras para as vendas por mês:

vendas_por_mes.plot(kind='bar')
plt.title('Vendas por Mês')
plt.xlabel('Mês')
plt.ylabel('Total de Vendas')
plt.show()

# Supondo que você tenha um DataFrame chamado df com os dados de vendas

# Agrupar por produto e calcular a quantidade total vendida de cada um
produtos_mais_vendidos = df.groupby('Produto')['Quantidade'].sum().sort_values(ascending=False)

# Mostrar os produtos mais vendidos
print("Produtos mais vendidos:")
print(produtos_mais_vendidos.head(10))  # Mostra os 10 produtos mais vendidos, por exemplo

# Supondo que você tenha um DataFrame chamado df com os dados de vendas

# Agrupar por ID Loja e calcular o total vendido por loja
vendas_por_loja = df.groupby('ID Loja')['Valor Final'].sum().sort_values(ascending=False)

# Mostrar as lojas que mais vendem
print("Lojas que mais vendem:")
print(vendas_por_loja.head(10))  # Mostra as 10 lojas que mais vendem, por exemplo




