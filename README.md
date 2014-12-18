---
title: "README"
author: "Leif Olausson"
date: "Wednesday, December 17, 2014"
output: html_document
---

# Getting and Cleaning Data Course Project
## Background
The data used in the project (linked to from the course website) represent data collected from the accelerometers from the Samsung Galaxy S smartphone. A full description is available at the site where the data was obtained: 

<http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones> 

Here are the data for the project: 

<https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip>

## Summary
The data is read from website to dataset folder (UCI HAR Dataset) in the working directory and cleaned and transformed using the script run_analysis.R in this repo. The original data consists of measured and calculated motion variables representing observations of a number of individuals (subjects) that perform certain activities (walking, sitting etc). The original data are spread over a number of separate files and will through the script be merged into one data set that is further transformed to a tidy data set showing one observation (row) of average values for certain motion parameters for each individual subject and each activity performed by each individual.

##Codebook
There is a codebook in the repo describing the tidy data set resulting from running the script run_analysis.R on the original data.

## Description of run_analysis.R script
The code in the script is fully commented to explain the steps performed to merge, clean and transform the data to the resulting tidy data set. The main steps are as follows. The tasks mentioned  are with reference to the course project assignment.

#### Reading data to working directory, merging into one set and adding motion variable names (features)
```
## Getting and Cleaning Data Course project - See accompanying ReadMe and codebook
  library(dplyr)									## library needed for filtering operations
## UCI HAR Dataset folder located in the working directory
## The data set comprises of two subsets "train" and "test" 
## Each subset is broken down into three files for "subject", "activity" and "features" 
## Task 1
## Those files will for each subset be merged and further subsequentally merged (Task 1 in Course project)
## The "test" data set
	test_sub <- read.table("./UCI HAR Dataset/test/subject_test.txt") ## subject; dim 2947 1
	test_y <- read.table("./UCI HAR Dataset/test/y_test.txt")		## activity (test labels); dim 2947 1
	test_X <- read.table("./UCI HAR Dataset/test/X_test.txt")		## test derived data; dim 2947 561	
	test_Tot <- cbind(test_sub, test_y, test_X) 				## combined total set; dim 2947 563
## The "train" data set
	train_sub <- read.table("./UCI HAR Dataset/train/subject_train.txt") 	## subject; dim 2947 1
	train_y <- read.table("./UCI HAR Dataset/train/y_train.txt")		## activity (labels); dim 2947 1
	train_X <- read.table("./UCI HAR Dataset/train/X_train.txt")		## measure derived data; dim 2947 561	
	train_Tot <- cbind(train_sub, train_y, train_X) 				## combined total set; dim 2947 563
## Merging into one complete total data set
	total_set <- rbind(train_Tot, test_Tot)					## one data set dim 10299 563 - Task 1 complete
## Adding column names for the data set
	feature_names <- read.table("./UCI HAR Dataset/features.txt")	## variable names for the derived data 561 names
	names(total_set) <- c("Subject", "Activity", as.character(feature_names[, 2]))	## names for all 563 columns
	print("Task 1 completed")

```
#### EXtracts variables representing mean and standard deviation values

```
## Task 2
## Extracts variables (features) related to mean and std derived data in any way 
## directly (as a mean or std) or indirectly (through second variable) 86 variables
  s <- grep("mean|Mean|std|Std", colnames(total_set))			## columns referencing the words mean, Mean etc
	mean_std_set <- total_set[, c(1, 2, s)]					## new reduced data set created
	print("Task 2 completed")

```
#### Text labels entered for activity and variables
```
## Task 3
## Substitutes activity numbers with clear text (activity names: walking, sitting etc)
  activity_names <- read.table("./UCI HAR Dataset/activity_labels.txt")	## Activity names read from original data source
	for (i in 1:6) mean_std_set$Activity <- sub(i, activity_names[i, 2], mean_std_set$Activity) ## numbers replaced by names
	print("Task 3 completed")
## Task 3 in project complete
## Task 4
	## Descriptive variable names added as column names in task 1. Names used are feature names from the original source
	## The variable names are further transformed in step 5 (removing "dots")
``` 
#### Consolidating data to a tidy data set
Averaging motion values to one data value per individual subject and activity making it a summarized data set for further possible evaluations
```
## Task 5
  tidy_data_set <- data.frame()										  	## initialize tidy data set
	for (k in 1:length(unique(mean_std_set[, 1])))	{
		filt_by_subj <- filter(mean_std_set[, 1:length(mean_std_set[1, ])], Subject == k)  	## filter by subject
		for (i in 1:6)	{
			a <- filter(filt_by_subj, filt_by_subj[, 2] == activity_names[i, 2])		## filter by activity (act)	
			b <- colMeans(a[, 3:length(filt_by_subj[1, ])])						## means of variables by act & subject
			v <- data.frame(c(a[1, 1:2], b))
			tidy_data_set <- rbind(tidy_data_set, v)							## build tidy data set
		}
	}
	## Tidying the variable names by removing dots
	names(tidy_data_set) <- sub("\\.", "_", names(tidy_data_set))	
	names(tidy_data_set) <- sub("\\...", "",  names(tidy_data_set))
  
```
#### Writing to file (txt) and printing to console
```
  ## Writing to txt file in data set folder in working directory - to read use data <- read.table(file_path, header = TRUE)	
	write.table(w, file="./UCI HAR Dataset/tidy_data_set.txt", row.names = F)
	## Printing subset to console		
	print("Subset of tidy data set with means/standard dev of variables by subject and activity")
	print(tidy_data_set[1:18, 1:6])										## print sub set of tidy data set
  
```
#### Reading and viewing the tidy_data_set
The data set is written to a txt file in the original data folder. It is also located in this repo. It can be reasonbly well viewed by using Notepad in Windows. full quality read is obtained by reading back to R using read.table(file_path, header = TRUE)
