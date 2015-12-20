# Getting-and-Cleaning-Data-Course-Project
![](http://i.imgur.com/Gy09n0I.png)

The R script `run_analysis.R` has been created following the project instructions: 

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive variable names. 
5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

As a result, the script process the initial data (collected from the accelerometers from the Samsung Galaxy S smartphone) generating two files:

1. `ProcessedData.txt`: Contains the desired data (measurements of mean and standard deviation) for each subject and activity.
2. `TidyAveragesData.txt`: Contains the data corresponding to the average for each subject and activity.

#### Data:
The corresponding data can be downloaded [here](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip).
