###Getting and cleaning data codebook

# load plyr package
library(plyr)

# Download dataset and unzip data
if(!file.exists("./data")){dir.create("./data")}
download.file("https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip",destfile="./data/Dataset.zip")
unzip(zipfile="./data/Dataset.zip",exdir="./data")

# 1. Merges the training and the test sets to create one data set

# Read files with read.table()
# Train tables
subjectTrain <- read.table("./data/UCI HAR Dataset/train/subject_train.txt")
xTrain <- read.table("./data/UCI HAR Dataset/train/X_train.txt")
yTrain <- read.table("./data/UCI HAR Dataset/train/y_train.txt")

# Test tables
subjectTest <- read.table("./data/UCI HAR Dataset/test/subject_test.txt")
xTest <- read.table("./data/UCI HAR Dataset/test/X_test.txt")
yTest <- read.table("./data/UCI HAR Dataset/test/y_test.txt")

# Features
features <- read.table('./data/UCI HAR Dataset/features.txt')

# Activities labels
activityLabels = read.table('./data/UCI HAR Dataset/activity_labels.txt')

# Assign column names - part of "4"
colnames(xTrain) <- features[,2] 
colnames(yTrain) <-"activityId"
colnames(subjectTrain) <- "subjectId"

colnames(xTest) <- features[,2] 
colnames(yTest) <- "activityId"
colnames(subjectTest) <- "subjectId"

colnames(activityLabels) <- c('activityId','activityType')

# Merge all data in one set
mergedTrain <- cbind(yTrain, subjectTrain, xTrain)
mergedTest <- cbind(yTest, subjectTest, xTest)
mergedTrainAndTest <- rbind(mergedTrain, mergedTest)

# 2. Extracts only the measurements on the mean and standard deviation for each measurement

# Reading column names
colNames <- colnames(mergedTrainAndTest)

# Create vector for defining ID, mean and standard deviation
# Also part of "4"
meanAndStandard <- (grepl("activityId" , colNames) | 
                      grepl("subjectId" , colNames) | 
                      grepl("mean.." , colNames) | 
                      grepl("std.." , colNames) 
)

# Subset from mergedTrainAndTest
meanAndStandardSubset <- mergedTrainAndTest[ , meanAndStandard == TRUE]

# 3. Uses descriptive activity names to name the activities in the data set
# 4. Appropriately labels the data set with descriptive variable names.
mergedActivityNames <- merge(meanAndStandardSubset, activityLabels,
                              by='activityId',
                              all.x=TRUE)


# 5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

# Tidy data set 
tidy <- aggregate(. ~subjectId + activityId, mergedActivityNames, mean)
tidy <- tidy[order(tidy$subjectId, tidy$activityId),]

# Write tidy data set in txt file
write.table(tidy, "tidy.txt", row.name=FALSE)

library(knitr)
knit2html("run_analysis.R","codebook.Rmd")
