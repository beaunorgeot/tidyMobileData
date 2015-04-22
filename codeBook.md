#Code Book

The folowing describes the data from the UCI Human Activity Recognition Using Smartphones Data Set() or UC HAR). Additionally,the processing steps required to recreate both the long-format and wide-format tidy data sets that I created.

##Overview

One of the most exciting areas in all of data science right now is wearable computing.

The data represent data collected from the accelerometers from the Samsung Galaxy S smartphone. 

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist.

The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 



##Explanation of data in each file

2. features_info.txt:General names and descritptions of the types of measurements that were recorded. 

1. features.txt: A list with the names of the 561 types of measurements('features')

2. activity_labels.txt: Names and IDs for each of the 6 actions that the participants in the study performed.

3. X_train.txt: The recorded measurements for each of the actions of each of the subjects in the in the subset of volunteers called the 'training' group

5. y_train.txt: The reference ID numbers of the actions (walking,sitting,etc)for each of the observations in X_train.txt. Basically ID '1' maps to action 'walking'.

3. subject_train.txt: The ID numbers of the subjects for each of the observations in X_train.txt. This is a simple annoymization. Basically 'Joe Blow' maps to SubjNum1; 'John Doe' maps to SubjNum2;etc.

6. X_test.txt: Same as X_train, but for subjects in the in the subset of volunteers called the 'test' group


8. y_test.txt: Same as y_train, but for subjects in the in the subset of volunteers called the 'test' group

7. subject_test.txt: Same as subject_train, but for subjects in the in the subset of volunteers called the 'test' group


More information about the files is available in README.txt. 

###Units & data info
All initial acceleration measurements were measured using standard gravity units 'g'.These time domain signals (prefix 't' to denote time) were captured at a constant rate of 50 Hz. A Fourier Transform (FFT) was applied to some of these signals producing f-labeled equivalents.(Note the 'f' to indicate frequency domain signals). 

###File used for Analysis
Analysis was performed using only the files above; raw signal data was not used. Accordingly, the data files in the "Inertial Signals" folders within both test/train were ignored.

##Processing steps
The final goal is a table with a column for the subjects(identified by number), activities(by name),
a column for the mean & std for each measurement of each action (eg tBodyAcc,). 

Data files were read into data frames. Test and Train datasets were row-bound as they represented subsets of the same experiment. Subjects, Actions, and Measurements were column-bound to create single columns for each. Variable column names were added. 

All feature/measurement columns that did not contain the exact string "mean()" or "std()"were removed.  This left 66 feature columns, plus the subjNum and action columns.
The action column was converted from a integer to a factor, using labels describing the actions.

Two tidy data sets, one in long-data format ('longTidy') & one in wide-data format ('wideTidy') were created containing the mean of each measurement type for each subject and each action. The tidy data sets were output to .csv files.