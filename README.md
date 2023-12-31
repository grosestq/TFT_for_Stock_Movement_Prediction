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
- [Hardware requirements](#Hardware-requirements)
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

1 - [Download data](1_Data_download.ipynb) of stock information using yfinance.

2 - [Data preparation](2_Data_preparation.ipynb) produces all input variables and a portfolio table.

2b - [Data analysis](2b_Data_analysis.ipynb) provides the portfolio performance plot and summary statistics.

3 - Each model has its own Notebook. Note that rerunning a model would override the results, and therefore, it should be saved in subfolders such as No.1, No.2, etc.

4 - [Results](4_Results.ipynb) offers plots and data related to forecasting accuracy, trading strategy, and prediction interpretability.

## Results

Reproducing can be skipped by using the original results saved in the [results](results/) folder and executing the [Results](4_Results.ipynb) code. Please note that the original training logs will not be provided due to their sheer size, and as a result, the model's prediction insights cannot be reproduced.

## Hardware requirements

For the experiment, the following hardware was used:

- CPU: i5-6600 CPU @ 3.30GHz
- RAM: 16,0 GB 2133 MHz
- GPU: GeForce GTX 960 4 GB GDDR5

Using a GPU is highly recommended for working with the transformer models. A CPU-only setup can increase the training time by a factor of 10 compared to the proposed hardware setup.

The following calculation times were needed:

- ARIMA:              ~ 5 hours - rolling one-step forecast and hyperparameter tuning - CPU only
- FNN:                ~ 10 minutes - no hyperparameter tuning - CPU only
- TFT - Global:       ~ 6 hours - without hyperparameter tuning - with GPU
- TFT - Individual:   ~ 12 hours - without hyperparameter tuning - with GPU

## Project structure

```bash
├── data                                            -- stores input data
├── results                                         -- stores output
├
├── 1_Data_download.ipynb                           -- data download
├── 2_Data_preparation.ipynb                        -- data preparation
├── 2b_Data_analysis.ipynb                          -- data analysis
├── 3_ARIMA_Individual benchmark.ipynb              -- ARIMA model
├── 3_FNN_Global_benchmark.ipynb                    -- FNN model
├── 3_TFT_Global_sector.ipynb                       -- Global TFT model with static input
├── 3_TFT_Global.ipynb                              -- Global TFT model
├── 3_TFT_Individual.ipynb                          -- Individual TFT model
├── 4_Results.ipynb                                 -- results
├
├── README.md                                       -- project overview
└── requirements.txt                                -- necessary packages
```
