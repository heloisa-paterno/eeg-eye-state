# Predicting Eye State from EEG Signals

This project explores machine learning methods to predict eye state from EEG signals using the EEG Eye State dataset. It compares random train-test splits with time-aware validation to highlight issues of temporal leakage in EEG data.


## Project Goals

* Practice a full data science workflow on biological data
* Compare model performance with **random splits vs time-aware validation**
* Understand data leakage in time-series neuroscience data


## Dataset

EEG Eye State dataset from the UCI Machine Learning Repository.

* Labels: 0 = eyes open, 1 = eyes closed
* Each row corresponds to EEG recording at one time point


### How to download

1. Download dataset from UCI
2. Place `.arff` file inside `data/`
3. Run the notebook


## Methods

1. Load EEG data from ARFF
2. Inspect class balance and features
3. Build baseline Linear Model
4. Build Random Forest model
5. Evaluate with random train–test split
6. Evaluate with TimeSeries cross-validation
7. Compare results and interpret differences

Tools used:

* Python
* pandas
* scikit-learn
* Google Colab


## Results

| Method                      | Accuracy |
| --------------------------- | -------- |
| Random train–test split     | ~90%     |
| Time-aware cross-validation | ~53%     |


Random splitting gave very high accuracy because neighbouring EEG samples are very similar. The model saw almost identical patterns in training and testing, leading to overly optimistic performance.

When using time-based validation, accuracy dropped close to chance level. This shows the model does not generalise well across time and that EEG signals are noisy and difficult to model.


## Lessons Learned

* EEG data are temporally correlated
* Random splits can cause data leakage
* Cross-validation choice is critical in neuroscience ML
* High accuracy does not always mean a good model


## Possible Improvements

* Extract frequency-band EEG features
* Use windowed statistics such as rolling mean and rolling standard deviation
* Apply smoothing methods to reduce EEG noise
* Evaluate models on subject-independent datasets to obtain more reliable estimates of performance
* Try SVM or gradient boosting models
* Explore deep learning for EEG sequences


## Repository Structure

```
eeg-eye-state/
│
├── README.md
├── eye_state_from_eeg.ipynb
├── requirements.txt
├── data/README_data.md
└── figures/
```



## Requirements

```
pip install pandas numpy scikit-learn scipy matplotlib
```



## How to Run

1. Download dataset into `data/`
2. Open notebook in Google Colab or Jupyter
3. Run all cells



## Conclusion

This project shows that correct validation is essential in neuroscience machine learning. Even simple models can appear very accurate if the data is split incorrectly. Time-aware evaluation provides a more realistic estimate of performance when working with EEG signals.
