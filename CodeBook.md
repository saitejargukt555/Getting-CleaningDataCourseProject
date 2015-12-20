<h1> Code Book </h1>
The R script run_analysis.R and the downloaded data folder "UCI HAR Dataset" should be in the same working directory.

<h2> Variables and their treatment </h2>
<h3> Initial data </h3>
The data corresponds to the results of an experiment carried out with a group of 30 volunteers. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a Samsung Galaxy S II. For each record it is provided:

<ul>
  <li>Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.</li>
  <li>Triaxial Angular velocity from the gyroscope.</li>
  <li>A 561-feature vector with time and frequency domain variables.</li>
  <li>Its activity label.</li>
  <li>An identifier of the subject who carried out the experiment.</li>
</ul>
The relevant information about the files follows:
<ul>
  <li>'features_info.txt': Shows information about the variables used on the feature vector.</li>
  <li>'features.txt': List of all features.</li>
  <li>'activity_labels.txt': Links the class labels with their activity name.</li>
  <li>'train/X_train.txt': Training set.</li>
  <li>'train/y_train.txt': Training labels.</li>
  <li>'test/X_test.txt': Test set.</li>
  <li>'test/y_test.txt': Test labels.</li>
</ul>
And for both the train and test data the following files are given:
<ul>
  <li>'train/subject_train.txt': Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30.</li>
  <li>'train/Inertial Signals/total_acc_x_train.txt': The acceleration signal from the smartphone accelerometer X axis in standard gravity units 'g'. Every row shows a 128 element vector. The same description applies for the 'total_acc_x_train.txt' and 'total_acc_z_train.txt' files for the Y and Z axis. </li>
  <li>'train/Inertial Signals/body_acc_x_train.txt': The body acceleration signal obtained by subtracting the gravity from the total acceleration.</li>
  <li>'train/Inertial Signals/body_gyro_x_train.txt': The angular velocity vector measured by the gyroscope for each window sample. The units are radians/second. </li>
</ul>
Additional descriptions regarding the physical meaning of the data can be found in README.txt within the data folder "UCI HAR Dataset".

<h3> Processed data </h3>
Following the instrucions of the project the following variables were created and transformed:
<ul>
  <li>'Set': Contains the merged data of 'X_train.txt' and 'X_test'.</li>
  <li>'Subjects': Contains the merged data of 'subject_train.txt' and 'subject_test.txt'.</li>
  <li>'Labels': Contains the merged data of 'y_train.txt' and 'y_test.txt'.</li>
  <li>'AllFeatures': Contains all the features of 'features.txt'.</li>
  <li>'IndexDesiredFeatures': Contains the indices of the desired features to process (measurements on the mean and standard deviation).</li>
  <li>'SetDesiredFeatures': Contains the data only for the desired features.</li>
  <li>'AllActivities': Contains the six performed activities.</li>
</ul>
In order to use more human-friendly names, the built-in funcion gsub() has been repeatedly used in order to make changes like for example:
<ul>
  <li>tBodyAcc-mean()-X --> tBodyAcc-mean-X</li>
</ul> 
or:
<ul>
  <li>tBodyAcc-mean()-X --> tBodyAccMeanX</li>
</ul> 

<h2> Output </h2>
The R script run_analysis.R generates the following two data files:
<ul>
  <li>'ProcessedData.txt': Contains the desired data (10,299 observations of the 68 variables). The first two variables contain the subject ID number and the specific activity. The other 66 variables correspond to the different values of the mean and standard deviation obtained for the different features.</li>
  <li>'TidyAveragesData.txt': Contains the desired data of averages (180 observations of the 68 variables). The first two variables contain the subject ID number and the specific activity. The other 66 variables correspond to the average of each variable for each subject and each activity.</li>
</ul> 
Note that the activity names have been changed in the same way for both output files, for example:
<ul>
  <li>STANDING --> Standing</li>
</ul> 
But the feature names follow the distinction previously shown:
<ul>
  <li>tBodyAcc-mean()-X --> tBodyAcc-mean-X</li> for 'ProcessedData.txt'.
  <li>tBodyAcc-mean()-X --> tBodyAccMeanX</li> for 'TidyAveragesData.txt'.
</ul> 
