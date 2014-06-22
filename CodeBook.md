CodeBook 
========================================================

Coursera Getting And Cleaning Data - Course Project Code Book
--------------------------------------------------------
June 19, 2014

Version 1.0

Code book prepared by JDA, for the Getting And Cleaning Data Course Project
based on *Human Activity Recognition Using Smartphones Dataset* obtained from the following link:
        http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones
                
Since only measurements in the mean and standard deviation for each measurement 
were considered in this project, the variables with the suffix meanFreq() were 
discarded because they are averages obtained to calculate other data so they are
not a direct mean measurement as specified in the requirement. 

The following 68 variables were used and renamed with more descriptive variable names.


        SubjectId
                Identifier of the Subject that participate in the Experiment. (In this study are only 30 subjects).
                
        Activity
                Activity performed by the subject during the Observation.
                
        timeBodyAccelerationMeanX			
                Mean of the Body Time Acceleration in X axis.
                
        timeBodyAccelerationMeanY			
                Mean of the Body Time Acceleration in Y axis.
                
        timeBodyAccelerationMeanZ			
                Mean of the Body Time Acceleration in Z axis.
                
        timeBodyAccelerationStandardDeviationX		
                Standard Deviation of the Body Time Acceleration in X axis
        
        timeBodyAccelerationStandardDeviationY	
                Standard Deviation of the Body Time Acceleration in Y axis
        
        timeBodyAccelerationStandardDeviationZ		
                Standard Deviation of the Body Time Acceleration in Z axis
        
        timeGravityAccelerationMeanX		
                Mean of the Gravity Time Acceleration in X axis
        
        timeGravityAccelerationMeanY		
                Mean of the Gravity Time Acceleration in Y axis
                
        timeGravityAccelerationMeanZ			
                Mean of the Gravity Time Acceleration in Z axis
        
        timeGravityAccelerationStandardDeviationX	
                Standard Deviation of the Gravity Time Acceleration in X axis
        
        timeGravityAccelerationStandardDeviationY				
                Standard Deviation of the Gravity Time Acceleration in Y axis
        
        timeGravityAccelerationStandardDeviationZ				
                Standard Deviation of the Gravity Time Acceleration in Z axis
        
        timeBodyAccelerationJerkMeanX			
                Mean of the Body Jerk Time Acceleration in X axis
        
        timeBodyAccelerationJerkMeanY			
                Mean of the Body Jerk Time Acceleration in Y axis
        
        timeBodyAccelerationJerkMeanZ			
                Mean of the Body Jerk Time Acceleration in Z axis
        
        timeBodyAccelerationJerkStandardDeviationX			
                Standard Deviation of the Body Jerk Time Acceleration in X axis
        
        timeBodyAccelerationJerkStandardDeviationY			
                Standard Deviation of the Body Jerk Time Acceleration in Y axis
        
        timeBodyAccelerationJerkStandardDeviationZ			
                Standard Deviation of the Body Jerk Time Acceleration in Z axis
        
        timeBodyGyroMeanX			
                Mean of the Body Gyro Time in X axis
        
        timeBodyGyroMeanY			
                Mean of the Body Gyro Time in Y axis
        
        timeBodyGyroMeanZ			
                Mean of the Body Gyro Time in Z axis
        
        timeBodyGyroStandardDeviationX			
                Standard Deviation of the Body Gyro Time in X axis
        
        timeBodyGyroStandardDeviationY			
                Standard Deviation of the Body Gyro Time in Y axis
        
        timeBodyGyroStandardDeviationZ			
                Standard Deviation of the Body Gyro Time in Z axis
        
        timeBodyGyroJerkMeanX			
                Mean of the Body Gyro Jerk  Time in X axis
        
        timeBodyGyroJerkMeanY				
                Mean of the Body Gyro Jerk  Time in Y axis
        
        timeBodyGyroJerkMeanZ			
                Mean of the Body Gyro Jerk  Time in Z axis
        
        timeBodyGyroJerkStandardDeviationX			
                Standard Deviation of the Body Gyro Jerk  Time in Z axis
        
        timeBodyGyroJerkStandardDeviationY			
                Standard Deviation of the Body Gyro Jerk  Time in Z axis
        
        timeBodyGyroJerkStandardDeviationZ			
                Standard Deviation of the Body Gyro Jerk  Time in Z axis
        
        timeBodyAccelerationMagnitudeMean			
                Mean of the Body Acceleration Magnitude Time
        
        timeBodyAccelerationMagnitudeStandardDeviation	
                Standard Deviation of the Body Acceleration Magnitude Time
        
        timeGravityAccelerationMagnitudeMean			
                Mean of the Gravity Acceleration Magnitude Time
        
        timeGravityAccelerationMagnitudeStandardDeviation	
                Standard Deviation of the Gravity Acceleration Magnitude Time
        
        timeBodyAccelerationJerkMagnitudeMean			
                Mean of the Body Acceleration Jerk Magnitude Time
        
        timeBodyAccelerationJerkMagnitudeStandardDeviation	
                Standard Deviation of the Body Acceleration Jerk Magnitude Time
        
        timeBodyGyroMagnitudeMean			
                Mean of the Body Gyro Magnitude Time
        
        timeBodyGyroMagnitudeStandardDeviation		
                Standard Deviation of the Body Gyro Magnitude Time
        
        timeBodyGyroJerkMagnitudeMean			
                Mean of the Body Gyro Jerk Magnitude Time
        
        timeBodyGyroJerkMagnitudeStandardDeviation	
                Standard Deviation of the Body Gyro Jerk Magnitude Time
        
        frequencyBodyAccelerationMeanX			
                Mean of the Body Frequency Acceleration in X axis
        
        frequencyBodyAccelerationMeanY			
                Mean of the Body Frequency Acceleration in Y axis
        
        frequencyBodyAccelerationMeanZ			
                Mean of the Body Frequency Acceleration in Z axis
        
        frequencyBodyAccelerationStandardDeviationX	
                Standard Deviation of the Body Frequency Acceleration in X axis
        
        frequencyBodyAccelerationStandardDeviationY		
                Standard Deviation of the Body Frequency Acceleration in Y axis
        
        frequencyBodyAccelerationStandardDeviationZ	
                Standard Deviation of the Body Frequency Acceleration in Z axis
        
        frequencyBodyAccelerationJerkMeanX			
                Mean of the Body Jerk Frequency Acceleration in X axis
        
        frequencyBodyAccelerationJerkMeanY			
                Mean of the Body Jerk Frequency Acceleration in Y axis
        
        frequencyBodyAccelerationJerkMeanZ			
                Mean of the Body Jerk Frequency Acceleration in Z axis
        
        frequencyBodyAccelerationJerkStandardDeviationX		
                Standard Deviation of the Body Jerk Frequency Acceleration in X axis
        
        frequencyBodyAccelerationJerkStandardDeviationY		
                Standard Deviation of the Body Jerk Frequency Acceleration in Y axis
        
        frequencyBodyAccelerationJerkStandardDeviationZ		
                Standard Deviation of the Body Jerk Frequency Acceleration in Z axis
        
        frequencyBodyGyroMeanX			
                Mean of the Body Gyro Frequency in X axis
        
        frequencyBodyGyroMeanY			
                Mean of the Body Gyro Frequency in Y axis
        
        frequencyBodyGyroMeanZ			
                Mean of the Body Gyro Frequency in Z axis
        
        frequencyBodyGyroStandardDeviationX			
                Standard Deviation of the Body Gyro Frequency in X axis
        
        frequencyBodyGyroStandardDeviationY			
                Standard Deviation of the Body Gyro Frequency in Y axis
        
        frequencyBodyGyroStandardDeviationZ			
                Standard Deviation of the Body Gyro Frequency in Z axis
        
        frequencyBodyAccelerationMagnitudeMean			
                Mean of the Body Acceleration Magnitude Frequency
        
        frequencyBodyAccelerationMagnitudeStandardDeviation	
                Standard Deviation of the Body Acceleration Magnitude Frequency
        
        frequencyBodyAccelerationJerkMagnitudeMean		
                Mean of the Body Acceleration Jerk Magnitude Frequency
        
        frequencyBodyAccelerationJerkMagnitudeStandardDeviation	
                Standard Deviation of the Body Acceleration Jerk Magnitude Frequency
        
        frequencyBodyGyroMagnitudeMean			
                Mean of the Body Gyro Magnitude Frequency
        
        frequencyBodyGyroMagnitudeStandardDeviation	
                Standard Deviation of the Body Gyro Magnitude Frequency
        
        frequencyBodyGyroJerkMagnitudeMean		
                Mean of the Body Gyro Jerk Magnitude Frequency
        
        frequencyBodyGyroJerkMagnitudeStandardDeviation		
                Standard Deviation of the Body Gyro Jerk Magnitude Frequency
        


