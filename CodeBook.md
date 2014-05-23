## CodeBook: Data Science Specialization course series: Getting and Cleaning Data Course Project

============================================================================================
### Original raw data sets: Human Activity Recognition Using Smartphones Dataset Version 1.0:

Jorge L. Reyes-Ortiz, Davide Anguita, Alessandro Ghio, Luca Oneto.
Smartlab - Non Linear Complex Systems Laboratory
DITEN - Università degli Studi di Genova.
Via Opera Pia 11A, I-16145, Genoa, Italy.
activityrecognition@smartlab.ws

A full description is available at the site www.smartlab.ws where the data was obtained: 
http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones 

-------------------------------------------------------------------------------------------------
#### List of the original data sets inside the downloaded zip file:

   - 'README.txt': describes about the general information and background related to the data sets within the zip file.

   - 'features_info.txt': Shows information about the variables used on the feature vector.

   - 'features.txt': List of all features.

   - 'activity_labels.txt': Links the class labels with their activity name.

   - 'train/X_train.txt': Training set.

   - 'train/y_train.txt': Training labels.

   - 'test/X_test.txt': Test set.

   - 'test/y_test.txt': Test labels.
   
   - 'train/subject_train.txt':   Each row identifies the subject who performed the activity for each window sample.
      Its range is from 1 to 30. (for training set)
   
   - 'test/subject_test.txt':  Each row identifies the subject who performed the activity for each window sample.
      Its range is from 1 to 30. (for test set)
      
     The following data sets are not been used in the current project. 

   - 'train/Inertial Signals/total_acc_x_train.txt'; 'train/Inertial Signals/body_acc_x_train.txt';
     'train/Inertial Signals/body_gyro_x_train.txt'. More information related to these three data sets can be
     found in 'README.txt', 'feature_info.txt' and 'feature.txt' and the original website.
    
-------------------------------------------------------------------------------------------------------------
#### Background: feature selection, feature vector variables and unit

The following information is the hightlights/summary of the 'feature_info.txt' and 'feature.txt'

>The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years.
>Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING)
>wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope,
>they captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz.
>The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly
>partitioned into two sets, where 70% of the volunteers was selected for generating the training data
>and 30% the test data.
>
>The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ 
>and tGyro-XYZ. These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. 
>Then they were filtered using a median filter and a 3rd order low pass Butterworth filter with a corner frequency
>of 20 Hz to remove noise. Similarly, the acceleration signal was then separated into body and gravity acceleration
>signals (tBodyAcc-XYZ and tGravityAcc-XYZ) using another low pass Butterworth filter with a corner frequency of 0.3 Hz. 
>
>Subsequently, the body linear acceleration and angular velocity were derived in time to obtain Jerk signals
>(tBodyAccJerk-XYZ and tBodyGyroJerk-XYZ). Also the magnitude of these three-dimensional signals were calculated 
>using the Euclidean norm (tBodyAccMag, tGravityAccMag, tBodyAccJerkMag, tBodyGyroMag, tBodyGyroJerkMag). 
>
>Finally a Fast Fourier Transform (FFT) was applied to some of these signals producing fBodyAcc-XYZ,
>fBodyAccJerk-XYZ, fBodyGyro-XYZ, fBodyAccJerkMag, fBodyGyroMag, fBodyGyroJerkMag. 
>(Note the 'f' to indicate frequency domain signals). 
>
>These signals were used to estimate variables of the feature vector for each pattern:  
>'-XYZ' is used to denote 3-axial signals in the X, Y and Z directions.
>
>tBodyAcc-XYZ
>tGravityAcc-XYZ
>tBodyAccJerk-XYZ
>tBodyGyro-XYZ
>tBodyGyroJerk-XYZ
>tBodyAccMag
>tGravityAccMag
>tBodyAccJerkMag
>tBodyGyroMag
>tBodyGyroJerkMag
>fBodyAcc-XYZ
>fBodyAccJerk-XYZ
>fBodyGyro-XYZ
>fBodyAccMag
>fBodyAccJerkMag
>fBodyGyroMag
>fBodyGyroJerkMag
>
>Additional vectors obtained by averaging the signals in a signal window sample. 
>These are used on the angle() variable:
>
>gravityMean
>tBodyAccMean
>tBodyAccJerkMean
>tBodyGyroMean
>tBodyGyroJerkMean
>
>The set of variables that were estimated from these signals are: 
>
>mean(): Mean value
>std(): Standard deviation
>mad(): Median absolute deviation 
>max(): Largest value in array
>min(): Smallest value in array
>sma(): Signal magnitude area
>energy(): Energy measure. Sum of the squares divided by the number of values. 
>iqr(): Interquartile range 
>entropy(): Signal entropy
>arCoeff(): Autorregresion coefficients with Burg order equal to 4
>correlation(): correlation coefficient between two signals
>maxInds(): index of the frequency component with largest magnitude
>meanFreq(): Weighted average of the frequency components to obtain a mean frequency
>skewness(): skewness of the frequency domain signal 
>kurtosis(): kurtosis of the frequency domain signal 
>bandsEnergy(): Energy of a frequency interval within the 64 bins of the FFT of each window.
>angle(): Angle between to vectors.

##### Unit:

  Features are normalized and bounded within [-1,1]. In other words, they are unitless.

------------------------------------------------------------------------------------------------
#### Original data sets: selected input data variables

Based on the requirement of the course project, I only selected those input variables
related to the measurements on the mean and standard deviation for each measurement.
(see the section of "Instruction and Requirements" in README.md)

They are the following:

tBodyAcc-mean()-X           tBodyAcc-mean()-Y           tBodyAcc-mean()-Z           tBodyAcc-std()-X           
tBodyAcc-std()-Y            tBodyAcc-std()-Z            tGravityAcc-mean()-X        tGravityAcc-mean()-Y       
tGravityAcc-mean()-Z        tGravityAcc-std()-X         tGravityAcc-std()-Y         tGravityAcc-std()-Z        
tBodyAccJerk-mean()-X       tBodyAccJerk-mean()-Y       tBodyAccJerk-mean()-Z       tBodyAccJerk-std()-X       
tBodyAccJerk-std()-Y        tBodyAccJerk-std()-Z        tBodyGyro-mean()-X          tBodyGyro-mean()-Y         
tBodyGyro-mean()-Z          tBodyGyro-std()-X           tBodyGyro-std()-Y           tBodyGyro-std()-Z          
tBodyGyroJerk-mean()-X      tBodyGyroJerk-mean()-Y      tBodyGyroJerk-mean()-Z      tBodyGyroJerk-std()-X      
tBodyGyroJerk-std()-Y       tBodyGyroJerk-std()-Z       tBodyAccMag-mean()          tBodyAccMag-std()          
tGravityAccMag-mean()       tGravityAccMag-std()        tBodyAccJerkMag-mean()      tBodyAccJerkMag-std()      
tBodyGyroMag-mean()         tBodyGyroMag-std()          tBodyGyroJerkMag-mean()     tBodyGyroJerkMag-std()     
fBodyAcc-mean()-X           fBodyAcc-mean()-Y           fBodyAcc-mean()-Z           fBodyAcc-std()-X           
fBodyAcc-std()-Y            fBodyAcc-std()-Z            fBodyAccJerk-mean()-X       fBodyAccJerk-mean()-Y      
fBodyAccJerk-mean()-Z       fBodyAccJerk-std()-X        fBodyAccJerk-std()-Y        fBodyAccJerk-std()-Z       
fBodyGyro-mean()-X          fBodyGyro-mean()-Y          fBodyGyro-mean()-Z          fBodyGyro-std()-X          
fBodyGyro-std()-Y           fBodyGyro-std()-Z           fBodyAccMag-mean()          fBodyAccMag-std()          
fBodyBodyAccJerkMag-mean()  fBodyBodyAccJerkMag-std()   fBodyBodyGyroMag-mean()     fBodyBodyGyroMag-std()     
fBodyBodyGyroJerkMag-mean() fBodyBodyGyroJerkMag-std() 

The complete list of variables of each feature vector is available in 'features.txt'


---------------------------------------------------------------------------------------------------------
---------------------------------------------------------------------------------------------------------
### Tidy data sets

#### Tiday data set: new variable names

* New variable names were from selected input data variables (see previous section)
* The names were modified mainly to avoid any unnecessary errors in R when this tidy data set 
  is used as an input data during any data analysis in the future. The methods and reasons are 
  based on the instruction from the course video-sildes (Week 4: Editing text variables).
  
  + The following were modified:
    -- lower cases; removed bad characters "()"; replaced "-" to "."

* The activity names are also be modified such as: lower cases; removed "_"
  new activity names: laying, sitting, standing, walking, walkingdownstairs and walkingupstairs.
  
-------------------------------------------------------------------------------------------------------------
#### Tidy data set: data structure

* There are 180 observations of 68 variables.

> str(tidydfrm) ## using 'str' function in R
'data.frame':	180 obs. of  68 variables:
 $ activity                 : chr  "laying" "laying" "laying" "laying" ...
 $ subject                  : int  1 2 3 4 5 6 7 8 9 10 ...
 $ tbodyacc.mean.x          : num  0.222 0.281 0.276 0.264 0.278 ...
 $ tbodyacc.mean.y          : num  -0.0405 -0.0182 -0.019 -0.015 -0.0183 ...
 $ tbodyacc.mean.z          : num  -0.113 -0.107 -0.101 -0.111 -0.108 ...
 $ tbodyacc.std.x           : num  -0.928 -0.974 -0.983 -0.954 -0.966 ...
 $ tbodyacc.std.y           : num  -0.837 -0.98 -0.962 -0.942 -0.969 ...
 $ tbodyacc.std.z           : num  -0.826 -0.984 -0.964 -0.963 -0.969 ...
 $ tgravityacc.mean.x       : num  -0.249 -0.51 -0.242 -0.421 -0.483 ...
 $ tgravityacc.mean.y       : num  0.706 0.753 0.837 0.915 0.955 ...
 $ tgravityacc.mean.z       : num  0.446 0.647 0.489 0.342 0.264 ...
 $ tgravityacc.std.x        : num  -0.897 -0.959 -0.983 -0.921 -0.946 ...
 $ tgravityacc.std.y        : num  -0.908 -0.988 -0.981 -0.97 -0.986 ...
 $ tgravityacc.std.z        : num  -0.852 -0.984 -0.965 -0.976 -0.977 ...
 $ tbodyaccjerk.mean.x      : num  0.0811 0.0826 0.077 0.0934 0.0848 ...
 $ tbodyaccjerk.mean.y      : num  0.00384 0.01225 0.0138 0.00693 0.00747 ...
 $ tbodyaccjerk.mean.z      : num  0.01083 -0.0018 -0.00436 -0.00641 -0.00304 ...
 $ tbodyaccjerk.std.x       : num  -0.958 -0.986 -0.981 -0.978 -0.983 ...
 $ tbodyaccjerk.std.y       : num  -0.924 -0.983 -0.969 -0.942 -0.965 ...
 $ tbodyaccjerk.std.z       : num  -0.955 -0.988 -0.982 -0.979 -0.985 ...
 $ tbodygyro.mean.x         : num  -0.01655 -0.01848 -0.02082 -0.00923 -0.02189 ...
 $ tbodygyro.mean.y         : num  -0.0645 -0.1118 -0.0719 -0.093 -0.0799 ...
 $ tbodygyro.mean.z         : num  0.149 0.145 0.138 0.17 0.16 ...
 $ tbodygyro.std.x          : num  -0.874 -0.988 -0.975 -0.973 -0.979 ...
 $ tbodygyro.std.y          : num  -0.951 -0.982 -0.977 -0.961 -0.977 ...
 $ tbodygyro.std.z          : num  -0.908 -0.96 -0.964 -0.962 -0.961 ...
 $ tbodygyrojerk.mean.x     : num  -0.107 -0.102 -0.1 -0.105 -0.102 ...
 $ tbodygyrojerk.mean.y     : num  -0.0415 -0.0359 -0.039 -0.0381 -0.0404 ...
 $ tbodygyrojerk.mean.z     : num  -0.0741 -0.0702 -0.0687 -0.0712 -0.0708 ...
 $ tbodygyrojerk.std.x      : num  -0.919 -0.993 -0.98 -0.975 -0.983 ...
 $ tbodygyrojerk.std.y      : num  -0.968 -0.99 -0.987 -0.987 -0.984 ...
 $ tbodygyrojerk.std.z      : num  -0.958 -0.988 -0.983 -0.984 -0.99 ...
 $ tbodyaccmag.mean         : num  -0.842 -0.977 -0.973 -0.955 -0.967 ...
 $ tbodyaccmag.std          : num  -0.795 -0.973 -0.964 -0.931 -0.959 ...
 $ tgravityaccmag.mean      : num  -0.842 -0.977 -0.973 -0.955 -0.967 ...
 $ tgravityaccmag.std       : num  -0.795 -0.973 -0.964 -0.931 -0.959 ...
 $ tbodyaccjerkmag.mean     : num  -0.954 -0.988 -0.979 -0.97 -0.98 ...
 $ tbodyaccjerkmag.std      : num  -0.928 -0.986 -0.976 -0.961 -0.977 ...
 $ tbodygyromag.mean        : num  -0.875 -0.95 -0.952 -0.93 -0.947 ...
 $ tbodygyromag.std         : num  -0.819 -0.961 -0.954 -0.947 -0.958 ...
 $ tbodygyrojerkmag.mean    : num  -0.963 -0.992 -0.987 -0.985 -0.986 ...
 $ tbodygyrojerkmag.std     : num  -0.936 -0.99 -0.983 -0.983 -0.984 ...
 $ fbodyacc.mean.x          : num  -0.939 -0.977 -0.981 -0.959 -0.969 ...
 $ fbodyacc.mean.y          : num  -0.867 -0.98 -0.961 -0.939 -0.965 ...
 $ fbodyacc.mean.z          : num  -0.883 -0.984 -0.968 -0.968 -0.977 ...
 $ fbodyacc.std.x           : num  -0.924 -0.973 -0.984 -0.952 -0.965 ...
 $ fbodyacc.std.y           : num  -0.834 -0.981 -0.964 -0.946 -0.973 ...
 $ fbodyacc.std.z           : num  -0.813 -0.985 -0.963 -0.962 -0.966 ...
 $ fbodyaccjerk.mean.x      : num  -0.957 -0.986 -0.981 -0.979 -0.983 ...
 $ fbodyaccjerk.mean.y      : num  -0.922 -0.983 -0.969 -0.944 -0.965 ...
 $ fbodyaccjerk.mean.z      : num  -0.948 -0.986 -0.979 -0.975 -0.983 ...
 $ fbodyaccjerk.std.x       : num  -0.964 -0.987 -0.983 -0.98 -0.986 ...
 $ fbodyaccjerk.std.y       : num  -0.932 -0.985 -0.971 -0.944 -0.966 ...
 $ fbodyaccjerk.std.z       : num  -0.961 -0.989 -0.984 -0.98 -0.986 ...
 $ fbodygyro.mean.x         : num  -0.85 -0.986 -0.97 -0.967 -0.976 ...
 $ fbodygyro.mean.y         : num  -0.952 -0.983 -0.978 -0.972 -0.978 ...
 $ fbodygyro.mean.z         : num  -0.909 -0.963 -0.962 -0.961 -0.963 ...
 $ fbodygyro.std.x          : num  -0.882 -0.989 -0.976 -0.975 -0.981 ...
 $ fbodygyro.std.y          : num  -0.951 -0.982 -0.977 -0.956 -0.977 ...
 $ fbodygyro.std.z          : num  -0.917 -0.963 -0.967 -0.966 -0.963 ...
 $ fbodyaccmag.mean         : num  -0.862 -0.975 -0.966 -0.939 -0.962 ...
 $ fbodyaccmag.std          : num  -0.798 -0.975 -0.968 -0.937 -0.963 ...
 $ fbodybodyaccjerkmag.mean : num  -0.933 -0.985 -0.976 -0.962 -0.977 ...
 $ fbodybodyaccjerkmag.std  : num  -0.922 -0.985 -0.975 -0.958 -0.976 ...
 $ fbodybodygyromag.mean    : num  -0.862 -0.972 -0.965 -0.962 -0.968 ...
 $ fbodybodygyromag.std     : num  -0.824 -0.961 -0.955 -0.947 -0.959 ...
 $ fbodybodygyrojerkmag.mean: num  -0.942 -0.99 -0.984 -0.984 -0.985 ...
 $ fbodybodygyrojerkmag.std : num  -0.933 -0.989 -0.983 -0.983 -0.983 ...
 
 ---------------------------------------------------------------------------------------------
 ---------------------------------------------------------------------------------------------
 ### Study Design Summary
 
 * How to collect the data
 
   This is a course project. The location of this original raw data set for this course project 
   is provided via the link (see the section of Data Resources in README.md)
   https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
   
   
 * The purposes/goal of this study design
 
   The first priority of this study design is fulfiled  all the purposes and requirements
   of this project (see the sections of "Purpose and Goal" and "Instructions and Requirements")
   in README.md.
 
---------------------------------------------------------------------------------------
### Instruction list to reproduce the tidy data set

This section is also in the section of "My work to the project" in README.md

#### Obtain the raw data sets and put them in the working directory (via Rstudio)

    * The following steps were performed in a PC running the operation system Window 8.1.
      The data cleaning processes were performed in Rstudio with R version 3.1.0
     
      + download the raw data from the following website:
      https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip
      
      + using the following R command to download the data:
      >setInternet2(TRUE)   
      >url_proj <- "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"
      >download.file(urlproj, destfile="Dataset.zip", mode="wb")
      
      + unzip the raw data sets
      
        >unzip("Dataset.zip")
      
      + put the raw data sets in the selected working directory called "datacleaningproject"
        that is same name as in a repo in my Github account. 
        (In other words, my working directory: "C:/Users/SJ/datacleaningproject")
        
        > getwd()
        
        [1] "C:/Users/SJ/datacleaningproject"
        
#### Create a tidy data via a R script called run_analysis.R
      
    * Preparation:  data sets and script
         + The data sets and run_analysis.R must be in same the working directory.
           (It is based on one of the requirements this project: The code should have 
            a file run_analysis.R in the main directory that can be run as long as the Samsung
            data is in your working directory. 
            (see "Instructions and Requirements" section in README.md)
      
         + The input raw data for the run_analys.R are:
        
            ./train/X_train.txt, ./train/y_train.txt, subject_train.txt;
            ./test/X_test.txt, ./test/y_test.txt,  subjecct_test.txt;
            ./activity_labels.txt, ./features.txt
        
         + The output tidy data created from run_analysis.R are:
            ./tidy_average_data.txt (180 rows)
            ./combinedcleaningdata.txt (optional)
        
    * How the script run_analysis.R via Rstudio
         + Run the script via source("run_analysis.R")
       
         + There are 5 main steps in run_analysis.R to process the raw data sets and create the tidy data set.
         
           Step-1: Merges the training and the test data sets to create one data set (such as):
              Load and read the input raw sets; merge three pairs data set (e.g.: X_train.txt, X_test.txt;
              y_train.txt, y_test.txt; subject_train.txt, subject_text.txt) into three single data set
              via "rbind" function.
            
           Setp-2: Extracts only the measurements on the mean and standard deviation for each measurement.
              This step is mainly done by the "grep" function by providing the key search patterns
              "-mean\\(\\)|-std\\(\\)".
            
              ++ column names from the data sets were changed into lower-case to avoid any uncessary typos
               (based on the intruction from the "Week4 slide-notes: Editing Text Variables" from 
               Coursera course Getting and Cleaning Data); characters "()" were replaced "" and
               characters "-" was replaced to "." via "gsub" function.
               
           Step-3: Uses descriptive activity names to name the activities in the data set.
              This step is mainly to produce a one-column data frame called "joinlabel" containing
              descriptive activity names.
            
           Step-4: Appropriately labels the data set with descriptive activity names.
              The step is mainly to combine three joined data frames into one data frame called
              "cleandata". This is the first cleaned data frame toward to the final tidy data set.
              An (optional/temporary) output file is created called "combinedcleandata.txt" just in case
              for an emergency.
            
           Step-5: Creates a second, independent tidy data set with the average of each variable
              for each activity and each subject.
              
              + It is necessary to install and to load the package "reshape2" before to perform
              any processes.
              
              + The final tidy data frame called "tidydfrm" via "melt" function and then "dcast" function.
            
              + Finally, a file called "tidy_average_data.txt" was created via "write.table" function.
                This is the final output tidy processed data.
              
              + The detailed description of "tidy_average_data.txt" and the given raw data set
                are in the sections of "Tidy data set" and "Original raw data sets" respectively.

-------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------
#### R code: run_analysis.R



=============================================================================================================







