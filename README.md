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
python main.py --data_path ./dataset/Custom/national_illness.csv --dataset Custom --target OT --model LinearRegression --transform BoxCox
```
**2. to predict ETT data**
```
python main.py --data_path ./dataset/Custom/national_illness.csv --dataset ETT --target OT --model LinearRegression --transform BoxCox
```

**3. to predict M4 data**
```
python main.py --data_path ./dataset/Custom/national_illness.csv --dataset M4 --target OT --model LinearRegression --transform BoxCox
```
## Datasets used for testing

