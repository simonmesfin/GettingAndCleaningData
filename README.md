# GettingAndCleaningData

The Assignment 

Getting and Cleaning Data Course Projectless 
The purpose of this project is to demonstrate your ability to collect, work with, and clean a data set. The goal is to prepare tidy data that can be used for later analysis. You will be graded by your peers on a series of yes/no questions related to the project. You will be required to submit: 1) a tidy data set as described below, 2) a link to a Github repository with your script for performing the analysis, and 3) a code book that describes the variables, the data, and any transformations or work that you performed to clean up the data called CodeBook.md. You should also include a README.md in the repo with your scripts. This repo explains how all of the scripts work and how they are connected.

One of the most exciting areas in all of data science right now is wearable computing - see for example this article . Companies like Fitbit, Nike, and Jawbone Up are racing to develop the most advanced algorithms to attract new users. The data linked to from the course website represent data collected from the accelerometers from the Samsung Galaxy S smartphone. A full description is available at the site where the data was obtained:

http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones

Here are the data for the project:

https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip

You should create one R script called run_analysis.R that does the following.

Merges the training and the test sets to create one data set.
Extracts only the measurements on the mean and standard deviation for each measurement.
Uses descriptive activity names to name the activities in the data set
Appropriately labels the data set with descriptive variable names.
From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject. 

Purpose

This assignment demonstrates how to work with data split among several sources, how to combine and transform that data into a tidy data set and then perform summarizations on the tidy data.

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
