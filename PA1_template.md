# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data
setwd("/Users/tgdwaana/sync/git/RepData_PeerAssessment1_github")

fileName <- "activity.zip"
fileNameCSV <- gsub("zip", "csv", fileName)

unzip(fileName, fileNameCSV)
data <- read.csv(fileNameCSV, header=TRUE, sep=",", na.strings="NA")
data$date <- as.Date(da)
summary(data)

## What is mean total number of steps taken per day?

1. Calculate the total number of steps taken per day
2. Make a histogram of the total number of steps taken each day
3. Calculate and report the mean and median of the total number of steps taken per day

Get the total number of steps take per day

    totalSteps <- tapply(data$steps, data$date, FUN=sum)

Plot histogram of the total number of steps taken each day    

    hist(totalSteps, xlab="total steps per day", 
      ylab="frequency", main="histogram of total steps per day")

Calculate the mean of the median of the total number of steps taken per day

    mean(totalSteps, na.rm=TRUE)
    median(totalSeps, na.rm=TRUE)


## What is the average daily activity pattern?

1. Make a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all days (y-axis)
2. Which 5-minute interval, on average across all the days in the dataset, contains the maximum number of steps?

## Imputing missing values

Note that there are a number of days/intervals where there are missing values (coded as NA). The presence of missing days may introduce bias into some calculations or summaries of the data.

1. Calculate and report the total number of missing values in the dataset (i.e. the total number of rows with NAs)
2. Devise a strategy for filling in all of the missing values in the dataset. The strategy does not need to be sophisticated. For example, you could use the mean/median for that day, or the mean for that 5-minute interval, etc.
3. Create a new dataset that is equal to the original dataset but with the missing data filled in.
4. Make a histogram of the total number of steps taken each day and Calculate and report the mean and median total number of steps taken per day. Do these values differ from the estimates from the first part of the assignment? What is the impact of imputing missing data on the estimates of the total daily number of steps?


## Are there differences in activity patterns between weekdays and weekends?

For this part the weekdays() function may be of some help here. Use the dataset with the filled-in missing values for this part.

1. Create a new factor variable in the dataset with two levels – “weekday” and “weekend” indicating whether a given date is a weekday or weekend day.
2. Make a panel plot containing a time series plot (i.e. type = "l") of the 5-minute interval (x-axis) and the average number of steps taken, averaged across all weekday days or weekend days (y-axis). See the README file in the GitHub repository to see an example of what this plot should look like using simulated data.
