---
editor_options: 
  markdown: 
    wrap: 72
---

# KEY - EDA with Numerical Data

YOUR NAME

-   [Before You Begin](#before-you-begin)
-   [EDA with Numerical Data!](#eda-with-numerical-data)
-   [By the end of this tutorial I should be able
    to…](#by-the-end-of-this-tutorial-i-should-be-able-to)
    -   [1: Load the proper libraries before I start exploring the
        data.](#1-load-the-proper-libraries-before-i-start-exploring-the-data)
        -   [1.1: Tasks and Questions](#11-tasks-and-questions)
    -   [2: View the data](#2-view-the-data)
        -   [2.1: Tasks and Questions](#21-tasks-and-questions)
        -   [2.2: Tasks and Questions](#22-tasks-and-questions)
    -   [3: Build a histogram.](#3-build-a-histogram)
        -   [3.1: Tasks and Questions](#31-tasks-and-questions)
        -   [3.2: Tasks and Questions](#32-tasks-and-questions)
    -   [4: Build a density curve.](#4-build-a-density-curve)
        -   [4.1: Tasks and Questions](#41-tasks-and-questions)
    -   [5: Generate summary statistics to support a histogram and
        density
        curve.](#5-generate-summary-statistics-to-support-a-histogram-and-density-curve)
        -   [5.1: Tasks and Questions](#51-tasks-and-questions)
    -   [6: Adjust the histogram to include some data visualization best
        practices.](#6-adjust-the-histogram-to-include-some-data-visualization-best-practices)
        -   [6.1: Adding Labels](#61-adding-labels)
        -   [6.2: Adjusting Bins](#62-adjusting-bins)
        -   [6.3: Adjusting Scales](#63-adjusting-scales)
        -   [6.4: Clean Up](#64-clean-up)
        -   [6.5: Fill the Bars and Add
            Color](#65-fill-the-bars-and-add-color)
        -   [6.6: Put it all together.](#66-put-it-all-together)
        -   [7 Bonus:](#7-bonus)

## Before You Begin {#before-you-begin}

Be sure to **read everything** as the structure of the tutorial is such
that everything builds upon the items that came before it.

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
Any text highlighted in this red border will require you to either
**edit and run a code chunk or just run a code chunk**.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
Any text highlighted in this blue border will **require you to answer a
question**. You can type your response directly in the box with the blue
border.
:::

# EDA with Numerical Data! {#eda-with-numerical-data}

You’ve just finished one tutorial that got your wheels turning! If that
was your first time writing code, congrats on taking the dive into an
exciting new challenge!

Over the past few weeks, you’ve built an understanding of the types of
visualizations you can create, the statistics you can generate to
support those visualization, how to uncover and describe insights
gleaned from those calculations and visualizations. With that strong
foundation laid down, you are now **ready to explore real data to begin
uncovering the stories hidden within them.**

# By the end of this tutorial I should be able to… {#by-the-end-of-this-tutorial-i-should-be-able-to}

1: Load the proper libraries before I start exploring the data.

2: View the data

3: Build a histogram.

4: Build a density curve.

5: Generate summary statistics to support a histogram and density curve.

6: Adjust histogram to include some data visualization best practices.

## 1: Load the proper libraries before I start exploring the data.

For this tutorial, we will use two packages: `tidyverse` and
`openintro`.

`Tidyverse` is made up of a collection of packages that include tools
making it easier to visualize, summarize, and wrangle data.

`Openintro` is a package referenced in our textbook, Introduction to
Modern Statistics. Among other things, it includes a number of datasets.
During this tutorial, you will generate similar visualizations to those
seen when reading.

### 1.1: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
1.  Run the following code.
:::

``` r
library(tidyverse)
```

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
```

``` r
library(openintro)
```

```         
Loading required package: airports
Loading required package: cherryblossom
Loading required package: usdata
```

## 2: View the data

For this tutorial, we will use the dataset titled `loan50` provided in
the `openintro` package. You first read about this dataset in [Chapter 1
of Introduction to Modern
Statistics](https://openintro-ims.netlify.app/data-hello#data-basics).

The data in `loan50` includes 50 randomly sampled loans offered through
Lending Club, which is a peer-to-peer lending company.

Again, the Name_of_the_Dataset is `loan50`.

### 2.1: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
1.Run the following code to view the data.
:::

``` r
view(loan50)
```

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
2.  Run the following code to get a glimpse of the data.
    -   This will show you the number of observations, the number of
        variables, the names of them, and the type of them.

    -   The names of the variables listed down the first column just
        after each \$.

    -   The type is listed inbetween these symbols \<\>. For more
        information on this, [please feel free to click through this
        slide
        deck.](https://sta199-f25.github.io/slides/05-exploratory-data-analysis-I-slides.html#/variable-types-district)

    -   The names of the variables listed down the first column just
        after each \$.
:::

``` r
glimpse(loan50)
```

```         
Rows: 50
Columns: 18
$ state                   <fct> NJ, CA, SC, CA, OH, IN, NY, MO, FL, FL, MD, HI…
$ emp_length              <dbl> 3, 10, NA, 0, 4, 6, 2, 10, 6, 3, 8, 10, 10, 2,…
$ term                    <dbl> 60, 36, 36, 36, 60, 36, 36, 36, 60, 60, 36, 36…
$ homeownership           <fct> rent, rent, mortgage, rent, mortgage, mortgage…
$ annual_income           <dbl> 59000, 60000, 75000, 75000, 254000, 67000, 288…
$ verified_income         <fct> Not Verified, Not Verified, Verified, Not Veri…
$ debt_to_income          <dbl> 0.55752542, 1.30568333, 1.05628000, 0.57434667…
$ total_credit_limit      <int> 95131, 51929, 301373, 59890, 422619, 349825, 1…
$ total_credit_utilized   <int> 32894, 78341, 79221, 43076, 60490, 72162, 2872…
$ num_cc_carrying_balance <int> 8, 2, 14, 10, 2, 4, 1, 3, 10, 4, 3, 4, 3, 2, 3…
$ loan_purpose            <fct> debt_consolidation, credit_card, debt_consolid…
$ loan_amount             <int> 22000, 6000, 25000, 6000, 25000, 6400, 3000, 1…
$ grade                   <fct> B, B, E, B, B, B, D, A, A, C, D, A, A, A, A, E…
$ interest_rate           <dbl> 10.90, 9.92, 26.30, 9.92, 9.43, 9.92, 17.09, 6…
$ public_record_bankrupt  <int> 0, 1, 0, 0, 0, 0, 0, 0, 0, 1, 0, 0, 0, 0, 0, 0…
$ loan_status             <fct> Current, Current, Current, Current, Current, C…
$ has_second_income       <lgl> FALSE, FALSE, FALSE, FALSE, FALSE, FALSE, FALS…
$ total_income            <dbl> 59000, 60000, 75000, 75000, 254000, 67000, 288…
```

**Are you confused? I certainly would be!** Before diving into any
exploration, you need to first be sure you understand the data

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
3.  Click this link
    <https://www.openintro.org/data/index.php?data=loan50> to learn more
    about this dataset.
:::

**For the next five questions, use information from the link you just
read and the code your ran in questions 1 and 2 of this section.**

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
4.  From what platform was this data taken?

    This data was taken from Lending Club.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
5.  What does that platform do?

    Lending Club is an online platform this makes it possible for people
    to lend to one another.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
6.  What are the observational units in the `loan50` dataset?

    The observational units are loans given out on Lending Club.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
7.  How many observations are there?

    There are 50 loans in this data frame.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
8.  How many variables are there?

    There are 18 variables.
:::

***\*\*Important Note: or the rest of this tutorial, you will work with
a smaller version of this data set. We’ll keep the 50 rows, but select 7
of the 18 variables we started with.***

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
9.  Run the code below makes this new and smaller data frame.
:::

``` r
loan50_small <- loan50 |>
                select(loan_amount, interest_rate, term, grade, 
                       state, total_income, homeownership)
```

***To better understand the code above, this is how you could read it in
plain English:***

We will name a new data frame `loan50_small`. To do so we take the
`loan50` data AND THEN

`select` the variables
`loan_amount, interest_rate, term, grade, state, total_income, homeownership`.

### 2.2: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
1.  What is the name of the new data frame created in the lines of code
    above? Type the name EXACTLY how it appears above. (Hint: Copying
    and pasting is your friend! Also, if you double click on text it
    will highlight it for you. Give it a try!)

    loan50_small
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
2.  When you are reading code and come across the symbol \|\>, which is
    called pipe, you should say, “And \_\_\_\_\_\_.” *Tip: read the text
    just below the code chunk above to help you answer this question.*

Then
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
3.  List all of the variables and state whether they are categorical or
    numerical? Type the names of the variables EXACTLY how they appear
    in the code above. *Hint: Copying and pasting is your friend!*

`loan_amount` - numerical

`interest_rate` - numerical

`term` - numerical

`grade` - categorical

`state` - categorical

`total_income` - numerical

`homeownership` - numerical
:::

## 3: Build a histogram.

Throughout this year, you’ve learned how to ask statistical questions
and choose the visualizations and statistics that will allow you to
begin answering those questions.

Your process of doing those things has gone something like…

To answer this question I…

-   need this data frame

-   specifically need this variable

-   need to put it on the \_\_\_\_\_ axis

-   and I want to make this visualization.

Fortunately, the structure of the code you will write to create
visualizations in R follows this same structure.

The code below reads like this…

-   Use the Name_of_Data_Frame AND THEN

-   Make a plot with the following aesthetics: the x-axis is this
    Numerical_Variable and ADD

-   A histogram.

``` r
loan50_small |>
  ggplot(aes(x = loan_amount)) +
  geom_histogram()
```

```         
`stat_bin()` using `bins = 30`. Pick better value `binwidth`.
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/example%20histogram-1.png)

### 3.1: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
1.  Run the code above.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
2.  What is a question that could be explored with the histogram created
    by the code above?

    What size loans tend to be given out on Lending Club?
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
3.  Describe the shape of the distribution and what that tells you about
    the loan amounts.

The distribution of loans is skewed to the right, meaning that most
loans are less than \$20,000 while a small number of loans are \$30,000
or more.
:::

### 3.2: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
1.  Write a statistical question that could be answered by creating a
    histogram using the data frame named `loan50_small`. *(use a
    different variable than the one used in 3.1)*

    What is the typical income of someone taking a loan out on Lending
    Club?
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
2.  What is the numerical variable you would need to use to create a
    histogram to help answer your question. Write the name EXACTLY as it
    appears in the data frame.

total_income
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
3.  In the code below, replace `NAME_OF_DATA_FRAME` with loan50_small.
:::

``` r
loan50_small |>
  ggplot(aes(x = total_income)) +
  geom_histogram()
```

```         
`stat_bin()` using `bins = 30`. Pick better value `binwidth`.
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/your%20first%20histogram-1.png)

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
4.  In the code above, replace `NUMERICAL_VARIABLE` with the name you
    wrote in question 2 and then run the chunk of code.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
5.  Describe the distribution. Be sure to comment on the shape, center,
    and spread of the distribution.

The interest rates on Lending Club loans tend to fall below 11%. The
median interest appears to be 10%. The distribution in skewed to the
right, which means that while many of interest rates are below 11%,
there are a few loans that had interest rates of 20 to 28 percent.
:::

## 4: Build a density curve.

### 4.1: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
1.  Copy the code from above that was used to create a histogram showing
    the distribution of `loan_amount` and paste it into the gray section
    below question 3 of this section. The grey space has the label your
    first density curve.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
2.  If you are about to change your visualization from a histogram to a
    density curve, will you need to change the variable listed on the
    x-axis?

No, you will not need to change the variable on the x-axis as we are
still going to explore the distribution of loan amounts.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
3.  In the code below, change geom_histogram() to geom_density() and
    then run the entire code chuck.
:::

``` r
loan50_small |>
  ggplot(aes(x = loan_amount)) +
  geom_density()
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/your%20first%20density%20curve-1.png)

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
4.  Bonus: True or False - You can create a density curve for a discrete
    numeric variable. (Explain your answer.)

No. A density curve is continuous and therefore can only be used for
numeric variables taht are continuous.
:::

## 5: Generate summary statistics to support a histogram and density curve.

As we’ve talked about a number of times in class, let the computer do
the work when it comes to calculations. You won’t reach for your phone
calculator or a piece of paper to calculate statistics for large
datasets.

The structure of the code used to perform these calculations goes like
this…

-   Look at this data AND THEN

-   select this/these variable(s) AND THEN

-   generate the summary statistics

Below is the code to generate the summary statistics for the histogram I
created.

***Important Notes:***

-   *The word before the = will be the name of the calculation. This
    name can be anything, though it should help remind you what
    calculation you are doing.*

-   *The text you see after = is the actual code that will perform the
    calculation. This has to be exactly as you see it.*

-   The text inside the () is the variable on which you want that
    calculation run.

-   `Mean = mean(loan_amount)` For this line, you are going to name the
    calculation `Mean` and have the computer run the `mean` function for
    the variable `loan_amount` variable.

``` r
loan50_small |>
  select(loan_amount) |>
  summarise(
    Mean = mean(loan_amount),
    Median = median(loan_amount),
    SD = sd(loan_amount),
    IQR = IQR(loan_amount),
    Q_one = quantile(loan_amount, 0.25),
    Q_three = quantile(loan_amount, 0.75),
    minimum_value = min(loan_amount),
    maximum_value = max(loan_amount),
    number_observations = n()
  )
```

```         
# A tibble: 1 × 9
   Mean Median     SD   IQR Q_one Q_three minimum_value maximum_value
  <dbl>  <dbl>  <dbl> <dbl> <dbl>   <dbl>         <int>         <int>
1 17083  15500 10455. 16875  7125   24000          3000         40000
# ℹ 1 more variable: number_observations <int>
```

### 5.1: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
1.  Write the code that would generate the summary statistics that could
    be used to help answer the questions **you wrote in 3.2**. *Hint:
    Copy and Paste is your friend!*
:::

``` r
loan50_small |>
  select(total_income) |>
  summarise(
    Mean = mean(total_income),
    Median = median(total_income),
    SD = sd(total_income),
    IQR = IQR(total_income),
    Q_one = quantile(total_income, 0.25),
    Q_three = quantile(total_income, 0.75),
    minimum_value = min(total_income),
    maximum_value = max(total_income)
  )
```

```         
# A tibble: 1 × 8
     Mean Median     SD   IQR Q_one Q_three minimum_value maximum_value
    <dbl>  <dbl>  <dbl> <dbl> <dbl>   <dbl>         <dbl>         <dbl>
1 105221.  78750 68142. 59000 60000  119000         28800        325000
```

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
2.  Copy and Paste the code for your histogram and your summary stats
    into the space below so that you have both your visualization and
    statistics in one location.

3.  Run the code.
:::

``` r
loan50_small |>
  ggplot(aes(x = total_income)) +
  geom_histogram()
```

```         
`stat_bin()` using `bins = 30`. Pick better value `binwidth`.
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/viz%20and%20stats-1.png)

``` r
loan50_small |>
  select(total_income) |>
  summarise(
    Mean = mean(total_income),
    Median = median(total_income),
    SD = sd(total_income),
    IQR = IQR(total_income),
    Q_one = quantile(total_income, 0.25),
    Q_three = quantile(total_income, 0.75),
    minimum_value = min(total_income),
    maximum_value = max(total_income)
  )
```

```         
# A tibble: 1 × 8
     Mean Median     SD   IQR Q_one Q_three minimum_value maximum_value
    <dbl>  <dbl>  <dbl> <dbl> <dbl>   <dbl>         <dbl>         <dbl>
1 105221.  78750 68142. 59000 60000  119000         28800        325000
```

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
4.  Describe the distribution of the numerical variable you choose when
    creating the data visualization. Be sure to comment on the shape,
    center, and spread of the distribution using statistical vocabulary
    you have learned in this class and the appropriate statistics you
    generated.

The distribution of total income for folks getting loans on Lending Club
is skewed to the right with total incomes tending to be around \$78,750.
The middle 50% of total incomes range from \$60,000 to \$119,000. While
75% of folks getting a loan have incomes less that \$119,000, just 5
people have incomes over \$200,000.
:::

## 6: Adjust the histogram to include some data visualization best practices.

You may be saying to yourself, “Those histograms didn’t look that great
and were poorly labeled.” If you said something like that, you are
correct.

### 6.1: Adding Labels

In this section, we will add on various **layers** to our code to adjust
different aspects of the **visualization used to analyze the
distribution of the variable `loan_amount`.**

Let’s start by adding a title, subtitle, and labels to each axis of the
*first histogram made in this tutorial*. Notice in the code below how
the first four lines are the exact same as what we started with above.
To add labels to our visualization, we use `labs`.

#### 6.1: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
1.  Add a title, subtitle, and labels for each axis by typing in between
    each `""`.

2.  Run the code chunk
:::

``` r
loan50_small |>
  ggplot(aes(x = loan_amount)) +
  geom_histogram() +
  labs(
    title ="What size loans to people get at Lending Club?",
    subtitle = "Sample of 50 loans from Lending Club",
    x = "Loan Amount ($)",
    y = "Number of Loans"
  )
```

```         
`stat_bin()` using `bins = 30`. Pick better value `binwidth`.
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/add%20labels%20to%20my%20histogram-1.png)

### 6.2: Adjusting Bins

Since you’ve calculated the summary statistics above you know the loan
amounts have a large range. Also, when looking at the visualization,
it’s not clear as to what the bin width is. When choosing a bin width,
it’s important to **choose one that is relevant**. Also, the bin width
should help to create a visualization that does not either oversimplify
the distribution or create unnecessary clutter. Certainly, those last
two statements are not very definitive. This is where the creativity and
clear and effective communication come into play.

In the code below, you will see that there is NOT a new layer. We added
an **element** to the histogram so it adjusts the bin width.

#### 6.2: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
1.  What bin width do you think will be best for the histogram showing
    the distribution of loan amounts? (see histogram and statistics)

I would argue that a binwidth of 2500 would better suit this example.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
2.  Write the number you choose in question 1 after `binwidth =` in the
    code below.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
3.  Write in the title, subtitle, and labels for each axis into the code
    below.

4.  Run the chunk of code.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
5.  After running it, adjust the binwidth to a value that you think
    creates the best possible histogram.
:::

``` r
loan50_small |>
  ggplot(aes(x = loan_amount)) +
  geom_histogram(binwidth = 2500) +
  labs(
    title ="What size loans to people get at Lending Club?",
    subtitle = "Sample of 50 loans from Lending Club",
    x = "Loan Amount ($)",
    y = "Number of Loans"
  )
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/adjust%20the%20bins-1.png)

### 6.3: Adjusting Scales

You may also want to adjust the **scales** on the x and y axes.

Be careful when adjusting scales!! Do not distort the story being told!
Whole books are written about topics like this so we’ll talk more about
this as we continue to build visualizations.

A good general rule, keep it simple!

#### 6.3: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
1.  Copy the code used to generate the histogram in 6.2 Tasks and
    Questions #5 and paste it into the gray space below.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
2.  When you have a continuous variable on the x-axis, you can use the
    following to adjust the scale:

`scale_x_continuous(limits = c(min, max), breaks = seq(min, max, ticks))`

Edit the words min, max, and ticks in the code you see in the previous
line. min = minimum value for x-axis max = maximum value for x-axis
ticks = where you want the markings along the x-axis.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
3.  Put a `+` at the end of the code you pasted into the section below
    and then jump to the next line.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
4.  Paste the scale_x_continuous code you adjusted into the last row of
    the code chunk below.
:::

``` r
loan50_small |>
  ggplot(aes(x = loan_amount)) +
  geom_histogram(binwidth = 2500) +
  labs(
    title ="What size loans to people get at Lending Club?",
    subtitle = "Sample of 50 loans from Lending Club",
    x = "Loan Amount ($)",
    y = "Number of Loans"
  ) +
  scale_x_continuous(breaks = seq(0, 45000, 5000)) +
  coord_cartesian(xlim = c(0, 45000))
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/adjust%20scales-1.png)

### 6.4: Clean Up

Alright, you have done a lot to improve the original histogram that
appeared! Let’s keep getting your visualization ready for prime time!

Removing clutter is often a wise choice when designing a visualization.
That is what you will do now.

#### 6.4: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
1.  Copy and past the code from 6.3 into the gray space below.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
2.  At the end of the line with `scale_x_continuous` put a `+`
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
3.  On the next line write in `theme_minimal()` and then run the entire
    chunk of code.
:::

``` r
loan50_small |>
  ggplot(aes(x = loan_amount)) +
  geom_histogram(binwidth = 2500)+
  labs(
    title ="What size loans to people get at Lending Club?",
    subtitle = "Sample of 50 loans from Lending Club",
    x = "Loan Amount ($)",
    y = "Number of Loans"
  ) +
  scale_x_continuous(limits = c(0, 45000), breaks = seq(0, 45000, 5000)) +
  coord_cartesian(xlim = c(0, 45000)) +
  theme_minimal()
```

```         
Warning: Removed 2 rows containing missing values or values outside the scale range
(`geom_bar()`).
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/clean%20up-1.png)

### 6.5: Fill the Bars and Add Color

#### 6.5: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
1.  What are Lending Clubs 2 main corporate colors? Hint: Google is your
    friend.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #FF585D; border-radius: 5px;"}
2.  Do a Google search for Lending Clubs corporate colors in hex code.
    Hex code is used to get specific colors and is formatted with \#
    followed by a combination of 6 letters and/or numbers. White for
    example is #ffffff.
    -   Copy one of the color hex codes into the `""` that come after
        `fill =` .

    -   Copy the other color into the `""` after `color =` .
:::

``` r
loan50_small |>
  ggplot(aes(x = loan_amount)) +
  geom_histogram(binwidth = 2500, fill = "#002a4e", color = "#ef4123") +
  labs(
    title ="What size loans to people get at Lending Club?",
    subtitle = "Sample of 50 loans from Lending Club",
    x = "Loan Amount ($)",
    y = "Number of Loans"
  ) +
  scale_x_continuous(limits = c(0, 45000), breaks = seq(0, 45000, 5000)) +
  coord_cartesian(xlim = c(0, 45000)) +
  theme_minimal()
```

```         
Warning: Removed 2 rows containing missing values or values outside the scale range
(`geom_bar()`).
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/fill%20and%20color-1.png)

### 6.6: Put it all together.

You’ve done a lot so far! Congrats! One by one, you adjusted various
elements of the histogram showing the loan amount data. **Now you are
going to work with the histogram you created in part 3.2 questions 3 and
4.**

#### 6.6: Tasks and Questions

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
1.  Copy and paste the code you wrote for 3.2 question numbers 3 and 4
    into the gray space below and then run the code.
:::

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
2.  Adjust the following elements of the histogram:

-   labels.
-   bin width
-   axis scales
-   theme
-   fill and color
:::

``` r
loan50_small |>
  ggplot(aes(x = total_income)) +
  geom_histogram(binwidth = 25000, fill = "#002a4e", color = "#ef4123") +
  labs(
    title ="What incomes do people who get loans from Lending Club tend to have?",
    subtitle = "Sample of 50 loans from Lending Club",
    x = "Total Income ($)",
    y = "Number of Loans"
  ) +
  scale_x_continuous(limits = c(0, 400000), breaks = seq(0, 400000, 50000)) +
  theme_minimal()
```

```         
Warning: Removed 2 rows containing missing values or values outside the scale range
(`geom_bar()`).
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/put%20it%20all%20together-1.png)

### 7 Bonus:

#### Bonus Tasks

::: {style="color: black; background-color: white; padding: 15px; border: 5px solid #006CB3; border-radius: 5px;"}
1.  Turn the histogram you just made into a density curve.

2.  Add a vertical line that represents the median of the data being
    visualized. *(Hint: [Gemini](https://gemini.google.com/) or
    [CoPilot](https://copilot.microsoft.com/) can be very helpful.)*
:::

``` r
loan50_small |>
  ggplot(aes(x = total_income)) +
  geom_density(fill = "#002a4e", color = "#ef4123", alpha = 0.5) +
  geom_vline(aes(xintercept = median(total_income)),
             color = "grey",
             linetype = "dashed",
             size = 1) +
  labs(
    title ="What incomes do people who get loans from Lending Club tend to have?",
    subtitle = "Sample of 50 loans from Lending Club",
    x = "Total Income ($)",
    y = ""
  ) +
  scale_x_continuous(limits = c(0, 400000), breaks = seq(0, 400000, 50000)) +
  theme_minimal() +
  theme(axis.text.y = element_blank())  # Removes y-axis numbers
```

```         
Warning: Using `size` aesthetic for lines was deprecated in ggplot2 3.4.0.
ℹ Please use `linewidth` instead.
```

![](2_KEY_EDA_Numerical_Data_files/figure-commonmark/bonus%20median%20line-1.png)
