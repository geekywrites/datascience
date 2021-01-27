# Data-Scientist-Roadmap(2021)

I just found this data science skills roadmap, drew by [Swami Chandrasekaran](http://nirvacana.com/thoughts/becoming-a-data-scientist/) on his cool blog.

****

![roadmap-picture](http://nirvacana.com/thoughts/wp-content/uploads/2013/07/RoadToDataScientist1.png)

****

Jobs linked to __data science__ are becoming __more and more popular__. A __bunch of tutorials__ could easily complete this roadmap, helping whoever wants to __start learning stuff about data science__.

For the moment, a lot is __got on wikipedia__ (except for codes, always handmade). Any help's thus welcome!

## Rules

* __Feel free to fork this repository and pull requests__.
* Always comment your code.
* Please respect topology for filenames.
* There's one README for each directory.
* Also, could be great to share useful links or ressources in README files.


# 1_ Fundamentals


## 1_ Matrices & Algebra fundamentals

### About

In mathematics, a matrix is a __rectangular array of numbers, symbols, or expressions, arranged in rows and columns__. A matrix could be reduced as a submatrix of a matrix by deleting any collection of rows and/or columns.

![matrix-image](https://upload.wikimedia.org/wikipedia/commons/b/bb/Matrix.svg)

### Operations

There are a number of basic operations that can be applied to modify matrices:

* [Addition](https://en.wikipedia.org/wiki/Matrix_addition)
* [Scalar Multiplication](https://en.wikipedia.org/wiki/Scalar_multiplication)
* [Transposition](https://en.wikipedia.org/wiki/Transpose)
* [Multiplication](https://en.wikipedia.org/wiki/Matrix_multiplication)


## 2_ Hash function, binary tree, O(n)

### Hash function

#### Definition

A hash function is __any function that can be used to map data of arbitrary size to data of fixed size__. One use is a data structure called a hash table, widely used in computer software for rapid data lookup. Hash functions accelerate table or database lookup by detecting duplicated records in a large file.

![hash-image](https://upload.wikimedia.org/wikipedia/commons/5/58/Hash_table_4_1_1_0_0_1_0_LL.svg)

### Binary tree

#### Definition

In computer science, a binary tree is __a tree data structure in which each node has at most two children__, which are referred to as the left child and the right child.

![binary-tree-image](https://upload.wikimedia.org/wikipedia/commons/f/f7/Binary_tree.svg)

### O(n)

#### Definition

In computer science, big O notation is used to __classify algorithms according to how their running time or space requirements grow as the input size grows__. In analytic number theory, big O notation is often used to __express a bound on the difference between an arithmetical function and a better understood approximation__.

## 3_ Relational algebra, DB basics

### Definition

Relational algebra is a family of algebras with a __well-founded semantics used for modelling the data stored in relational databases__, and defining queries on it.

The main application of relational algebra is providing a theoretical foundation for __relational databases__, particularly query languages for such databases, chief among which is SQL.

### Natural join

#### About

In SQL language, a natural junction between two tables will be done if :

* At least one column has the same name in both tables
* Theses two columns have the same data type
    * CHAR (character)
    * INT (integer)
    * FLOAT (floating point numeric data)
    * VARCHAR (long character chain)
    
#### mySQL request

        SELECT <COLUMNS>
        FROM <TABLE_1>
        NATURAL JOIN <TABLE_2>

        SELECT <COLUMNS>
        FROM <TABLE_1>, <TABLE_2>
        WHERE TABLE_1.ID = TABLE_2.ID

## 4_ Inner, Outer, Cross, theta-join

### Inner join

The INNER JOIN keyword selects records that have matching values in both tables.

#### Request

      SELECT column_name(s)
      FROM table1
      INNER JOIN table2 ON table1.column_name = table2.column_name;

![inner-join-image](https://www.w3schools.com/sql/img_innerjoin.gif)

### Outer join

The FULL OUTER JOIN keyword return all records when there is a match in either left (table1) or right (table2) table records.

#### Request

      SELECT column_name(s)
      FROM table1
      FULL OUTER JOIN table2 ON table1.column_name = table2.column_name; 

![outer-join-image](https://www.w3schools.com/sql/img_fulljoin.gif)

### Left join

The LEFT JOIN keyword returns all records from the left table (table1), and the matched records from the right table (table2). The result is NULL from the right side, if there is no match.

#### Request

      SELECT column_name(s)
      FROM table1
      LEFT JOIN table2 ON table1.column_name = table2.column_name;

![left-join-image](https://www.w3schools.com/sql/img_leftjoin.gif)

### Right join

The RIGHT JOIN keyword returns all records from the right table (table2), and the matched records from the left table (table1). The result is NULL from the left side, when there is no match.
#### Request

      SELECT column_name(s)
      FROM table1
      RIGHT JOIN table2 ON table1.column_name = table2.column_name;

![left-join-image](https://www.w3schools.com/sql/img_rightjoin.gif)

## 5_ CAP theorem

It is impossible for a distributed data store to simultaneously provide more than two out of the following three guarantees:
 
* Every read receives the most recent write or an error.
* Every request receives a (non-error) response – without guarantee that it contains the most recent write.
* The system continues to operate despite an arbitrary number of messages being dropped (or delayed) by the network between nodes.

In other words, the CAP Theorem states that in the presence of a network partition, one has to choose between consistency and availability. Note that consistency as defined in the CAP Theorem is quite different from the consistency guaranteed in ACID database transactions.

## 6_ Tabular data

Tabular data are __opposed to relational__ data, like SQL database.

In tabular data, __everything is arranged in columns and rows__. Every row have the same number of column (except for missing value, which could be substituted by "N/A".

The __first line__ of tabular data is most of the time a __header__, describing the content of each column.

The most used format of tabular data in data science is __CSV___. Every column is surrounded by a character (a tabulation, a coma ..), delimiting this column from its two neighbours.

## 7_ Entropy

Entropy is a __measure of uncertainty__. High entropy means the data has high variance and thus contains a lot of information and/or noise.

For instance, __a constant function where f(x) = 4 for all x has no entropy and is easily predictable__, has little information, has no noise and can be succinctly represented . Similarly, f(x) = ~4 has some entropy while f(x) = random number is very high entropy due to noise.

## 8_ Data frames & series

A data frame is used for storing data tables. It is a list of vectors of equal length.

A series is a series of data points ordered.

## 9_ Sharding

*Sharding* is **horizontal(row wise) database partitioning** as opposed to **vertical(column wise) partitioning** which is *Normalization*

Why use Sharding?

1. Database systems with large data sets or high throughput applications can challenge the capacity of a single server.
2. Two methods to address the growth : Vertical Scaling and Horizontal Scaling
3. Vertical Scaling

    * Involves increasing the capacity of a single server
    * But due to technological and economical restrictions, a single machine may not be sufficient for the given workload.

4. Horizontal Scaling
    * Involves dividing the dataset and load over multiple servers, adding additional servers to increase capacity as required
    * While the overall speed or capacity of a single machine may not be high, each machine handles a subset of the overall workload, potentially providing better efficiency than a single high-speed high-capacity server. 
    * Idea is to use concepts of Distributed systems to achieve scale
    * But it comes with same tradeoffs of increased complexity that comes hand in hand with distributed systems.
    * Many Database systems provide Horizontal scaling via Sharding the datasets.

## 10_ OLAP

Online analytical processing, or OLAP, is an approach to answering multi-dimensional analytical (MDA) queries swiftly in computing. 

OLAP is part of the __broader category of business intelligence__, which also encompasses relational database, report writing and data mining. Typical applications of OLAP include ___business reporting for sales, marketing, management reporting, business process management (BPM), budgeting and forecasting, financial reporting and similar areas, with new applications coming up, such as agriculture__.

The term OLAP was created as a slight modification of the traditional database term online transaction processing (OLTP).

## 11_ Multidimensional Data model

## 12_ ETL

* Extract
  * extracting the data from the multiple heterogenous source system(s)
  * data validation to confirm whether the data pulled has the correct/expected values in a given domain

* Transform
  * extracted data is fed into a pipeline which applies multiple functions on top of data
  * these functions intend to convert the data into the format which is accepted by the end system
  * involves cleaning the data to remove noise, anamolies and redudant data
* Load
  * loads the transformed data into the end target

## 13_ Reporting vs BI vs Analytics

## 14_ JSON and XML

### JSON

JSON is a language-independent data format. Example describing a person:
	
	{
	  "firstName": "John",
	  "lastName": "Smith",
	  "isAlive": true,
	  "age": 25,
	  "address": {
	    "streetAddress": "21 2nd Street",
	    "city": "New York",
	    "state": "NY",
	    "postalCode": "10021-3100"
	  },
	  "phoneNumbers": [
	    {
	      "type": "home",
	      "number": "212 555-1234"
	    },
	    {
	      "type": "office",
	      "number": "646 555-4567"
	    },
	    {
	      "type": "mobile",
	      "number": "123 456-7890"
	    }
	  ],
	  "children": [],
	  "spouse": null
	}

## XML

Extensible Markup Language (XML) is a markup language that defines a set of rules for encoding documents in a format that is both human-readable and machine-readable.
 
 	<CATALOG>
	  <PLANT>
	    <COMMON>Bloodroot</COMMON>
	    <BOTANICAL>Sanguinaria canadensis</BOTANICAL>
	    <ZONE>4</ZONE>
	    <LIGHT>Mostly Shady</LIGHT>
	    <PRICE>$2.44</PRICE>
	    <AVAILABILITY>031599</AVAILABILITY>
	  </PLANT>
	  <PLANT>
	    <COMMON>Columbine</COMMON>
	    <BOTANICAL>Aquilegia canadensis</BOTANICAL>
	    <ZONE>3</ZONE>
	    <LIGHT>Mostly Shady</LIGHT>
	    <PRICE>$9.37</PRICE>
	    <AVAILABILITY>030699</AVAILABILITY>
	  </PLANT>
	  <PLANT>
	    <COMMON>Marsh Marigold</COMMON>
	    <BOTANICAL>Caltha palustris</BOTANICAL>
	    <ZONE>4</ZONE>
	    <LIGHT>Mostly Sunny</LIGHT>
	    <PRICE>$6.81</PRICE>
	    <AVAILABILITY>051799</AVAILABILITY>
	  </PLANT>
	</CATALOG>

## 15_ NoSQL

noSQL is oppsed to relationnal databases (stand for __N__ot __O__nly __SQL__). Data are not structured and there's no notion of keys between tables.

Any kind of data can be stored in a noSQL database (JSON, CSV, ...) whithout thinking about a complex relationnal scheme.

__Commonly used noSQL stacks__: Cassandra, MongoDB, Redis, Oracle noSQL ...

## 16_ Regex

### About

__Reg__ ular __ex__ pressions (__regex__) are commonly used in informatics.

It can be used in a wide range of possibilities :
* Text replacing
* Extract information in a text (email, phone number, etc)
* List files with the .txt extension ..

http://regexr.com/ is a good website for experimenting on Regex.

### Utilisation

To use them in [Python](https://docs.python.org/3/library/re.html), just import:

    import re

## 17_ Vendor landscape

## 18_ Env Setup

# 2_ Statistics


[Statistics-101 for data noobs](https://medium.com/@debuggermalhotra/statistics-101-for-data-noobs-2e2a0e23a5dc)

## 1_ Pick a dataset

### Datasets repositories

#### Generalists

- [KAGGLE](https://www.kaggle.com/datasets)
- [Google](https://toolbox.google.com/datasetsearch)

#### Medical

- [PMC](https://www.ncbi.nlm.nih.gov/pmc/)

#### Other languages

##### French

- [DATAGOUV](https://www.data.gouv.fr/fr/)

## 2_ Descriptive statistics

### Mean

In probability and statistics, population mean and expected value are used synonymously to refer to one __measure of the central tendency either of a probability distribution or of the random variable__ characterized by that distribution.

For a data set, the terms arithmetic mean, mathematical expectation, and sometimes average are used synonymously to refer to a central value of a discrete set of numbers: specifically, the __sum of the values divided by the number of values__.

![mean_formula](https://wikimedia.org/api/rest_v1/media/math/render/svg/bd2f5fb530fc192e4db7a315777f5bbb5d462c90)

### Median

The median is the value __separating the higher half of a data sample, a population, or a probability distribution, from the lower half__. In simple terms, it may be thought of as the "middle" value of a data set.

### Descriptive statistics in Python

[Numpy](http://www.numpy.org/) is a python library widely used for statistical analysis.

#### Installation

    pip3 install numpy

#### Utilization
    
    import numpy

## 3_ Exploratory data analysis

The step includes visualization and analysis of data. 

Raw data may possess improper distributions of data which may lead to issues moving forward.

Again, during applications we must also know the distribution of data, for instance, the fact whether the data is linear or spirally distributed.

[Guide to EDA in Python](https://towardsdatascience.com/data-preprocessing-and-interpreting-results-the-heart-of-machine-learning-part-1-eda-49ce99e36655)

##### Libraries in Python 

[Matplotlib](https://matplotlib.org/)

Library used to plot graphs in Python

__Installation__:

    pip3 install matplotlib

__Utilization__:

    import matplotlib.pyplot as plt

[Pandas](https://pandas.pydata.org/)

Library used to large datasets in python

__Installation__:

    pip3 install pandas

__Utilization__:

    import pandas as pd
    
[Seaborn](https://seaborn.pydata.org/)

Yet another Graph Plotting Library in Python.

__Installation__:

    pip3 install seaborn

__Utilization__:

    import seaborn as sns


#### PCA

PCA stands for principle component analysis.

We often require to shape of the data distribution as we have seen previously. We need to plot the data for the same.

Data can be Multidimensional, that is, a dataset can have multiple features. 

We can plot only two dimensional data, so, for multidimensional data, we project the multidimensional distribution in two dimensions, preserving the principle components of the distribution, in order to get an idea of the actual distribution through the 2D plot. 

It is used for dimensionality reduction also. Often it is seen that several features do not significantly contribute any important insight to the data distribution. Such features creates complexity and increase dimensionality of the data. Such features are not considered which results in decrease of the dimensionality of the data.

[Mathematical Explanation](https://medium.com/towards-artificial-intelligence/demystifying-principal-component-analysis-9f13f6f681e6)

[Application in Python](https://towardsdatascience.com/data-preprocessing-and-interpreting-results-the-heart-of-machine-learning-part-2-pca-feature-92f8f6ec8c8)

## 4_ Histograms

Histograms are representation of distribution of numerical data. The procedure consists of binnng the numeric values using range divisions i.e, the entire range in which the data varies is split into several fixed intervals. Count or frequency of occurences of the numbers in the range of the bins are represented.

[Histograms](https://en.wikipedia.org/wiki/Histogram)

![plot](https://upload.wikimedia.org/wikipedia/commons/thumb/1/1d/Example_histogram.png/220px-Example_histogram.png)

In python, __Pandas__,__Matplotlib__,__Seaborn__ can be used to create Histograms.

## 5_ Percentiles & outliers

### Percentiles

Percentiles are numberical measures in statistics, which represents how much or what percentage of data falls below a given number or instance in a numerical data distribution. 

For instance, if we say 70 percentile, it represents, 70% of the data in the ditribution are below the given numerical value. 

[Percentiles](https://en.wikipedia.org/wiki/Percentile)

### Outliers

Outliers are data points(numerical) which have significant differences with other data points. They differ from majority of points in the distribution. Such points may cause the central measures of distribution, like mean, and median. So, they need to be detected and removed.

[Outliers](https://www.itl.nist.gov/div898/handbook/prc/section1/prc16.htm)

__Box Plots__ can be used detect Outliers in the data. They can be created using __Seaborn__ library

![Image_Box_Plot](https://miro.medium.com/max/612/1*105IeKBRGtyPyMy3-WQ8hw.png)
  
## 6_ Probability theory

__Probability__ is the likelihood of an event in a Random experiment. For instance, if a coin is tossed, the chance of getting a head is 50% so, probability is 0.5.

__Sample Space__: It is the set of all possible outcomes of a Random Experiment. 
__Favourable Outcomes__: The set of outcomes we are looking for in a Random Experiment

__Probability = (Number of Favourable Outcomes) / (Sample Space)__

__Probability theory__ is a branch of mathematics that is associated with the concept of probability.

[Basics of Probability](https://towardsdatascience.com/basic-probability-theory-and-statistics-3105ab637213)

## 7_ Bayes theorem

### Conditional Probability:

It is the probability of one event occurring, given that another event has already occurred. So, it gives a sense of relationship between two events and the probabilities of the occurences of those events.

It is given by:

__P( A | B )__ : Probability of occurence of A, after B occured.

The formula is given by: 

![formula](https://wikimedia.org/api/rest_v1/media/math/render/svg/74cbddb93db29a62d522cd6ab266531ae295a0fb)

So, P(A|B) is equal to Probablity of occurence of A and B, divided by Probability of occurence of B.

[Guide to Conditional Probability](https://en.wikipedia.org/wiki/Conditional_probability)

### Bayes Theorem

Bayes theorem provides a way to calculate conditional probability. Bayes theorem is widely used in machine learning most in Bayesian Classifiers.  

According to Bayes theorem the probability of A, given that B has already occurred is given by Probability of A multiplied by the probability of B given A has already occurred divided by the probability of B.

__P(A|B) =  P(A).P(B|A) / P(B)__


[Guide to Bayes Theorem](https://machinelearningmastery.com/bayes-theorem-for-machine-learning/)


## 8_ Random variables

Random variable are the numeric outcome of an experiment or random events. They are normally a set of values. 

There are two main types of Random Variables:

__Discrete Random Variables__: Such variables take only a finite number of distinct values

__Continous Random Variables__: Such variables can take an infinite number of possible values.


## 9_ Cumul Dist Fn (CDF)

In probability theory and statistics, the cumulative distribution function (CDF) of a real-valued random variable __X__, or just distribution function of __X__, evaluated at __x__, is the probability that __X__ will take a value less than or equal to __x__.

The cumulative distribution function of a real-valued random variable X is the function given by:

![CDF](https://wikimedia.org/api/rest_v1/media/math/render/svg/f81c05aba576a12b4e05ee3f4cba709dd16139c7)

Resource:

[Wikipedia](https://en.wikipedia.org/wiki/Cumulative_distribution_function)

## 10_ Continuous distributions

A continuous distribution describes the probabilities of the possible values of a continuous random variable. A continuous random variable is a random variable with a set of possible values (known as the range) that is infinite and uncountable.

## 11_ Skewness

Skewness is the measure of assymetry in the data distribution or a random variable distribution about its mean. 

Skewness can be positive, negative or zero. 

![skewed image](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f8/Negative_and_positive_skew_diagrams_%28English%29.svg/446px-Negative_and_positive_skew_diagrams_%28English%29.svg.png)

__Negative skew__: Distribution Concentrated in the right, left tail is longer.

__Positive skew__: Distribution Concentrated in the left, right tail is longer.

Variation of central tendency measures are shown below.


![cet](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cc/Relationship_between_mean_and_median_under_different_skewness.png/434px-Relationship_between_mean_and_median_under_different_skewness.png)

Data Distribution are often Skewed which may cause trouble during processing the data. __Skewed Distribution can be converted to Symmetric Distribution, taking Log of the distribution__.

##### Skew Distribution

![Skew](https://miro.medium.com/max/379/1*PLSczKIQRc8ZtlvHED-6mQ.png)

##### Log of the Skew Distribution.

![log](https://miro.medium.com/max/376/1*4GFayBYKIiqAcyI69wIFzA.png)


[Guide to Skewness](https://en.wikipedia.org/wiki/Skewness)


## 12_ ANOVA

ANOVA stands for __analysis of variance__. 

It is used to compare among groups of data distributions.

Often we are provided with huge data. They are too huge to work with. The total data is called the __Population__.

In order to work with them, we pick random smaller groups of data. They are called __Samples__.

ANOVA is used to compare the variance among these groups or samples. 

Variance of  group is given by:

![var](https://miro.medium.com/max/446/1*yzAMFVIEFysMKwuT0YHrZw.png)

The differences in the collected samples are observed using the differences between the means of the groups. We often use the __t-test__ to compare the means and also to check if the samples belong to the same population,

Now, t-test can only be possible among two groups. But, often we get more groups or samples.

If we try to use t-test for more than two groups we have to perform t-tests multiple times, once for each pair. This is where ANOVA is used.

ANOVA has two components:

__1.Variation within each group__

__2.Variation between groups__

It works on a ratio called the  __F-Ratio__

It is given by:

![F-ratio](https://miro.medium.com/max/491/1*I5dSwtUICySQ5xvKmq6M8A.png)

F ratio shows how much of the total variation comes from the variation between groups and how much comes from the variation within groups. If much of the variation comes from the variation between groups, it is more likely that the mean of groups are different. However, if most of the variation comes from the variation within groups, then we can conclude the elements in a group are different rather than entire groups. The larger the F ratio, the more likely that the groups have different means.


Resources:

[Defnition](https://statistics.laerd.com/statistical-guides/one-way-anova-statistical-guide.php)

[GUIDE 1](https://towardsdatascience.com/anova-analysis-of-variance-explained-b48fee6380af)

[Details](https://medium.com/@StepUpAnalytics/anova-one-way-vs-two-way-6b3ff87d3a94)


## 13_ Prob Den Fn (PDF)

It stands for probability density function. 

__In probability theory, a probability density function (PDF), or density of a continuous random variable, is a function whose value at any given sample (or point) in the sample space (the set of possible values taken by the random variable) can be interpreted as providing a relative likelihood that the value of the random variable would equal that sample.__

The probability density function (PDF) P(x) of a continuous distribution is defined as the derivative of the (cumulative) distribution function D(x).

It is given by the integral of the function over a given range.

![PDF](https://wikimedia.org/api/rest_v1/media/math/render/svg/45fd7691b5fbd323f64834d8e5b8d4f54c73a6f8)

## 14_ Central Limit theorem

## 15_ Monte Carlo method

## 16_ Hypothesis Testing

### Types of curves

We need to know about two distribution curves first.

Distribution curves reflect the probabilty of finding an instance or a sample of a population at a certain value of the distribution.

__Normal Distribution__

![normal distribution](https://sciences.usca.edu/biology/zelmer/305/norm/stanorm.jpg)

The normal distribution represents how the data is distributed. In this case, most of the data samples in the distribution are scattered at and around the mean of the distribution. A few instances are scattered or present at the long tail ends of the distribution.

Few points about Normal Distributions are:

1. The curve is always Bell-shaped. This is because most of the data is found around the mean, so the proababilty of finding a sample at the mean or central value is more.

2. The curve is symmetric

3. The area under the curve is always 1. This is because all the points of the distribution must be present under the curve

4. For Normal Distribution, Mean and Median lie on the same line in the distribution. 

__Standard Normal Distribution__

This type of distribution are normal distributions which following conditions.

1. Mean of the distribution is 0

2. The Standard Deviation of the distribution is equal to 1.

The idea of Hypothesis Testing works completely on the data distributions.

### Hypothesis Testing

Hypothesis testing is a statistical method that is used in making statistical decisions using experimental data. Hypothesis Testing is basically an assumption that we make about the population parameter.

For example, say, we take the hypothesis that boys in a class are taller than girls. 

The above statement is just an assumption on the population of the class.

__Hypothesis__ is just an assumptive proposal or statement made on the basis of observations made on a set of information or data. 

We initially propose two mutually exclusive statements based on the population of the sample data. 

The initial one is called __NULL HYPOTHESIS__. It is denoted by H0.

The second one is called __ALTERNATE HYPOTHESIS__. It is denoted by H1 or Ha. It is used as a contrary to Null Hypothesis. 

Based on the instances of the population we accept or reject the NULL Hypothesis and correspondingly we reject or accept the ALTERNATE Hypothesis.
 
#### Level of Significance

It is the degree which we consider to decide whether to accept or reject the NULL hypothesis. When we consider a hypothesis on a population, it is not the case that 100% or all instances of the population abides the assumption, so we decide a __level of significance as a cutoff degree, i.e, if our level of significance is 5%, and (100-5)% = 95% of the data abides by the assumption, we accept the Hypothesis.__

__It is said with 95% confidence, the hypothesis is accepted__

![curve](https://i.stack.imgur.com/d8iHd.png)

The non-reject region is called __acceptance region or beta region__. The rejection regions are called __critical or alpha regions__. __alpha__ denotes the __level of significance__.

If level of significance is 5%. the two alpha regions have (2.5+2.5)% of the population and the beta region has the 95%. 

The acceptance and rejection gives rise to two kinds of errors:

__Type-I Error:__ NULL Hypothesis is true, but wrongly Rejected.

__Type-II Error:__ NULL Hypothesis if false but is wrongly accepted.

![hypothesis](https://microbenotes.com/wp-content/uploads/2020/07/Graphical-representation-of-type-1-and-type-2-errors.jpg)

### Tests for Hypothesis

__One Tailed Test__: 

![One-tailed](https://prwatech.in/blog/wp-content/uploads/2019/07/onetailtest.png)

This is a test for Hypothesis, where the rejection region is only one side of the sampling distribution. The rejection region may be in right tail end or in the left tail end.

The idea is if we say our level of significance is 5% and we consider a hypothesis "Hieght of Boys in a class is <=6 ft". We consider the hypothesis true if atmost 5% of our population are more than 6 feet. So, this will be one-tailed as the test condition only restricts one tail end, the end with hieght > 6ft. 

![Two Tailed](https://i0.wp.com/www.real-statistics.com/wp-content/uploads/2012/11/two-tailed-significance-testing.png)

In this case, the rejection region extends at both tail ends of the distribution.

The idea is if we say our level of significance is 5% and we consider a hypothesis "Hieght of Boys in a class is !=6 ft".

Here, we can accept the NULL hyposthesis iff atmost 5% of the population is less than or greater than 6 feet. So, it is evident that the crirtical region will be at both tail ends and the region is 5% / 2 = 2.5% at both ends of the distribution. 



## 17_ p-Value

Before we jump into P-values we need to look at another important topic in the context: Z-test.

### Z-test

We need to know two terms: __Population and Sample.__

__Population__ describes the entire available data distributed. So, it refers to all records provided in the dataset.

__Sample__ is said to be a group of data points randomly picked from a population or a given distribution. The size of the sample can be any number of data points, given by __sample size.__

__Z-test__ is simply used to determine if a given sample distribution belongs to a given population. 

Now,for Z-test we have to use __Standard Normal Form__ for the standardized comparison measures.

![std1](https://miro.medium.com/max/700/1*VYCN5b-Zubr4rrc9k37SAg.png)

As we already have seen, standard normal form is a normal form with mean=0 and standard deviation=1.

The __Standard Deviation__ is a measure of how much differently the points are distributed around the mean.

![std2](https://miro.medium.com/max/640/1*kzFQaZ08dTjlPq1zrcJXgg.png)

It states that approximately 68% , 95% and 99.7% of the data lies within 1, 2 and 3 standard deviations of a normal distribution respectively.

Now, to convert the normal distribution to standard normal distribution we need a standard score called Z-Score.
It is given by:

![Z-score](https://miro.medium.com/max/125/1*X--kDNyurDEo2zKbSDDf-w.png)

x = value that we want to standardize

µ = mean of the distribution of x

σ = standard deviation of the distribution of x

We need to know another concept __Central Limit Theorem__.

##### Central Limit Theorem 

_The theorem states that the mean of the sampling distribution of the sample means is equal to the population mean irrespective if the distribution of population where sample size is greater than 30._

And

_The sampling distribution of sampling mean will also follow the normal distribution._

So, it states, if we pick several samples from a distribution with the size above 30, and pick the static sample means and use the sample means to create a distribution, the mean of the newly created sampling distribution is equal to the original population mean.

According to the theorem, if we draw samples of size N, from a population with population mean μ and population standard deviation σ, the condition stands:

![std3](https://miro.medium.com/max/121/0*VPW964abYGyevE3h.png)

i.e, mean of the distribution of sample means is equal to the sample means.

The standard deviation of the sample means is give by:

![std4](https://miro.medium.com/max/220/0*EMx4C_A9Efsd6Ef6.png)

The above term is also called standard error.

We use the theory discussed above for Z-test. If the sample mean lies close to the population mean, we say that the sample belongs to the population and if it lies at a distance from the population mean, we say the sample is taken from a different population.

To do this we use a formula and check if the z statistic is greater than or less than 1.96 (considering two tailed test, level of significance = 5%)

![los](https://miro.medium.com/max/424/0*C9XaCIUWoJaBSMeZ.gif)

![std5](https://miro.medium.com/max/137/1*DRiPmBtjK4wmidq9Ha440Q.png)
 
 The above formula gives Z-static

z = z statistic

X̄ = sample mean

μ = population mean

σ = population standard deviation

n = sample size

Now, as the Z-score is used to standardize the distribution, it gives us an idea how the data is distributed overall.

### P-values

It is used to check if the results are statistically significant based on the significance level.  

Say, we perform an experiment and collect observations or data. Now, we make a hypothesis (NULL hypothesis) primary, and a second hypothesis, contradictory to the first one called the alternative hypothesis.

Then we decide a level of significance which serve as a threshold for our null hypothesis. The P value actually gives the probability of the statement. Say, the p-value of our alternative hypothesis is 0.02, it means the probability of alternate hypothesis happenning is 2%. 

Now, the level of significance into play to decide if we can allow 2% or p-value of 0.02. It can be said as a level of endurance of the null hypothesis. If our level of significance is 5% using a two tailed test, we can allow 2.5% on both ends of the distribution, we accept the NULL hypothesis, as level of significance > p-value of alternate hypothesis. 

But if the p-value is greater than level of significance, we tell that the result is __statistically significant, and we reject NULL hypothesis.__ .

Resources:

1. https://medium.com/analytics-vidhya/everything-you-should-know-about-p-value-from-scratch-for-data-science-f3c0bfa3c4cc

2. https://towardsdatascience.com/p-values-explained-by-data-scientist-f40a746cfc8

3.https://medium.com/analytics-vidhya/z-test-demystified-f745c57c324c

## 18_ Chi2 test

Chi2 test is extensively used in data science and machine learning problems for feature selection.

A chi-square test is used in statistics to test the independence of two events. So, it is used to check for independence of features used. Often dependent features are used which do not convey a lot of information but adds dimensionality to a feature space.

It is one of the most common ways to examine relationships between two or more categorical variables.

It involves calculating a number, called the chi-square statistic - χ2. Which follows a chi-square distribution.

It is given as the summation of the difference of the expected values and observed value divided by the observed value.

![Chi2](https://miro.medium.com/max/266/1*S8rfFkmLhDbOz4RGNwuz6g.png)


Resources:

[Definitions](investopedia.com/terms/c/chi-square-statistic.asp)

[Guide 1](https://towardsdatascience.com/chi-square-test-for-feature-selection-in-machine-learning-206b1f0b8223)

[Guide 2](https://medium.com/swlh/what-is-chi-square-test-how-does-it-work-3b7f22c03b01)

[Example of Operation](https://medium.com/@kuldeepnpatel/chi-square-test-of-independence-bafd14028250)


## 19_ Estimation

## 20_ Confid Int (CI)

## 21_ MLE

## 22_ Kernel Density estimate

In statistics, kernel density estimation (KDE) is a non-parametric way to estimate the probability density function of a random variable. Kernel density estimation is a fundamental data smoothing problem where inferences about the population are made, based on a finite data sample.

Kernel Density estimate can be regarded as another way to represent the probability distribution. 

![KDE1](https://upload.wikimedia.org/wikipedia/commons/thumb/2/2a/Kernel_density.svg/250px-Kernel_density.svg.png)

It consists of choosing a kernel function. There are mostly three used.

1. Gaussian 

2. Box

3. Tri

The kernel function depicts the probability of finding a data point. So, it is highest at the centre and decreases as we move away from the point.

We assign a kernel function over all the data points and finally calculate the density of the functions, to get the density estimate of the distibuted data points. It practically adds up the Kernel function values at a particular point on the axis. It is as shown below.

![KDE 2](https://upload.wikimedia.org/wikipedia/commons/thumb/4/41/Comparison_of_1D_histogram_and_KDE.png/500px-Comparison_of_1D_histogram_and_KDE.png)

Now, the kernel function is given by:

![kde3](https://wikimedia.org/api/rest_v1/media/math/render/svg/f3b09505158fb06033aabf9b0116c8c07a68bf31)

where K is the kernel — a non-negative function — and h > 0 is a smoothing parameter called the bandwidth. 

The 'h' or the bandwidth is the parameter, on which the curve varies.

![kde4](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e5/Comparison_of_1D_bandwidth_selectors.png/220px-Comparison_of_1D_bandwidth_selectors.png)

Kernel density estimate (KDE) with different bandwidths of a random sample of 100 points from a standard normal distribution. Grey: true density (standard normal). Red: KDE with h=0.05. Black: KDE with h=0.337. Green: KDE with h=2.

Resources:

[Basics](https://www.youtube.com/watch?v=x5zLaWT5KPs)

[Advanced](https://jakevdp.github.io/PythonDataScienceHandbook/05.13-kernel-density-estimation.html)

## 23_ Regression

Regression tasks deal with predicting the value of a __dependent variable__ from a set of __independent variables.__

Say, we want to predict the price of a car. So, it becomes a dependent variable say Y, and the features like engine capacity, top speed, class, and company become the independent variables, which helps to frame the equation to obtain the price.

If there is one feature say x. If the dependent variable y is linearly dependent on x, then it can be given by __y=mx+c__, where the m is the coefficient of the independent in the equation, c is the intercept or bias.

The image shows the types of regression

![types](https://miro.medium.com/max/2001/1*dSFn-uIYDhDfdaG5GXlB3A.png)

[Guide to Regression](https://towardsdatascience.com/a-deep-dive-into-the-concept-of-regression-fb912d427a2e)

## 24_ Covariance

### Variance
The variance is a measure of how dispersed or spread out the set is. If it is said that the variance is zero, it means all the elements in the dataset are same. If the variance is low, it means the data are slightly dissimilar. If the variance is very high, it means the data in the dataset are largely dissimilar. 

Mathematically, it is a measure of how far each value in the data set is from the mean.

Variance (sigma^2) is given by summation of the square of distances of each point from the mean, divided by the number of points

![formula var](https://cdn.sciencebuddies.org/Files/474/9/DefVarEqn.jpg)

### Covariance

Covariance gives us an idea about the degree of association between two considered random variables. Now, we know random variables create distributions. Distribution are a set of values or data points which the variable takes and we can easily represent as vectors in the vector space.

For vectors covariance is defined as the dot product of two vectors. The value of covariance can vary from positive infinity to negative infinity. If the two distributions or vectors grow in the same direction the covariance is positive and vice versa. The Sign gives the direction of variation and the Magnitude gives the amount of variation.  

Covariance is given by:

![cov_form](https://cdn.corporatefinanceinstitute.com/assets/covariance1.png)

where Xi and Yi denotes the i-th point of the two distributions and X-bar and Y-bar represent the mean values of both the distributions, and n represents the number of values or data points in the distribution. 

## 25_ Correlation

Covariance measures the total relation of the variables namely both direction and magnitude. Correlation is a scaled measure of covariance. It is dimensionless and independent of scale. It just shows the strength of variation for both the variables.

Mathematically, if we represent the distribution using vectors, correlation is said to be the cosine angle between the vectors. The value of correlation varies from +1 to -1. +1 is said to be a strong positive correlation and -1 is said to be a strong negative correlation. 0 implies no correlation, or the two variables are independent of each other. 

Correlation is given by:

![corr](https://cdn.corporatefinanceinstitute.com/assets/covariance3.png)

Where:

ρ(X,Y) – the correlation between the variables X and Y

Cov(X,Y) – the covariance between the variables X and Y

σX – the standard deviation of the X-variable

σY – the standard deviation of the Y-variable

Standard deviation is given by square roo of variance.

## 26_ Pearson coeff

## 27_ Causation

## 28_ Least2-fit

## 29_ Euclidian Distance

__Eucladian Distance is the most used and standard measure for the distance between two points.__

It is given as the square root of sum of squares of the difference between coordinates of two points.

__The Euclidean distance between two points in Euclidean space is a number, the length of a line segment between the two points. It can be calculated from the Cartesian coordinates of the points using the Pythagorean theorem, and is occasionally called the Pythagorean distance.__

__In the Euclidean plane, let point p have Cartesian coordinates (p_{1},p_{2}) and let point q have coordinates (q_{1},q_{2}). Then the distance between p and q is given by:__

![eucladian](https://wikimedia.org/api/rest_v1/media/math/render/svg/9c0157084fd89f5f3d462efeedc47d3d7aa0b773)

### Artificial Intelligence

- [CS 188 - Introduction to Artificial Intelligence, UC Berkeley - Spring 2015](http://www.infocobuild.com/education/audio-video-courses/computer-science/cs188-spring2015-berkeley.html)
- [6.034 Artificial Intelligence, MIT OCW](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-034-artificial-intelligence-fall-2010/lecture-videos/)
- [CS221: Artificial Intelligence: Principles and Techniques - Autumn 2019 - Stanford University](https://www.youtube.com/playlist?list=PLoROMvodv4rO1NB9TD4iUZ3qghGEGtqNX)
- [15-780 - Graduate Artificial Intelligence, Spring 14, CMU](http://www.cs.cmu.edu/~zkolter/course/15-780-s14/lectures.html)
- [CSE 592 Applications of Artificial Intelligence, Winter 2003 - University of Washington](https://courses.cs.washington.edu/courses/csep573/03wi/lectures/index.htm)
- [CS322 - Introduction to Artificial Intelligence, Winter 2012-13 - UBC](http://www.cs.ubc.ca/~mack/CS322/) ([YouTube](https://www.youtube.com/playlist?list=PLDPnGbm0sUmpzvcGvktbz446SLdFbfZVU))
- [CS 4804: Introduction to Artificial Intelligence, Fall 2016](https://www.youtube.com/playlist?list=PLUenpfvlyoa1iiSbGy9BBewgiXjzxVgBd)
- [CS 5804: Introduction to Artificial Intelligence, Spring 2015](https://www.youtube.com/playlist?list=PLUenpfvlyoa0PB6_kqJ9WU7m6i6z1RhfJ)
- [Artificial Intelligence - IIT Kharagpur](https://nptel.ac.in/courses/106105077/)
- [Artificial Intelligence - IIT Madras](https://nptel.ac.in/courses/106106126/)
- [Artificial Intelligence(Prof.P.Dasgupta) - IIT Kharagpur](https://nptel.ac.in/courses/106105079/)
- [MOOC - Intro to Artificial Intelligence - Udacity](https://www.youtube.com/playlist?list=PLAwxTw4SYaPlqMkzr4xyuD6cXTIgPuzgn)
- [MOOC - Artificial Intelligence for Robotics - Udacity](https://www.youtube.com/playlist?list=PLAwxTw4SYaPkCSYXw6-a_aAoXVKLDwnHK)
- [Graduate Course in Artificial Intelligence, Autumn 2012 - University of Washington](https://www.youtube.com/playlist?list=PLbQ3Aya0VERDoDdbMogU9EASJGWris9qG)
- [Agent-Based Systems 2015/16- University of Edinburgh](http://groups.inf.ed.ac.uk/vision/VIDEO/2015/abs.htm)
- [Informatics 2D - Reasoning and Agents 2014/15- University of Edinburgh](http://groups.inf.ed.ac.uk/vision/VIDEO/2014/inf2d.htm)
- [Artificial Intelligence - Hochschule Ravensburg-Weingarten](https://www.youtube.com/playlist?list=PL39B5D3AFC249556A)
- [Deductive Databases and Knowledge-Based Systems - Technische Universität Braunschweig, Germany](http://www.ifis.cs.tu-bs.de/teaching/ws-1516/KBS)
- [Artificial Intelligence: Knowledge Representation and Reasoning - IIT Madras](https://nptel.ac.in/courses/106106140/)
- [Semantic Web Technologies by Dr. Harald Sack - HPI](https://www.youtube.com/playlist?list=PLoOmvuyo5UAeihlKcWpzVzB51rr014TwD)
- [Knowledge Engineering with Semantic Web Technologies by Dr. Harald Sack - HPI](https://www.youtube.com/playlist?list=PLoOmvuyo5UAcBXlhTti7kzetSsi1PpJGR)

--------------

### Machine Learning

- **Introduction to Machine Learning**

	- [MOOC Machine Learning Andrew Ng - Coursera/Stanford](https://www.youtube.com/playlist?list=PLLssT5z_DsK-h9vYZkQkYNWcItqhlRJLN) ([Notes](http://www.holehouse.org/mlclass/))
	- [Introduction to Machine Learning for Coders](https://course.fast.ai/ml.html)
	- [MOOC - Statistical Learning, Stanford University](http://www.dataschool.io/15-hours-of-expert-machine-learning-videos/)
	- [Foundations of Machine Learning Boot Camp, Berkeley Simons Institute](https://www.youtube.com/playlist?list=PLgKuh-lKre11GbZWneln-VZDLHyejO7YD)
	- [CS155 - Machine Learning & Data Mining, 2017 - Caltech](https://www.youtube.com/playlist?list=PLuz4CTPOUNi6BfMrltePqMAHdl5W33-bC) ([Notes](http://www.yisongyue.com/courses/cs155/2017_winter/)) ([2016](https://www.youtube.com/playlist?list=PL5HdMttxBY0BVTP9y7qQtzTgmcjQ3P0mb))
	- [CS 156 - Learning from Data, Caltech](https://work.caltech.edu/lectures.html)
	- [10-601 - Introduction to Machine Learning (MS) - Tom Mitchell - 2015, CMU](http://www.cs.cmu.edu/~ninamf/courses/601sp15/lectures.shtml) ([YouTube](https://www.youtube.com/playlist?list=PLAJ0alZrN8rD63LD0FkzKFiFgkOmEtltQ))
	- [10-601 Machine Learning | CMU | Fall 2017](https://www.youtube.com/playlist?list=PL7k0r4t5c10-g7CWCnHfZOAxLaiNinChk)
	- [10-701 - Introduction to Machine Learning (PhD) - Tom Mitchell, Spring 2011, CMU](http://www.cs.cmu.edu/~tom/10701_sp11/lectures.shtml) ([Fall 2014](https://www.youtube.com/playlist?list=PL7y-1rk2cCsDZCVz2xS7LrExqidHpJM3B)) ([Spring 2015 by Alex Smola](https://www.youtube.com/playlist?list=PLZSO_6-bSqHTTV7w9u7grTXBHMH-mw3qn))
	- [10 - 301/601 - Introduction to Machine Learning - Spring 2020 - CMU](https://www.youtube.com/playlist?list=PLpqQKYIU-snAPM89YPPwyQ9xdaiAdoouk)
	- [CMS 165 Foundations of Machine Learning and Statistical Inference - 2020 - Caltech](https://www.youtube.com/playlist?list=PLVNifWxslHCDlbyitaLLYBOAEPbmF1AHg)
	- [Microsoft Research - Machine Learning Course](https://www.youtube.com/playlist?list=PL34iyE0uXtxo7vPXGFkmm6KbgZQwjf9Kf)
	- [CS 446 - Machine Learning, Spring 2019, UIUC](https://courses.engr.illinois.edu/cs446/sp2019/AGS/_site/)([ Fall 2016 Lectures](https://www.youtube.com/playlist?list=PLQcasX5-oG91TgY6A_gz-IW7YSpwdnD2O))
	- [undergraduate machine learning at UBC 2012, Nando de Freitas](https://www.youtube.com/playlist?list=PLE6Wd9FR--Ecf_5nCbnSQMHqORpiChfJf)
	- [CS 229 - Machine Learning - Stanford University](https://see.stanford.edu/Course/CS229) ([Autumn 2018](https://www.youtube.com/playlist?list=PLoROMvodv4rMiGQp3WXShtMGgzqpfVfbU))
	- [CS 189/289A Introduction to Machine Learning, Prof Jonathan Shewchuk - UCBerkeley](https://people.eecs.berkeley.edu/~jrs/189/)
	- [CPSC 340: Machine Learning and Data Mining (2018) - UBC](https://www.youtube.com/playlist?list=PLWmXHcz_53Q02ZLeAxigki1JZFfCO6M-b)
	- [CS4780/5780 Machine Learning, Fall 2013 - Cornell University](http://www.cs.cornell.edu/courses/cs4780/2013fa/)
	- [CS4780/5780 Machine Learning, Fall 2018 - Cornell University](http://www.cs.cornell.edu/courses/cs4780/2018fa/page18/index.html) ([Youtube](https://www.youtube.com/playlist?list=PLl8OlHZGYOQ7bkVbuRthEsaLr7bONzbXS))
	- [CSE474/574 Introduction to Machine Learning - SUNY University at Buffalo](https://www.youtube.com/playlist?list=PLEQDy5tl3xkMzk_zlo2DPzXteCquHA8bQ)
	- [CS 5350/6350 - Machine Learning, Fall 2016, University of Utah](https://www.youtube.com/playlist?list=PLbuogVdPnkCozRSsdueVwX7CF9N4QWL0B)
	- [ECE 5984 Introduction to Machine Learning, Spring 2015 - Virginia Tech](https://filebox.ece.vt.edu/~s15ece5984/)
	- [CSx824/ECEx242 Machine Learning, Bert Huang, Fall 2015 - Virginia Tech](https://www.youtube.com/playlist?list=PLUenpfvlyoa0rMoE5nXA8kdctBKE9eSob)
	- [STA 4273H - Large Scale Machine Learning, Winter 2015 - University of Toronto](http://www.cs.toronto.edu/~rsalakhu/STA4273_2015/lectures.html)
	- [CS 485/685 Machine Learning, Shai Ben-David, University of Waterloo](https://www.youtube.com/channel/UCR4_akQ1HYMUcDszPQ6jh8Q/videos)
	- [STAT 441/841 Classification Winter 2017 , Waterloo](https://www.youtube.com/playlist?list=PLehuLRPyt1HzXDemu7K4ETcF0Ld_B5adG)
	- [10-605 - Machine Learning with Large Datasets, Fall 2016 - CMU](https://www.youtube.com/channel/UCIE4UdPoCJZMAZrTLuq-CPQ/videos)
	- [Information Theory, Pattern Recognition, and Neural Networks - University of Cambridge](https://www.youtube.com/playlist?list=PLruBu5BI5n4aFpG32iMbdWoRVAA-Vcso6)
	- [Python and machine learning - Stanford Crowd Course Initiative](https://www.youtube.com/playlist?list=PLVxFQjPUB2cnYGZPAGG52OQc9SpWVKjjB)
	- [MOOC - Machine Learning Part 1a - Udacity/Georgia Tech](https://www.youtube.com/playlist?list=PLAwxTw4SYaPl0N6-e1GvyLp5-MUMUjOKo) ([Part 1b](https://www.youtube.com/playlist?list=PLAwxTw4SYaPlkESDcHD-0oqVx5sAIgz7O) [Part 2](https://www.youtube.com/playlist?list=PLAwxTw4SYaPmaHhu-Lz3mhLSj-YH-JnG7) [Part 3](https://www.youtube.com/playlist?list=PLAwxTw4SYaPnidDwo9e2c7ixIsu_pdSNp))
	- [Machine Learning and Pattern Recognition 2015/16- University of Edinburgh](http://groups.inf.ed.ac.uk/vision/VIDEO/2015/mlpr.htm)
	- [Introductory Applied Machine Learning 2015/16- University of Edinburgh](http://groups.inf.ed.ac.uk/vision/VIDEO/2015/iaml.htm)
	- [Pattern Recognition Class (2012)- Universität Heidelberg](https://www.youtube.com/playlist?list=PLuRaSnb3n4kRDZVU6wxPzGdx1CN12fn0w)
	- [Introduction to Machine Learning and Pattern Recognition - CBCSL OSU](https://www.youtube.com/playlist?list=PLcXJymqaE9PPGGtFsTNoDWKl-VNVX5d6b)
	- [Introduction to Machine Learning - IIT Kharagpur](https://nptel.ac.in/courses/106105152/)
	- [Introduction to Machine Learning - IIT Madras](https://nptel.ac.in/courses/106106139/)
	- [Pattern Recognition - IISC Bangalore](https://nptel.ac.in/courses/117108048/)
	- [Pattern Recognition and Application - IIT Kharagpur](https://nptel.ac.in/courses/117105101/)
	- [Pattern Recognition - IIT Madras](https://nptel.ac.in/courses/106106046/)
	- [Machine Learning Summer School 2013 - Max Planck Institute for Intelligent Systems Tübingen](https://www.youtube.com/playlist?list=PLqJm7Rc5-EXFv6RXaPZzzlzo93Hl0v91E)
	- [Machine Learning - Professor Kogan (Spring 2016) - Rutgers](https://www.youtube.com/playlist?list=PLauepKFT6DK_1_plY78bXMDj-bshv7UsQ)
	- [CS273a: Introduction to Machine Learning](http://sli.ics.uci.edu/Classes/2015W-273a) ([YouTube](https://www.youtube.com/playlist?list=PLkWzaBlA7utJMRi89i9FAKMopL0h0LBMk))
	- [Machine Learning Crash Course 2015](https://www.youtube.com/playlist?list=PLyGKBDfnk-iD5dK8N7UBUFVVDBBtznenR)
	- [COM4509/COM6509 Machine Learning and Adaptive Intelligence 2015-16](http://inverseprobability.com/mlai2015/)
	- [10715 Advanced Introduction to Machine Learning](https://sites.google.com/site/10715advancedmlintro2017f/lectures)
	- [Introduction to Machine Learning - Spring 2018 - ETH Zurich](https://www.youtube.com/playlist?list=PLzn6LN6WhlN273tsqyfdrBUsA-o5nUESV)
	- [Machine Learning - Pedro Domingos- University of Washington](https://www.youtube.com/user/UWCSE/playlists?view=50&sort=dd&shelf_id=16)
	- [Advanced Machine Learning - 2019 - ETH Zürich](https://www.youtube.com/playlist?list=PLY-OA_xnxFwSe98pzMGVR4bjAZZYrNT7L)
	- [Machine Learning (COMP09012)](https://www.youtube.com/playlist?list=PLyH-5mHPFffFwz7Twap0XuVeUJ8vuco9t)
	- [Probabilistic Machine Learning 2020 - University of Tübingen](https://www.youtube.com/playlist?list=PL05umP7R6ij1tHaOFY96m5uX3J21a6yNd)
	- [Statistical Machine Learning 2020 - Ulrike von Luxburg - University of Tübingen](https://www.youtube.com/playlist?list=PL05umP7R6ij2XCvrRzLokX6EoHWaGA2cC)
	- [COMS W4995 - Applied Machine Learning - Spring 2020 - Columbia University](https://www.cs.columbia.edu/~amueller/comsw4995s20/schedule/)
	
- **Data Mining**

	- [CSEP 546, Data Mining - Pedro Domingos, Sp 2016 - University of Washington](https://courses.cs.washington.edu/courses/csep546/16sp/) ([YouTube](https://www.youtube.com/playlist?list=PLTPQEx-31JXgtDaC6-3HxWcp7fq4N8YGr))
	- [CS 5140/6140 - Data Mining, Spring 2016, University of Utah](https://www.cs.utah.edu/~jeffp/teaching/cs5140.html) ([Youtube](https://www.youtube.com/playlist?list=PLbuogVdPnkCpXfb43Wvc7s5fXWzedwTPB))
	- [CS 5955/6955 - Data Mining, University of Utah](http://www.cs.utah.edu/~jeffp/teaching/cs5955.html) ([YouTube](https://www.youtube.com/channel/UCcrlwW88yMcXujhGjSP2WBg/videos))
	- [Statistics 202 - Statistical Aspects of Data Mining, Summer 2007 - Google](http://www.stats202.com/original_index.html) ([YouTube](https://www.youtube.com/playlist?list=PLFE776F2C513A744E))
	- [MOOC - Text Mining and Analytics by ChengXiang Zhai](https://www.youtube.com/playlist?list=PLLssT5z_DsK8Xwnh_0bjN4KNT81bekvtt)
	- [Information Retrieval SS 2014, iTunes - HPI](https://itunes.apple.com/us/itunes-u/information-retrieval-ss-2014/id874200291)
	- [MOOC - Data Mining with Weka](https://www.youtube.com/playlist?list=PLm4W7_iX_v4NqPUjceOGd-OKNVO4c_cPD)
	- [CS 290 DataMining Lectures](https://www.youtube.com/playlist?list=PLB4CCA346A5741C4C)
	- [CS246 - Mining Massive Data Sets, Winter 2016, Stanford University](https://web.stanford.edu/class/cs246/) ([YouTube](https://www.youtube.com/channel/UC_Oao2FYkLAUlUVkBfze4jg/videos))
	- [Data Mining: Learning From Large Datasets - Fall 2017 - ETH Zurich](https://www.youtube.com/playlist?list=PLY-OA_xnxFwRHZO6L6yT253VPgrZazQs6)
	- [Information Retrieval - Spring 2018 - ETH Zurich](https://www.youtube.com/playlist?list=PLzn6LN6WhlN1ktkDvNurPSDwTQ_oGQisn)
	- [CAP6673 - Data Mining and Machine Learning - FAU](http://www.cse.fau.edu/~taghi/classes/cap6673/)([Video lectures](https://vimeo.com/album/1505953))
	- [Data Warehousing and Data Mining Techniques - Technische Universität Braunschweig, Germany](http://www.ifis.cs.tu-bs.de/teaching/ws-1617/dwh)
- **Data Science**
	- [Data 8: The Foundations of Data Science - UC Berkeley](http://data8.org/) ([Summer 17](http://data8.org/su17/))
	- [CSE519 - Data Science Fall 2016 - Skiena, SBU](https://www.youtube.com/playlist?list=PLOtl7M3yp-DVBdLYatrltDJr56AKZ1qXo)
	- [CS 109 Data Science, Harvard University](http://cs109.github.io/2015/pages/videos.html) ([YouTube](https://www.youtube.com/playlist?list=PLb4G5axmLqiuneCqlJD2bYFkBwHuOzKus))
	- [6.0002 Introduction to Computational Thinking and Data Science - MIT OCW](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-0002-introduction-to-computational-thinking-and-data-science-fall-2016/lecture-videos/)
	- [Data 100 - Summer 19- UC Berkeley](https://www.youtube.com/playlist?list=PLPHXc20GewP8J56CisONS_mFZWZAfa7jR)
	- [Distributed Data Analytics (WT 2017/18) - HPI University of Potsdam](https://www.tele-task.de/series/1179/)
	- [Statistics 133 - Concepts in Computing with Data, Fall 2013 - UC Berkeley](https://www.youtube.com/playlist?list=PL-XXv-cvA_iDsSPnMJlnhIyADGUmikoIO)
	- [Data Profiling and Data Cleansing (WS 2014/15) - HPI University of Potsdam](https://www.tele-task.de/series/1027/)
	- [AM 207 - Stochastic Methods for Data Analysis, Inference and Optimization, Harvard University](http://am207.github.io/2016/index.html)
	- [CS 229r - Algorithms for Big Data, Harvard University](http://people.seas.harvard.edu/~minilek/cs229r/fall15/lec.html) ([Youtube](https://www.youtube.com/playlist?list=PL2SOU6wwxB0v1kQTpqpuu5kEJo2i-iUyf))
	- [Algorithms for Big Data - IIT Madras](https://nptel.ac.in/courses/106106142/)
- **Probabilistic Graphical Modeling**
	- [MOOC - Probabilistic Graphical Models - Coursera](https://www.youtube.com/playlist?list=PLvfF4UFg6Ejj6SX-ffw-O4--SPbB9P7eP)
	- [CS 6190 - Probabilistic Modeling, Spring 2016, University of Utah](https://www.youtube.com/playlist?list=PLbuogVdPnkCpvxdF-Gy3gwaBObx7AnQut)
	- [10-708 - Probabilistic Graphical Models, Carnegie Mellon University](https://www.cs.cmu.edu/~epxing/Class/10708-20/lectures.html)
	- [Probabilistic Graphical Models, Daphne Koller, Stanford University](http://openclassroom.stanford.edu/MainFolder/CoursePage.php?course=ProbabilisticGraphicalModels)
	- [Probabilistic Models - UNIVERSITY OF HELSINKI](https://www.cs.helsinki.fi/en/courses/582636/2015/K/K/1)
	- [Probabilistic Modelling and Reasoning 2015/16- University of Edinburgh](http://groups.inf.ed.ac.uk/vision/VIDEO/2015/pmr.htm)
	- [Probabilistic Graphical Models, Spring 2018 - Notre Dame](https://www.youtube.com/playlist?list=PLd-PuDzW85AcV4bgdu7wHPL37hm60W4RM)
- **Deep Learning**
	- [6.S191: Introduction to Deep Learning - MIT](http://introtodeeplearning.com/)
	- [Deep Learning CMU](https://www.youtube.com/channel/UC8hYZGEkI2dDO8scT8C5UQA/videos)
	- [Part 1: Practical Deep Learning for Coders, v3 - fast.ai](https://course.fast.ai/)
	- [Part 2: Deep Learning from the Foundations - fast.ai](https://course.fast.ai/part2)
	- [Deep learning at Oxford 2015 - Nando de Freitas](https://www.youtube.com/playlist?list=PLE6Wd9FR--EfW8dtjAuPoTuPcqmOV53Fu)
	- [6.S094: Deep Learning for Self-Driving Cars - MIT](https://www.youtube.com/playlist?list=PLrAXtmErZgOeiKm4sgNOknGvNjby9efdf)
	- [CS294-129 Designing, Visualizing and Understanding Deep Neural Networks](https://bcourses.berkeley.edu/courses/1453965/pages/cs294-129-designing-visualizing-and-understanding-deep-neural-networks) ([YouTube](https://www.youtube.com/playlist?list=PLkFD6_40KJIxopmdJF_CLNqG3QuDFHQUm))
	- [CS230: Deep Learning - Autumn 2018 - Stanford University](https://www.youtube.com/playlist?list=PLoROMvodv4rOABXSygHTsbvUz4G_YQhOb)
	- [STAT-157 Deep Learning 2019 - UC Berkeley ](https://www.youtube.com/playlist?list=PLZSO_6-bSqHQHBCoGaObUljoXAyyqhpFW)
	- [Full Stack DL Bootcamp 2019 - UC Berkeley](https://www.youtube.com/playlist?list=PL_Ig1a5kxu5645uORPL8xyvHr91Lg8G1l)
	- [Deep Learning, Stanford University](http://openclassroom.stanford.edu/MainFolder/CoursePage.php?course=DeepLearning)
	- [MOOC - Neural Networks for Machine Learning, Geoffrey Hinton 2016 - Coursera](https://www.youtube.com/playlist?list=PLoRl3Ht4JOcdU872GhiYWf6jwrk_SNhz9)
	- [Deep Unsupervised Learning -- Berkeley Spring 2020](https://www.youtube.com/playlist?list=PLwRJQ4m4UJjPiJP3691u-qWwPGVKzSlNP)
	- [Stat 946 Deep Learning - University of Waterloo](https://www.youtube.com/playlist?list=PLehuLRPyt1Hyi78UOkMPWCGRxGcA9NVOE)
	- [Neural networks class - Université de Sherbrooke](http://info.usherbrooke.ca/hlarochelle/neural_networks/content.html) ([YouTube](https://www.youtube.com/playlist?list=PL6Xpj9I5qXYEcOhn7TqghAJ6NAPrNmUBH))
	- [CS294-158 Deep Unsupervised Learning SP19](https://www.youtube.com/channel/UCf4SX8kAZM_oGcZjMREsU9w/videos)
	- [DLCV - Deep Learning for Computer Vision - UPC Barcelona](https://www.youtube.com/playlist?list=PL-5eMc3HQTBavDoZpFcX-bff5WgQqSLzR)
	- [DLAI - Deep Learning for Artificial Intelligence @ UPC Barcelona](https://www.youtube.com/playlist?list=PL-5eMc3HQTBagIUjKefjcTbnXC0wXC_vd)
	- [Neural Networks and Applications - IIT Kharagpur](https://nptel.ac.in/courses/117105084/)
	- [UVA DEEP LEARNING COURSE](http://uvadlc.github.io/#lecture)
	- [Nvidia Machine Learning Class](https://www.youtube.com/playlist?list=PLTIkHmXc-7an8xbwhAJX-LQ4D4Uf-ar5I)
	- [Deep Learning - Winter 2020-21 - Tübingen Machine Learning](https://www.youtube.com/playlist?list=PL05umP7R6ij3NTWIdtMbfvX7Z-4WEXRqD)
- **Reinforcement Learning**
	- [CS234: Reinforcement Learning - Winter 2019 - Stanford University](https://www.youtube.com/playlist?list=PLoROMvodv4rOSOPzutgyCTapiGlY2Nd8u)
	- [Introduction to reinforcement learning - UCL](https://www.youtube.com/playlist?list=PLqYmG7hTraZDM-OYHWgPebj2MfCFzFObQ)
	- [Advanced Deep Learning & Reinforcement Learning - UCL](https://www.youtube.com/playlist?list=PLqYmG7hTraZDNJre23vqCGIVpfZ_K2RZs)
	- [Reinforcement Learning - IIT Madras](https://www.youtube.com/playlist?list=PLyqSpQzTE6M_FwzHFAyf4LSkz_IjMyjD9)
	- [CS885 Reinforcement Learning - Spring 2018 - University of Waterloo](https://www.youtube.com/playlist?list=PLdAoL1zKcqTXFJniO3Tqqn6xMBBL07EDc)
	- [CS 285 - Deep Reinforcement Learning- UC Berkeley](https://www.youtube.com/playlist?list=PLkFD6_40KJIwhWJpGazJ9VSj9CFMkb79A)
	- [CS 294 112 - Reinforcement Learning](https://www.youtube.com/playlist?list=PLkFD6_40KJIxJMR-j5A1mkxK26gh_qg37)
	- [NUS CS 6101 - Deep Reinforcement Learning](https://www.youtube.com/playlist?list=PLllwxvcS7ca5wOmRLKm6ri-OaC0INYehv)
	- [ECE 8851: Reinforcement Learning](https://www.youtube.com/playlist?list=PL_Nk3YvgORJs1tCLQnlnSRsOJArj_cP9u)
	- [CS294-112, Deep Reinforcement Learning Sp17](http://rll.berkeley.edu/deeprlcourse/) ([YouTube](https://www.youtube.com/playlist?list=PLkFD6_40KJIwTmSbCv9OVJB3YaO4sFwkX))
	- [UCL Course 2015 on Reinforcement Learning by David Silver from DeepMind](http://www0.cs.ucl.ac.uk/staff/d.silver/web/Teaching.html) ([YouTube](https://www.youtube.com/watch?v=2pWv7GOvuf0))
	- [Deep RL Bootcamp - Berkeley Aug 2017](https://sites.google.com/view/deep-rl-bootcamp/lectures)
	- [Reinforcement Learning - IIT Madras](https://www.youtube.com/playlist?list=PLyqSpQzTE6M_FwzHFAyf4LSkz_IjMyjD9)
- **Advanced Machine Learning**
	- [Machine Learning 2013 - Nando de Freitas, UBC](https://www.youtube.com/playlist?list=PLE6Wd9FR--EdyJ5lbFl8UuGjecvVw66F6)
	- [Machine Learning, 2014-2015, University of Oxford](https://www.cs.ox.ac.uk/people/nando.defreitas/machinelearning/)
	- [10-702/36-702 - Statistical Machine Learning - Larry Wasserman, Spring 2016, CMU](https://www.stat.cmu.edu/~ryantibs/statml/) ([Spring 2015](https://www.youtube.com/playlist?list=PLjbUi5mgii6BWEUZf7He6nowWvGne_Y8r))
	- [10-715 Advanced Introduction to Machine Learning - CMU](http://www.cs.cmu.edu/~bapoczos/Classes/ML10715_2015Fall/) ([YouTube](https://www.youtube.com/playlist?list=PL4DwY1suLMkcu-wytRDbvBNmx57CdQ2pJ))
	- [CS 281B - Scalable Machine Learning, Alex Smola, UC Berkeley](http://alex.smola.org/teaching/berkeley2012/syllabus.html)
	- [18.409 Algorithmic Aspects of Machine Learning Spring 2015 - MIT](https://www.youtube.com/playlist?list=PLB3sDpSRdrOvI1hYXNsa6Lety7K8FhPpx)
	- [CS 330 - Deep Multi-Task and Meta Learning - Fall 2019 - Stanford University](https://cs330.stanford.edu/) ([Youtube](https://www.youtube.com/playlist?list=PLoROMvodv4rMC6zfYmnD7UG3LVvwaITY5))
- **ML based Natural Language Processing and Computer Vision**
	- [CS 224d - Deep Learning for Natural Language Processing, Stanford University](http://cs224d.stanford.edu/syllabus.html) ([Lectures - Youtube](https://www.youtube.com/playlist?list=PLCJlDcMjVoEdtem5GaohTC1o9HTTFtK7_))
	- [CS 224N - Natural Language Processing, Stanford University](http://web.stanford.edu/class/cs224n/) ([Lecture videos](https://www.youtube.com/playlist?list=PLgtM85Maly3n2Fp1gJVvqb0bTC39CPn1N))
	- [CS 124 - From Languages to Information - Stanford University](https://www.youtube.com/channel/UC_48v322owNVtORXuMeRmpA/playlists?view=50&sort=dd&shelf_id=2)
	- [MOOC - Natural Language Processing, Dan Jurafsky & Chris Manning - Coursera](https://www.youtube.com/playlist?list=PL6397E4B26D00A269)
	- [fast.ai Code-First Intro to Natural Language Processing](https://www.youtube.com/playlist?list=PLtmWHNX-gukKocXQOkQjuVxglSDYWsSh9) ([Github](https://github.com/fastai/course-nlp))
	- [MOOC - Natural Language Processing - Coursera, University of Michigan](https://www.youtube.com/playlist?list=PLLssT5z_DsK8BdawOVCCaTCO99Ya58ryR)
	- [CS 231n - Convolutional Neural Networks for Visual Recognition, Stanford University](https://www.youtube.com/playlist?list=PL3FW7Lu3i5JvHM8ljYj-zLfQRF3EO8sYv)
	- [CS224U: Natural Language Understanding - Spring 2019 - Stanford University](https://www.youtube.com/playlist?list=PLoROMvodv4rObpMCir6rNNUlFAn56Js20)
	- [Deep Learning for Natural Language Processing, 2017 - Oxford University](https://github.com/oxford-cs-deepnlp-2017/lectures)
	- [Machine Learning for Robotics and Computer Vision, WS 2013/2014 - TU München](https://vision.in.tum.de/teaching/ws2013/ml_ws13) ([YouTube](https://www.youtube.com/playlist?list=PLTBdjV_4f-EIiongKlS9OKrBEp8QR47Wl))
	- [Informatics 1 - Cognitive Science 2015/16- University of Edinburgh](http://groups.inf.ed.ac.uk/vision/VIDEO/2015/inf1cs.htm)
	- [Informatics 2A - Processing Formal and Natural Languages 2016-17 - University of Edinburgh](http://www.inf.ed.ac.uk/teaching/courses/inf2a/schedule.html)
	- [Computational Cognitive Science 2015/16- University of Edinburgh](http://groups.inf.ed.ac.uk/vision/VIDEO/2015/ccs.htm)
	- [Accelerated Natural Language Processing 2015/16- University of Edinburgh](http://groups.inf.ed.ac.uk/vision/VIDEO/2015/anlp.htm)
	- [Natural Language Processing - IIT Bombay](https://nptel.ac.in/courses/106101007/)
	- [NOC:Deep Learning For Visual Computing - IIT Kharagpur](https://nptel.ac.in/courses/108/105/108105103/)
	- [CS 11-747 - Neural Nets for NLP - 2019 - CMU](https://www.youtube.com/playlist?list=PL8PYTP1V4I8Ajj7sY6sdtmjgkt7eo2VMs)
	- [Natural Language Processing - Michael Collins - Columbia University](https://www.youtube.com/playlist?list=PLA212ij5XG8OTDRl8IWFiJgHR9Ve2k9pv)
	- [Deep Learning for Computer Vision - University of Michigan](https://www.youtube.com/playlist?list=PL5-TkQAfAZFbzxjBHtzdVCWE0Zbhomg7r)
	- [CMU CS11-737 - Multilingual Natural Language Processing](https://www.youtube.com/playlist?list=PL8PYTP1V4I8CHhppU6n1Q9-04m96D9gt5)
- **Time Series Analysis**
	- [02417 Time Series Analysis](https://www.youtube.com/playlist?list=PLtiTxpFJ4k6TZ0g496fVcQpt_-XJRNkbi)
	- [Applied Time Series Analysis](https://www.youtube.com/playlist?list=PLl0FT6O_WWDBm-4W-eoK34omYmEMseQDX)
- **Misc Machine Learning Topics**
	- [EE364a: Convex Optimization I - Stanford University](http://web.stanford.edu/class/ee364a/videos.html)
	- [CS 6955 - Clustering, Spring 2015, University of Utah](https://www.youtube.com/playlist?list=PLbuogVdPnkCpRvi-qSMCdOwyn4UYoPxTI)
	- [Info 290 - Analyzing Big Data with Twitter, UC Berkeley school of information](http://blogs.ischool.berkeley.edu/i290-abdt-s12/) ([YouTube](https://www.youtube.com/playlist?list=PLE8C1256A28C1487F))
	- [10-725 Convex Optimization, Spring 2015 - CMU](http://www.stat.cmu.edu/~ryantibs/convexopt-S15/)
	- [10-725 Convex Optimization: Fall 2016 - CMU](http://www.stat.cmu.edu/~ryantibs/convexopt/)
	- [CAM 383M - Statistical and Discrete Methods for Scientific Computing, University of Texas](http://granite.ices.utexas.edu/coursewiki/index.php/Main_Page)
	- [9.520 - Statistical Learning Theory and Applications, Fall 2015 - MIT](https://www.youtube.com/playlist?list=PLyGKBDfnk-iDj3FBd0Avr_dLbrU8VG73O)
	- [Reinforcement Learning - UCL](https://www.youtube.com/playlist?list=PLacBNHqv7n9gp9cBMrA6oDbzz_8JqhSKo)
	- [Regularization Methods for Machine Learning 2016](http://academictorrents.com/details/493251615310f9b6ae1f483126292378137074cd) ([YouTube](https://www.youtube.com/playlist?list=PLbF0BXX_6CPJ20Gf_KbLFnPWjFTvvRwCO))
	- [Statistical Inference in Big Data - University of Toronto](http://fields2015bigdata2inference.weebly.com/materials.html)
	- [10-725 Optimization Fall 2012 - CMU](http://www.cs.cmu.edu/~ggordon/10725-F12/schedule.html)
	- [10-801 Advanced Optimization and Randomized Methods - CMU](http://www.cs.cmu.edu/~suvrit/teach/aopt.html) ([YouTube](https://www.youtube.com/playlist?list=PLjTcdlvIS6cjdA8WVXNIk56X_SjICxt0d))
	- [Reinforcement Learning 2015/16- University of Edinburgh](http://groups.inf.ed.ac.uk/vision/VIDEO/2015/rl.htm)
	- [Reinforcement Learning - IIT Madras](https://nptel.ac.in/courses/106106143/)
	- [Statistical Rethinking Winter 2015 - Richard McElreath](https://www.youtube.com/playlist?list=PLDcUM9US4XdMdZOhJWJJD4mDBMnbTWw_z)
	- [Music Information Retrieval - University of Victoria, 2014](http://marsyas.cs.uvic.ca/mirBook/course/)
	- [PURDUE Machine Learning Summer School 2011](https://www.youtube.com/playlist?list=PL2A65507F7D725EFB)
	- [Foundations of Machine Learning - Blmmoberg Edu](https://bloomberg.github.io/foml/#home)
	- [Introduction to reinforcement learning - UCL](https://www.youtube.com/playlist?list=PLqYmG7hTraZDM-OYHWgPebj2MfCFzFObQ)
	- [Advanced Deep Learning & Reinforcement Learning - UCL](https://www.youtube.com/playlist?list=PLqYmG7hTraZDNJre23vqCGIVpfZ_K2RZs)
	- [Web Information Retrieval (Proff. L. Becchetti - A. Vitaletti)](https://www.youtube.com/playlist?list=PLAQopGWlIcya-9yzQ8c8UtPOuCv0mFZkr)
	- [Big Data Systems (WT 2019/20) - Prof. Dr. Tilmann Rabl - HPI](https://www.tele-task.de/series/1286/)
	- [Distributed Data Analytics (WT 2017/18) - Dr. Thorsten Papenbrock - HPI](https://www.tele-task.de/series/1179/)

- **Probability & Statistics**

	- [6.041 Probabilistic Systems Analysis and Applied Probability - MIT OCW](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-041sc-probabilistic-systems-analysis-and-applied-probability-fall-2013/)
	- [Statistics 110 - Probability - Harvard University](https://www.youtube.com/playlist?list=PL2SOU6wwxB0uwwH80KTQ6ht66KWxbzTIo)
	- [STAT 2.1x: Descriptive Statistics | UC Berkeley](https://www.youtube.com/playlist?list=PL_Ig1a5kxu56TfFnGlRlH2YpOBWGiYsQD)
	- [STAT 2.2x: Probability | UC Berkeley](https://www.youtube.com/playlist?list=PL_Ig1a5kxu57qPZnHm-ie-D7vs9g7U-Cl)
	- [MOOC - Statistics: Making Sense of Data, Coursera](http://academictorrents.com/details/a0cbaf3e03e0893085b6fbdc97cb6220896dddf2)
	- [MOOC - Statistics One - Coursera](https://www.youtube.com/playlist?list=PLycnP7USbo1V3jlyjAzWUB201cLxPq4NP)
	- [Probability and Random Processes - IIT Kharagpur](https://nptel.ac.in/courses/117105085/)
	- [MOOC - Statistical Inference - Coursera](https://www.youtube.com/playlist?list=PLgIPpm6tJZoSvrYM54BUqJJ4CWrYeGO40)
	- [131B - Introduction to Probability and Statistics, UCI](https://www.youtube.com/playlist?list=PLqOZ6FD_RQ7k-j-86QUC2_0nEu0QOP-Wy)
	- [STATS 250 - Introduction to Statistics and Data Analysis, UMichigan](https://www.youtube.com/playlist?list=PL432AB57AF9F43D4F)
	- [Sets, Counting and Probability - Harvard](http://matterhorn.dce.harvard.edu/engage/ui/index.html#/1999/01/82347)
	- [Opinionated Lessons in Statistics](http://www.opinionatedlessons.org/) ([Youtube](https://www.youtube.com/playlist?list=PLUAHeOPjkJseXJKbuk9-hlOfZU9Wd6pS0))
	- [Statistics - Brandon Foltz](https://www.youtube.com/user/BCFoltz/playlists)
	- [Statistical Rethinking: A Bayesian Course Using R and Stan](https://github.com/rmcelreath/statrethinking_winter2019) ([Lectures - Aalto University](https://aalto.cloud.panopto.eu/Panopto/Pages/Sessions/List.aspx#folderID=%22f0ec3a25-9e23-4935-873b-a9f401646812%22)) ([Book](http://www.stat.columbia.edu/~gelman/book/))
	 - [02402 Introduction to Statistics E12 - Technical University of Denmark](https://www.youtube.com/playlist?list=PLMn2aW3wpAtPC8tZHQy6nwWsFG7P6sPqw) ([F17](https://www.youtube.com/playlist?list=PLgowegO9Se58_BnUNnaARajEE_bX-GJEz))
- **Linear Algebra**
	- [18.06 - Linear Algebra, Prof. Gilbert Strang, MIT OCW](https://ocw.mit.edu/courses/mathematics/18-06sc-linear-algebra-fall-2011/)
	- [18.065 Matrix Methods in Data Analysis, Signal Processing, and Machine Learning - MIT OCW](https://ocw.mit.edu/courses/mathematics/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/video-lectures/)
	- [Linear Algebra (Princeton University)](https://www.youtube.com/playlist?list=PLGqzsq0erqU7w7ZrTZ-pWWk4-AOkiGEGp)
	- [MOOC: Coding the Matrix: Linear Algebra through Computer Science Applications - Coursera](http://academictorrents.com/details/54cd86f3038dfd446b037891406ba4e0b1200d5a)
	- [CS 053 - Coding the Matrix - Brown University](http://cs.brown.edu/courses/cs053/current/lectures.htm) ([Fall 14 videos](https://cs.brown.edu/video/channels/coding-matrix-fall-2014/))
	- [Linear Algebra Review - CMU](http://www.cs.cmu.edu/~zkolter/course/linalg/outline.html)
	- [A first course in Linear Algebra - N J Wildberger - UNSW](https://www.youtube.com/playlist?list=PL44B6B54CBF6A72DF)
	- [INTRODUCTION TO MATRIX ALGEBRA](http://ma.mathforcollege.com/youtube/index.html)
	- [Computational Linear Algebra - fast.ai](https://www.youtube.com/playlist?list=PLtmWHNX-gukIc92m1K0P6bIOnZb-mg0hY) ([Github](https://github.com/fastai/numerical-linear-algebra))
- [10-600 Math Background for ML - CMU](https://www.youtube.com/playlist?list=PL7y-1rk2cCsA339crwXMWUaBRuLBvPBCg)
- [MIT 18.065 Matrix Methods in Data Analysis, Signal Processing, and Machine Learning](https://ocw.mit.edu/courses/mathematics/18-065-matrix-methods-in-data-analysis-signal-processing-and-machine-learning-spring-2018/video-lectures/)
- [36-705 - Intermediate Statistics - Larry Wasserman, CMU](http://www.stat.cmu.edu/~larry/=stat705/) ([YouTube](https://www.youtube.com/playlist?list=PLcW8xNfZoh7eI7KSWneVWq-7wr8ffRtHF))
- [Combinatorics - IISC Bangalore](https://nptel.ac.in/courses/106108051/)
- [Advanced Engineering Mathematics - Notre Dame](https://www.youtube.com/playlist?list=PLd-PuDzW85Ae4pzlylMLzq_a-RHPx8ryA)
- [Statistical Computing for Scientists and Engineers - Notre Dame](https://www.youtube.com/playlist?list=PLd-PuDzW85AeltIRcjDY7Z4q49NEAuMcA)
- [Statistical Computing, Fall 2017 - Notre Dame](https://www.youtube.com/playlist?list=PLd-PuDzW85AcSgNGnT5TUHt85SrCljT3V)
- [Mathematics for Machine Learning, Lectures by Ulrike von Luxburg - Tübingen Machine Learning](https://www.youtube.com/playlist?list=PL05umP7R6ij1a6KdEy8PVE9zoCv6SlHRS)


-------------------------

### Robotics

- [CS 223A - Introduction to Robotics, Stanford University](https://see.stanford.edu/Course/CS223A)
- [6.832 Underactuated Robotics - MIT OCW](https://ocw.mit.edu/courses/electrical-engineering-and-computer-science/6-832-underactuated-robotics-spring-2009/)
- [CS287 Advanced Robotics at UC Berkeley Fall 2019 -- Instructor: Pieter Abbeel](https://www.youtube.com/playlist?list=PLwRJQ4m4UJjNBPJdt8WamRAt4XKc639wF)
- [CS 287 - Advanced Robotics, Fall 2011, UC Berkeley](https://people.eecs.berkeley.edu/~pabbeel/cs287-fa11/) ([Videos](http://rll.berkeley.edu/cs287/lecture_videos/))
- [CS235 - Applied Robot Design for Non-Robot-Designers - Stanford University](https://www.youtube.com/user/StanfordCS235/videos)
- [Lecture: Visual Navigation for Flying Robots](https://vision.in.tum.de/teaching/ss2012/visnav2012) ([YouTube](https://www.youtube.com/playlist?list=PLTBdjV_4f-EKeki5ps2WHqJqyQvxls4ha))
- [CS 205A: Mathematical Methods for Robotics, Vision, and Graphics (Fall 2013)](https://www.youtube.com/playlist?list=PLQ3UicqQtfNvQ_VzflHYKhAqZiTxOkSwi)
- [Robotics 1, Prof. De Luca, Università di Roma](http://www.dis.uniroma1.it/~deluca/rob1_en/material_rob1_en_2014-15.html) ([YouTube](https://www.youtube.com/playlist?list=PLAQopGWlIcyaqDBW1zSKx7lHfVcOmWSWt))
- [Robotics 2, Prof. De Luca, Università di Roma](http://www.diag.uniroma1.it/~deluca/rob2_en/material_rob2_en.html) ([YouTube](https://www.youtube.com/playlist?list=PLAQopGWlIcya6LnIF83QlJTqvpYmJXnDm))
- [Robot Mechanics and Control, SNU](https://www.youtube.com/playlist?list=PLkjy3Accn-E7mlbuSF4aajcMMckG4wLvW)
- [Introduction to Robotics Course - UNCC](https://www.youtube.com/playlist?list=PL4847E1D1C121292F)
- [SLAM Lectures](https://www.youtube.com/playlist?list=PLpUPoM7Rgzi_7YWn14Va2FODh7LzADBSm)
- [Introduction to Vision and Robotics 2015/16- University of Edinburgh](http://groups.inf.ed.ac.uk/vision/VIDEO/2015/ivr.htm)
- [ME 597 – Autonomous Mobile Robotics – Fall 2014](http://wavelab.uwaterloo.ca/index6ea9.html?page_id=267)
- [ME 780 – Perception For Autonomous Driving – Spring 2017](http://wavelab.uwaterloo.ca/indexaef8.html?page_id=481)
- [ME780 – Nonlinear State Estimation for Robotics and Computer Vision – Spring 2017](http://wavelab.uwaterloo.ca/indexe9a5.html?page_id=533)
- [METR 4202/7202 -- Robotics & Automation - University of Queensland](http://robotics.itee.uq.edu.au/~metr4202/lectures.html)
- [Robotics - IIT Bombay](https://nptel.ac.in/courses/112101099/)
- [Introduction to Machine Vision](https://www.youtube.com/playlist?list=PL1pxneANaikCO1-Z0XTaljLR3SE8tgRXY)
- [6.834J Cognitive Robotics - MIT OCW ](https://ocw.mit.edu/courses/aeronautics-and-astronautics/16-412j-cognitive-robotics-spring-2016/)
- [Hello (Real) World with ROS – Robot Operating System - TU Delft](https://ocw.tudelft.nl/courses/hello-real-world-ros-robot-operating-system/)
- [Programming for Robotics (ROS) - ETH Zurich](https://www.youtube.com/playlist?list=PLE-BQwvVGf8HOvwXPgtDfWoxd4Cc6ghiP)
- [Mechatronic System Design - TU Delft](https://ocw.tudelft.nl/courses/mechatronic-system-design/)
- [CS 206 Evolutionary Robotics Course Spring 2020](https://www.youtube.com/playlist?list=PLAuiGdPEdw0inlKisMbjDypCbvcb_GBN9)
- [Foundations of Robotics - UTEC 2018-I](https://www.youtube.com/playlist?list=PLoWGuY2dW-Acmc8V5NYSAXBxADMm1rE4p)
- [Robotics - Youtube](https://www.youtube.com/playlist?list=PL_onPhFCkVQhuPiUxUW2lFHB39QsavEEA)
- [Robotics and Control: Theory and Practice IIT Roorkee](https://www.youtube.com/playlist?list=PLLy_2iUCG87AjAXKbNMiKJZ2T9vvGpMB0)
- [Mechatronics](https://www.youtube.com/playlist?list=PLtuwVtW88fOeTFS_szBWif0Mcc0lfNWaz)
- [ME142 - Mechatronics Spring 2020 - UC Merced](https://www.youtube.com/playlist?list=PL-euleXgwWUNQ80DGq6qopHBmHcQyEyNQ)
- [Mobile Sensing and Robotics - Bonn University](https://www.youtube.com/playlist?list=PLgnQpQtFTOGQJXx-x0t23RmRbjp_yMb4v)
- [MSR2 - Sensors and State Estimation Course (2020) - Bonn University](https://www.youtube.com/playlist?list=PLgnQpQtFTOGQh_J16IMwDlji18SWQ2PZ6)
- [SLAM Course (2013) - Bonn University](https://www.youtube.com/playlist?list=PLgnQpQtFTOGQrZ4O5QzbIHgl3b1JHimN_)
- [ENGR486 Robot Modeling and Control (2014W)](https://www.youtube.com/playlist?list=PLJzZfbLAMTelwaLxFXteeblbY2ytU2AxX)
- [Robotics by Prof. D K Pratihar - IIT Kharagpur](https://www.youtube.com/playlist?list=PLbRMhDVUMngcdUbBySzyzcPiFTYWr4rV_)
- [Introduction to Mobile Robotics - SS 2019 - Universität Freiburg](http://ais.informatik.uni-freiburg.de/teaching/ss19/robotics/)
- [Robot Mapping - WS 2018/19 - Universität Freiburg](http://ais.informatik.uni-freiburg.de/teaching/ws18/mapping/)
- [Mechanism and Robot Kinematics - IIT Kharagpur](https://nptel.ac.in/courses/112/105/112105236/)
- [Self-Driving Cars - Cyrill Stachniss - Winter 2020/21 - University of Bonn) ](https://www.youtube.com/playlist?list=PLgnQpQtFTOGQo2Z_ogbonywTg8jxCI9pD)
- [Mobile Sensing and Robotics 1 – Part Stachniss (Jointly taught with PhoRS) - University of Bonn](https://www.ipb.uni-bonn.de/msr1-2020/)
- [Mobile Sensing and Robotics 2 – Stachniss & Klingbeil/Holst - University of Bonn](https://www.ipb.uni-bonn.de/msr2-2020/)


----------------------------------

## 500 + 𝗔𝗿𝘁𝗶𝗳𝗶𝗰𝗶𝗮𝗹 𝗜𝗻𝘁𝗲𝗹𝗹𝗶𝗴𝗲𝗻𝗰𝗲 𝗣𝗿𝗼𝗷𝗲𝗰𝘁 𝗟𝗶𝘀𝘁 𝘄𝗶𝘁𝗵 𝗰𝗼𝗱𝗲

*500 AI Machine learning Deep learning Computer vision NLP Projects with code*

***This list is continuously updated.*** - You can take pull request and contribute.

| Sr No | Name                                                         | Link                                |
| ----- | ------------------------------------------------------------ | ----------------------------------- |
| 1     | 180 Machine learning Project                                 | [is.gd/MLtyGk](http://is.gd/MLtyGk) |
| 2     | 12 Machine learning Object Detection                         | [is.gd/jZMP1A](http://is.gd/jZMP1A) |
| 3     | 20 NLP Project with Python                                   | [is.gd/jcMvjB](http://is.gd/jcMvjB) |
| 4     | 10 Machine Learning Projects on Time Series Forecasting      | [is.gd/dOR66m](http://is.gd/dOR66m) |
| 5     | 20 Deep Learning Projects Solved and Explained with Python   | [is.gd/8Cv5EP](http://is.gd/8Cv5EP) |
| 6     | 20 Machine learning Project                                  | [is.gd/LZTF0J](http://is.gd/LZTF0J) |
| 7     | 30 Python Project Solved and Explained                       | [is.gd/xhT36v](http://is.gd/xhT36v) |
| 8     | Machine learning Course for Free                             | https://lnkd.in/ekCY8xw             |
| 9     | 5 Web Scraping Projects with Python                          | [is.gd/6XOTSn](http://is.gd/6XOTSn) |
| 10    | 20 Machine Learning Projects on Future Prediction with Python | [is.gd/xDKDkl](http://is.gd/xDKDkl) |
| 11    | 4 Chatbot Project With Python                                | [is.gd/LyZfXv](http://is.gd/LyZfXv) |
| 12    | 7 Python Gui project                                         | [is.gd/0KPBvP](http://is.gd/0KPBvP) |
| 13    | All Unsupervised learning Projects                           | [is.gd/cz11Kv](http://is.gd/cz11Kv) |
| 14    | 10 Machine learning Projects for Regression Analysis         | [is.gd/k8faV1](http://is.gd/k8faV1) |
| 15    | 10 Machine learning Project for Classification with Python   | [is.gd/BJQjMN](http://is.gd/BJQjMN) |
| 16    | 6 Sentimental Analysis Projects with python                  | [is.gd/WeiE5p](http://is.gd/WeiE5p) |
| 17    | 4 Recommendations Projects with Python                       | [is.gd/pPHAP8](http://is.gd/pPHAP8) |
| 18    | 20 Deep learning Project with python                         | [is.gd/l3OCJs](http://is.gd/l3OCJs) |
| 19    | 5 COVID19 Projects with Python                               | [is.gd/xFCnYi](http://is.gd/xFCnYi) |
| 20    | 9 Computer Vision Project with python                        | [is.gd/lrNybj](http://is.gd/lrNybj) |
| 21    | 8 Neural Network Project with python                         | [is.gd/FCyOOf](is.gd/FCyOOf)        |
| 22    | 5 Machine learning Project for healthcare                    | https://bit.ly/3b86bOH              |
| 23    | 5 NLP Project with Python                                    | https://bit.ly/3hExtNS              |
| 24    | 47 Machine Learning Projects for 2021                        | https://bit.ly/356bjiC              |
| 25    | 19 Artificial Intelligence Projects for 2021                 | https://bit.ly/38aLgsg              |
| 26    | 28 Machine learning Projects for 2021                        | https://bit.ly/3bguRF1              |
| 27    | 16 Data Science Projects with Source Code for 2021           | https://bit.ly/3oa4zYD              |
| 28    | 24 Deep learning Projects with Source Code for 2021          | https://bit.ly/3rQrOsU              |
| 29    | 25 Computer Vision Projects with Source Code for 2021        | https://bit.ly/2JDMO4I              |
| 30    | 23 Iot Projects with Source Code for 2021                    | https://bit.ly/354gT53              |
| 31    | 27 Django Projects with Source Code for 2021                 | https://bit.ly/2LdRPRZ              |
| 32    | 37 Python Fun Projects with Code for 2021                    | https://bit.ly/3hBHzz4              |
| 33    | 500 + Top Deep learning Codes                                | https://bit.ly/3n7AkAc              |
| 34    | 500 + Machine learning Codes                                 | https://bit.ly/3b32n13              |
| 35    | 20+ Machine Learning Datasets & Project Ideas                | https://bit.ly/3b2J48c              |
| 36    | 1000+ Computer vision codes                                  | https://bit.ly/2LiX1nv              |
| 37    | 300 + Industry wise Real world projects with code            | https://bit.ly/3rN7lVR              |
| 38    | 1000 + Python Project Codes                                  | https://bit.ly/3oca2xM              |
| 39    | 363 + NLP Project with Code                                  | https://bit.ly/3b442DO              |
| 40    | 50 + Code ML Models (For iOS 11) Projects                    | https://bit.ly/389dB2s              |
| 41    | 180 + Pretrained Model Projects for Image, text, Audio and Video | https://bit.ly/3hFyQMw              |
| 42    | 50 + Graph Classification Project List                       | https://bit.ly/3rOYFhH              |
| 43    | 100 + Sentence Embedding(NLP Resources)                      | https://bit.ly/355aS8c              |
| 44    | 100 + Production Machine learning Projects                   | https://bit.ly/353ckI0              |
| 45    | 300 + Machine Learning Resources Collection                  | https://bit.ly/3b2LjIE              |
| 46    | 70 + Awesome AI                                              | https://bit.ly/3hDIXkD              |
| 47    | 150 + Machine learning Project Ideas with code               | https://bit.ly/38bfpbg              |
| 48    | 100 + AutoML Projects with code                              | https://bit.ly/356zxZX              |
| 49    | 100 + Machine Learning Model Interpretability Code Frameworks | https://bit.ly/3n7FaNB              |
| 50    | 120 + Multi Model Machine learning Code Projects             | https://bit.ly/38QRI76              |
| 51    | Awesome Chatbot Projects                                     | https://bit.ly/3rQyxmE              |
| 52    | Awesome ML Demo Project with iOS                             | https://bit.ly/389hZOY              |
| 53    | 100 + Python based Machine learning Application Projects     | https://bit.ly/3n9zLWv              |
| 54    | 100 + Reproducible Research Projects of ML and DL            | https://bit.ly/2KQ0J8C              |
| 55    | 25 + Python Projects                                         | https://bit.ly/353fRpK              |
| 56    | 8 + OpenCV Projects                                          | https://bit.ly/389mj0B              |
| 57    | 1000 + Awesome Deep learning Collection                      | https://bit.ly/3b0a9Jj              |
| 58    | 200 + Awesome NLP learning Collection                        | https://bit.ly/3b74b9o              |
| 59    | 200 + The Super Duper NLP Repo                               | https://bit.ly/3hDNnbd              |
| 60    | 100 + NLP dataset for your Projects                          | https://bit.ly/353h2Wc              |
| 61    | 364 + Machine Learning Projects definition                   | https://bit.ly/2X5QRdb              |
| 62    | 300+ Google Earth Engine Jupyter Notebooks to Analyze Geospatial Data | https://bit.ly/387JwjC              |
| 63    | 1000 + Machine learning Projects Information                 | https://bit.ly/3rMGk4N              |
| 64.   | 11 Computer Vision Projects with code                        | https://bit.ly/38gz2OR              |
| 65.   | 13 Computer Vision Projects with Code                        | https://bit.ly/3hMJdhh              |
| 66.   | 13 Cool Computer Vision GitHub Projects To Inspire You       | https://bit.ly/2LrSv6d              |
| 67.   | Open-Source Computer Vision Projects (With Tutorials)        | https://bit.ly/3pUss6U              |
| 68.   | OpenCV Computer Vision Projects with Python                  | https://bit.ly/38jmGpn              |
| 69.   | 100 + Computer vision Algorithm Implementation               | https://bit.ly/3rWgrzF              |
| 70.   | 80 + Computer vision Learning code                           | https://bit.ly/3hKCpkm              |
| 71.   | Deep learning Treasure                                       | https://bit.ly/359zLQb              |
