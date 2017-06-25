
The data used for the project is here:
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip.
The files are split between test data, training data and two meta files as explained below.
•	features.txt - Contains the variable names for the test and training data
•	activity_labels.txt - Links the class labels with their activity name
•	test\subject_test.txt - Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30
•	test\y_test.txt - Activity labels for the test set
•	test\X-test.txt - Test data set containing 561 variables
•	train\subject_train.txt - Each row identifies the subject who performed the activity for each window sample. Its range is from 1 to 30
•	train\y_train.txt - Activity labels for the train set
•	train\X-train.txt - Train data set containing 561 variables
Included in the github repository are the following files:
•	This ReadMe file
•	tidydata.txt - The outcome data table from the project
•	Codebook.MD - A listing and description of all the variables in the tidydata.txt file
•	run_analysis.R - An R script detailing how to reproduce the tidydata.txt file
To read the tidydata.txt into R, use the following script with the file in your working directory.


write.table(groupData, "MeanData.txt", row.names = FALSE)
