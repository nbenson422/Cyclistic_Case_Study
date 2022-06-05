Cyclistic Report - Google Data Analytics Capstone - Case Study 1
================
Nolan Benson

-   [Introduction](#introduction)
-   [Ask](#ask)
    -   [Guiding questions](#guiding-questions)
    -   [Key Tasks](#key-tasks)
    -   [Deliverables](#deliverables)
-   [Prepare](#prepare)
    -   [Guiding questions](#guiding-questions-1)
    -   [Key tasks](#key-tasks-1)
    -   [Deliverables](#deliverables-1)
-   [Process](#process)
    -   [Code](#code)
        -   [Packages and Libraries](#packages-and-libraries)
        -   [Concatening](#concatening)
    -   [Data Cleaning](#data-cleaning)
        -   [Removing Duplicates](#removing-duplicates)
        -   [Parsing datetime columns](#parsing-datetime-columns)
    -   [Manipulating the data](#manipulating-the-data)
        -   [ride_length](#ride_length)
        -   [year_month](#year_month)
        -   [weekday](#weekday)
        -   [start_hour](#start_hour)
        -   [Saving results as a new .CSV](#saving-results-as-a-new-csv)
    -   [Guiding questions](#guiding-questions-2)
    -   [Key tasks](#key-tasks-2)
    -   [Deliverables](#deliverables-2)
-   [Analyze](#analyze)
    -   [Code](#code-1)
        -   [Data Distribution](#data-distribution)
        -   [Casuals vs. Members](#casuals-vs-members)
        -   [Month](#month)
        -   [Weekday](#weekday-1)
        -   [Starting hour](#starting-hour)
    -   [Guiding questions](#guiding-questions-3)
    -   [Key tasks](#key-tasks-3)
    -   [Deliverables](#deliverables-3)
-   [Share](#share)
    -   [Guiding questions](#guiding-questions-4)
    -   [Key tasks](#key-tasks-4)
    -   [Deliverables](#deliverables-4)
-   [Act](#act)
    -   [Guiding questions](#guiding-questions-5)
    -   [Key tasks](#key-tasks-5)
    -   [Deliverables](#deliverables-5)
-   [Conclusion](#conclusion)

### Introduction

This is my analysis and conclusion(s) for the Google Data Analytics
Capstone - Case Study 1. [Please follow this
link](https://www.coursera.org/learn/google-data-analytics-capstone) to
find the full document to the case study and this portion of the course.

This report will follow the steps in the data analysis process which are
Ask, Prepare, Process, Analyze, Share, and Act. This process ensures
that the report is thorough and accurate.

-   Each step will follow its own roadmap with:
    -   Code, if needed on the step.
    -   Guiding questions, with answers.
    -   Key tasks, as a checklist.
    -   Deliverables, as a checklist.

### Ask

Starting with the ask step, getting familiar with the context of the
issue at hand is important. Please review the following text from the
Cyclistic document to become familiar with the task at hand in the case
study.

> Scenario

> You are a junior data analyst working in the marketing analyst team at
> Cyclistic, a bike-share company in Chicago. The director of marketing
> believes the company’s future success depends on maximizing the number
> of annual memberships. Therefore, your team wants to understand how
> casual riders and annual members use Cyclistic bikes dierently. From
> these insights, your team will design a new marketing strategy to
> convert casual riders into annual members. But first, Cyclistic
> executives must approve your recommendations, so they must be backed
> up with compelling data insights and professional data visualizations.

> Characters and teams

> Cyclistic: A bike-share program that features more than 5,800 bicycles
> and 600 docking stations. Cyclistic sets itself apart by also oering
> reclining bikes, hand tricycles, and cargo bikes, making bike-share
> more inclusive to people with disabilities and riders who can’t use a
> standard two-wheeled bike. The majority of riders opt for traditional
> bikes; about 8% of riders use the assistive options. Cyclistic users
> are more likely to ride for leisure, but about 30% use them to commute
> to work each day.  
> Lily Moreno: The director of marketing and your manager. Moreno is
> responsible for the development of campaigns and initiatives to
> promote the bike-share program. These may include email, social media,
> and other channels.  
> Cyclistic marketing analytics team: A team of data analysts who are
> responsible for collecting, analyzing, and reporting data that helps
> guide Cyclistic marketing strategy. You joined this team six months
> ago and have been busy learning about Cyclistic’s mission and business
> goals — as well as how you, as a junior data analyst, can help
> Cyclistic achieve them.  
> Cyclistic executive team: The notoriously detail-oriented executive
> team will decide whether to approve the recommended marketing program.

##### Guiding questions

-   What is the problem you are trying to solve?

    Differentiate between annual members and casual riders, providing
    context to create the best marketing strategies to turn casual
    riders into annual members. Essentially, what is the most effective
    way to convert casual riders into membes?

-   How can your insights drive business decisions?

    These insights can provide context to the marketing team about what
    will likely be the most effective ways to advertise to and convert
    casual riders to members.

##### Key Tasks

-   Identify the business task. \[completed\]

-   Consider key stakeholders. \[completed\]

##### Deliverables

-   A clear statement of the business task. \[completed\]

    Analyze the data from Cyclistic in order to differentiate key
    statistics between members and casual riders and how advertising
    media can influence them.

### Prepare

The data for this project was provided by Google via this
[link](https://divvy-tripdata.s3.amazonaws.com/index.html).
Specifically, I utilized the last 12 months of Cyclistic ride data
available, which ranged from May 2021 to April 2022.

##### Guiding questions

-   Where is your data located?

    The data is located at the previous
    [link](https://divvy-tripdata.s3.amazonaws.com/index.html) via
    Google. It is accessible by anyone.

-   How is the data organized?

    The data is segmented by month and year starting from when the data
    was first recorded to the most recent month that data is available.
    Each month is saved on a separate .CSV file.

-   Are there issues with bias or credibility in this data? Does your
    data ROCCC?

    There should not be any issue with bias in this data considering it
    comes directly from Cyclistic’s database. In turn, this speaks to
    its credibility as well. It appears to be a set of systematically
    collected data based on rides and has an extremely large volume of
    ride data. The data also satisfies ROCCC because it’s reliable,
    original, comprehensive, current and cited.

-   How are you addressing licensing, privacy, security, and
    accessibility?

    Cyclistic owns the data and any licensing meaning there is no issue
    with licensing or our accessibility to the data. Personal and
    sensitive information regarding the riders has also been removed.

-   How did you verify the data’s integrity?

    Each of the files contained the same number and names of columns and
    each data type was consistent across similar columns.

-   How does it help you answer your question?

    The data will help to answer the question by providing insight and
    context through how members and casual riders differ on certain
    variables.

-   Are there any problems with the data?

    There are missing values in multiple rows of the data in certain
    columns most likely coming from errors inputting. More diversified
    information regarding the riders themselves would be helpful as
    well.

##### Key tasks

-   Download data and store it appropriately. \[completed\]
-   Identify how it’s organized. \[completed\]
-   Sort and filter the data. \[completed\]
-   Determine the credibility of the data. \[completed\]

##### Deliverables

-   A description of all data sources used. \[completed\]

    The main data source used is the most recent 12 months (May 2021 -
    April 2022) of riding data provided by the Cyclistic company via
    this [link](https://divvy-tripdata.s3.amazonaws.com/index.html).

### Process

This step involves getting the data ready for analysis. Here, a main key
will be merging all of the individual .CSV files into one large .CSV to
streamline the working process.

##### Code

###### Packages and Libraries

``` r
r = getOption("repos")
r["CRAN"] = "http://cran.us.r-project.org"
options(repos = r)

## Installing packages needed for analysis

install.packages("tidyverse")
```

    ## Installing package into 'C:/Users/Nolan/AppData/Local/R/win-library/4.2'
    ## (as 'lib' is unspecified)

    ## package 'tidyverse' successfully unpacked and MD5 sums checked
    ## 
    ## The downloaded binary packages are in
    ##  C:\Users\Nolan\AppData\Local\Temp\RtmpEByNUg\downloaded_packages

``` r
install.packages("ggplot2")
```

    ## Installing package into 'C:/Users/Nolan/AppData/Local/R/win-library/4.2'
    ## (as 'lib' is unspecified)

    ## package 'ggplot2' successfully unpacked and MD5 sums checked
    ## 
    ## The downloaded binary packages are in
    ##  C:\Users\Nolan\AppData\Local\Temp\RtmpEByNUg\downloaded_packages

``` r
install.packages("lubridate")
```

    ## Installing package into 'C:/Users/Nolan/AppData/Local/R/win-library/4.2'
    ## (as 'lib' is unspecified)

    ## package 'lubridate' successfully unpacked and MD5 sums checked
    ## 
    ## The downloaded binary packages are in
    ##  C:\Users\Nolan\AppData\Local\Temp\RtmpEByNUg\downloaded_packages

``` r
install.packages("plyr")
```

    ## Installing package into 'C:/Users/Nolan/AppData/Local/R/win-library/4.2'
    ## (as 'lib' is unspecified)

    ## package 'plyr' successfully unpacked and MD5 sums checked
    ## 
    ## The downloaded binary packages are in
    ##  C:\Users\Nolan\AppData\Local\Temp\RtmpEByNUg\downloaded_packages

``` r
install.packages("dplyr")
```

    ## Installing package into 'C:/Users/Nolan/AppData/Local/R/win-library/4.2'
    ## (as 'lib' is unspecified)

    ## package 'dplyr' successfully unpacked and MD5 sums checked

    ## Warning: cannot remove prior installation of package 'dplyr'

    ## Warning in file.copy(savedcopy, lib, recursive = TRUE): problem copying C:
    ## \Users\Nolan\AppData\Local\R\win-library\4.2\00LOCK\dplyr\libs\x64\dplyr.dll
    ## to C:\Users\Nolan\AppData\Local\R\win-library\4.2\dplyr\libs\x64\dplyr.dll:
    ## Permission denied

    ## Warning: restored 'dplyr'

    ## 
    ## The downloaded binary packages are in
    ##  C:\Users\Nolan\AppData\Local\Temp\RtmpEByNUg\downloaded_packages

``` r
## Loading libraries needed

library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✔ ggplot2 3.3.6     ✔ purrr   0.3.4
    ## ✔ tibble  3.1.7     ✔ dplyr   1.0.9
    ## ✔ tidyr   1.2.0     ✔ stringr 1.4.0
    ## ✔ readr   2.1.2     ✔ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## ✖ dplyr::filter() masks stats::filter()
    ## ✖ dplyr::lag()    masks stats::lag()

``` r
library(ggplot2)
library(lubridate)
```

    ## 
    ## Attaching package: 'lubridate'

    ## The following objects are masked from 'package:base':
    ## 
    ##     date, intersect, setdiff, union

``` r
library(plyr); library(dplyr)
```

    ## ------------------------------------------------------------------------------

    ## You have loaded plyr after dplyr - this is likely to cause problems.
    ## If you need functions from both plyr and dplyr, please load plyr first, then dplyr:
    ## library(plyr); library(dplyr)

    ## ------------------------------------------------------------------------------

    ## 
    ## Attaching package: 'plyr'

    ## The following objects are masked from 'package:dplyr':
    ## 
    ##     arrange, count, desc, failwith, id, mutate, rename, summarise,
    ##     summarize

    ## The following object is masked from 'package:purrr':
    ## 
    ##     compact

###### Concatening

Merging all of the CSV files into one data frame.

``` r
## Obtaining and combining data from csv files into R

csv_files <- list.files(path = "C:/Users/Nolan/Desktop/CSV", recursive = TRUE, full.names=TRUE)

cyclistic_all <- do.call(rbind.fill, lapply(csv_files, read.csv))
```

##### Data Cleaning

###### Removing Duplicates

``` r
## Removing duplicates from the data, creating a new dataset

cyclistic_dup_free <- cyclistic_all[!duplicated(cyclistic_all$ride_id), ]

## Printing the number of duplicate rows which were deleted

print(paste("Removed", nrow(cyclistic_all) - nrow(cyclistic_dup_free), "duplicated rows"))
```

    ## [1] "Removed 8 duplicated rows"

###### Parsing datetime columns

``` r
## Formatting the date & time in certain columns

cyclistic_dup_free$started_at <- as.POSIXct(cyclistic_dup_free$started_at, "%Y-%m-%d %H:%M:%S")
```

    ## Warning in strptime(xx, f, tz = tz): unknown timezone '%Y-%m-%d %H:%M:%S'

    ## Warning in as.POSIXct.POSIXlt(x): unknown timezone '%Y-%m-%d %H:%M:%S'

    ## Warning in strptime(x, f, tz = tz): unknown timezone '%Y-%m-%d %H:%M:%S'

    ## Warning in as.POSIXct.POSIXlt(as.POSIXlt(x, tz, ...), tz, ...): unknown timezone
    ## '%Y-%m-%d %H:%M:%S'

``` r
cyclistic_dup_free$ended_at <- as.POSIXct(cyclistic_dup_free$ended_at, "%Y-%m-%d %H:%M:%S")
```

    ## Warning in strptime(xx, f, tz = tz): unknown timezone '%Y-%m-%d %H:%M:%S'

    ## Warning in as.POSIXct.POSIXlt(x): unknown timezone '%Y-%m-%d %H:%M:%S'

    ## Warning in strptime(x, f, tz = tz): unknown timezone '%Y-%m-%d %H:%M:%S'

    ## Warning in as.POSIXct.POSIXlt(as.POSIXlt(x, tz, ...), tz, ...): unknown timezone
    ## '%Y-%m-%d %H:%M:%S'

##### Manipulating the data

Adding certain columns for variables which will help the analysis moving
forward.

###### ride_length

Adding a column to show the length of each ride in minutes.

``` r
## Adding a column for ride length

cyclistic_dup_free2 <- cyclistic_dup_free %>%
  mutate(ride_length = as.numeric(cyclistic_dup_free$ended_at - cyclistic_dup_free$started_at) / 60)

## Seeing an overview of the new column

summary(cyclistic_dup_free2$ride_length)
```

    ##     Min.  1st Qu.   Median     Mean  3rd Qu.     Max.     NA's 
    ##   -58.03     6.45    11.52    21.14    20.95 55944.15        1

``` r
## Looks like there are rides that are negative in length and unreasonably long. Reducing data to 2% to 98% in terms of ride length
## Removing the bottom and top 2% of data rows

cyclistic_cleaner <- cyclistic_dup_free2 %>%
  filter(between(ride_length, quantile(ride_length, 0.02, na.rm = TRUE), quantile(ride_length, 0.98, na.rm = TRUE)))

print(paste("Removed", nrow(cyclistic_dup_free2) - nrow(cyclistic_cleaner), "rows as outliers" ))
```

    ## [1] "Removed 230124 rows as outliers"

###### year_month

Adding a column to display the year and month of the ride.

``` r
## Adding a column to display which month of what year the ride takes place in

cyclistic_clean <- cyclistic_cleaner %>%
  mutate(year_month = paste(strftime(cyclistic_cleaner$started_at, "%Y"),
    "-",
    strftime(cyclistic_cleaner$started_at, "%m"),
    paste("(",strftime(cyclistic_cleaner$started_at, "%b"), ")", sep = "")))
unique(cyclistic_clean$year_month)
```

    ##  [1] "2021 - 05 (May)" "2021 - 04 (Apr)" "2021 - 06 (Jun)" "2021 - 07 (Jul)"
    ##  [5] "2021 - 08 (Aug)" "2021 - 09 (Sep)" "2021 - 10 (Oct)" "2021 - 11 (Nov)"
    ##  [9] "2021 - 12 (Dec)" "2022 - 01 (Jan)" "2022 - 02 (Feb)" "2022 - 03 (Mar)"
    ## [13] "2022 - 04 (Apr)"

###### weekday

Adding a column to show the day of the week for each ride.

``` r
## Adding a column to dictate what day of the week the ride occured on

cyclistic_clean2 <- cyclistic_clean %>%
  mutate(weekday = paste(strftime(cyclistic_clean$ended_at, "%u"), "-", strftime(cyclistic_clean$ended_at, "%a")))
unique(cyclistic_clean2$weekday)
```

    ## [1] "7 - Sun" "3 - Wed" "2 - Tue" "1 - Mon" "6 - Sat" "4 - Thu" "5 - Fri"

###### start_hour

Adding a column for the start hour of each ride.

``` r
## Adding a column that outlines what hour the ride starts in

cyclistic_clean3 <- cyclistic_clean2 %>%
  mutate(start_hour = strftime(cyclistic_clean2$ended_at, "%H"))
unique(cyclistic_clean3$start_hour)
```

    ##  [1] "08" "10" "14" "07" "16" "12" "20" "18" "21" "11" "19" "13" "17" "05" "22"
    ## [16] "15" "09" "06" "04" "23" "03" "02" "00" "01"

###### Saving results as a new .CSV

``` r
## Saving a CSV of the data up to this point

cyclistic_clean3 %>%
  write.csv("cyclistic_clean.csv")
```

    ## Warning in as.POSIXlt.POSIXct(x, tz): unknown timezone '%Y-%m-%d %H:%M:%S'

    ## Warning in as.POSIXlt.POSIXct(x, tz): unknown timezone '%Y-%m-%d %H:%M:%S'

##### Guiding questions

-   What tools are you choosing and why?

    I decided to use R for this case study. I made this decision because
    of the large quantity of data I am working with as well as its
    ability to produce visuals and reports.

-   Have you ensured your data’s integrity?

    I have. The data is consistent, accurate, and well representative.

-   What steps have you taken to ensure that your data is clean?

    I have removed any instances of duplicate rows of data. Also, I
    ensured that the columns were in the correct format. Additionally, I
    removed any data rows where the ride length was calculated to be
    negative or unreasonably long.

-   How can you verify that your data is clean and ready to analyze?

    This report can attest to the cleanliness of the data in question.

-   Have you documented your cleaning process so you can review and
    share those results?

    Yes, the cleaning process is documented and shown in this report.

##### Key tasks

-   Check the data for errors. \[completed\]  
-   Choose your tools. \[completed\]  
-   Transform the data so you can work with it effectively.
    \[completed\]  
-   Document the cleaning process. \[completed\]

##### Deliverables

-   Documentation of any cleaning or manipulation of data. \[completed\]

### Analyze

Here we will explore the data and find the key differences between
members and riders, allowing us to draw effective conclusions regarding
marketing.

##### Code

``` r
## Creating a function to alter the width and height of plots easily

fig <- function(width, heigth){options(repr.plot.width = width, repr.plot.height = heigth)}

## Changing the name so that it is easier to call

cyclistic <- cyclistic_clean3

## Viewing data summary to see if there is anything that stands out

summary(cyclistic)
```

    ## Warning in as.POSIXlt.POSIXct(x, tz): unknown timezone '%Y-%m-%d %H:%M:%S'

    ## Warning in as.POSIXlt.POSIXct(x, tz): unknown timezone '%Y-%m-%d %H:%M:%S'

    ##    ride_id          rideable_type        started_at                    
    ##  Length:5527428     Length:5527428     Min.   :2021-05-01 00:00:11.00  
    ##  Class :character   Class :character   1st Qu.:2021-07-08 06:23:17.00  
    ##  Mode  :character   Mode  :character   Median :2021-09-01 12:38:26.50  
    ##                                        Mean   :2021-09-19 06:26:18.93  
    ##                                        3rd Qu.:2021-11-04 16:55:15.50  
    ##                                        Max.   :2022-04-30 23:59:52.00  
    ##                                                                        
    ##     ended_at                      start_station_name start_station_id  
    ##  Min.   :2021-05-01 00:03:26.00   Length:5527428     Length:5527428    
    ##  1st Qu.:2021-07-08 06:35:33.75   Class :character   Class :character  
    ##  Median :2021-09-01 12:53:12.00   Mode  :character   Mode  :character  
    ##  Mean   :2021-09-19 06:42:17.91                                        
    ##  3rd Qu.:2021-11-04 17:06:56.75                                        
    ##  Max.   :2022-05-01 00:37:56.00                                        
    ##                                                                        
    ##  end_station_name   end_station_id       start_lat       start_lng     
    ##  Length:5527428     Length:5527428     Min.   :41.64   Min.   :-87.84  
    ##  Class :character   Class :character   1st Qu.:41.88   1st Qu.:-87.66  
    ##  Mode  :character   Mode  :character   Median :41.90   Median :-87.64  
    ##                                        Mean   :41.90   Mean   :-87.65  
    ##                                        3rd Qu.:41.93   3rd Qu.:-87.63  
    ##                                        Max.   :45.64   Max.   :-73.80  
    ##                                                                        
    ##     end_lat         end_lng       member_casual      Version..1.0      
    ##  Min.   :41.39   Min.   :-88.97   Length:5527428     Length:5527428    
    ##  1st Qu.:41.88   1st Qu.:-87.66   Class :character   Class :character  
    ##  Median :41.90   Median :-87.64   Mode  :character   Mode  :character  
    ##  Mean   :41.90   Mean   :-87.65                                        
    ##  3rd Qu.:41.93   3rd Qu.:-87.63                                        
    ##  Max.   :42.13   Max.   :-87.49                                        
    ##  NA's   :737     NA's   :737                                           
    ##   ride_length      year_month          weekday           start_hour       
    ##  Min.   : 1.383   Length:5527428     Length:5527428     Length:5527428    
    ##  1st Qu.: 6.617   Class :character   Class :character   Class :character  
    ##  Median :11.517   Mode  :character   Mode  :character   Mode  :character  
    ##  Mean   :15.983                                                           
    ##  3rd Qu.:20.367                                                           
    ##  Max.   :89.183                                                           
    ## 

###### Data Distribution

We will look at the data and certain variables to see how the data is
distributed among members and casuals as well as other categories.

###### Casuals vs. Members

What percentage of rides belong to members/casuals respectively?

``` r
## Determining what percentage of users(rides) are members vs casuals

cyclistic %>%
  dplyr::group_by(member_casual) %>%
  dplyr::summarize(count = length(ride_id),
            '%' = (length(ride_id) / nrow(cyclistic)) * 100)
```

    ## # A tibble: 2 × 3
    ##   member_casual   count   `%`
    ##   <chr>           <int> <dbl>
    ## 1 casual        2388351  43.2
    ## 2 member        3139077  56.8

``` r
## Changing scientific notation to normal numbers

options(scipen = 100, digits = 4)

## Creating first plot showing member vs casual rideshare

fig(16,8)
ggplot(cyclistic_clean, aes(member_casual, fill = member_casual)) + 
  geom_bar() +
  labs(x = "Casuals and Members", y = "Ride Count", title = "Chart01 - Casual vs. Member Ride Share")
```

![](Cyclistic_Report1_files/figure-gfm/unnamed-chunk-13-1.png)<!-- -->

###### Month

How does the number of rides change by month for both members and
casuals?

``` r
## Summarizing certain data by month of the year

cyclistic %>%
  dplyr::group_by(year_month) %>%
  dplyr::summarise(count = length(ride_id),
            '%' = (length(ride_id) / nrow(cyclistic)) * 100,
            'mem_percentage' = (sum(member_casual == "member") / length(ride_id)) * 100,
            'cas_percentage' = (sum(member_casual == "casual") / length(ride_id)) * 100,
            'Mem. vs Cas. Perc. Difference' = mem_percentage - cas_percentage)
```

    ## # A tibble: 13 × 6
    ##    year_month       count     `%` mem_percentage cas_percentage `Mem. vs Cas. …`
    ##    <chr>            <int>   <dbl>          <dbl>          <dbl>            <dbl>
    ##  1 2021 - 04 (Apr)    634  0.0115           42.9           57.1          -14.2  
    ##  2 2021 - 05 (May) 504732  9.13             53.0           47.0            5.98 
    ##  3 2021 - 06 (Jun) 694798 12.6              50.4           49.6            0.725
    ##  4 2021 - 07 (Jul) 787080 14.2              47.2           52.8           -5.60 
    ##  5 2021 - 08 (Aug) 769451 13.9              49.6           50.4           -0.806
    ##  6 2021 - 09 (Sep) 728117 13.2              52.6           47.4            5.24 
    ##  7 2021 - 10 (Oct) 609287 11.0              59.8           40.2           19.6  
    ##  8 2021 - 11 (Nov) 349475  6.32             70.6           29.4           41.1  
    ##  9 2021 - 12 (Dec) 241277  4.37             72.0           28.0           43.9  
    ## 10 2022 - 01 (Jan)  99776  1.81             82.8           17.2           65.7  
    ## 11 2022 - 02 (Feb) 111507  2.02             81.8           18.2           63.6  
    ## 12 2022 - 03 (Mar) 274071  4.96             69.0           31.0           37.9  
    ## 13 2022 - 04 (Apr) 357223  6.46             66.5           33.5           33.1

``` r
## Found that there is data from 2021 - 04 which should not be included, cleaning data

cyclistic <- subset(cyclistic, year_month != "2021 - 04 (Apr)")
```

``` r
## Rerunning previous code to check if the data correction was effective

cyclistic %>%
  dplyr::group_by(year_month) %>%
  dplyr::summarise(count = length(ride_id),
                   '%' = (length(ride_id) / nrow(cyclistic)) * 100,
                   'mem_percentage' = (sum(member_casual == "member") / length(ride_id)) * 100,
                   'cas_percentage' = (sum(member_casual == "casual") / length(ride_id)) * 100,
                   'Mem. vs Cas. Perc. Difference' = mem_percentage - cas_percentage)
```

    ## # A tibble: 12 × 6
    ##    year_month       count   `%` mem_percentage cas_percentage `Mem. vs Cas. Pe…`
    ##    <chr>            <int> <dbl>          <dbl>          <dbl>              <dbl>
    ##  1 2021 - 05 (May) 504732  9.13           53.0           47.0              5.98 
    ##  2 2021 - 06 (Jun) 694798 12.6            50.4           49.6              0.725
    ##  3 2021 - 07 (Jul) 787080 14.2            47.2           52.8             -5.60 
    ##  4 2021 - 08 (Aug) 769451 13.9            49.6           50.4             -0.806
    ##  5 2021 - 09 (Sep) 728117 13.2            52.6           47.4              5.24 
    ##  6 2021 - 10 (Oct) 609287 11.0            59.8           40.2             19.6  
    ##  7 2021 - 11 (Nov) 349475  6.32           70.6           29.4             41.1  
    ##  8 2021 - 12 (Dec) 241277  4.37           72.0           28.0             43.9  
    ##  9 2022 - 01 (Jan)  99776  1.81           82.8           17.2             65.7  
    ## 10 2022 - 02 (Feb) 111507  2.02           81.8           18.2             63.6  
    ## 11 2022 - 03 (Mar) 274071  4.96           69.0           31.0             37.9  
    ## 12 2022 - 04 (Apr) 357223  6.46           66.5           33.5             33.1

``` r
## Creating graph for rides by month

fig(16,8)
ggplot(cyclistic, aes(year_month, fill = member_casual)) +
         geom_bar() +
         labs(x = "Month", y = "Ride Count", title = "Chart02 - Casual vs. Member Ride Share By Month") +
         coord_flip()
```

![](Cyclistic_Report1_files/figure-gfm/unnamed-chunk-16-1.png)<!-- -->

Let’s look at what we learned and can infer from this chart:

-   The month with the largest ride share was July 2021 with 14.2%.

-   Casual riders retained the larger ride share percentage in July and
    August of 2021. All other months members had the higher proportion
    of ride share.

-   There appears to be a cyclical pattern over the data in line with
    the seasons. There is a higher number of rides in the summer
    compared to the winter months.

-   Members have a significantly higher ride share percentage in the
    winter months.

Considering that the data appears to follow the cycle of the seasons, we
should look at the average temperature in Chicago and how that might
correlate to our data. The temperature data will be taken from
[here](https://en.wikipedia.org/wiki/Climate_of_Chicago) (Daily mean °F,
1991–2020).

``` r
## Creating objects for the temp in Chicago

mean_temperature_chicago <- c(32.8, 36.8, 47.9, 60.0, 71.5, 81.2, 85.2, 83.1, 76.5, 63.7, 49.6, 37.7)

month <- c("01 - Jan", "02 - Feb", "03 - Mar", "04 - Apr", "05 - May", "06 - Jun", "07 - Jul", "08 - Aug", "09 - Sep", "10 - Oct", "11 - Nov", "12 - Dec")
```

``` r
## Creating a plot to show the average temperature by month, can compare to ride share

fig(16,8)
data.frame(month, mean_temperature_chicago) %>%
  ggplot(aes(x = month, y = mean_temperature_chicago)) +
  labs(x = "Month", y = "Mean Temperature (F)", title = "Chart03 - Mean Temperature Chicago (1991 - 2020)") +
  geom_col() +
  theme(axis.text.x = element_text(angle = 70, hjust = 1))
```

![](Cyclistic_Report1_files/figure-gfm/unnamed-chunk-18-1.png)<!-- -->

Main takeaway when comparing temperature data to ride share data:

-   There seems to be a significant correlation between the average
    temperature in F and the number of rides for that month. The higher
    the average temperature, the higher number of rides.

###### Weekday

How much of the data is present on each particular weekday? Which
weekdays are most popular?

``` r
## Summarizing data of ride share by weekday and by member or casual

cyclistic %>%
  dplyr::group_by(weekday) %>%
  dplyr::summarize(count = length(ride_id),
            '%' = (length(ride_id) / nrow(cyclistic)) * 100,
            'members_percentage' = (sum(member_casual == "member") / length(ride_id)) * 100,
            'casuals_percentage' = (sum(member_casual == "casual") / length(ride_id)) * 100,
            'Member vs. Casual Percent Difference' = members_percentage - casuals_percentage)
```

    ## # A tibble: 7 × 6
    ##   weekday  count   `%` members_percentage casuals_percentage `Member vs. Casua…`
    ##   <chr>    <int> <dbl>              <dbl>              <dbl>               <dbl>
    ## 1 1 - Mon 700727  12.7               61.8               38.2               23.7 
    ## 2 2 - Tue 745322  13.5               65.4               34.6               30.8 
    ## 3 3 - Wed 768375  13.9               64.5               35.5               29.0 
    ## 4 4 - Thu 766437  13.9               62.3               37.7               24.6 
    ## 5 5 - Fri 816874  14.8               55.6               44.4               11.2 
    ## 6 6 - Sat 960109  17.4               44.9               55.1              -10.1 
    ## 7 7 - Sun 768950  13.9               46.7               53.3               -6.56

``` r
## Creating plot based on rides by weekday

fig(16,8)
ggplot(cyclistic, aes(weekday, fill = member_casual)) +
  geom_bar() +
  labs(x = "Weekday", y = "Ride Count", title = "Chart04 - Rides by Weekday") +
  coord_flip()
```

![](Cyclistic_Report1_files/figure-gfm/unnamed-chunk-20-1.png)<!-- -->

Things to take note of from this data/chart:

-   Saturday recorded the largest number of total rides at 17.4%, Friday
    was second at 14.8%, and the rest of the days were relatively
    similar in percentages.

-   The weekend (Friday to Sunday) retained the highest ride share
    percentage.

-   Members had the highest ride share percentage on each day other than
    Saturday and Sunday where casual riders had a higher percentage.

-   Casual riders were much more active on weekends.

###### Starting hour

``` r
## Summarizing by start hour, skimming data

cyclistic %>%
  dplyr::group_by(start_hour) %>%
  dplyr::summarize(count = length(ride_id),
            '%' = (length(ride_id) / nrow(cyclistic)) * 100,
            'members_percentage' = (sum(member_casual == "member") / length(ride_id)) * 100,
            'casuals_percentage' = (sum(member_casual == "casual") / length(ride_id)) * 100,
            'member_vs_casual_percent_difference' = members_percentage - casuals_percentage)
```

    ## # A tibble: 24 × 6
    ##    start_hour  count   `%` members_percentage casuals_percenta… member_vs_casua…
    ##    <chr>       <int> <dbl>              <dbl>             <dbl>            <dbl>
    ##  1 00          23605 0.427               52.2              47.8             4.33
    ##  2 01          47451 0.859               73.5              26.5            46.9 
    ##  3 02         112476 2.04                78.1              21.9            56.2 
    ##  4 03         197876 3.58                78.3              21.7            56.6 
    ##  5 04         237881 4.30                75.2              24.8            50.4 
    ##  6 05         205477 3.72                67.7              32.3            35.3 
    ##  7 06         220379 3.99                60.3              39.7            20.6 
    ##  8 07         273315 4.95                57.3              42.7            14.5 
    ##  9 08         323524 5.85                55.7              44.3            11.5 
    ## 10 09         334796 6.06                53.3              46.7             6.70
    ## # … with 14 more rows

``` r
## Creating plot for above data

fig(16, 8)
cyclistic %>%
  ggplot(aes(start_hour, fill=member_casual)) +
  labs(x = "Hour", y = "Ride Count", title = "Chart05 - Ride Share By Hour") +
  geom_bar() +
  theme(axis.text.x = element_text(angle = 50, hjust = 1))
```

![](Cyclistic_Report1_files/figure-gfm/unnamed-chunk-22-1.png)<!-- -->

What we can see from this chart:

-   The largest number of rides start in the afternoon.

-   The most rides begin sometime in the 1pm hour.

-   Members have a higher ride share earlier in the day from around 12am
    to 9am.

-   Casuals tend to ride more often from 9am to 12am.

Let’s also look at the data of the starting hour for each ride but by
each weekday as well.

``` r
## Creating plot for starting hour for each weekday

fig(25,15)
cyclistic %>%
  ggplot(aes(start_hour, fill=member_casual)) +
  geom_bar() +
  labs(x = "Hour", y = "Ride_Count", title = "Chart06 - Ride Share By Hour Each Day") +
  facet_wrap(~ weekday) +
  theme(axis.text.x = element_text(angle = 90, hjust = 1)) +
  theme(axis.text.x = element_text(size = 8))
```

![](Cyclistic_Report1_files/figure-gfm/unnamed-chunk-23-1.png)<!-- -->

Looking at this chart, there is a clear difference between days in the
middle of the week and the weekend. Let’s look at each separately and
compare.

``` r
fig(25,15)
cyclistic %>%
    mutate(type_of_weekday = ifelse(weekday == '6 - Sat' | weekday == '7 - Sun',
                                   'weekend',
                                   'midweek')) %>%
    ggplot(aes(start_hour, fill = member_casual)) +
    labs(x = "Hour of the day", y = "Ride Count", title = "Chart 06 - Distribution by hour (Midweek vs. Weekend)") +
    geom_bar() +
    facet_wrap(~ type_of_weekday) +
    theme(axis.text.x = element_text(angle = 90, hjust = 1)) +
    theme(axis.text.x = element_text(size = 8))
```

![](Cyclistic_Report1_files/figure-gfm/unnamed-chunk-24-1.png)<!-- -->

Key differences between the two charts:

-   The amount of rides shown does not mean much considering there are 5
    weekdays and only 2 days on the weekend.

-   The weekend seems to have a much more smooth distribution of rides
    by hour when compared weekdays which seem a big more jagged.

-   There seems to be a large jump in the number of rides on weekdays
    between roughly 6am and 8am and also 5pm and 6pm. This is likely a
    reflection of the workday.

It is natural to ask or wonder why the weekend and weekdays vary so much
in terms of the data. As mentioned above, weekdays are typically more
influenced by routine such as work, grocery trips, going to lunch,
dropping kids off at daycare, going to the gym, and more. The weekend is
less predictable as people typically have more freedom outside of that
routine.

##### Guiding questions

-   How should you organize your data to perform analysis on it?

    In this case study, I organized the data by first merging all data
    into one data frame, cleaning it, and then creating a new .CSV file
    to store that data.

-   Has your data been properly formatted?

    Yes, each column in consistent in name, data type, and total rows.

-   What surprises did you discover in the data?

    The biggest surprise, or perhaps the most interesting thing to note,
    was the stark difference between the data for weekdays and the
    weekend. The data is emblematic of how people live their lives on
    certain days.

-   What trends or relationships did you find in the data?

    -   In total, there are more member rides than casual rides.
    -   There appears to be a correlation between average temperature
        and the number of rides with the summer months retaining the
        highest ride share percentage.
    -   There is a large difference in the data from the weekend to days
        in the midweek which is important to note.
    -   Members appear to use bikes for scheduled events where casual
        riders seem to use them more sporadically.
    -   The time of day has a heavy influence on the number of rides.

-   How will these insights help answer your business questions?

    These insights give more information and context about the
    differences between members and casuals. This will allow a more
    efficient marketing campaign to convert casuals to members.

##### Key tasks

-   Aggregate your data so it’s useful and accessible. \[completed\]
-   Organize and format your data. \[completed\]
-   Perform calculations. \[completed\]
-   Identify trends and relationships. \[completed\]

##### Deliverables

-   A summary of your analysis. \[completed\]

### Share

Most often, the sharing portion of the process is done through
presentations, but since I am not presenting directly to anyone I will
be sharing this R notebook report instead. This will allow any parties
to be able to analyze and review my data analysis process in a thorough
manner.

Let us review what we found in the data and draw some conclusions from
those results.

What we know about the data:

-   Members account for 13.6% more of the data than casual riders.

-   Summer months where the average temperature is highest retains the
    highest percentage of ride share.

-   July 2021 recorded the largest ride share at 14.2% of total rides
    occurring in this month.

-   In all but two months (July and August) members recorded more rides
    than casual riders.

-   There is a strong correlation between average monthly temperature
    and the number of rides in a month.

-   The afternoon sees a larger number of overall rides compared to the
    morning or evening.

-   There is a significant difference in data trends between weekday
    rides and weekend rides most likely connected to weekday routines
    and obligations such as work.

Leaving the data and the aforementioned trends, there are still
questions left to be asked. One question might be why are there more
member rides than casual rides? One possibility is that members have a
bigger need for bikes or are more aware for their need for bikes ahead
of time than casuals. The higher proportion of member rides during cold
months helps to support this ideal. If casuals had a similar need or
demand for bikes, then this would not be the case.

Another question that arises is why are there more bike rides occurring
on the weekends compared to the average single weekday? One possible
explanation is that there is a higher demand for the bikes for
recreation from casual riders. This is supported by casuals having a
higher proportion of rides on weekends and the starting hour
visualization being more smooth when compared to that of weekdays.

Differences between members and casuals:

-   Members ride most often on weekdays and casuals ride most often on
    weekends as shown by the proportion of ride share.

-   There are a higher number of casual rides on weekends.

-   There are more members riding during the morning, mainly between
    12am and 9am. While there are more casuals between 9am and 12am
    (save for hours where work lets out).

-   A large increase in rides can be seen weekdays between 6am to 8am
    for members. Another big increase is from 5pm to 6pm. With declines
    in between those time frames.

-   Casuals follow a smoother distribution, peaking on Sundays and
    having low points on Wednesday/Thursday.

-   Casuals are much more active between 11am and 6pm on weekends when
    compared to members.

From these differences, we can infer that members have a more fixed need
or demand for bikes compared to casuals. Members most likely use bikes
for weekday routine activities. Some possibilities include:

-   Going to work.
-   Routine exercise.
-   Going to scheduled destinations such as a gym or class.

This idea is supported in that there are more member rides between 6am
to 8am and 5pm to 6pm which correspond to commutes to and from work.
Also, in contrast, the reason casual riders retain a higher percentage
of ride share on weekends is that those routines do not occur on
weekends and rides on these days are more likely for recreation.

Overall, concluding thoughts:

-   Members use the bikes for scheduled, routine activities such as
    going to work or classes.

-   Bikes are more often used for recreation on the weekends, usually by
    casual riders.

-   The number of rides is likely influenced by the temperature outside.

##### Guiding questions

-   Were you able to answer the question of how annual members and
    casual riders use Cyclistic bikes differently?

    Yes, through the analysis of ride data I was able to determine how
    members and casuals differ.

-   What story does your data tell?

    The story that the data tells is that members and casuals use bikes
    for different reasons. Members most likely use bikes for routine
    events such as work or class corresponding to using bikes at set
    times throughout the week. Casuals tend to have a more even
    dispersion of starting hours and are most active on weekends
    indicating the use of bikes for recreation or unplanned travel.

-   How do your findings relate to your original question?

    These findings help to provide context as to why both members and
    casuals use bikes which answers the question as to why the two
    differ. Furthermore, knowing why each use bikes helps to create more
    effective marketing campaigns.

-   Who is your audience? What is the best way to communicate with them?

    The main target audience is my Cyclistic marketing analytics team
    and Lily Moreno. The best way to communicate is through a
    presentation and explanation of my findings as well as supplying
    this notebook for them to peruse to their liking.

-   Can data visualization help you share your findings?

    Yes, data visualization allows the viewer to quickly understand the
    data and the story it is telling.

-   Is your presentation accessible to your audience?

    Yes, all charts and data are made using distinct colors and labels
    and can be easily understood by most.

##### Key tasks

-   Determine the best way to share your findings. \[completed\]
-   Create effective data visualizations. \[completed\]
-   Present your findings. \[completed\]
-   Ensure your work is accessible. \[completed\]

##### Deliverables

-   Supporting visualizations and key findings \[completed\]

### Act

Most likely, the act phase would be done by the Cyclistic marketing
team. The main takeaway will be the top three recommendations for the
marketing team.

##### Guiding questions

-   What is your final conclusion based on your analysis?

    Different habits and needs determine the difference between members
    and casuals. The specific conclusion(s) will be stated in the
    deliverables section of this step.

-   How could your team and business apply your insights?

    My insights could be use to direct a marketing campaign towards
    casuals with the goal of turning them into members. The insights
    provide context of ways in which to advertise the bikes to casuals.
    For example, they could create ads stating that bikes can be used
    for both recreation and daily travel to work or class.

-   What next steps would you or your stakeholders take based on your
    findings?

    There are two main avenues which we could decide to go down. The
    first being to conduct further analysis on other data or variables
    to try and improve the quality of our conclusions. The second and
    more likely step would be to begin work on a marketing campaign
    targeting casuals using the trends identified in my analysis.

-   Is there additional data you could use to expand on your findings?

    -   Daily temperature data to compare with number of rides on
        specific dates.

    -   More information on members such as reasons for having a
        membership (limit inputs).

    -   Age and other demographics of riders.

##### Key tasks

-   Create your portfolio. \[completed\]
-   Add your case study. \[completed\]
-   Practice presenting your case study to a friend or family member.
    \[completed\]

##### Deliverables

-   Your top three recommendations based on your analysis. \[completed\]

1.  Create advertisements and a marketing campaign around bikes being
    used for more than simply recreation and as a possible mode of
    transportation to and from work. You can show professionals using
    the bikes and continue to perpetuate the idea that it is healthy and
    good for the environment. These ads could be effective on social
    networking sites and professional social networks such as LinkedIn
    or Handshake.

2.  Develop advertisements focusing on the reliability and consistency
    of using bikes instead of other modes of transportation. Perhaps
    give examples of how cars break down while bikes are much more
    reliable and the user is more in control compared to other public
    transportation.

3.  Since there is a large decrease in rides during the winter months
    most likely due to the decrease in temperature, it may be good to
    add incentives during these months to increase the number of rides.
    Perhaps this can be a reduction in price, a membership exclusively
    for winter months, or single use coupons. Also, you can advertise
    that biking is a great way to warm up during the winter.

### Conclusion

This case study marks the end of my journey on the Google Data Analytics
Professional Certificate. This program has taught me a great deal in
many different areas. I have gained skills and experience with R, SQL,
Tableau, and other important services. Completing this case study was
more difficult than I had expected, but it has helped me sharpen my
skills with R and I understand the data analysis process much more now
having done it.
