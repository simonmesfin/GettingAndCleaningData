# GettingAndCleaningData

Overview
This assignment demonstrates how to work with data split among several sources, combine and transform that data into a tidy data set and perform summarizations on the tidy data. A full description of the data used in this project can be found at The UCI Machine Learning Repository
The source data for this project can be found here.

Project Summary
This repo was created to complete the assignment for week 4 of Getting and Cleaning Data Coursera course.
•	First, download and unzip the data file into your R working directory.
•	Second, download the R source code into your R working directory.
•	Finally, execute R source code to generate tidy data file.

Data description
The variables in the data X are sensor signals measured with waist-mounted smartphone from 30 subjects. The variable in the data Y indicates activity type the subjects performed during recording.

Code explanation
The code combined training dataset and test dataset, and extracted partial variables to create another dataset with the averages of each variable for each activity.

New dataset
The new generated dataset contained variables calculated based on the mean and standard deviation. Each row of the dataset is an average of each activity type for all subjects.

The code was written based on the instruction of this assignment
Read training and test dataset, variable names and subject index into R environment.
1.	Merges the training and the test sets to create one data set. Use command rbind to combine training and test set,
2.	Extracts only the measurements on the mean and standard deviation for each measurement. Use grep command to get column indexes for variable name contains "mean()" or "std()",
3.	Uses descriptive activity names to name the activities in the data set Convert activity labels to characters and add a new column as factor,
4.	Appropriately labels the data set with descriptive variable names. Give the selected descriptive names to variable columns, and
5.	From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject. Use pipeline command to create a new tidy dataset with command group_by and summarize_each in dplyr package.

Activity Labels

WALKING (value 1): subject was walking during the test
WALKING_UPSTAIRS (value 2): subject was walking up a staircase during the test
WALKING_DOWNSTAIRS (value 3): subject was walking down a staircase during the test
SITTING (value 4): subject was sitting during the test
STANDING (value 5): subject was standing during the test
LAYING (value 6): subject was laying down during the test

Outcome

When the run_analysis.R script is run, the resulting table is a tidy data set.
The data is considered to be tidy when:
1.	Each variable must have its own column.
2.	Each observation must have its own row.
3.	Each value must have its own cell.
source: Hadley Wickham's paper on tidy data http://http://www.jstatsoft.org/v59/i10/paper

The output of the script is tidy because each column represents a variable and each row represents an observation, in this case a subject's activity is measured across several smartphone sensor readings. Additionally, all columns have descriptive names and all activities have been converted from code numbers to descriptive activity name.

The assignment also requires that only the measurements on the mean and standard deviation for each measurement are extracted. The method used to select those variable looks for the strings "mean()" and "std()" and not the strings "mean" and "std" since the latter would include several variables that are not means of measurement data, such as meanFreq, which is a weighted average and not a mean.

Included in the github repository are the following files:
•	This ReadMe file
•	tidydata.txt - The outcome data table from the project
•	Codebook.MD - A listing and description of all the variables in the tidydata.txt file
•	run_analysis.R - An R script detailing how to reproduce the tidydata.txt file
To read the tidydata.txt into R, use the following script with the file in your working directory.

write.table(groupData, "MeanData.txt", row.names = FALSE)
