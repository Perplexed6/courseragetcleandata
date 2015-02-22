This codebook describes the steps I have undertaken to achieve the target. Unfortunately I have not been able to complete the assignment and I am outlying the steps which have been successful.


STEP1: cREATING A DIRECTORY

if (!file.exists("./coursedata")){
dir.create("./coursedata")
}
#Above creates a directory called coursedata.



STEP2: DOWNLOADING AND UNZIPPING THE FILE IN THE DIRECTORY

fileUrl <- "http://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"
download.file(fileUrl, destfile = "./coursedata/UCI HAR Dataset.zip", method="internal")
#Above downloads the zipped file into the folder created.

unzip("./coursedata/UCI HAR Dataset.zip", exdir = "./coursedata")
#Above unzips the zipped folder



STEP3:UNDERSTANDING THE DIFFERENT FILES AND READING THE FILES ACCORDINGLY. ADDING COLUMN NAMES AND ROW NAMES APPROPRIATELY FOR TESTDATA.

Xtest <- read.table("test/X_test.txt")
#Above reads the data of Xtest

colnames <- read.table("features.txt")
#Above reads the data of features of Xtest


names(Xtest) <-colnames[ ,2]
#Above inserts column names for Xtest data using data from features

attr(Xtest, "row.names") <- c("WALKING", "WALKING-UPSTAIRS", "WALKING DOWNSTAIRS", "SITTING", "STANDING", "LAYING")
#Above adds row names to Xtest data

subjectXtest <- read.table("test/subject_test.txt")
#Above reads subject test data (ie participant number)



STEP4:TRYING TO ADD PARTICIPANT NUMBER TO TESTDATA BUT UNABLE TO DO SO.

cbind(subjectXtest,Xtest)
#This was aimed in matching participant number to Xtest data but does not work!
I have not been able to carry on further!



STEP5:READING THE TRAIN DATA, ADDING COLUMN NAMES AND ROW NAMES ACCORDINGLY TO TRAINDATA

Xtrain <- read.table("train/X_train.txt")
#Above reads the data of Xtrain

colnames <- read.table("features.txt")
#Above reads the data of features of Xtrain

names(Xtrain) <-colnames[ ,2]
#Above inserts column names for Xtrain data using data from features

attr(Xtrain, "row.names") <- c("WALKING", "WALKING-UPSTAIRS", "WALKING DOWNSTAIRS", "SITTING", "STANDING", "LAYING")
#Above adds row names to Xtrain data


STEP6: READING SUBJECT (PARTICIPANTS NUMBER) BUT UNABLE TO BIND THIS WITH TRAINDATA

subjectXtrain <- read.table("train/subject_train.txt")
#Above reads subject train data (ie participant number)

cbind(subjectXtrain,Xtrain)
#This was aimed in matching participant number to Xtrain data but does not work!
I have not been able to carry on further!

