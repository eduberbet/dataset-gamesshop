# Dataset GamesShop

✴️ Base de dados de uma fabricante de consoles para análises de dados.

## Descrição

Este repositório contém dados de vendas de consoles de uma grande fabricante. O objetivo é fornecer uma base de dados para análises de dados e previsões de tendências de vendas futuras.

## Estrutura do Projeto

- `data/`: Diretório contendo os arquivos de dados.
  - `vendas-console.csv`: Arquivo CSV contendo os dados de vendas dos consoles.
- `scripts/`: Diretório contendo scripts para análise de dados.

## Como Usar

1. Clone o repositório:
    ```bash
    git clone https://github.com/eduberbet/dataset-gamesshop.git
    ```

2. Navegue até o diretório do projeto:
    ```bash
    cd dataset-gamesshop
    ```

3. Explore os dados no diretório `data/`.

## Análise de Dados

Para realizar análises de dados e previsão de tendências de vendas futuras, siga os passos abaixo:

1. **Pré-processamento dos Dados**:
    - Carregue os dados do arquivo `vendas-console.csv`.
    - Limpe e organize os dados conforme necessário (remoção de valores nulos, formatação de colunas, etc).

2. **Análise Exploratória dos Dados (EDA)**:
    - Visualize as vendas ao longo do tempo.
    - Identifique padrões sazonais e tendências gerais.
    - Utilize gráficos como linhas do tempo, histogramas e boxplots.

3. **Modelagem e Previsão**:
    - Divida os dados em conjuntos de treinamento e teste.
    - Utilize modelos de séries temporais (ARIMA, SARIMA) ou modelos de aprendizado de máquina (Regressão Linear, Redes Neurais) para prever as vendas futuras.
    - Avalie a performance do modelo utilizando métricas apropriadas (RMSE, MAE, etc).

## Exemplo de Script para Análise

```python
import pandas as pd
import matplotlib.pyplot as plt
from statsmodels.tsa.arima_model import ARIMA

# Carregar dados
data = pd.read_csv('data/vendas-console.csv')

# Pré-processamento
data['Date'] = pd.to_datetime(data['Date'])
data.set_index('Date', inplace=True)

# Análise Exploratória
plt.figure(figsize=(10,6))
plt.plot(data['Sales'])
plt.title('Vendas de Consoles ao Longo do Tempo')
plt.xlabel('Data')
plt.ylabel('Vendas')
plt.show()

# Modelagem e Previsão
model = ARIMA(data['Sales'], order=(5,1,0))
model_fit = model.fit(disp=0)
forecast = model_fit.forecast(steps=12)

# Visualização da Previsão
plt.figure(figsize=(10,6))
plt.plot(data['Sales'], label='Vendas Históricas')
plt.plot(forecast[0], label='Previsão de Vendas')
plt.title('Previsão de Vendas Futuras')
plt.xlabel('Data')
plt.ylabel('Vendas')
plt.legend()
plt.show()
```

## Contribuições

Contribuições são bem-vindas! Por favor, siga os passos abaixo para contribuir:

1. Fork este repositório.
2. Crie uma nova branch:
    ```bash
    git checkout -b feature/nome-da-sua-feature
    ```
3. Faça suas alterações e commit:
    ```bash
    git commit -m 'Adiciona nova funcionalidade'
    ```
4. Envie para o repositório remoto:
    ```bash
    git push origin feature/nome-da-sua-feature
    ```
5. Abra um Pull Request.

## Licença

Este projeto não possui uma licença específica.

## Contato

Para mais informações, entre em contato com [eduberbet](https://github.com/eduberbet).
