# PythonDados
Repositório para aprendizado de bibliotecas em Python para Ciência de Dados.

# Início
Comecei o desenvolvimento utilizando a biblioteca Pandas para aprendizado.
<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/ed/Pandas_logo.svg/1920px-Pandas_logo.svg.png" width="50%" height="25%">

## Pandas
Pandas é uma biblioteca de código aberto para a linguagem de programação Python, amplamente utilizada em ciência e análise de dados. A principal função do Pandas é facilitar a manipulação e análise de grandes conjuntos de dados de forma eficiente e intuitiva. Pandas fornece duas estruturas de dados principais: Series e DataFrame.

- ***Series*** é uma estrutura de dados unidimensional que pode armazenar dados de qualquer tipo (inteiros, floats, strings, etc.).
- ***DataFrame*** é uma estrutura de dados bidimensional, semelhante a uma planilha do Excel ou uma tabela em um banco de dados.

Segue um exemplo de código que fiz utilizando a biblioteca Pandas:
```py
#Importação da biblioteca de definição do apelido
import pandas as pd

#Leitura da base de dados
df = pd.read_csv('uf.csv')
display(df)

# Concatenando colunas e valores na consulta
concatColunas = display(df.loc[df['sigla_uf'] == 'SP'][df['ano'] == 2015]), 
(df.loc[df['sigla_uf'] == 'SP'][df['ano'] == 2009])
```
<img src="https://github.com/theusouza0/PythonDados/assets/75237625/acf20783-0c5d-4ff4-a3d4-cc5279ceacb5" width="40%" height="25%">

# Matplotlib e Pyplot

*Matplotlib* é uma biblioteca de visualização de dados para a linguagem de programação Python. É amplamente utilizado para criar gráficos estáticos, animados e interativos. A biblioteca é extremamente versátil e pode ser usada para gerar uma ampla variedade de gráficos, desde gráficos de linha simples até gráficos de superfície 3D complexos.
*Pyplot* é um módulo do Matplotlib que fornece uma interface de estilo MATLAB para criar figuras e gráficos. 

Agora um exemplo de utilização da bibloteca:
```py
#Importação da biblioteca de definição do apelido
import matplotlib.pyplot as plt

#Leitura da base de dados e tratamento de colunas e linhas
dfTeste = pd.read_csv('uf.csv')
dfTeste = dfTeste.drop(columns=['numero_consumidores'])
dfTeste = dfTeste.drop(dfTeste[dfTeste.tipo_consumo != "Total"].index)
dfTeste = dfTeste.drop(dfTeste[dfTeste.sigla_uf != 'SP'].index)
dfTeste = dfTeste.drop(dfTeste[dfTeste.mes != 1].index)

#Convertendo o consumo de Megawatt hora para Terawatt hora
if dfTeste['consumo'].min() >= (10**5):
    dfTeste["consumo"] = dfTeste['consumo']/(10**6)

plt.subplots(figsize=(17,9)) #Tamanho do gráfico
plt.bar(dfTeste['ano'],dfTeste['consumo'], color='y', width=0.6) #Gerando gráfico
plt.title('Consumo de energia elétrica no mês de Janeiro em São Paulo de 2004 até 2021') #Título do gráfico
plt.xlabel('Anos'), plt.ylabel('Valor em TWh') #Legenda para o eixo X e Y
plt.xticks(dfTeste['ano']) #Valores para cada barra no eixo X
plt.show()
```
<img src="https://github.com/theusouza0/PythonDados/assets/75237625/8c70b5ae-8fca-4d75-b075-6431191dce76" width="80%" height="50%">
