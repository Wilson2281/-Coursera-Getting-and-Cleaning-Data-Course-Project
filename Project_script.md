**Download the data file from the web site**

```
rawDataDir <- "./rawData"
rawDataUrl <- "https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip"
rawDataFilename <- "rawData.zip"
rawDataDFn <- paste(rawDataDir, "/", "rawData.zip", sep = "")
dataDir <- "./rawData/data"

if (!file.exists(rawDataDir)) {
      dir.create(rawDataDir)
      download.file(url = rawDataUrl, destfile = rawDataDFn)
}
if (!file.exists(dataDir)) {
            unzip(zipfile = rawDataDFn, exdir = dataDir)
}
```
**Create the activity, subject and feature**

*activity*
```
activity_train <-read.table(paste(sep="",rawDataDir,"./data/UCI HAR Dataset/train/Y_train.txt"))
activity_test <-read.table(paste(sep="",rawDataDir,"./data/UCI HAR Dataset/test/Y_test.txt"))
```
*subject*
```
subject_train <-read.table(paste(sep="",rawDataDir,"./data/UCI HAR Dataset/train/subject_train.txt"))
subject_test <-read.table(paste(sep="",rawDataDir,"./data/UCI HAR Dataset/test/subject_test.txt"))
```
*feature*
```
feature_train <- read.table(paste(sep="",rawDataDir,"./data/UCI HAR Dataset/train/X_train.txt"))
feature_test <- read.table(paste(sep="",rawDataDir,"./data/UCI HAR Dataset/test/X_test.txt"))
```
**Create data**
```
data_activity <- rbind(activity_train,activity_test)
data_subject <- rbind(subject_train,subject_test)
data_feature <- rbind(feature_train,feature_test)

```
