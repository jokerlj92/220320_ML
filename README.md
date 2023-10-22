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
python main.py --data_path ./dataset/Custom/national_illness.csv --dataset ETT --model LinearRegression --transform BoxCox
```

**3. to predict M4 data**
```
python main.py --data_path ./dataset/Custom/national_illness.csv --dataset M4 --model LinearRegression --transform BoxCox
```

you can change to different "model" and "transform", they have the choices below:
model:
- ZeroForecast
- MeanForecast
- LinearRegression
- ExponentialSmoothing
- 
transform:
- IdentityTransform
- Normalization
- Standardization
- MeanNormalization
- BoxCox
- 
## Datasets used for testing

