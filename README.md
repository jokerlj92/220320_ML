# 时间序列分析_HW1
## Install necessary dependencies
- python = 3.9
- numpy
- argparse
- matplotlib
- sklearn
- pandas

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

| Dataset  | Model | Transform | MSE  | MAE  | MAPE | SMAPE | MASE |
| -------- | ----- | --------- | ----- | ----- | ----- | ----- | ----- |
| national_illness  | LR    | None      |    41873290900.54705  |  157843.04140472738    |  14.200357488256222    |    14.548925243195988   |  0.6666227076832995    |
|          |       | Normalization |   80442016844.21046   |  231471.33907994715    |   22.445034850135823   |   19.678602755137977    |   1.1335854469331883   |
|          |       | Standardization       |   143727161926.8681   |   313829.04224244953   |  30.460664307055165    |   25.06320481346373    |   1.6514045954144452   |
|          |       | MeanNormalization       |  124655037792.7749    |  302760.356631112    |   29.541107595428787   |    24.752765513332992   |   1.52317329972204   |
|          |       | Box-Cox   |  42638375744.62222    |   159929.04183991143   |  14.398231461498552    |    14.797632468908793   |  0.6788536693224265    |
|          | ES   | None      |      |      |      |       |      |
|          |       | Normalization |      |      |      |       |      |
|          |       | Standardization       |      |      |      |       |      |
|          |       | MeanNormalization       |      |      |      |       |      |
|          |       | Box-Cox   |      |      |      |       |      
















