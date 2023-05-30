# high-frequency-price-prediction
Aplicação de modelos LSTM em conjunto com técnicas de filtragem (Método Percentil e Filtro de Hampel) e indicadores (Bandas de Bollinger e Order Flow Imbalance) para previsão de preços de ação em alta frequência.

Amostras de dados de alta frequência:
https://lobsterdata.com/info/DataSamples.php
(Códigos utilizam uma amostra da MSFT Level: 50)

Nome dos modelos:
-> PRICE_ONLY : Apenas preço
-> BB : Bandas de Bollinger e preço
-> OFI : Order Flow Imbalance e preço

Descrição dos arquivos em ordem:
1- PREPROCESSING.ipynb: 
          ->Data Profiling: Examinação e identificação dos dados
          ->Data Cleansing: Remoção de tipos de ordens indesejadas (Order Type: )
          ->Data Reduction: Método Percentil (Remoção de outliers extremos) e Filtro de Hampel (Minimização de ruído)
          ->Data Transformation & Enrichment: Criação de 2 parâmetros (BB e OFI)
2- KT_ + Nome do Modelo:
          ->Busca automática pelos melhores hiperparâmetros:
            ->Unidades LSTM
            ->Unidades Dense
            ->Taxa de Aprendizado          
3- LSTM_+ Nome do Modelo: 
          ->Treinamento do modelo com split train/test = 80/20
          ->Padronização dos dados (StandardScaler)
          ->Aplicação de hiperparâmetros encontrados no Keras-Tuner
