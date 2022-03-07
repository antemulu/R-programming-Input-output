# R-programming-Input-output
##
## Attaching package: 'data.table'

## The following object is masked from 'package:pryr':
##
##     address
library(pryr)
library(ISLR)
library(boot)
library(data.table)
#Import!dataset!into!R.

x <- read.table("C:/Users/Owner/Downloads/Assignment 6 Dataset (1).txt", header = TRUE,sep="," )

str(x)

## 'data.frame':    20 obs. of  4 variables:
##  $ Name : chr  "Raul" "Booker" "Lauri" "Leonie" ...
##  $ Age  : int  25 18 21 21 22 20 23 24 21 23 ...
##  $ Sex  : chr  "Male" "Male" "Female" "Female" ...
##  $ Grade: int  80 83 90 91 85 69 91 97 78 81 ...

#:!run!plyer!generates for!the!mean!of!both!Age!and!Grade!split!by!gendor

y = ddply(x,"Sex",transform, Grade.Average=mean(Grade))

y <- ddply(x,"Sex",transform, Grade.Average=mean(Grade))

print(y)

##         Name Age    Sex Grade Grade.Average
## 1      Lauri  21 Female    90       86.9375
## 2     Leonie  21 Female    91       86.9375
## 3    Sherlyn  22 Female    85       86.9375
## 4    Mikaela  20 Female    69       86.9375
## 5       Aiko  24 Female    97       86.9375
## 6   Tiffaney  21 Female    78       86.9375
## 7     Corina  23 Female    81       86.9375
## 8  Petronila  23 Female    98       86.9375
## 9     Alecia  20 Female    87       86.9375
## 10   Shemika  23 Female    97       86.9375
## 11    Fallon  22 Female    90       86.9375
## 12   Deloris  21 Female    67       86.9375
## 13    Randee  23 Female    91       86.9375
## 14     Eboni  20 Female    84       86.9375
## 15   Delfina  19 Female    93       86.9375
## 16 Ernestina  19 Female    93       86.9375
## 17      Raul  25   Male    80       80.2500
## 18    Booker  18   Male    83       80.2500
## 19   Raphael  23   Male    91       80.2500
## 20      Milo  19   Male    67       80.2500

#:!Print!this!to!a!file

z <- write.table(y,"Sorted_Average")

z <- write.table(y,"Sorted_Average",sep=",")

#Filter!the!names!in!the!given!list!for!names!that!contain!the!letter i.

newx <- subset(x,grepl("[iI]",x$Name))

newx

##         Name Age    Sex Grade
## 3      Lauri  21 Female    90
## 4     Leonie  21 Female    91
## 6    Mikaela  20 Female    69
## 8       Aiko  24 Female    97
## 9   Tiffaney  21 Female    78
## 10    Corina  23 Female    81
## 11 Petronila  23 Female    98
## 12    Alecia  20 Female    87
## 13   Shemika  23 Female    97
## 15   Deloris  21 Female    67
## 17     Eboni  20 Female    84
## 18   Delfina  19 Female    93
## 19 Ernestina  19 Female    93
## 20      Milo  19   Male    67

x2 <- subset(x, grepl("i",x$Name))

print(x2)

##         Name Age    Sex Grade
## 3      Lauri  21 Female    90
## 4     Leonie  21 Female    91
## 6    Mikaela  20 Female    69
## 8       Aiko  24 Female    97
## 9   Tiffaney  21 Female    78
## 10    Corina  23 Female    81
## 11 Petronila  23 Female    98
## 12    Alecia  20 Female    87
## 13   Shemika  23 Female    97
## 15   Deloris  21 Female    67
## 17     Eboni  20 Female    84
## 18   Delfina  19 Female    93
## 19 Ernestina  19 Female    93
## 20      Milo  19   Male    67



First I loaded the required library on My RStudio next, using the read.table function I imported the dataset from my directory to read and then run plyer that generates for the mean of both Age and Grade split by gender. Finally to print this in to file I used the function write.table
