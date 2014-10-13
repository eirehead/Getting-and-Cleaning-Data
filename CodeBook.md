# CodeBook
The file explains the data generate by running the run_analysis.R script.

## Input
The data used on this script can be found [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)
The data is found in a folder titled **UCI HAR Dataset**, we will use the following files:
* activity_labels.txt
* features.txt
* subject_test.txt
* subject_train.txt
* X_test.txt
* X_train.txt
* y_test.txt
* y_train.txt

**Put the UCI HAR Dataset in your R working directory**

## Output

Two datasets are generated.  The first one extracts only the measurements on the mean and the standard deviation [dataset1.csv] for each measurement.

The second [dataset2.csv] creates a second tidy data set with the average of each variable for each activity and each subject.

**The datasets will be saved in your working directory**

## Variables

## Dataset1.csv

The dataset does not add features but only creates a subset and merges two datasets into one.

1. subjectnumber (integer) - an identifier of the subject who carried out the experiment
2. activitycode (integer) - an identifier of the activity performed by the subject
3. activitydescription (factor) - activity description
4. (4-82) data columns (numeric) - for more information about these variables see *Features Selection* section

*activitycode* and *activitydescription* are related this way
1. WALKING
2. WALKING_UPSTAIRS
3. WALKING_DOWNSTAIRS
4. SITTING
5. STANDING
6. LAYING

The original dataset only includes the *activitycode* and puts the description in another file.  The **run_analysis.R** script gets the description and merges i with their corresponding codes so the dataset is easier to understand.

## Dataset2.csv

The dataset gets the mean for the data columns (dataset1.csv) by subject and activity.  Empty combinations (for example, subject 1 does not perform activity 2) are deleted.

1. subject.activity (factor) - an identifier with the format subjectnumber.activitycode
2. (2-80) data columns (numeric) - for more information about these variables see *Feature Selection* section

## Feature Selection

**Important - This section was extracted from the features_info.txt file in the original dataset.**

The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.  These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz.  Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency of 20 Hz to remove noise.  Similarly, the acceleration signal was then separated into body and gravity acceleration signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz.

Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals (tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ).  Also the magnitude of these three-dimensional signals were calculated using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag).

Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ, fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag, tBodyGyroJerkMag). (Note the 'f' to indicate frequency domain signals).

These signals were used to estimate variables of the feature vector for each pattern:
'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.

* tBodyAcc-XYZ
* tGravityAcc-XYZ
* tBodyAccJerk-XYZ
* tBodyGyro-XYZ
* tBodyGyroJerk-XYZ
* tBodyAccMag
* tGravityAccMag
* tBodyAccJerkMag
* tBodyGyroMag
* tBodyGyroJerkMag
* fBodyAcc-XYZ
* fBodyAccJerk-XYZ
* fBodyGyro-XYZ
* fBodyAccMag
* fBodyAccJerkMag
* fBodyGyroMag
* fBodyGyroJerkMag

The set of variables that were estimated from these signals are:

* mean(): Mean value
* std(): Standard deviation
* mad(): Median absolute deviation
* max(): Largest value in array
* min(): Smallest value in array
* small(): Signal magnitude area
* energy(): Energy measure. Sum of the squares divided by the number of values.
* iqr(): Interquartile range
* entropy(): Signal entropy
* arCoeff(): Autorregresion coefficients with Burg order equal to 4
* correlation(): correlation coefficient between two signals
* maxlnds(): index of the frequency component with larest magnitude
* meanFreq(): Weighted average of the frequency components to obtain a mean frequency
* skewness(): skewness of the frequency domain signal
* kurtosis(): kurtosis of the frequency domain signal
* bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window
* angle(): Angle between two vectors

Additional vectors obtained by averaging the signals in a signal window sample.  These are used on angle() variable:

* gravityMean
* tBodyAccMean
* tBodyAccJerkMean
* tBodyGyroMean
* tBodyGyroJerkMean
