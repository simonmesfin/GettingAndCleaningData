Data Set Information

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data.

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

Attribute Information

For each record in the dataset it is provided:

Triaxial acceleration from the accelerometer (total acceleration) and the estimated body acceleration.
Triaxial Angular velocity from the gyroscope.
Its activity label.

Section 1. Merge the training and the test sets to create one data set.
After setting the source directory for the files, read into tables the data located in https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip.
The files are split between test data, training data and two meta files as explained below.
•	featureName\features.txt - Contains the variable names for the test and training data
•	activityName\activity_labels.txt - Links the class labels with their activity name
•	test.subject\subject_test.txt - Each row identifies the subject which perform the activity for each window sample, range from 1 - 30
•	test.y\y_test.txt - Activity labels for the test set
•	test.x\x_test.txt - Test data set containing 561 variables
•	train.subject\subject_train.txt - Each row identifies subject which perform the activity for each window sample, range is from 1 - 30
•	train.y\y_train.txt - Activity labels for the train set
•	train.x\x_train.txt - Train data set containing 561 variables
Assign column names and merge to create one data set.

Section 2. Extract only the measurements on the mean and standard deviation for each measurement.
Create a logical vector that contains TRUE values for the ID, mean and stdev columns and FALSE values for the others. Subset this data to keep only the necessary columns.

Section 3. Use descriptive activity names to name the activities in the data set
Merge data subset with the activityType table to include the descriptive activity names

Section 4. Appropriately label the data set with descriptive activity names.
Use gsub function for pattern replacement to clean up the data labels.

Section 5. Create a second, independent tidy data set with the average of each variable for each activity and each subject.
Per the project instructions, we need to produce only a data set with the average of each variable for each activity and subject


Variable Names

 [1] "subject"                              "activity"                            
 [3] "timeBodyAccMean-X"                    "timeBodyAccMean-Y"                   
 [5] "timeBodyAccMean-Z"                    "timeBodyAccStd-X"                    
 [7] "timeBodyAccStd-Y"                     "timeBodyAccStd-Z"                    
 [9] "timeGravityAccMean-X"                 "timeGravityAccMean-Y"                
[11] "timeGravityAccMean-Z"                 "timeGravityAccStd-X"                 
[13] "timeGravityAccStd-Y"                  "timeGravityAccStd-Z"                 
[15] "timeBodyAccJerkMean-X"                "timeBodyAccJerkMean-Y"               
[17] "timeBodyAccJerkMean-Z"                "timeBodyAccJerkStd-X"                
[19] "timeBodyAccJerkStd-Y"                 "timeBodyAccJerkStd-Z"                
[21] "timeBodyGyroMean-X"                   "timeBodyGyroMean-Y"                  
[23] "timeBodyGyroMean-Z"                   "timeBodyGyroStd-X"                   
[25] "timeBodyGyroStd-Y"                    "timeBodyGyroStd-Z"                   
[27] "timeBodyGyroJerkMean-X"               "timeBodyGyroJerkMean-Y"              
[29] "timeBodyGyroJerkMean-Z"               "timeBodyGyroJerkStd-X"               
[31] "timeBodyGyroJerkStd-Y"                "timeBodyGyroJerkStd-Z"               
[33] "timeBodyAccMagMean"                   "timeBodyAccMagStd"                   
[35] "timeGravityAccMagMean"                "timeGravityAccMagStd"                
[37] "timeBodyAccJerkMagMean"               "timeBodyAccJerkMagStd"               
[39] "timeBodyGyroMagMean"                  "timeBodyGyroMagStd"                  
[41] "timeBodyGyroJerkMagMean"              "timeBodyGyroJerkMagStd"              
[43] "frequenceBodyAccMean-X"               "frequenceBodyAccMean-Y"              
[45] "frequenceBodyAccMean-Z"               "frequenceBodyAccStd-X"               
[47] "frequenceBodyAccStd-Y"                "frequenceBodyAccStd-Z"               
[49] "frequenceBodyAccMeanFreq-X"           "frequenceBodyAccMeanFreq-Y"          
[51] "frequenceBodyAccMeanFreq-Z"           "frequenceBodyAccJerkMean-X"          
[53] "frequenceBodyAccJerkMean-Y"           "frequenceBodyAccJerkMean-Z"          
[55] "frequenceBodyAccJerkStd-X"            "frequenceBodyAccJerkStd-Y"           
[57] "frequenceBodyAccJerkStd-Z"            "frequenceBodyAccJerkMeanFreq-X"      
[59] "frequenceBodyAccJerkMeanFreq-Y"       "frequenceBodyAccJerkMeanFreq-Z"      
[61] "frequenceBodyGyroMean-X"              "frequenceBodyGyroMean-Y"             
[63] "frequenceBodyGyroMean-Z"              "frequenceBodyGyroStd-X"              
[65] "frequenceBodyGyroStd-Y"               "frequenceBodyGyroStd-Z"              
[67] "frequenceBodyGyroMeanFreq-X"          "frequenceBodyGyroMeanFreq-Y"         
[69] "frequenceBodyGyroMeanFreq-Z"          "frequenceBodyAccMagMean"             
[71] "frequenceBodyAccMagStd"               "frequenceBodyAccMagMeanFreq"         
[73] "frequenceBodyBodyAccJerkMagMean"      "frequenceBodyBodyAccJerkMagStd"      
[75] "frequenceBodyBodyAccJerkMagMeanFreq"  "frequenceBodyBodyGyroMagMean"        
[77] "frequenceBodyBodyGyroMagStd"          "frequenceBodyBodyGyroMagMeanFreq"    
[79] "frequenceBodyBodyGyroJerkMagMean"     "frequenceBodyBodyGyroJerkMagStd"     
[81] "frequenceBodyBodyGyroJerkMagMeanFreq"
