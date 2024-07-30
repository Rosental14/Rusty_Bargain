# Rusty Bargain: Predicting Used Car Prices

## Descrição do Projeto

Rusty Bargain é um serviço de venda de carros usados que está desenvolvendo um aplicativo para atrair novos clientes. Esse aplicativo permite que os usuários descubram rapidamente o valor de mercado de seus carros usados. O aplicativo fornece acesso a dados históricos, especificações técnicas, versões, entre outras características.

O objetivo deste projeto é construir modelos (Regressão Linear, Floresta Aleatória, CatBoost e LGBM) para determinar o valor dos carros usados e compará-los em relação a:

- Qualidade da predição
- Velocidade da predição
- Tempo necessário para o treinamento

## Instruções do Projeto

### Passos Realizados:

1. **Preparação dos Dados:**
   - Download e visualização dos dados.
   - Limpeza e pré-processamento dos dados, incluindo seleção de características, tratamento de valores ausentes, codificação de características categóricas e transformação de características numéricas e ordinais.  
  <br>

2. **Treinamento de Modelos:**
   - Treinamento de diferentes modelos com vários hiperparâmetros.
   - Comparação de métodos de gradient boosting com floresta aleatória e regressão linear.
<br>

3. **Análise dos Modelos:**
   - Avaliação da velocidade e qualidade dos modelos.
   - Uso da métrica RMSE (Root Mean Squared Error) para avaliar a performance dos modelos.

### Modelos Utilizados:

- Regressão Linear: Usada como referência para avaliar outros métodos.
- Floresta Aleatória
- LightGBM
- CatBoost

### Avaliação dos Modelos:

- **Qualidade da Predição:** Medida pelo RMSE.
- **Velocidade da Predição:** Avaliada pelo tempo necessário para fazer predições.
- **Tempo de Treinamento:** Avaliado pelo tempo necessário para treinar os modelos.

### Ferramentas e Bibliotecas:

- Python
- Pandas
- Scikit-learn
- LightGBM
- CatBoost
- Jupyter Notebook

## Descrição dos Dados

O conjunto de dados utilizado está armazenado no arquivo `car_data.csv` e inclui as seguintes características:

- `DateCrawled` — Data em que o perfil foi baixado do banco de dados
- `VehicleType` — Tipo de carroçaria do veículo
- `RegistrationYear` — Ano de matrícula do veículo
- `Gearbox` — Tipo de caixa de transmissão
- `Power` — Potência (hp)
- `Model` — Modelo do veículo
- `Mileage` — Quilometragem (km)
- `RegistrationMonth` — Mês de registro do veículo
- `FuelType` — Tipo de combustível
- `Brand` — Marca do veículo
- `NotRepaired` — Veículo reparado ou não
- `DateCreated` — Data de criação do perfil
- `NumberOfPictures` — Número de fotos do veículo
- `PostalCode` — Código postal do proprietário do perfil (usuário)
- `LastSeen` — Data da última atividade do usuário  
<br>
- **Objetivo:** `Price` — Preço (Euro)

## Conclusões

**Em relação ao REQM**, os melhores resultados obtidos foram os dos modelos CatBoost e LGBM. Porém, o resultado obtido pelo modelo de Floresta Aleatória também foi aceitável. O pior resultado foi o do modelo de Regressão Linear, apresentando um erro muito maior do que o dos outros modelos treinados.

**Em relação ao tempo de treinamento** dos modelos observamos que o melhor desempenho, com larga vantagem, é o do modelo de Regressão Linear, que demorou apenas 12 segundos. O segundo melhor desempenho foi do modelo de Floresta Aleatória, mas já consumindo um tempo de 370 segundos (30 vezes maior do que o tempo gasto pela Regressão Linear). Em seguida, tivemos o modelo CatBoost, que consumiu um tempo de 550 segundos (45 vezes mais do que o modelo de Regressão) e, por último, o modelo de LGBM, que levou 1220 segundos para o treinamento do modelo (mais do que o dobro do tempo gasto pelo CatBoost e mais de 100 vezes o tempo gasto pela Regressão Linear).

**Em relação ao tempo para predição** com os dados de teste, todos os modelos apresentaram resultados satisfatórios, pois todos estiveram abaixo de 1 segundo. Porém, se compararmos uns com os outros, podemos observar que o modelo CatBoost apresentou um desempenho melhor, sendo de 0.08 segundo, seguido por Regressão Linear (0.1 s), Floresta Aleatória (0.15 s) e LGBM, que apresentou de longe o pior desempenho (0.61 s). Portanto, para este conjunto de dados, o desempenho de todos foi aceitável. Porém, se considerarmos um conjunto de dados muito maior, com milhões ou bilhões de linhas, o desempenho pode ser mais impactado. Portanto, o modelo CatBoost apresentaria um resultado melhor nesses casos.

## Como Executar

1. **Clone o repositório:** git clone https://github.com/Rosental14/Rusty_Bargain.git

2. **Navegue até o diretório do projeto:** cd Rusty_Bargain

3. **Instale as dependências:** pip install -r requirements.txt

4. **Execute o Jupyter Notebook** para visualizar o código e os resultados: rusty_bargain_carros.ipynb