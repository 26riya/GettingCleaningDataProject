
# Step 1: Load required libraries
library(dplyr)

# Step 2: Read data

# Features and activity labels
features <- read.table("data/UCI HAR Dataset/features.txt", stringsAsFactors = FALSE)
activity_labels <- read.table("data/UCI HAR Dataset/activity_labels.txt", stringsAsFactors = FALSE)

# Training data
X_train <- read.table("data/UCI HAR Dataset/train/X_train.txt")
y_train <- read.table("data/UCI HAR Dataset/train/y_train.txt")
subject_train <- read.table("data/UCI HAR Dataset/train/subject_train.txt")

# Test data
X_test <- read.table("data/UCI HAR Dataset/test/X_test.txt")
y_test <- read.table("data/UCI HAR Dataset/test/y_test.txt")
subject_test <- read.table("data/UCI HAR Dataset/test/subject_test.txt")

# Step 3: Merge datasets
X <- rbind(X_train, X_test)
y <- rbind(y_train, y_test)
subject <- rbind(subject_train, subject_test)

# Step 4: Name columns
colnames(X) <- features$V2
colnames(y) <- "Activity"
colnames(subject) <- "Subject"

# Combine all
data <- cbind(subject, y, X)

# Step 5: Extract mean & std only
data_subset <- data %>%
  select(Subject, Activity, contains("mean"), contains("std"))

# Step 6: Use descriptive activity names
data_subset$Activity <- factor(data_subset$Activity,
                               levels = activity_labels$V1,
                               labels = activity_labels$V2)

# Step 7: Clean variable names
colnames(data_subset) <- gsub("[()]", "", colnames(data_subset))
colnames(data_subset) <- gsub("-", "_", colnames(data_subset))
colnames(data_subset) <- gsub("mean", "Mean", colnames(data_subset))
colnames(data_subset) <- gsub("std", "StdDev", colnames(data_subset))

# Step 8: Create tidy dataset (average of each variable)
tidy_data <- data_subset %>%
  group_by(Subject, Activity) %>%
  summarise_all(mean)

# Step 9: Write output
write.table(tidy_data, "tidy_data.txt", row.names = FALSE)

# Done!