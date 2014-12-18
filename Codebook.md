---
title: "Codebook Course project"
author: "Leif Olausson"
date: "Thursday, December 18, 2014"
output: html_document
---
## Getting and Cleaning Data Course project
### Description
The data set described here is based on data from "Human Activity Recognition Using Smartphones Dataset Version 1.0" (See References).

The data consists of measured and calculated motion variables representing observations of a number of individuals (subjects) that perform certain activities (walking, sitting etc). The data set shows one observation (row) of values for certain motion parameters for each individual subject and each activity performed by each individual.

### Usage
tidy_data_set

### Variables
For each record it is provided (see Format and structure below):

* An identifier (number) of the subject who carried out the experiment.
    + Reference Subject
* Its activity label. 
    + WALKING etc
* Triaxial acceleration (X, Y, Z) from the accelerometer (total acceleration) and the estimated body acceleration.
    +  tBodyAcc_meanX etc representing mean (meanX) and standard deviation (stdX) numbers calculated over a large number of observations
    +  Similar for frequency of certain motions "jerks"
* Triaxial Angular velocity from the gyroscope.
    +  angle_ variables as mean and standard deviation values as above

### Format and structure

```
'data.frame':   180 obs. of  88 variables:
 $ Subject                          : int  1 1 1 1 1 1 2 2 2 2 ...
 $ Activity                         : Factor w/ 6 levels "WALKING","WALKING_UPSTAIRS",..: 1 2 3 4 5 6 1 2 3 4 ...
 $ tBodyAcc_meanX                   : num  0.277 0.255 0.289 0.261 0.279 ...
 $ tBodyAcc_meanY                   : num  -0.01738 -0.02395 -0.00992 -0.00131 -0.01614 ...
 $ tBodyAcc_meanZ                   : num  -0.1111 -0.0973 -0.1076 -0.1045 -0.1106 ...
 $ tBodyAcc_stdX                    : num  -0.284 -0.355 0.03 -0.977 -0.996 ...
 $ tBodyAcc_stdY                    : num  0.11446 -0.00232 -0.03194 -0.92262 -0.97319 ...
 $ tBodyAcc_stdZ                    : num  -0.26 -0.0195 -0.2304 -0.9396 -0.9798 ...
 $ tGravityAcc_meanX                : num  0.935 0.893 0.932 0.832 0.943 ...
 $ tGravityAcc_meanY                : num  -0.282 -0.362 -0.267 0.204 -0.273 ...
 $ tGravityAcc_meanZ                : num  -0.0681 -0.0754 -0.0621 0.332 0.0135 ...
 $ tGravityAcc_stdX                 : num  -0.977 -0.956 -0.951 -0.968 -0.994 ...
 $ tGravityAcc_stdY                 : num  -0.971 -0.953 -0.937 -0.936 -0.981 ...
 $ tGravityAcc_stdZ                 : num  -0.948 -0.912 -0.896 -0.949 -0.976 ...
 $ tBodyAccJerk_meanX               : num  0.074 0.1014 0.0542 0.0775 0.0754 ...
 $ tBodyAccJerk_meanY               : num  0.028272 0.019486 0.02965 -0.000619 0.007976 ...
 $ tBodyAccJerk_meanZ               : num  -0.00417 -0.04556 -0.01097 -0.00337 -0.00369 ...
 $ tBodyAccJerk_stdX                : num  -0.1136 -0.4468 -0.0123 -0.9864 -0.9946 ...
 $ tBodyAccJerk_stdY                : num  0.067 -0.378 -0.102 -0.981 -0.986 ...
 $ tBodyAccJerk_stdZ                : num  -0.503 -0.707 -0.346 -0.988 -0.992 ...
 $ tBodyGyro_meanX                  : num  -0.0418 0.0505 -0.0351 -0.0454 -0.024 ...
 $ tBodyGyro_meanY                  : num  -0.0695 -0.1662 -0.0909 -0.0919 -0.0594 ...
 $ tBodyGyro_meanZ                  : num  0.0849 0.0584 0.0901 0.0629 0.0748 ...
 $ tBodyGyro_stdX                   : num  -0.474 -0.545 -0.458 -0.977 -0.987 ...
 $ tBodyGyro_stdY                   : num  -0.05461 0.00411 -0.12635 -0.96647 -0.98773 ...
 $ tBodyGyro_stdZ                   : num  -0.344 -0.507 -0.125 -0.941 -0.981 ...
 $ tBodyGyroJerk_meanX              : num  -0.09 -0.1222 -0.074 -0.0937 -0.0996 ...
 $ tBodyGyroJerk_meanY              : num  -0.0398 -0.0421 -0.044 -0.0402 -0.0441 ...
 $ tBodyGyroJerk_meanZ              : num  -0.0461 -0.0407 -0.027 -0.0467 -0.049 ...
 $ tBodyGyroJerk_stdX               : num  -0.207 -0.615 -0.487 -0.992 -0.993 ...
 $ tBodyGyroJerk_stdY               : num  -0.304 -0.602 -0.239 -0.99 -0.995 ...
 $ tBodyGyroJerk_stdZ               : num  -0.404 -0.606 -0.269 -0.988 -0.992 ...
 $ tBodyAccMag_mean..               : num  -0.137 -0.1299 0.0272 -0.9485 -0.9843 ...
 $ tBodyAccMag_std..                : num  -0.2197 -0.325 0.0199 -0.9271 -0.9819 ...
 $ tGravityAccMag_mean..            : num  -0.137 -0.1299 0.0272 -0.9485 -0.9843 ...
 $ tGravityAccMag_std..             : num  -0.2197 -0.325 0.0199 -0.9271 -0.9819 ...
 $ tBodyAccJerkMag_mean..           : num  -0.1414 -0.4665 -0.0894 -0.9874 -0.9924 ...
 $ tBodyAccJerkMag_std..            : num  -0.0745 -0.479 -0.0258 -0.9841 -0.9931 ...
 $ tBodyGyroMag_mean..              : num  -0.161 -0.1267 -0.0757 -0.9309 -0.9765 ...
 $ tBodyGyroMag_std..               : num  -0.187 -0.149 -0.226 -0.935 -0.979 ...
 $ tBodyGyroJerkMag_mean..          : num  -0.299 -0.595 -0.295 -0.992 -0.995 ...
 $ tBodyGyroJerkMag_std..           : num  -0.325 -0.649 -0.307 -0.988 -0.995 ...
 $ fBodyAcc_meanX                   : num  -0.2028 -0.4043 0.0382 -0.9796 -0.9952 ...
 $ fBodyAcc_meanY                   : num  0.08971 -0.19098 0.00155 -0.94408 -0.97707 ...
 $ fBodyAcc_meanZ                   : num  -0.332 -0.433 -0.226 -0.959 -0.985 ...
 $ fBodyAcc_stdX                    : num  -0.3191 -0.3374 0.0243 -0.9764 -0.996 ...
 $ fBodyAcc_stdY                    : num  0.056 0.0218 -0.113 -0.9173 -0.9723 ...
 $ fBodyAcc_stdZ                    : num  -0.28 0.086 -0.298 -0.934 -0.978 ...
 $ fBodyAcc_meanFreqX               : num  -0.2075 -0.4187 -0.3074 -0.0495 0.0865 ...
 $ fBodyAcc_meanFreqY               : num  0.1131 -0.1607 0.0632 0.0759 0.1175 ...
 $ fBodyAcc_meanFreqZ               : num  0.0497 -0.5201 0.2943 0.2388 0.2449 ...
 $ fBodyAccJerk_meanX               : num  -0.1705 -0.4799 -0.0277 -0.9866 -0.9946 ...
 $ fBodyAccJerk_meanY               : num  -0.0352 -0.4134 -0.1287 -0.9816 -0.9854 ...
 $ fBodyAccJerk_meanZ               : num  -0.469 -0.685 -0.288 -0.986 -0.991 ...
 $ fBodyAccJerk_stdX                : num  -0.1336 -0.4619 -0.0863 -0.9875 -0.9951 ...
 $ fBodyAccJerk_stdY                : num  0.107 -0.382 -0.135 -0.983 -0.987 ...
 $ fBodyAccJerk_stdZ                : num  -0.535 -0.726 -0.402 -0.988 -0.992 ...
 $ fBodyAccJerk_meanFreqX           : num  -0.209 -0.377 -0.253 0.257 0.314 ...
 $ fBodyAccJerk_meanFreqY           : num  -0.3862 -0.5095 -0.3376 0.0475 0.0392 ...
 $ fBodyAccJerk_meanFreqZ           : num  -0.18553 -0.5511 0.00937 0.09239 0.13858 ...
 $ fBodyGyro_meanX                  : num  -0.339 -0.493 -0.352 -0.976 -0.986 ...
 $ fBodyGyro_meanY                  : num  -0.1031 -0.3195 -0.0557 -0.9758 -0.989 ...
 $ fBodyGyro_meanZ                  : num  -0.2559 -0.4536 -0.0319 -0.9513 -0.9808 ...
 $ fBodyGyro_stdX                   : num  -0.517 -0.566 -0.495 -0.978 -0.987 ...
 $ fBodyGyro_stdY                   : num  -0.0335 0.1515 -0.1814 -0.9623 -0.9871 ...
 $ fBodyGyro_stdZ                   : num  -0.437 -0.572 -0.238 -0.944 -0.982 ...
 $ fBodyGyro_meanFreqX              : num  0.0148 -0.1875 -0.1005 0.1892 -0.1203 ...
 $ fBodyGyro_meanFreqY              : num  -0.0658 -0.4736 0.0826 0.0631 -0.0447 ...
 $ fBodyGyro_meanFreqZ              : num  0.000773 -0.133374 -0.075676 -0.029784 0.100608 ...
 $ fBodyAccMag_mean..               : num  -0.1286 -0.3524 0.0966 -0.9478 -0.9854 ...
 $ fBodyAccMag_std..                : num  -0.398 -0.416 -0.187 -0.928 -0.982 ...
 $ fBodyAccMag_meanFreq..           : num  0.1906 -0.0977 0.1192 0.2367 0.2846 ...
 $ fBodyBodyAccJerkMag_mean..       : num  -0.0571 -0.4427 0.0262 -0.9853 -0.9925 ...
 $ fBodyBodyAccJerkMag_std..        : num  -0.103 -0.533 -0.104 -0.982 -0.993 ...
 $ fBodyBodyAccJerkMag_meanFreq..   : num  0.0938 0.0854 0.0765 0.3519 0.4222 ...
 $ fBodyBodyGyroMag_mean..          : num  -0.199 -0.326 -0.186 -0.958 -0.985 ...
 $ fBodyBodyGyroMag_std..           : num  -0.321 -0.183 -0.398 -0.932 -0.978 ...
 $ fBodyBodyGyroMag_meanFreq..      : num  0.268844 -0.219303 0.349614 -0.000262 -0.028606 ...
 $ fBodyBodyGyroJerkMag_mean..      : num  -0.319 -0.635 -0.282 -0.99 -0.995 ...
 $ fBodyBodyGyroJerkMag_std..       : num  -0.382 -0.694 -0.392 -0.987 -0.995 ...
 $ fBodyBodyGyroJerkMag_meanFreq..  : num  0.191 0.114 0.19 0.185 0.334 ...
 $ angle_tBodyAccMeanavity.         : num  0.060454 0.096086 -0.002695 0.027442 -0.000222 ...
 $ angle_tBodyAccJerkMeanravityMean.: num  -0.00793 -0.06108 0.08993 0.02971 0.02196 ...
 $ angle_tBodyGyroMeanavityMean.    : num  0.0131 -0.1947 0.0633 0.0677 -0.0338 ...
 $ angle_tBodyGyroJerkMeanavityMean.: num  -0.0187 0.0657 -0.04 -0.0649 -0.0279 ...
 $ angle_XavityMean.                : num  -0.729 -0.647 -0.744 -0.591 -0.743 ...
 $ angle_YavityMean.                : num  0.277 0.3348 0.2672 -0.0605 0.2702 ...
 $ angle_ZavityMean.                : num  0.0689 0.0742 0.065 -0.218 0.0123 ...

```
### Statistical summary
Summary for part of the data set (1 subject, all activities and a three motion variables)
```
   Subject                     Activity    tBodyAcc_meanX     tBodyAcc_meanY        tBodyAcc_meanZ      
 "Min.   : 1.0  " "WALKING           :30  " "Min.   :0.2216  " "Min.   :-0.040514  " "Min.   :-0.15251  "
 "1st Qu.: 8.0  " "WALKING_UPSTAIRS  :30  " "1st Qu.:0.2712  " "1st Qu.:-0.020022  " "1st Qu.:-0.11207  "
 "Median :15.5  " "WALKING_DOWNSTAIRS:30  " "Median :0.2770  " "Median :-0.017262  " "Median :-0.10819  "
 "Mean   :15.5  " "SITTING           :30  " "Mean   :0.2743  " "Mean   :-0.017876  " "Mean   :-0.10916  "
 "3rd Qu.:23.0  " "STANDING          :30  " "3rd Qu.:0.2800  " "3rd Qu.:-0.014936  " "3rd Qu.:-0.10443  "
 "Max.   :30.0  " "LAYING            :30  " "Max.   :0.3015  " "Max.   :-0.001308  " "Max.   :-0.07538  "
```
### Reading data set and example view of data in R
```
Reading with data <- read.table(file_path, header = TRUE) and viewing a subset gives as an example the following:
```

```
   Subject           Activity tBodyAcc_meanX tBodyAcc_meanY tBodyAcc_meanZ tBodyAcc_stdX tBodyAcc_stdY
1        1            WALKING      0.2773308   -0.017383819     -0.1111481   -0.28374026   0.114461337
2        1   WALKING_UPSTAIRS      0.2554617   -0.023953149     -0.0973020   -0.35470803  -0.002320265
3        1 WALKING_DOWNSTAIRS      0.2891883   -0.009918505     -0.1075662    0.03003534  -0.031935943
4        1            SITTING      0.2612376   -0.001308288     -0.1045442   -0.97722901  -0.922618642
5        1           STANDING      0.2789176   -0.016137590     -0.1106018   -0.99575990  -0.973190056
6        1             LAYING      0.2215982   -0.040513953     -0.1132036   -0.92805647  -0.836827406
7        2            WALKING      0.2764266   -0.018594920     -0.1055004   -0.42364284  -0.078091253
8        2   WALKING_UPSTAIRS      0.2471648   -0.021412113     -0.1525139   -0.30437641   0.108027280
9        2 WALKING_DOWNSTAIRS      0.2776153   -0.022661416     -0.1168129    0.04636668   0.262881789
10       2            SITTING      0.2770874   -0.015687994     -0.1092183   -0.98682228  -0.950704499

```
### Source
Data source: 

<https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip>

Full description: 

<http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones> 

### References
```
==================================================================
Human Activity Recognition Using Smartphones Dataset
Version 1.0
==================================================================
Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
Smartlab - Non Linear Complex Systems Laboratory
DITEN - Universit� degli Studi di Genova.
Via Opera Pia 11A, I-16145, Genoa, Italy.
activityrecognition@smartlab.ws
www.smartlab.ws
==================================================================
```