# EEG Eye State Dataset

This project uses the **EEG Eye State** dataset available from the UCI Machine Learning Repository.

The dataset contains EEG recordings collected over time, where each row corresponds to a single time point measurement across multiple EEG channels.

The final column represents eye state:

- 0 → Eyes open  
- 1 → Eyes closed  

The data is time-ordered and should be treated as a time-series dataset.


## Structure

- 14 EEG signal channels (continuous numerical values)
- 1 binary target column (eye state)


## Important Notes

- The dataset is stored in `.arff` format.
- When loaded into Python, the target column presented data as objects, which was converted to integer format (`0` and `1`) for compatibility with scikit-learn.
- No personal or identifying information is included in the dataset.

Because the dataset is time-ordered, random train–test splits may cause **temporal leakage**. Proper time-aware validation methods should be used.


## How to Download

Visit the UCI Machine Learning Repository and search for **EEG Eye State**.
OR Use the link: https://archive.ics.uci.edu/dataset/264/eeg+eye+state


## Citation

Roesler, O. (2013). EEG Eye State [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C57G7J.
