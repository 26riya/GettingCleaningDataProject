# Code Book

## Dataset Description

The dataset contains measurements collected from accelerometers and gyroscopes from 30 subjects performing different activities.

---

## Variables

### Identifiers
- Subject: Identifier of the subject (1–30)
- Activity: Type of activity performed
  - WALKING
  - WALKING_UPSTAIRS
  - WALKING_DOWNSTAIRS
  - SITTING
  - STANDING
  - LAYING

---

### Measurements

The dataset includes:

- Time domain signals (tBodyAcc, tGravityAcc, etc.)
- Frequency domain signals (fBodyAcc, fBodyGyro, etc.)

Each measurement includes:
- Mean values (Mean)
- Standard deviation values (StdDev)

---

## Data Cleaning Process

The following transformations were applied:

1. Combined training and test datasets into one dataset
2. Extracted only mean and standard deviation features
3. Replaced activity IDs with descriptive names
4. Renamed variables to improve readability:
   - Removed special characters
   - Replaced abbreviations (mean → Mean, std → StdDev)
5. Created a tidy dataset by computing the average of each variable for each subject and activity

---

## Final Output

- tidy_data.txt

This dataset contains the average of each selected variable grouped by subject and activity.