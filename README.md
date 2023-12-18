<p><img width=100%  src= "https://i.ibb.co/GskFKfv/Capa-Prevendo-atrasos.png" alt="logo"></p>


<p align="center">
    <!-- Python -->
    <img alt="python" src="https://img.shields.io/badge/python-FFFFFF?style=flat&labelColor=154C79&color=FFFFFF&logo=python&logoColor=FFFFFF">
    <!-- Pandas -->
    <img alt="pandas" src="https://img.shields.io/badge/pandas-FFFFFF?style=flat&labelColor=154C79&color=FFFFFF&logo=pandas&logoColor=FFFFFF">
    <!-- Numpy -->
    <img alt="numpy" src="https://img.shields.io/badge/numpy-FFFFFF?style=flat&labelColor=154C79&color=FFFFFF&logo=numpy&logoColor=FFFFFF">
    <!-- Seaborn -->
    <img alt="seaborn" src="https://img.shields.io/badge/seaborn-FFFFFF?style=flat&labelColor=154C79&color=FFFFFF&logo=seaborn&logoColor=FFFFFF">
    <!-- Matplotlib -->
    <img alt="matplotlib" src="https://img.shields.io/badge/matplotlib-FFFFFF?style=flat&labelColor=154C79&color=FFFFFF&logo=matplotlib&logoColor=FFFFFF">
    <!-- Scikit-learn -->
    <img alt="scikit-learn" src="https://img.shields.io/badge/sklearn-FFFFFF?style=flat&labelColor=154C79&color=FFFFFF&logo=scikitlearn&logoColor=FFFFFF">
    <!-- Yellowbrick -->
    <img alt="Yellowbrick" src="https://img.shields.io/badge/yellowbrick-FFFFFF?style=flat&labelColor=154C79&color=FFFFFF&logo=yellowbrick&logoColor=FFFFFF">
    <!-- Status -->
    <img alt="status" src="https://img.shields.io/badge/Status-Concluído-FFFFFF?style=flat&logoColor=1ED760&labelColor=000000">
</p>

# Projeto: Prevendo atrasos de voos
Este projeto visa desenvolver um modelo preditivo para antecipar a ocorrência de atrasos nos voos, permitindo uma gestão ágil e eficiente do planejamento de estacionamento de aeronaves. 

# Índice 

* [Descrição do Projeto](#descrição-do-projeto)
* [Funcionalidades e Demonstração da Aplicação](#funcionalidades-e-demonstração-da-aplicação)
* [Tecnologias utilizadas](#tecnologias-utilizadas)
* [Conclusão](#conclusão)
* [Licença](#licença)

# Descrição do projeto
Este repositório visa a otimização aeroportuária através de um modelo preditivo para a previsão de atrasos em voos. Foi feito construção de um modelo de regressão para antecipar atrasos, permitindo ajustes ágeis nos planos de estacionamento. O objetivo é reduzir o tempo de espera dos passageiros e aprimorar as operações do aeroporto. Este projeto foi criado para  fins de aprendizado e aplicação dos conhecimentos adquiridos referente o modelo de regressão.

# Funcionalidades e Demonstração da Aplicação
- O modelo prevê atrasos de voos a partir de dados de entradas, retornando o tempo de atraso em minutos.

Para acessar e executar o projeto, seguir os seguintes passos:
1. Faça download do arquivo [modelo_producao.pkl](https://github.com/CrisNakamura/previsao_atraso_voo/blob/main/modelo_producao.pkl)
2. Importe biblioteca pickle para carregar o modelo salvo da seguinte forma ou faça download do arquivo [testando_modelo.ipynb](https://github.com/CrisNakamura/previsao_atraso_voo/blob/main/testando_modelo.ipynb):
```python
import pickle
from warnings import simplefilter
simplefilter(action='ignore', category=UserWarning)

file_path = 'modelo_producao.pkl'

try:
    with open(file_path, 'rb') as file:
        model = pickle.load(file)
    print("Modelo carregado com sucesso!")
except Exception as e:
    print("Ocorreu um erro ao carregar o modelo:", str(e))
```
3. Insira novos dados para o modelo retornar a previsão de atraso. No exemplo abaixo, estamos inserindo os seguintes dados:
```
schengen: 0
arrival_time: 10.8941
is_holiday: 0
is_weekend: 0
airline_BZ: 0
airline_MM: 0
airline_YE: 1
aircraft_type_Airbus A320: 1
aircraft_type_Airbus A330: 0
aircraft_type_Boeing 737: 0
aircraft_type_Boeing 777: 0
aircraft_type_Boeing 787: 0
aircraft_type_Embraer E175: 0
```
```python
nova_amostra = [0.0, 10.8941, 0.0, 0.0, 0.0, 0.0, 1.0, 1.0, 0.0, 0.0, 0.0, 0.0, 0.0]

# Exemplo de previsão com dados de entrada 'X'
print(f'Previsão de atraso: {round(model.predict([nova_amostra])[0], 2)} minutos')
```

# Tecnologias utilizadas
- **Linguagem:** Python 3.11.5
- **Bibliotecas:** 
    - Pandas: 2.1.1
    - Matplotlib: 3.8.0
    - Seaborn: 0.12.2
    - NumPy: 1.24.3
    - Scikit-learn: 1.3.0
    - Yellowbrick: 1.5

# Conclusão
Neste projeto foi possível adquirir uma boa base para realizar:
- Análise exploratória dos dados;
- Preparação dos dados via Feature engineering;
- Implementação e otimização do algoritmo RandomForestRegressor;
- Seleção das features mais importantes;

# Licença
[MIT License](https://opensource.org/license/mit/)