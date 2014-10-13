# Getting and Cleaning Data-Coursera
This is a repository with the code for the Getting and Cleaning Data peer assignment.

# The data
The data used on this script can be found [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)
The data is in a folder titled **UCI HAR Dataset**.  We will use the following files:
* activity_labels.txt
* features.txt
* subject_test.txt
* subject_train.txt
* X_test.txt
* X_train.txt
* y_test.txt
* y_train.txt

**For the script to work, save the UCI HAR Dataset in your R working directory**

# The code

This project has one script **run_analysis.R**.  This code turns all the above files on two tidy datasets by doing the following:

1. Merges the training and the test sets to create one dataset.
2. Extract only the measurements on the mean and standard deviation (dataset1.csv) for each measurement.
3. Uses descriptive activity ames to name the activities in the dataset.
4. Appropriately labels the dataset with descriptive activity names.
5. Creates a second, independant tidy dataset with the average of each variable (dataset2.csv) for each activity and each subject.

Detailed information about generated datasets can be found on the CodeBook.md file.
