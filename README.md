# Getting and Cleaning Data-Coursera
This is a repository with the code for the Getting and Cleaning Data peer assignment.

# The data
The data used on this script can be found [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)
The data is in a folder titled **UCI HAR Dataset**.  The following files are used:
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
This project has one script **run_analysis.R**.

Two output files are generated
* merged_data.txt which contains a dataframe called *cleanedData*
* data_with_means.txt which contains a dataframe called *result*

Detailed information about generated datasets can be found on the CodeBook.md file.
