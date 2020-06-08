# Spectral Temporal Graph Neural Network for Multivariate Time-series Forecasting

This repository is the official implementation of Spectral Temporal Graph Neural Network for
Multivariate Time-series Forecasting.

<!-- > 📋Optional: include a graphic explaining your approach/main result, bibtex entry, link to demos, blog posts and tutorials -->

## Requirements

To install requirements:

```setup
pip install -r requirements.txt
```

<!-- > 📋Describe how to set up the environment, e.g. pip/conda/docker commands, download datasets, etc... -->

## Training and Evaluation

The training procedure and evaluation procedure are all included in the `main.py`. To train and evaluate on some dataset, run the following command:

```train & evaluate
python main.py --dataset <path_to_data>
```

<!-- The hyperparameters are set as default pramaters for reproduction convenience, so no more parameters need to be specified in the above command. -->

## Datasets

[METR-LA](http://pems.dot.ca.gov/?dnode=Clearinghouse&type=station_5min&district_id=3&submit=Submit),
[PEMS-BAY](http://pems.dot.ca.gov/?dnode=Clearinghouse&type=station_5min&district_id=3&submit=Submit),
[PEMS03](http://pems.dot.ca.gov/?dnode=Clearinghouse&type=station_5min&district_id=3&submit=Submit),
[PEMS04](http://pems.dot.ca.gov/?dnode=Clearinghouse&type=station_5min&district_id=3&submit=Submit),
[PEMS07](http://pems.dot.ca.gov/?dnode=Clearinghouse&type=station_5min&district_id=3&submit=Submit),
[PEMS08](http://pems.dot.ca.gov/?dnode=Clearinghouse&type=station_5min&district_id=3&submit=Submit),
[Solar](https://www.nrel.gov/grid/solar-power-data.html),
[Electricity](https://archive.ics.uci.edu/ml/datasets/ElectricityLoadDiagrams20112014),
[ECG](http://www.timeseriesclassification.com/description.php?Dataset=ECG5000)

Since complex reorganizations need to be conducted on the above datasets provided in the urls before fed into StemGNN model, we provide a organized version of PEMS07 ([./dataset/PeMS07.csv](./dataset/PeMS07.csv)) for reproduction convenience. The PeMS07.csv is in shape of `T*N`, where `T` denotes total number of timestamps, `N` denotes number of nodes.

## Results

Our model achieves the following performance on the 9 datasets included in the code repo:

**Table 1** (predict horizon: 3 steps)
| Dataset | MAE  | RMSE | MAPE(%) |
| -----   | ---- | ---- | ---- |
| METR-LA | 2.56 | 5.06 | 6.46 |
| PEMS-BAY | 1.23 | 2.48 | 2.63 |
| PEMS07 | 2.14 | 4.01 | 5.01 |
| Solar | 1.52 | 1.53 | 1.42 |
| Electricity | 0.04 | 0.06 | 14.77 |
| ECG | 0.05 | 0.07 | 10.58 |

**Table 2** (predict horizon: 12 steps)
| Dataset | MAE  | RMSE | MAPE |
| -----   | ---- | ---- | ---- |
| PEMS03 | 14.32 | 21.64 | 16.24 |
| PEMS04 | 20.24 | 32.15 | 10.03 |
| PEMS08 | 15.83 | 24.93 | 9.26 |

<!-- > 📋Include a table of results from your paper, and link back to the leaderboard for clarity and context. If your main result is a figure, include that figure and link to the command or notebook to reproduce it.  -->