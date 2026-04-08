# Getting and Cleaning Data Course Project

## Overview
This project demonstrates how to clean and prepare a dataset for analysis using the Human Activity Recognition Using Smartphones dataset.

The goal is to create a tidy dataset that contains the average of each variable for each activity and each subject.

---

## Dataset
The dataset was obtained from:
https://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

It contains data collected from accelerometers and gyroscopes of Samsung Galaxy S smartphones.

---

## Files Included

- run_analysis.R  
  Script that performs all data cleaning and transformation steps

- tidy_data.txt  
  Final tidy dataset with the average of each variable for each activity and subject

- CodeBook.md  
  Description of variables and transformations

---

## How the Script Works

The script performs the following steps:

1. Merges the training and test datasets
2. Extracts only the measurements on the mean and standard deviation
3. Uses descriptive activity names
4. Labels the dataset with descriptive variable names
5. Creates a second tidy dataset with the average of each variable for each subject and activity

---

## How to Run

1. Download and unzip the dataset
2. Place it inside a folder named `data`
3. Run `run_analysis.R`

---

## Output

The script generates:
tidy_data.txt