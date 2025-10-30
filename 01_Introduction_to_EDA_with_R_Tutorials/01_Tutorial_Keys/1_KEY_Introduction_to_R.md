# KEY - Tutorial 1: Introduction to R and RStudio
KEY

- [Before You Begin](#before-you-begin)
- [Welcome to R and RStudio!](#welcome-to-r-and-rstudio)
- [By the end of this tutorial I should be able
  to…](#by-the-end-of-this-tutorial-i-should-be-able-to)
  - [1: Describe what a package is and know when to run a
    library.](#1-describe-what-a-package-is-and-know-when-to-run-a-library)
    - [1.1: Tasks and Questions](#11-tasks-and-questions)
  - [2: Use R as a calculator](#2-use-r-as-a-calculator)
    - [2.1: Tasks and Questions](#21-tasks-and-questions)
  - [3: Name functions](#3-name-functions)
    - [3.1: Tasks and Questions](#31-tasks-and-questions)
  - [4: Create a vector](#4-create-a-vector)
    - [4.1: Tasks and Questions](#41-tasks-and-questions)
  - [5: Create a data frame](#5-create-a-data-frame)
    - [5.1: Tasks and Questions](#51-tasks-and-questions)
    - [5.2: Tasks and Questions](#52-tasks-and-questions)

## Before You Begin

Be sure to **read everything** as the structure of the tutorial is such
that everything builds upon the items that came before it.

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;">

Any text highlighted in this red border will require you to either
**edit and run a code chunk or just run a code chunk**.

</div>

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;">

Any text highlighted in this blue border will **require you to answer a
question**. You can type your response directly in the box with the blue
border.

</div>

# Welcome to R and RStudio!

Congratulations! You are taking the first step toward becoming a data
scientist. R is a powerful statistical programming language and RStudio
on Posit Cloud, the IDE (integrated development area), is the place
where we will do our work with R.

This tutorial is the first in a series of tutorials that will help you
begin to learn how to to explore data using R.

# By the end of this tutorial I should be able to…

1: Describe what a package is and know when to run a library.

2: Use R as a calculator

3: Name functions

4: Create a vector

5: Create a data frame

## 1: Describe what a package is and know when to run a library.

If you were to build something, you would need to get some tools and
organize those tools in various toolboxes. To build a house you’d need a
variety of toolboxes because there are many different types of things
you need to get done. For example, building the frame would require
different set of tools than painting all of the rooms.

When working with R you can think of **packages as your toolboxes**.
They are made up of various functions that make certain tasks easier.
However, before using them, you first need to go buy them. Once you
bought them and brought them home, you then pick them up off the shelf.
Running the line `library(package_name)` is equivalent to grabbing your
toolbox off the shelf before you start to work. If you don’t grab the
toolbox off of the shelf or, in other words, run the libraries, your
code will not run.

***Long story short…always run the libraries code first!***

`tidyverse` is a very robust package that we will use all of the time.

### 1.1: Tasks and Questions

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;">

1.  ***Run the following code by clicking the green play button located
    on the top right of the code chunk below.***

    *(Note:You can run code by either clicking the green play button or
    highlighting the code you want to run and hitting command+return on
    your keyboard. The green play button will run the whole chunk while
    the keyboard option will mentioned above will only run the code
    you’ve selected.)*

</div>

``` r
library(tidyverse)
```

    ── Attaching core tidyverse packages ──────────────────────── tidyverse 2.0.0 ──
    ✔ dplyr     1.1.4     ✔ readr     2.1.5
    ✔ forcats   1.0.1     ✔ stringr   1.5.2
    ✔ ggplot2   4.0.0     ✔ tibble    3.3.0
    ✔ lubridate 1.9.4     ✔ tidyr     1.3.1
    ✔ purrr     1.1.0     
    ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ✖ dplyr::filter() masks stats::filter()
    ✖ dplyr::lag()    masks stats::lag()
    ℹ Use the conflicted package (<http://conflicted.r-lib.org/>) to force all conflicts to become errors

## 2: Use R as a calculator

At its most basic level, R can be used as a calculator. **Keep your
phone in your pocket or backpack** and stay on task if you need to
perform a calculation.

### 2.1: Tasks and Questions

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;">

1.  Below is an example of a calculation. In the gray space (aka code
    chunk) below, write your own calculation and then hit the play
    button.

</div>

``` r
#Example
3+2
```

    [1] 5

``` r
#1 - Type your calculation below

4+5
```

    [1] 9

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;">

2.  Write another calculation that requires you to add two numbers
    together and then divide that sum by 10

</div>

``` r
#2 - Type your calculation below

(5+15)/10
```

    [1] 2

## 3: Name functions

As you start to explore data, you will have many lines of code that
wrangles your data and creates many statistics and visualizations.
Staying organized is important. One way to do that is naming certain
chunks of code. When you want to run that code again, you **run the
name** of the code instead of the whole long chunk.

`name <- thing you want to name` *(Note: the \<- is made using the
greater than and the minus sign)*

(Note: That little arrow is made by typing the greater than sign and
minus sign on keyboard)

Naming tips:

- use \_ instead of spaces. Example john_adams
- keep it short yet something that will help you remember what it
  represents. Ex. `grades_hist` could be used to name a histogram
  showing the distributions of grades.

### 3.1: Tasks and Questions

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;">

1.  Copy one of the calculations you did in 2.1 Tasks and Questions and
    paste it into the code chunk below.

2.  Click in front of the first number in your calculation and type in a
    name for your calculation and then add the arrow `<-`. Here is an
    example: my_first_calculation \<- 3+2

3.  Type the name of your calculation on the line below what you did for
    question 2 and then run the code.

4.  Create and name 2 more calculations.

5.  Use the **names** to multiply all of your equations together.

</div>

``` r
my_first_calculation <- 4+5
my_first_calculation
```

    [1] 9

``` r
second_calculation <- 5*6
second_calculation
```

    [1] 30

``` r
third_calculation <- 12/4
third_calculation
```

    [1] 3

``` r
my_first_calculation*second_calculation*third_calculation
```

    [1] 810

## 4: Create a vector

A vector is a sequence of either numbers or characters. Here are some
examples.

**Here is an example of a numeric vector**

In this example, we create a vector of numeric values and then give it a
name. `rivers_numeric_vector` is written on a line of its own so we can
see a printout of the vector. Run the code to see what happens.

``` r
rivers_numeric_vector <- c(1915,333,6,12)

rivers_numeric_vector
```

    [1] 1915  333    6   12

**In this example, we create a vector of characters and then give it a
name.**

Remember, run the name of the vector by itself to see it.

``` r
rivers_character_vector <- c("red", "white", "black", "gray")

rivers_character_vector
```

    [1] "red"   "white" "black" "gray" 

### 4.1: Tasks and Questions

In the gray space below…

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;">

1.  Create and name a numeric vector that has 4 observations.

</div>

``` r
my_numeric_vector <- c(1,2,3,4)
my_numeric_vector
```

    [1] 1 2 3 4

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;">

2.  Create and name a character vector that has 4 observations.

</div>

``` r
my_char_vector <- c("Rivers", "RSC", "Campe Nonesuch", "Rivers Fan Zone")
my_char_vector
```

    [1] "Rivers"          "RSC"             "Campe Nonesuch"  "Rivers Fan Zone"

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;">

Bonus: Name the significance of each number in the vector created above
titled, `rivers_numeric_vector`.

c(1915,333,6,12)

1915 = The year Rivers School was founded

333 = The street number for Rivers School

6 = The first grade level at the Rivers School

12 = The highest grade level at the Rivers School

</div>

## 5: Create a data frame

As you’ve learned before, we will want our data frames organized as tidy
data frames. When data is organized in such a way, each column is a
variable and the rows are for each observational unit or case.

Most often, we will load in data to Rstudio or use data included within
various packages. For this exercise, we will build a data frame.

Here is an example of a data frame. Use it to answer the tasks and
questions section below.

``` r
rivers_data <- data.frame(
                    important_numbers = c(1915,333,6,12),
                    riv_colors = c("red", "white", "black", "gray")
                    )
rivers_data
```

      important_numbers riv_colors
    1              1915        red
    2               333      white
    3                 6      black
    4                12       gray

### 5.1: Tasks and Questions

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;">

1.  What is the name of this data frame? Type it EXACTLY how it appears
    in the code above.

    The name of the data frame is rivers_data.

</div>

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;">

2.  How many variables are in this data frame and what are their names?
    Type the names EXACTLY how they appear in the code above.

    There are two variables. important_numbers and riv_colors

</div>

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;">

3.  What types of variables are they?

    important_numbers is a numeric variable. riv_colors is a categorical
    variable.

</div>

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;">

4.  How many observations are in this data frame?

    There are 4 observations.

</div>

### 5.2: Tasks and Questions

<div style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;">

1.  In the gray space below, create and name a data frame that includes
    two variables and 4 observations.

</div>

``` r
# 1: Create and name your data frame in the lines below.

answer_key_data <- data.frame(
  my_numeric_vector = c(1,2,3,4), 
  my_char_vector = c("Rivers", "RSC", "Campe Nonesuch", "Rivers Fan Zone")
)

answer_key_data
```

      my_numeric_vector  my_char_vector
    1                 1          Rivers
    2                 2             RSC
    3                 3  Campe Nonesuch
    4                 4 Rivers Fan Zone
