# 时间序列分析_HW1
## Install necessary dependencies
- python = 3.9
- numpy = 1.25.2
- argparse = 1.4.0
- matplotlib = 3.7.2
- sklearn = 1.3.0
- pandas = 2.0.3

## How to run the code
**1. to predict custom data**
```
python main.py --data_path ./dataset/Custom/national_illness.csv --dataset Custom --model LinearRegression --transform BoxCox
```
**2. to predict ETT data**
```
python main.py --data_path ./dataset/ETT-small/ETTh1.csv --dataset ETT --model LinearRegression --transform BoxCox
```

**3. to predict M4 data**
```
python main.py --data_path ./dataset/m4 --train_data_path /Daily-train.csv --test_data_path /Daily-test.csv --dataset M4 --model LinearRegression --transform BoxCox
```

you can change to different "model" and "transform", they have the choices below:
- model:
  - ZeroForecast
  - MeanForecast
  - LinearRegression
  - ExponentialSmoothing
  - 
- transform:
  - IdentityTransform
  - Normalization
  - Standardization
  - MeanNormalization
  - BoxCox

## Datasets used for testing
- Custom dataset
  - national_illness
  - exchange_rate
  - electricity
  - traffic
  - weather
- ETT-samll dataset
  -ETTh1
  -ETTh2
  -ETTm1
  -ETTm2

| Dataset  | Model | Transform | MSE  | MAE  | MAPE | SMAPE | MASE |
| -------- | ----- | --------- | ----- | ----- | ----- | ----- | ----- |
| national_illness  | LR    | None      |   4.187e+10   |  1.578e+05    |  1.420e+01    |   1.455e+01   |  6.666e-01    |
|          |       | Normalization |   8.044e+10   |  2.315e+05    |   2.245e+01   |   1.968e+01    |   1.134e+00   |
|          |       | Standardization   |   1.437e+11   |   3.138e+05   |   3.046e+01    |   2.506e+01    |   1.651e+00   |
|          |       | MeanNormalization   |  1.247e+11   |  3.028e+05   |   2.954e+01   |   2.475e+01   |   1.523e+00   |
|          |       | Box-Cox   |  4.264e+10    |   1.599e+05   |  1.440e+01   |   1.480e+01   |  6.789e-01   |
|          | ExponentialSmoothing   | None      |   7.101e+10   |  2.205e+05    |    1.949e+01  |    2.019e+01   |   1.051e+00   |
|          |       | Normalization |   8.877e+10   |  2.452e+05    |   2.429e+01   |   2.108e+01    |   1.099e+00   |
|          |       | Standardization     |   1.265e+11   |   2.877e+05   |   2.923e+01   |    2.394e+01   |  1.360e+00    |
|          |       | MeanNormalization    |   1.299e+11   |   2.939e+05   |   2.979e+01   |    2.437e+01   |   1.374e+00   |
|          |       | Box-Cox   |   7.273e+10   |  2.233e+05    |   1.967e+01   |   2.047e+01   |   1.068e+00   |      
|          | MeanForecast   | None      |   8.300e+10   |  2.486e+05    |    2.079e+01  |    2.307e+01   |   1.204e+00   |
|          |       | Normalization |  5.434e+10  |  1.992e+05    |   1.828e+01   |   1.760e+01    |   8.639e-01   |
|          |       | Standardization     |  6.427e+10   |   2.125e+05   |   2.102e+01  |   1.872e+01   |   9.496e-01   |
|          |       | MeanNormalization    |   6.427e+10   |   2.125e+05   |   2.102e+01   |   1.872e+01   |   9.496e-01   |
|          |       | Box-Cox   |   8.645e+10   |  2.549e+05    |   2.129e+01   |    2.374e+01   |   1.236e+00   |
| ETTh1  | LR    | None      |   3.451e+00   |   1.370e+00   |   3.603e+04   |   3.169e+01   |   1.105e+00   |
|          |       | Normalization |   1.339e+01  |   3.037e+00   |  1.234e+05    |  5.169e+01    |   2.853e+00   |
|          |       | Standardization   |  1.557e+01    |   3.272e+00   |   1.339e+05   |   5.406e+01   |   3.095e+00   |
|          |       | MeanNormalization   |  1.404e+01   |   3.122e+00   |  1.290e+05    |  5.254e+01    |   2.932e+00   |
|          |       | Box-Cox   |   3.679e+00  |  1.423e+00    |   3.047e+04   |   3.522e+01   |   1.154e+00   |
|          | ExponentialSmoothing   | None      |   4.136e+00   |   1.538e+00   |   4.114e+04   |  3.499e+01    |   1.277e+00   |
|          |       | Normalization |  1.377e+01   |   3.050e+00   |   1.226e+05   |  5.175e+01    |  2.866e+00    |
|          |       | Standardization   |   1.555e+01   |   3.260e+00   |   1.351e+05   |   5.370e+01   |   3.085e+00   |
|          |       | MeanNormalization   |  1.434e+01   |    3.137e+00  |    1.279e+05  |   5.267e+01   |   2.946e+00   |
|          |       | Box-Cox   |   4.291e+00  |   1.568e+00   |  3.612e+04    |   3.821e+01   |  1.303e+00    |  
|          | MeanForecast   | None      |      |      |      |      |      |
|          |       | Normalization |     |      |      |      |      |
|          |       | Standardization   |      |      |      |      |      |
|          |       | MeanNormalization   |     |      |      |      |      |
|          |       | Box-Cox   |     |      |      |      |      |
















