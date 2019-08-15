An Introduction to the Tidyverse | Session One
====================================
author: Tim Hargreaves
date: [Session Date TBC]
width: 1440
height: 900



Accessing Resources
====================================

These slides, as well as other resources for the course can be found on the corresponding GitHub repository:

https://github.com/THargreaves/introtothetidyverse

I will also send a copy out via email at the end of the session.

Introductions
====================================
type: section

About Me
====================================
type: sub-section

Who Am I?
====================================
left: 70%

* Tim Hargreaves
* Ex-student of Alsager Sixth Form
* Studying Mathematics and Statistics at the University of Warwick
* Work heavily with data and machine-learning models
* Currently undertaking a year-long placement at AstraZeneca
* Previously worked with dunnhumby and Bet365

***

![Warwick Logo](images/company_logos/warwick_logo.png)

![AstraZeneca Logo](images/company_logos/astrazeneca_logo.jpg)

![dunnhumby Logo](images/company_logos/dunnhumby_logo.png)

![Bet365 Logo](images/company_logos/bet365_logo.png)

Contact Details
====================================

* Best way to contact me is via email: tim.hargreaves@icloud.com
* Feel free to connect with me on LinkedIn: www.linkedin.com/in/tim-hargreaves/
* Check out my blog for data science applications: www.ttested.com

About The Course
====================================
type: sub-section

Prerequisites
====================================

* The only real expectation of this course is that you have general numerical literacy and can navigate around a computer
* Previous programming experience will make learning easier but is not expected at all

Basis of the Course
====================================
left: 70%

* Based on the book *R for Data Science* by Hadley Wickham & Garrett Grolemund
* Many sections have been removed (originally ~500 pages)
* Freely available to read at [r4ds.had.co.nz](r4ds.had.co.nz)

This course differs from R4DS in two ways:

* More focus on immediate gains rather than complete mastery of the tidyverse
* Examples centre around the use of the A-Level weather dataset

***

![R for Data Science Cover](images/r4ds_cover.png)

What Will This Course Teach You?
====================================

This course aims to teach you how to:

* Set up R, RStudio, and the tidyverse on your computer
* Import a data set from the web and clean it
* Wrangle a data set from one form to another
* Transform a data set to help answer a question
* Visualise a data set using plots and graphs
* Communicate data honestly and effectively

What Won't This Course Teach You?
====================================

Sections of the R4DS book not covered in this course include:

* Working with relational (multi-table) data sets (maybe?)
* Handling non-categorical text data
* Iterative techniques
* Statistical modelling
* Communicating results with wider audiences

Why Bother Learning the Tidyverse?
====================================

**Why learn data analytics?**

* Data skills are currently in high demand
* In our modern economy, almost all professions process data in some way

**Why use the tidyverse?**

* Far more powerful and expandable than Excel or Tableau
* Open-source and free to use (unlike SAS or SPSS)
* A large and beginner-friendly community
* A lot more intuitive than more conventional programming languages (Python, Julia)

Course Agenda
====================================

* The course will be ran weekly for six weeks
* The last session will be a DataViz Battle (with prizes)
* Each session will be split into three parts:
  * Recap of the last session and answers to any common questions I have received
  * Presentation covering new material alongside live-coding examples
  * Time to apply the new techniques to a problem sheet
  
The Tidy-what?
====================================
type: section

Foundations
====================================
type: sub-section

What is R?
====================================

* Programming language for statistical computing and graphics
* Built upon an historic language (S) which was developed in the mid-70s
* Known for being highly extensible
* Completely free and open-source with a large, friendly community

R is an incredibly powerful tool. It can be used for machine learning, statistical modelling, big data, and much more. It is also capable of producing websites, interactive notebooks, and presentations (such as this one!).

Setting Up R
====================================

**Installation**

* Go to [CRAN](https://cran.r-project.org/), the *comprehensive R archive network*
* Select the download link that matches your operating system
* Choose the `base` installation and download the latest version
* Install as you would any other program

**Running**

* If the installation was successful, you will have a new entry in your start menu called *R x64 [Version Number]*
* Clicking this will open a program in which you can write R code

Problem:
====================================
type: alert

The standard R code editor is difficult to use, missing useful features, and frankly quite ugly

Solution:
====================================
type: prompt

Install RStudio and use it on top of R

What is RStudio?
====================================

* Integrated development environment (IDE) specifically made for programming in R
* Contains a rich set of features to allow you to code in R with less hassle
* Displays your code and its output in a much clearer way and gives you access to extra features such as help files, code history, and environment variables

Essentially, unless you are trying to provoke a headache, it is advised to do all R programming in RStudio.

Setting Up RStudio
====================================

* The latest version of RStudio can easily be download from [www.rstudio.com/download](www.rstudio.com/download)
* This can also be reached by simply searching for RStudio
* Once installed, you can open the program and all of the behind-the-scenes communication with your R installation will be done automatically.

NB: RStudio does not work as a standalone program. You will still need R installed even if you intend to only write code in RStudio.

Navigating RStudio
====================================
left: 40%

* Opening RStudio will confront you with an interface similar to this
* It is likely though, that the code editor will be hidden, with the console taking up the whole of left hand side
* For the time being, we will type our code directly into the console

***

![RStudio Interface](images/rstudio_interface.png)

Running R Code
====================================

* R code can be executed by typing directly into the console and pressing the `enter` key
* For example, you can add together two numbers with


```r
1 + 2
```

```
[1] 3
```

* Here the first line shows what I typed into the console and the second shows the output that R gave us

The Tidyverse
====================================
type: sub-section

What is the Tidyverse?
====================================

* The power of R comes from its extendibility
* Whereas the built-in capabilities of R are somewhat limited, additional *packages* can be installed to let you do more powerful things
* A package is a collection of functions, data, and documentation which extend the usual capacity of R
* The tidyverse is a collection of packages for performing clean and efficient data analysis

What is the Tidyverse? (cont.)
====================================
left: 70%


* The packages in the tidyverse are each designed for a specific area of data analysis
* For example there are packages for data importing, visualisation, and data manipulation
* They share a common philosophy of data and so work completely naturally together

***

![Tidyverse Hex](images/tidyverse_hex.png)

Using the Tidyverse
====================================

* The tidyverse can be installed by running the following command in the RStudio console


```r
install.packages('tidyverse')
```

* You only need to install this package once per computer, though running the command multiple times will do no harm
* If you then wish to use the tidyverse, you must first run the command


```r
library('tidyverse')
```

* This must be re-run each time you open RStudio

Data Visualisation - ggplot2
====================================
type: section

Introduction
====================================
type: sub-section

Where Are We?
====================================

* When learning new data analytics techniques, it is useful to know where these new skills fit into the overall 'map' of data analytics
* Here is such a map (though there will be many other equally correct representations)

![Data Analysis Map - Visualise](images/data_analysis_map_visualise.png)

Where Are We? (cont.)
====================================

* By beginning this course by learning how to perform data visualisation, we are taking things slightly out of order
* The pay-off for learning data visualisation is very clear however and so we will start there and return to early topics in the future
* This means that, until next week, we will be forced to used datasets that are included in the tidyverse

What is ggplot2?
====================================
left: 70%

* `ggplot2` is one of the many packages included in the tidyverse
*  It allows you to easy construct stylish graphs using a coherent and consistent system
*  A `ggplot2` graph is follows the *grammar of graphics*, in which plots are built by adding layers one at a time

***

![ggplot2 Hex](images/ggplot2_hex.jpg)

First Steps
====================================
type: sub-section

The mpg Data Frame
====================================

* Before we plot our first graph, we need a dataset to work with
* Since we do not yet know how to import our own, let's use a built-in dataset - `mpg`


```r
mpg
```

```
# A tibble: 234 x 11
   manufacturer model displ  year   cyl trans drv     cty   hwy fl    class
   <chr>        <chr> <dbl> <int> <int> <chr> <chr> <int> <int> <chr> <chr>
 1 audi         a4      1.8  1999     4 auto~ f        18    29 p     comp~
 2 audi         a4      1.8  1999     4 manu~ f        21    29 p     comp~
 3 audi         a4      2    2008     4 manu~ f        20    31 p     comp~
 4 audi         a4      2    2008     4 auto~ f        21    30 p     comp~
 5 audi         a4      2.8  1999     6 auto~ f        16    26 p     comp~
 6 audi         a4      2.8  1999     6 manu~ f        18    26 p     comp~
 7 audi         a4      3.1  2008     6 auto~ f        18    27 p     comp~
 8 audi         a4 q~   1.8  1999     4 manu~ 4        18    26 p     comp~
 9 audi         a4 q~   1.8  1999     4 auto~ 4        16    25 p     comp~
10 audi         a4 q~   2    2008     4 manu~ 4        20    28 p     comp~
# ... with 224 more rows
```

The mpg Data Frame (cont.)
====================================

* This dataset contains observations collected by the EPA on 38 models of cars
* The variables in `mpg` include:
  * `displ` - a car's engine size (in litres)
  * `hwy` - a car's fuel efficiency on the highway (in miles per gallon)
* We can use this dataset to answer the question "do cars with larger engines use more fuel than cars with smaller engines?"
* You may know the answer to this already but can we make our answer more precise? Is the trend linear or non-linear? Are there any exceptions to the general trend?

Our First ggplot
====================================

* We can plot the desired graph using the following code


```r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy))
```

<img src="session_one_presentation-figure/unnamed-chunk-5-1.png" title="plot of chunk unnamed-chunk-5" alt="plot of chunk unnamed-chunk-5" style="display: block; margin: auto;" />

Breaking the Code Down
====================================


```r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy))
```

* We first start by calling the `ggplot()` function. This creates an empty graph which we can then add layers to
* We pass in the `mpg` data frame as the `data` argument so that `ggplot2` knows we will be using that for our plot
* We then use the `+` symbol to add a new layer. Specifically we a point geometry using the `geom_point()` function
* We need to tell `ggplot2` which variables in the data frame to map to the various aesthetics of the plot. In this case, we just specify the variables mapping to the x and y coordinates

A General Template
====================================

* In general, our code will look something like the following


```r
ggplot(data = <DATA>) +
  <GEOM_FUNCTION>(mapping = aes(<MAPPINGS>))
```

* All we have to do is fill in the blanks 
* For example, we may want to ask how highway and city mileage are related



Aside: Working With Dataframes
====================================
type: sub-section

Printing Dataframes
====================================

* An entire dataframe can be printed to the console simply by typing it's name


```r
mpg
```

* The first few rows of a dataframe can be printed using the `head()` function


```r
head(mpg)
```

* A specific number of rows can be printed by specifying the parameter `n`


```r
head(mpg, n = 3)
```

* `tail()` works the same as `head()` but gives you the bottom few rows. It also has an optional `n` parameter

Dataframe Overviews
====================================

* The `str()` function displays the **str**ucture of a dataframe (column names, data types, etc.)


```r
str(mpg)
```

* The `summary()` function displays a statistical summary of each column of the dataframe


```r
summary(mpg)
```

Accessing Columns
====================================

* A specific column a dataframe can be accessed using either the `$` or `[[]]` accessor


```r
mpg$displ
```


```r
mpg[['displ']]
```

* The latter approach is favoured if a column name contains spaces

Further Aesthetic Mappings
====================================
type: sub-section

Explaining Outliers
====================================

* Looking at our graph, we appear to have a few outliers amongst the cars with large engines. 
* Perhaps introducing another variable into the plot will help us explain this
* Using our template from before, this is simple. All we have to do is add one more mapping to our list
* Perhaps a sensible suggestion would be to colour the data points by the type of car (SUV, compact, pick-up, etc.)
* This information is contained in the `class` column

Explaining Outliers (cont.)
====================================

* To add colour to our plot, we simply add a new mapping to the code we had before


```r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy, colour = class))
```

<img src="session_one_presentation-figure/unnamed-chunk-16-1.png" title="plot of chunk unnamed-chunk-16" alt="plot of chunk unnamed-chunk-16" style="display: block; margin: auto;" />

* It appears that the anomalous points correspond to 2-seater sports cars

More Aesthetics
====================================

* The point geometry can accept a wide range of aesthetics including:
  * `size` - the size of each point
  * `alpha` - the transparency of each point
  * `shape` - the shape of the plotting character for each point
* Depending on what type of data you are using (continuous, discrete, categorical, etc.) certain mappings will be more appropriate
* Whenever you set an aesthetic mapping, `ggplot2` will automatically scale your variable as well as create a legend for the new aesthetic

Manually Setting Aesthetics
====================================

* So far, we have controlled aesthetics by mapping a column of our data frame to them
* What if we want to manually set an aesthetic?
* We simply perform the mapping outside of the `aes()` function and assign the aesthetic a value rather than a variable


```r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy), colour = "orange")
```

<img src="session_one_presentation-figure/unnamed-chunk-17-1.png" title="plot of chunk unnamed-chunk-17" alt="plot of chunk unnamed-chunk-17" style="display: block; margin: auto;" />

Manually Setting Aesthetics (cont.)
====================================
left: 60%

* It is important to specify a value that makes sense for the aesthetic:
  * The name of a colour should be a character string or a colour code (e.g. '#467A9F')
  * The size of a point should be a number (in mm)
  * The shape of a point should be an integer chosen from the figure across or a single characcter to be used as the plotting character (e.g. 'P')
  * If hollow shapes (0-14) have a border determined by `colour`; the solid shapes (15-18) are filled with `colour`; and the filled shapes (21-24) have a border of `colour` and are filled with `fill`
  
  
***

![Shape List](images/shape_list.png)

Facets
====================================
type: sub-section

Introduction
====================================

* Aesthetics offer one method of adding additonal variables to a plot
* Another way, particulary when using categorical variabels, is to split a plot into facets
* Facets are subplots that each show a subset of the entire dataset
* Facets can be generated in two ways using either the `facet_wrap()` or `facet_grid` function

Using facet_wrap()
====================================

* `facet_wrap()` is used to facet a plot by a single variable
* The first argument of the `facet_wrap` should be a formula
* A formula is created using the `~` symbol followed by a variable name
* An example formula would be `~ class` which you read as "by `class`"
* The varible using in the formula should be discrete
* You can control the layout of the facets using the `nrow` or `ncol` parameters

Using facet_wrap() (cont.)
====================================


```r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy)) +
  facet_wrap(~ class, nrow = 2)
```

<img src="session_one_presentation-figure/unnamed-chunk-18-1.png" title="plot of chunk unnamed-chunk-18" alt="plot of chunk unnamed-chunk-18" style="display: block; margin: auto;" />

Using facet_wrap() (cont.)
====================================

* Facets can be combined with aesthetics
* A common application of this is adding colour
* In this case it is often worth specifying `show.legend = FALSE` in the geometry layer


```r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy, colour = class), show.legend = FALSE) +
  facet_wrap(~ class, nrow = 2)
```

<img src="session_one_presentation-figure/unnamed-chunk-19-1.png" title="plot of chunk unnamed-chunk-19" alt="plot of chunk unnamed-chunk-19" style="display: block; margin: auto;" />

Using facet_grid()
====================================

* `facet_grid()` is often used for faceting on a combination of two variables 
* As with `facet_wrap()`, the first argument of `facet_grid()` is also a formula
* This time however the formula should contain two variable names separated by a `~`
* The first variable will be used to facet the rows and the second, the columns

Using facet_grid() (cont.)
====================================


```r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy)) +
  facet_grid(drv ~ cyl)
```

<img src="session_one_presentation-figure/unnamed-chunk-20-1.png" title="plot of chunk unnamed-chunk-20" alt="plot of chunk unnamed-chunk-20" style="display: block; margin: auto;" />

Using facet_grid() (cont.)
====================================

* If you only wish to use `facet_grid()` with one variable, you can use a `.` instead of a varible name on one side of the formula


```r
ggplot(data = mpg) +
  geom_point(mapping = aes(x = displ, y = hwy)) +
  facet_grid(. ~ cyl)
```

<img src="session_one_presentation-figure/unnamed-chunk-21-1.png" title="plot of chunk unnamed-chunk-21" alt="plot of chunk unnamed-chunk-21" style="display: block; margin: auto;" />

Getting Help
====================================
type: sub-section

Course Resources
====================================

* This course is not designed to be learnt by watching, but **doing**
* Mistakes are expected, and it will take time to move these techniques into your memory
* These slides will available to review at any time
* I am contactable via email: `tim.hargreaves@icloud.com`
* Feel free to work together and ask lots of questions

Online Resources
====================================

* [Stack Overflow](https://stackoverflow.com/) is a great resource - avoid asking your own questions as almost every beginner question has already been asked
* Simply Googling your problem followed by one of R, Tidyverse, or the specific tidyverse package you are using will return you many helpful guides
* The tidyverse has a [website](https://www.tidyverse.org/) with help guides, tutorials, and full documentation

Help in R
====================================

* The R language contains well-written and lengthy help documents
* You can access these using the `?` symbol


```r
# help on a dataset
?mpg

# help on a function - don't add brackets!
?facet_wrap
```