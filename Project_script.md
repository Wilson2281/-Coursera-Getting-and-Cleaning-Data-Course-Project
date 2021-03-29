* Get the raw data from the Web

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
features <- read.table("./rawData/data/UCI HAR Dataset/features.txt", col.names = c("n","functions"))
/ create the file train
x_train <-read.table(paste(sep="",rawDataDir,"/data/UCI HAR Dataset/train/X_train.txt"))
y_train <- read.table(paste(sep = "",rawDataDir,"./data/UCI HAR Dataset/train/Y_train.txt"))
