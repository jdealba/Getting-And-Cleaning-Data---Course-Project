Coursera Getting And Cleaning Data - Course Project
========================================================
Version 1.0

June 19, 2014

This document explains the steps followed to process the data for the Coursera´s 
Getting And Cleaning Data Course Project.

This project is based on *Human Activity Recognition Using Smartphones Dataset* (1). 
The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist.(2)
        
NOTE: 
* The unzipped files of the *Human Activity Recognition Using Smartphones Dataset*  MUST be in the base directory of the R Project.
* The script uses the *reshape2* library.     

I create one R script called run_analysis.R that does the following. 

1.-Merges the training and the test sets to create one data set.
* To merge the training and test data sets, I read the files *subject_test.txt,
Y_test.txt and X_test.txt* for the test information and *subject_train.txt,
Y_train.txt and X_train.txt* for the train information and merge them in one 
dataframe.

```{r}
##Read Files subject_test.txt,Y_test.txt and X_test.txt
subject_test <- read.table("./UCI HAR Dataset/test/subject_test.txt",header=FALSE,col.names=c("SubjectId"));
Y_test <- read.table("./UCI HAR Dataset/test/Y_test.txt",header=FALSE, col.names=c("Activity"));
X_test <- read.table("./UCI HAR Dataset/test/X_test.txt",header=FALSE);

##Merge the test Information in one dataframe.
subject_test_complete <- cbind(subject_test,Y_test,X_test);
                               
##Read Files subject_train.txt,Y_train.txt and X_train.txt                          
subject_train <- read.table("./UCI HAR Dataset/train/subject_train.txt",header=FALSE,col.names=c("SubjectId"));
Y_train <- read.table("./UCI HAR Dataset/train/Y_train.txt",header=FALSE, col.names=c("Activity"));
X_train <- read.table("./UCI HAR Dataset/train/X_train.txt",header=FALSE);

##Merge the train Information in one dataframe.
subject_train_complete <- cbind(subject_train,Y_train,X_train);

##merge the test and test dataframes.
mergedData <-  rbind(subject_test_complete,subject_train_complete);
```

2.- Extracts only the measurements on the mean and standard deviation for each measurement.
* To extract only the mean and standard deviation of the original dataset, 
I read the names of the variables from the *features.txt* file and use the grep()
function to obtain a vector with the positions of the variables that contains 
in their names the word mean() or std(), the variables with the suffix
meanFreq() were discarded because they are averages obtained to calculate other 
data so they are not a direct mean measurement as specified in the requirement. 

```{r}
##Read the features.txt file.
features <- read.table("./UCI HAR Dataset/features.txt",header=FALSE, col.names=c("FeaturePosition","FeatureName"));
## convert to character the column FeatureName to apply grep() function.
features$FeatureName <- as.character(features$FeatureName);
## Apply grep() to Extract the position of the Variables that match exactly the string mean() and std().
meanFeatures <- grep('mean()', features$FeatureName,fixed=TRUE);
stdFeatures <- grep('std()', features$FeatureName,fixed=TRUE);

##Join the two vectors.
meanAndStdFeatures <- c(meanFeatures,stdFeatures);
##Order the joined vector.
meanAndStdFeatures <-  meanAndStdFeatures[order(meanAndStdFeatures)];
##meanAndStd <- c(1,2,meanAndStdFeatures + 2)

##filter only the mean and standard columns and consider the first 2 columns of subject and activity.
mergedData <- mergedData[,c(1,2,meanAndStdFeatures + 2)];

```

3.-Appropriately labels the data set with descriptive variable names.
* I filter the features dataframe to select only the mean and standard deviation
variables and replace strings in the name of the variable with the gsub() function,
to set more descriptive variable names in the Dataset.

```{r}
##Select only the variables of mean an Standard Deviation of the features dataframe
features <- features[meanAndStdFeatures,]
##rename the variables with more descriptive variable names.
features$FeatureName <- gsub('()',"",features$FeatureName,fixed=TRUE);
features$FeatureName <- gsub("-","",features$FeatureName);
features$FeatureName <- gsub("Acc","Acceleration",features$FeatureName);
features$FeatureName <- gsub("fBodyBody","frequencyBody",features$FeatureName);
features$FeatureName <- gsub("fBody","frequencyBody",features$FeatureName);
features$FeatureName <- gsub("Freq","Frequency",features$FeatureName);
features$FeatureName <- gsub("tBody","timeBody",features$FeatureName);
features$FeatureName <- gsub("Mag","Magnitude",features$FeatureName);
features$FeatureName <- gsub("tGravity","timeGravity",features$FeatureName);
features$FeatureName <- gsub("std","StandardDeviation",features$FeatureName);
features$FeatureName <- gsub("mean","Mean",features$FeatureName);
##Rename the variable names with more 
colnames(mergedData) <- c("SubjectId","Activity",features$FeatureName);

```

4.-Uses descriptive activity names to name the activities in the data set
* To use the descriptive activity names in the dataset, I read the *activity_labels.txt* 
file and convert to factor type the *Activity* Column of the dataset, then 
I set the levels with the names in the dataset of activity names.

```{r}
##reads the activity_labels.txt file
activityLabels <- read.table("./UCI HAR Dataset/activity_labels.txt",header=FALSE, col.names=c("ActivityId","ActivityName"));

##Converts in factor the numeric variable activity of the dataset
mergedData$Activity <-as.factor(mergedData$Activity);
##sets the leels of the factor according to the activity labels.
levels(mergedData$Activity) <- activityLabels$ActivityName;
##view the first 6 columns of the final mergedData
head(mergedData)

```


5.-Creates a second, independent tidy data set with the average of each variable
for each activity and each subject. 
* I create a tidy data set using the *melt()* function first to prepare 
the data and then using the *dcast()* function to obtain the means of the 
subject's activities, finally I write the result to a text file called 
*Means_of_mean_and_stdev_features.txt* with the *write.table()* function. 

```{r}
##melt the data set with the ids SubjectId and Activity
moltedData <- melt(mergedData, id=c("SubjectId","Activity"), );
## apply a dcast() function to obtain a tidy dataset with the means of the Subject's Activities.
tidyData <- dcast( moltedData, SubjectId + Activity ~ variable,mean);
## write the result tidy dataset to a file.
write.table(tidyData,"Means_of_mean_and_stdev_features.txt",row.names=FALSE);
```

### References
1.- Data set extracted from the Human Activity Recognition Using Smartphones 
Experiment  realized  in DITEN - University degli Studi di Genova.
activityrecognition@smartlab.ws, www.smartlab.ws

2.- For detailed information of the experiment see the README.txt file of
the dataset in the following link: 
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones