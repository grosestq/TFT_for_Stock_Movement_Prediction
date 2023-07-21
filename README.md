# Temporal Fusion Transformer for Stock Movement Prediction

**Type:** Master's Thesis

**Author:** Stefan Grosse

**1st Examiner:** Prof. Dr. Stefan Lessmann

**2nd Examiner:** Prof. Dr. Benjamin Fabian

![results](/results/Results1.png)

![results2](/results/Results2.png)

## Table of Content

- [Summary](#Summary)
- [Working with the repo](#Working-with-the-repo)
- [Reproducing results](#Reproducing-results)
- [Results](#Results)
- [Project structure](#Project-structure)

## Summary

Deep learning architectures are continuously evolving, expanding their application areas and improving performance. The Temporal Fusion Transformer (TFT), a novel deep neural network, combines multiple deep learning approaches to offer capabilities such as inherently interpretable model predictions and self-adaptive architectural complexity. In this study, we apply this new algorithm to predict stock movements by comparing individual and global modeling techniques. Additionally, we evaluate the performance of forecasting errors against simpler benchmark models and integrate a trading strategy for further assessment. In our proposed experimental setup, the TFT models achieve a predictive performance comparable to that of the comparative methods. However, both modeling approaches reveal distinct patterns when analyzing trading returns, which at best correspond to the performance of a buy-and-hold strategy.

**Keywords**: Deep learning · Attention mechanisms · Financial time series forecasting · Stock movement prediction · Trading strategy

**Full text**: 

## Working with the repo

The Python code is provided in Jupyter Notebooks.

The experiment was conducted using Python version 3.10.10 and the packages listed in the [requirements](requirements.txt) file.

For the TFT models, the code is written to utilize a CUDA-supported GPU.

The code can be easily modified to run in different environments, such as Google Colab or CPU-only setups, if required.

## Reproducing results

All results can be reproduced by following the steps from data download to producing results:

1 - [Download data](Data_download.ipynb) of stock information using yfinance.

2 - [Data preparation](Data_preparation.ipynb) produces all input variables and a portfolio table.

2b - [Data analysis](2b_Data_analysis.ipynb) provides a portfolio performance plot and summary statistics.

3 - Each model has its own Notebook. Note that rerunning a model would override the results, and therefore, it should be saved in subfolders such as No.1, No.2, etc.

4 - [Results](Results.ipynb) offers plots and data related to forecasting accuracy, trading strategy, and prediction interpretability.

## Results

Reproducing can be skipped by using the original results saved in the [results](results/) folder and executing the [Results](Results.ipynb) code. Please note that the original training logs will not be provided due to their sheer size, and as a result, the model's prediction insights cannot be reproduced.

## Project structure

```bash
├── data                                            -- stores input data
├── results                                         -- stores output
├
├── 1. Data download.ipynb                          -- data download
├── 2. Data preparation.ipynb                       -- data preparation
├── 2b. Data analysis.ipynb                         -- data analysis
├── 3. ARIMA - Individual benchmark.ipynb           -- ARIMA model
├── 3. FNN - Global benchmark.ipynb                 -- FNN model
├── 3. TFT - Global sector.ipynb                    -- Global TFT model with static input
├── 3. TFT - Global.ipynb                           -- Global TFT model
├── 3. TFT - Individual.ipynb                       -- Individual TFT model
├── 4. Results.ipynb                                -- results
├
├── README.md                                       -- project overview
└── requirements.txt                                -- necessary packages
```
