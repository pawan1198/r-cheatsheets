[<img src="https://www.r-project.org/Rlogo.png" align="right" width="200">](https://www.r-project.org/about.html)
## Author
[Pawan](author.md)
# Getting Started with R Cheat Sheet

R is one of the most popular programming languages in data science and is widely used across various industries and academia. It’s open-source, easy to learn, and capable of handling complex data and statistical manipulations, making it the preferred computing environment for many data scientists today.

This cheat sheet will cover an overview of getting started with R. 

You can find some useful cheatsheets [here](cheatsheets.md)  
[Installation of R and RStudio](episodes/installation.md)  
[Data Types in R](episodes/data-types-exported.html)  
[Data Frame in R](episodes/data-frame-exported.html)  
[Reshaping Data in R](episodes/reshaping-data-exported.html)  



# Using Packages in R
R packages are collections of functions and tools developed by the R community. They increase the power of R by improving existing base R functionalities or adding new ones.
``` r
## Lets you install new packages (e.g., tidyverse package)
install.packages("tidyverse")

##Lets you load and use packages (e.g., tidyverse package)
library(tidyverse)
```
#  The Working Directory
The working directory is a file path that R will use as the starting point for relative file paths. That is, it's the default location for importing and exporting files. An example of a working directory looks like "/file/path"
```r
##Returns your current working directory
getwd()

##Changes your current working directory to a desired file path
setwd("/file/path")
```
# Operators in R
## Arithmetic Operators in R
|Operator | Description|
|:-------|:--|
|a + b   |Sums two variables           |  
|a - b   |Subtracts two variables      |  
|a * b   |Multiply two variables       |  
|a / b   |Divide two variables         |  
|a ^ b   |Exponentiation of a variable |  
|a %% b  |The remainder of a variable  |  
|a %/% b |Integer division of variables|

## Relational Operators in R
|Operator|Description|
|--|--|
|a == b|Tests for equality|
|a != b|Tests for inequality|
|a > b|Tests for greater than|
|a < b|Tests for smaller than|
|a >= b|Tests for greater or equal than|
|a <= b|Tests for smaller or equal than|

## Logical Operators in R
|Operator|Description|
|--|--|
|!|Logical NOT|
|&|Element-wise Logical AND|
|&&|Logical AND|
|\| |Element-wise Logical OR|
|\|\| |Logical OR|

## Assignment Operators in R
Operator|Description
--|--
x <- 1, x = 1|Assigns a variable to x

## Other Operators in R
Operator|Description
--|--
%in%|Identifies whether an element belongs to a vector 
$|Allows you to access objects stored within an object
%>%|Part of magrittr package, it’s used to pass objects to functions

# Getting Started with Vectors in R
Vectors are one-dimensional arrays that can hold numeric data, character data, or logical data. In other words, a vector is a simple tool to store data.  
A vector is a contiguous collection of objects of the same type. Common types of vectors include logical, integer, double, and character.  

## Creating Vectors in R

A vector is a one-dimensional data set or a single-column data set, that doesn't have a row  
```r
c(1:59)
## output
[1]  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38
[39] 39 40 41 42 43 44 45 46 47 48 49 50 51 52 53 54 55 56 57 58 59
  
```
Here c called the command  
Within the brackets, the things called elements, and in the starting of elements inside the square bracket [] is the position of the element or the indicate the row number  

There are types of vector  
Numeric vector -  1,2,3,4   
Character vector - "A", "a", "b", "ram"  
Logical - True, False  
  
- Creates a vector using elements separated by commas
```r 
c(1,3,5)
##Output
$> 1 3 5
```
- Creates a vector of integers between two numbers
```r
1:7
##Output
$ 1 2 3 4 5 6 7
```
- Creates a vector between two numbers, with a specified interval between each element
```r
seq(2,8,by = 2)
##Output
$ 2 4 6 8
```
- Creates a vector of given elements repeated a number of times
```r
rep(2,8,times = 4)
##Output
$ 2 8 2 8 2 8 2 8
```
- Creates a vector of given elements repeating each element a number of times
```r
rep(2,8,each = 3)
##Output
$ 2 2 2 8 8 8 
```
## Vector Functions in R
+ `sort(my_vector)` : Returns my_vector sorted
+ `rev(my_vector)` : Reverses the order of my_vector
+ `table(my_vector)` : Count the values in a vector
+ `unique(my_vector)` : Distinct elements in a vector

## Selecting Vector Elements in R
+ `my_vector[6]` : Returns the sixth element of my_vector
+ `my_vector[-6]` : Returns all but the sixth element
+ `my_vector[2:6]` : Returns elements two to six
+ `my_vector[-(2:6)]` : Returns all elements except those between the second and the sixth
+ `my_vector[c(2,6)]` : Returns the second and sixth elements
+ `my_vector[x == 5]` : Returns elements equal to 5
+ `my_vector[x < 5 ]` : Returns elements less than 5
+ `my_vector[x %in% c(2, 5 ,8 )]` : Returns elements in the set {2, 5, 8} 

# Math Functions in R
+ `log(x)` : Returns the logarithm of a variable
+ `exp(x)` : Returns exponential of a variable
+ `max(x)` : Returns the maximum value of a vector
+ `min(x)` : Returns the minimum value of a vector
+ `mean(x)` : Returns the mean of a vector
+ `sum(x)` : Returns the sum of a vector
+ `median(x)` : Returns the median of a vector
+ `quantile(x)` : Percentage quantiles of a vector
+ `round(x, n)` : Round to n decimal places
+ `rank(x)` : Rank of elements in a vector
+ `signif(x, n)` : Round off n significant figures
+ `var(x)` : Variance of a vector
+ `cor(x, y)` : Correlation between two vectors
+ `sd(x)` : Standard deviation of a vector

# Getting Started with Strings in R
The `stringr` package makes it easier to work with strings in R - you should install and load this package to use the following functions.

## Find matches
+ Detects the presence of a pattern match in a string  
```r
str_detect(string, pattern, negate = FALSE) 
```
+ Detects the presence of a pattern match at the beginning of a string  
```r
str_starts(string, pattern, negate = FALSE) 
```
+ Finds the index of strings that contain pattern match  
```r
str_which(string, pattern, negate = FALSE) 
```
+ Locates the positions of pattern matches in a string  
```r
str_locate(string, pattern)
```
+ Counts the number of pattern matches in a string  
```r
str_count(string, pattern)
```
## Subset
+ Extracts substrings from a character vector  
```r
str_sub(string, start = 1L, end = -1L)
```
+ Returns strings that contain a pattern match  
```r
str_subset(string, pattern, negate = FALSE) 
```
+ Returns the first pattern match in each string as a vector  
```r
str_extract(string, pattern) 
```
+ Returns the first pattern match in each string as a matrix with a column for each group in the pattern  
```r
str_match(string, pattern)
```
## Mutate
+ Replaces substrings by identifying the substrings with str_sub() and assigning them to the results    
```r
str_sub() <- value 
```
+ Replaces the first matched pattern in each string    
```r
str_replace(string, pattern, replacement)  
```
+ Replaces all matched patterns in each string  
```r
str_replace_all(string, pattern, replacement) 
```
+ Converts strings to lowercase   
```r
str_to_lower(string) 
```
+ Converts strings to uppercase   
```r
str_to_upper(string) 
```
+ Converts strings to title case   
```r
str_to_title(string) 
```
## Join and split
+ Repeats strings n times  
```r
str_dup(string, n)
```
+ Splits a vector of strings into a matrix of substrings  
```r  
str_split_fixed(string, pattern, n) 
```
# Getting Started with Data Frames in R
A data frame has the variables of a data set as columns and the observations as rows.
+ This creates the data frame df, seen below  
```r 
df <- data.frame(x = 1:3, y = c("h", "i", "j"), z = 12:14)
#>x	y	z
#>1 h 12
#>2 i 13
#>3 j 14
```
+ This selects all columns of the third row  
```r
df[ ,3]
#> x y z
#> 3 j 14
```
+ This selects the column z  
```r
df$z
#>z
#>12 
#>13
#>14
```
+ This selects all rows of the second column  
```r  
df[ ,2]
#>y
#>h
#>i
#>j
```
+ This selects the third column of the second row  
```r  
df[2,3]  

#>13
```
# Manipulating Data Frames in R
+ Takes a sequence of vector, matrix, or data-frame arguments and combines them with columns  
```r
cbind(df1,df2)
```
+ Takes a sequence of vector, matrix, or data frame arguments and combines them with rows  
```r
rbind(df1,df2)
```
+ Extracts rows that meet logical criteria  
```r
filter(df, x == 2)
```
+ Removes rows with duplicate values  
```r
distinct(df, z)
```
+ Selects rows by position  
```r
slice(df, 10:15)
```
+ Selects rows with the highest values  
```r
slice_max(df, z, prop =  0.25)
```
+ Extracts column values as a vector, by name or index  
```r
pull(df, y)
```
+ Extracts columns as a table  
```r
select(df, x, y)
```
+ Moves columns to a new position  
```r
relocate(df, x, .after = last_col())
```
+ Renames columns  
```r
rename(df,"age"=z)
```
+ Orders rows by values of a column from high to low  
```r  
arrange(df, desc(x))
```
+ Computes table of summaries  
```r  
summarise(df, total = sum(x))
```
+ Computes table of summaries    
```r
summarise(df, total = sum(x))
```
+ Use group_by() to create a "grouped" copy of a table grouped by columns (similarly to a pivot table in spreadsheets). dplyr functions will then manipulate each "group" separately and combine the results  

``` r
df %>%   
    group_by(z) %>%   
    summarise(total = sum(x))  
summarise  
```
[Next](episodes/00-intro-eported.pdf)
