# tidyMobileData
Take disorganized data from multiple files and combine into single data-set in both long and wide data formats.

Data sets came from UC Irvine's  "Human Activity Recognition Using Smartphones" experiments. See their home page: [Smart Phone Experiment](http://archive.ics.uci.edu/ml/datasets/Human+Activity+Recognition+Using+Smartphones).  Data sets were combined into a single data frame containing average values for each of the measurements. 

Replication of results simply requires the original data set and a single script that I have created [r_analysis.R](https://github.com/beaunorgeot/tidyMobileData/blob/master/run_analysis.R).

##Steps to perform tidying
**Setup**
Get the data. Put the data in the same directory as the script to run the tidying and analysis (r_analysis.R). 

1. Get data here: [Zip](https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip)
2. Unzip the data file
3. Create a new directory and move the following data files to it:

	- features.txt
	- subject_train.txt
	- subject_test.txt
	- X_train.txt
	- X_test.txt
	- y_train.txt
	- y_test.txt
4. Move run_analysis.R to the same directory as the data files.
5. Open R and set your working directory for R to the directory that you created.

	setwd(""pathToYouDirectory")
	
6. Run run_analysis.R

**The output of the R script are two tidy data sets** 

	- longTidy.csv
	- wideTidy.csv

There are many times when long data is better for analysis, and some times were wide data is better. In gerenal, long is more useful, but wide is more intuitive for humans to look at. See this article for some more info: [Long vs Wide Data](http://seananderson.ca/2013/10/19/reshape.html)

Since we haven't decided what kind of analysis we'll be using our data for downstream, it's nice to have the data in both formats.


You can read more about the data and the analysis in the code book.


