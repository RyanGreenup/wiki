---
title: Applications of Big Data
description: Notes from the UWS unit on SQL, NoSQL and Hadoop.
published: true
date: 2021-02-23T00:20:49.656Z
tags: 
editor: markdown
dateCreated: 2021-02-23T00:20:49.656Z
---


# Table of Contents

1.  [Links](#org3882d90)
2.  [1-2 Intro to Python](#orgc81292a)
3.  [SQLite](#orge43150d)
    1.  [Lecture](#org70e3d5a)
        1.  [OverView](#org33e1fcf)
        2.  [SQL](#orgdd8d5f3)
        3.  [Data Analysis with SQL and Python](#org5e3417f)
4.  [NoSQL (MongoDB)](#org779376f)
    1.  [Lecture](#orge9ffce8)
    2.  [Practical](#orgf41ed29)
        1.  [Using ob-MongoDB](#org7917232)
    3.  [Notes](#orgf1a5396)
5.  [Practical; SQLite](#orga609d53)
    1.  [Export](#org1059145)
    2.  [Introduction](#orga1960d8)
    3.  [SQL Exercises](#org14d3651)
        1.  [Count the Number of Records](#org0500e1b)
        2.  [Count the number of students](#org108d679)
        3.  [Count the number of female students](#org4a56055)
        4.  [Male Students that Fail a Programming Class](#orgb5157cf)
        5.  [Lowest Vs Highest](#org64b3697)
        6.  [Youngest vs Oldest Student](#org448ce4f)
        7.  [Top Performers](#org4c863e2)
    4.  [Python and SQL Questions](#orgb00709c)
    5.  [Quiz](#org4a91d71)
        1.  [Inspect the Table](#orgc8679ef)
        2.  [Average Enrolments](#orgab812c1)
        3.  [Birth year of Oldest Student](#org6a95344)
        4.  [Birth year of Oldest Female Student](#org7c0763b)
        5.  [Family name of Youngest Male Student](#org5b413f6)
        6.  [Age Difference between oldest youngest male students](#org738afd1)
        7.  [Lowest Vs Highest](#org70f5975)
6.  [Practical; NoSQL; MongoDB](#org296a23d)
    1.  [Importing Data](#org036c6f6)
        1.  [Using mongoimport](#org18c758c)
        2.  [Loading the Database](#org94a7de0)
        3.  [Using the Mongo-compass program](#compass):ATTACH:
    2.  [Workflow](#orgaa029c4)
    3.  [List Movies](#orgafd63c5)
    4.  [Find Songs](#orgb0c39d9)
    5.  [Calculate the Average Price of Books](#org0bdff3e)
        1.  [Aggregate](#orgd90930c)
    6.  [Quizz 3](#orgd45588b)
        1.  [Inverse Word Count](#org5dfa72e)
        2.  [World Bank](#org0706db8)
7.  [Predictive Modelling](#org3bacfad)
    1.  [Classification](#orgc676527)
        1.  [SVM](#org630bc73)
        2.  [Trees](#org6cb4119)
        3.  [Classification Score](#org620782e)
        4.  [Decision Tree](#org3c62bc2)
        5.  [Random Forrest](#org398f095)
    2.  [Regression](#org0b63fc9)
        1.  [Linear Regression (Ordinary Least Squares)](#org22590ed)
        2.  [Sparse Linear Regression](#org117d367)
8.  [Exam Preparation](#orgac0ac1a)
    1.  [Plot a CSV](#org9eacb89)
        1.  [Chosen approach](#org432b8bb)
        2.  [Import a CSV](#org69b96d6)
        3.  [Plot the Data](#orge1788bf)
    2.  [SQL](#orgd7a8b78)
        1.  [(1) How many students are in the database?](#org4073bc7)
        2.  [(2) List the Unique Unit IDS in the Database](#orgfa149b4)
        3.  [3. Which Unit has the lowest Mark in the database?](#org4fdab51)
        4.  [4. Which unit has the lowest average mark in the database?](#org671fa7f)
        5.  [Which is the hardest unit](#org628bcb1)
    3.  [Create Moons Data](#orge0d1e5f)
        1.  [Summary](#org6603231)
        2.  [In Detail](#orgcff832f)
    4.  [Fit a KNN Classifier](#orgc5e7924)
        1.  [Documentation](#orgbb7e0e5)
        2.  [Fit the Model](#org9e9dafd)
        3.  [Measure the score](#orgef60a21)
    5.  [Creating Datasets with Scikit learn](#orge781a1d)
        1.  [Make Blobs](#org1073649)
9.  [Sqlite as a Text Searching tool](#orgc821d5a)



<a id="org3882d90"></a>

# Links

-   [Learning Guide](Material/301110_2020_Spring_Day_Learning_Guide.pdf)
-   [First Practical (Python)](file:///home/ryan/Dropbox/DataSci/BigData/Practicals/02_Practical_2-Python_Basics-II.md)
    -   [SQL and NoSQL Practical](file:///home/ryan/Sync/DataSci/BigData/Practicals/04-MongoDB.md)
-   [Lectures](Material/00_Slides_BigData.pdf)
-   [Practice Exam](bigdata_practice_exam.pdf)

Start Recoll for Material:

    recoll -c '/home/ryan/Sync/Studies/2020Spring/BigData/Material/.recoll' & disown


<a id="orgc81292a"></a>

# 1-2 Intro to Python

Basically just refer to the [First Practical](file:///home/ryan/Dropbox/DataSci/BigData/Practicals/02_Practical_2-Python_Basics-II.md).


<a id="orge43150d"></a>

# SQLite

-   
-   [Practical 03 - SQL-Lite](BigData/Practicals/PDF/03-Practical.pdf)
    -   [Working Org-File](file:///home/ryan/Dropbox/DataSci/BigData/Practicals/04-MongoDB.md)


<a id="org70e3d5a"></a>

## Lecture


<a id="org33e1fcf"></a>

### OverView

1.  Relational Databases

    RDBMS (Relational Database Managent Systems) include software such as:
    
    -   Oracle
    -   MS SQL
    -   MySQL
    -   SQL-Lite
    
    They all implement some version of the *Structured Query Language* (SQL).
    
    This unit will be concerned with SQLite, it is a simple standalone application with no need for installation.


<a id="orgdd8d5f3"></a>

### SQL

1.  Why SQL

    SQL is widely implemented language for databases, it scales ****up**** to large systems quite well but not out to parallel systems easily.

2.  Working with SQLite

    In org-mode the `ob-sqlite` package ([See this example](https://orgmode.org/worg/org-contrib/babel/languages/ob-doc-sqlite.org.html)
    ) can be quite handy, just specify the `:dir /path/to/dir` and `:db /path/to/file.sqlite` and sqlite databases can be manipulated from within `org-mode` like so:
    
        #+begin_src sqlite :dir /tmp/ :db test-sqlite.db
        create table greeting(one varchar(10), two varchar(10));
        insert into greeting values('Hello', 'world!');
        select * from greeting
        #+end_src
    
    Which can be embedded in `org-mode` like so:
    
        create table greeting(one varchar(10), two varchar(10));
        insert into greeting values('Hello', 'world!');
        select * from greeting
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-left" />
    
    <col  class="org-left" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-left">Hello</td>
    <td class="org-left">world!</td>
    </tr>
    </tbody>
    </table>
    
    This however means we don't need to open databases, so if you're ever at the shell, you can open a database with `.open /path/to/db.sqlite` like this:
    
        .open ./BigData/Practicals/Resources :db testdb.sqlite
    
    In this unit we have the `test.db.sqlite` file, in `SQL` we could show all the tables with `show tables;`, but in `sqlite` we just use `.tables` like so:
    
        .tables
    
        record
    
    This shows that the only table is a table ambiguously called record, we can investiage each row (also referred to as records)
    
        select * from record;
    
    There are a bunch of examples that we could use for the tutorial questions


<a id="org5e3417f"></a>

### Data Analysis with SQL and Python

1.  DONE How to Derive the Correlation Coefficient

    [This Paper](file:///home/ryan/Dropbox/Studies/2020Autumn/ThinkingAboutData/correlation.pdf)
    The Correlation coefficient can be interpreted in one of two ways:
    
    -   The covariance scaled relative to the \(x\) and \(y\) variance
        -   \(\rho = \frac{S_{x, y}}{s_x \cdot s_y}\)
    -   The rate of change of the line of best fit of the standardised data
        -   This is equivalent to the rate of change of the line of best fit divided by
            \((\frac{s_y}{s_x})\):
            -   \(\rho = b \cdot \frac{s_x}{s_y} \quad \iff \quad  \hat{y_i}=bx_i + c\)
    
    This can be seen by performing linear regression in *****R*****:
    
        head(cars)
        cars_std <- as.data.frame(scale(cars))
        y <- cars$dist
        x <- cars$speed
        
        ## Correlation Coefficient
        cor(x = cars$speed, y = cars$dist)
        
        ## Covariance
        cov(x = cars$speed, y = cars$dist)/sd(cars$speed)/sd(cars$dist)
        
        ## Standardised Rate of Change
        lm(dist ~ speed, data = cars_std)$coefficients[2]
        
        ### Using Standardised Rate of change
        lm(dist ~ speed, data = cars)$coefficients[2] / (sd(y)/sd(x))
    
          speed dist
        1     4    2
        2     4   10
        3     7    4
        4     7   22
        5     8   16
        6     9   10
        
        [1] 0.8068949
        
        [1] 0.8068949
        
            speed
        0.8068949
        
            speed
        0.8068949
    
        #+BEGIN_SRC R :cache yes :exports both :results output graphics :file ./test.png
          library("ggplot2")
          cars_std <- as.data.frame(scale(cars))
        
          ggplot(cars_std, aes(x = speed, y = dist)) +
          geom_point() +
          geom_smooth(method = "lm") +
          theme_bw()
    
    ![img](./Attachments/Thinking_About_Data/correlation_lm.png)
    
    This shows that despite noise data can still have a correlation coefficient of 1
    if the noise is evenly distributed in a way that the correlation coefficient can
    have a rate of change of 1.


<a id="org779376f"></a>

# NoSQL (MongoDB)

-   
-   [Practical 04 - Mongo DB PDF](BigData/Practicals/PDF/04-Practical.pdf)
    -   [Working Org-File](file:///home/ryan/Dropbox/DataSci/BigData/Practicals/04-MongoDB.md)


<a id="orge9ffce8"></a>

## Lecture


<a id="orgf41ed29"></a>

## Practical


<a id="org7917232"></a>

### Using ob-MongoDB

1.  Org Babel Mongo

    Support for MongoDB queries in org-mode blocks, like so:
    
        #+BEGIN_SRC mongo :db staff
        db.employees.count({country: "gb"});
        #+END_SRC
        
        #+RESULTS:
        : 15
    
    1.  Installation
    
        If you're hooked up to [MELPA](http://melpa.milkbox.net/):
        
            M-x package-refresh-contents
            M-x package-install RET ob-mongo
        
        Alternatively just grab the single `ob-mongo.el` file and install that in your preferred way.
    
    2.  Status
    
        Alpha. Safe to use, but feature-poor. It's still better than it not existing at all. ;-)
    
    3.  Options
    
        Each block supports the following arguments:
        
        <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
        
        
        <colgroup>
        <col  class="org-left" />
        
        <col  class="org-left" />
        
        <col  class="org-left" />
        
        <col  class="org-left" />
        </colgroup>
        <thead>
        <tr>
        <th scope="col" class="org-left">Argument</th>
        <th scope="col" class="org-left">Description</th>
        <th scope="col" class="org-left">Example</th>
        <th scope="col" class="org-left">Default</th>
        </tr>
        </thead>
        
        <tbody>
        <tr>
        <td class="org-left"><code>:db</code></td>
        <td class="org-left">Database name.</td>
        <td class="org-left"><code>#+BEGIN_SRC mongo :db staff</code></td>
        <td class="org-left">None.</td>
        </tr>
        
        
        <tr>
        <td class="org-left"><code>:host</code></td>
        <td class="org-left">Host</td>
        <td class="org-left"><code>#+BEGIN_SRC mongo :host localhost</code></td>
        <td class="org-left">None.</td>
        </tr>
        
        
        <tr>
        <td class="org-left"><code>:port</code></td>
        <td class="org-left">Port</td>
        <td class="org-left"><code>#+BEGIN_SRC mongo :port 27018</code></td>
        <td class="org-left">None.</td>
        </tr>
        
        
        <tr>
        <td class="org-left"><code>:user</code></td>
        <td class="org-left">Username</td>
        <td class="org-left"><code>#+BEGIN_SRC mongo :user root</code></td>
        <td class="org-left">None.</td>
        </tr>
        
        
        <tr>
        <td class="org-left"><code>:password</code></td>
        <td class="org-left">Password</td>
        <td class="org-left"><code>#+BEGIN_SRC mongo :password superword</code></td>
        <td class="org-left">None.</td>
        </tr>
        
        
        <tr>
        <td class="org-left"><code>:mongoexec</code></td>
        <td class="org-left">Mongo executable</td>
        <td class="org-left"><code>#+BEGIN_SRC mongo :mongoexec mongo26</code></td>
        <td class="org-left">"mongo"</td>
        </tr>
        </tbody>
        </table>
        
        All defaults are customizable with `M-x customize-group RET ob-mongo`.


<a id="orgf1a5396"></a>

## Notes

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">SQL Terms/Syntax</th>
<th scope="col" class="org-left">MongoDB Terms/Syntax</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">Database</td>
<td class="org-left">Database</td>
</tr>


<tr>
<td class="org-left">Table</td>
<td class="org-left">Collection</td>
</tr>


<tr>
<td class="org-left">Row</td>
<td class="org-left">Document</td>
</tr>


<tr>
<td class="org-left">Column</td>
<td class="org-left">Field</td>
</tr>


<tr>
<td class="org-left">Index</td>
<td class="org-left">Index</td>
</tr>


<tr>
<td class="org-left">Table</td>
<td class="org-left">$lookup or embedded docs</td>
</tr>


<tr>
<td class="org-left">Primary key</td>
<td class="org-left">Primary key</td>
</tr>


<tr>
<td class="org-left">Transactions</td>
<td class="org-left">Transactions</td>
</tr>
</tbody>
</table>


<a id="orga609d53"></a>

# Practical; SQLite


<a id="org1059145"></a>

## Export

The code blocks MUST be `begin_src sqlite` in order for the evaluation to work, however to export to minted they MUST be `begin_src sql` so I'll just have to use `sed` clean it up.

    sd -s '_src sqlite' '_src sqlite' 04-MongoDB.org

    sd -s '_src sqlite' '_src sqliteite'  04-MongoDB.org


<a id="orga1960d8"></a>

## Introduction

The database is <./testdb.sqlite>, we can investigate it like this:

    .tables

    record

now that we know that it has a table called record we can get column names from it using `.schema`:

    .schema record

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">CREATE TABLE record (</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">[Sid] INTEGER</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">[Sname] TEXT</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">[Sex] TEXT</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">[DOB] TEXT</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">[Uid] INTEGER</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">[Mark] REAL</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">[Uname] TEXT</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">[Utype] TEXT</td>
<td class="org-left">&#xa0;</td>
</tr>


<tr>
<td class="org-left">);</td>
<td class="org-left">&#xa0;</td>
</tr>
</tbody>
</table>

Alternatively the following could be used:

    PRAGMA table_info(record);

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-left">Sid</td>
<td class="org-left">INTEGER</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-left">Sname</td>
<td class="org-left">TEXT</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">2</td>
<td class="org-left">Sex</td>
<td class="org-left">TEXT</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">3</td>
<td class="org-left">DOB</td>
<td class="org-left">TEXT</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">4</td>
<td class="org-left">Uid</td>
<td class="org-left">INTEGER</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">5</td>
<td class="org-left">Mark</td>
<td class="org-left">REAL</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">6</td>
<td class="org-left">Uname</td>
<td class="org-left">TEXT</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">7</td>
<td class="org-left">Utype</td>
<td class="org-left">TEXT</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>

    select * from record limit 4

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-right">18395061</td>
<td class="org-left">Adam Ross</td>
<td class="org-left">M</td>
<td class="org-right">1988-06-20</td>
<td class="org-right">300580</td>
<td class="org-right">88.0</td>
<td class="org-left">Programming Fundamentals</td>
<td class="org-left">Programming</td>
</tr>


<tr>
<td class="org-right">18395061</td>
<td class="org-left">Adam Ross</td>
<td class="org-left">M</td>
<td class="org-right">1988-06-20</td>
<td class="org-right">300581</td>
<td class="org-right">79.0</td>
<td class="org-left">Programming Techniques</td>
<td class="org-left">Programming</td>
</tr>


<tr>
<td class="org-right">18395061</td>
<td class="org-left">Adam Ross</td>
<td class="org-left">M</td>
<td class="org-right">1988-06-20</td>
<td class="org-right">300585</td>
<td class="org-right">74.0</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-left">Analysis</td>
</tr>


<tr>
<td class="org-right">18395061</td>
<td class="org-left">Adam Ross</td>
<td class="org-left">M</td>
<td class="org-right">1988-06-20</td>
<td class="org-right">300144</td>
<td class="org-right">59.0</td>
<td class="org-left">Object Oriented Analysis</td>
<td class="org-left">Analysis</td>
</tr>
</tbody>
</table>


<a id="org14d3651"></a>

## SQL Exercises


<a id="org0500e1b"></a>

### Count the Number of Records

    select count(*) from record;

    5006


<a id="org108d679"></a>

### Count the number of students

    select count(*) from
           (select Distinct Sid from record)
           ;

    1000


<a id="org4a56055"></a>

### Count the number of female students

    select count(*) from
           (select Distinct Sid from record where Sex is "F")
           ;

    1000


<a id="orgb5157cf"></a>

### Male Students that Fail a Programming Class

Return a list of the male students who failed *Programming Techniques (300581)*, Display:

-   student IDs
-   Names
-   Marks

The `like` operator could be used:

    select Sname, Sid, Mark from record where Sex is "M" and Mark < 50 and Uname like "%prog%tech%";

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Joshua Shaw</td>
<td class="org-right">18776570</td>
<td class="org-right">46.0</td>
</tr>


<tr>
<td class="org-left">Keith Davis</td>
<td class="org-right">18941001</td>
<td class="org-right">49.0</td>
</tr>
</tbody>
</table>


<a id="org64b3697"></a>

### Lowest Vs Highest

Display:

-   Student IDs
-   Names

of students that are:

-   Female
-   Highest or Lowest mark in OOA

Notice that this seems wrong:

    select Sname, Sid, Uname, max(Mark), min(Mark) from record where Sex is "F" ;
    select Sname, Sid, Uname, min(Mark), min(Mark) from record where Sex is "F" ;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Jennifer Smith</td>
<td class="org-right">18612794</td>
<td class="org-left">Programming Techniques</td>
<td class="org-right">100.0</td>
<td class="org-right">34.0</td>
</tr>


<tr>
<td class="org-left">Jennifer Smith</td>
<td class="org-right">18612794</td>
<td class="org-left">Programming Techniques</td>
<td class="org-right">34.0</td>
<td class="org-right">34.0</td>
</tr>
</tbody>
</table>

And that this simply doesn't evaluate:

    select Sid, Sname from record where Sex = "F" and Mark = Max(Mark);

Instead you need to wrap the `Max(Mark)` call in a `(select )` statement.

    select Sid, Sname, Uname, Mark from  record where Sex is "F" and Mark = (select max(Mark) from record);
    select Sid, Sname, Uname, Mark from  record where Sex is "F" and Mark in (select max(Mark) from record);

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">17844194</td>
<td class="org-left">Rebecca Morris</td>
<td class="org-left">Network Technologies</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17267976</td>
<td class="org-left">Erin Phillips</td>
<td class="org-left">Network Technologies</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18183025</td>
<td class="org-left">Lindsey Mitchell</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18306683</td>
<td class="org-left">Cynthia Thomas</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18395645</td>
<td class="org-left">Shannon Evans</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17014005</td>
<td class="org-left">Kathryn Roberts</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17482984</td>
<td class="org-left">Allison Jones</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17267372</td>
<td class="org-left">Kristen Hughes</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17435628</td>
<td class="org-left">Stephanie Jones</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18233557</td>
<td class="org-left">Christina Jones</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17504162</td>
<td class="org-left">Amanda Evans</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18422958</td>
<td class="org-left">Lisa Bennett</td>
<td class="org-left">Network Technologies</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18435634</td>
<td class="org-left">Chelsea Russell</td>
<td class="org-left">Programming Fundamentals</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18435634</td>
<td class="org-left">Chelsea Russell</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18025468</td>
<td class="org-left">Sarah Williams</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17653287</td>
<td class="org-left">Jessica Reid</td>
<td class="org-left">Big Data</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18026521</td>
<td class="org-left">Danielle Williams</td>
<td class="org-left">Big Data</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18958966</td>
<td class="org-left">Jennifer Wilson</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18174160</td>
<td class="org-left">Lisa Jones</td>
<td class="org-left">Big Data</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17864868</td>
<td class="org-left">Lauren Hill</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17921398</td>
<td class="org-left">Jessica Wilson</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18740585</td>
<td class="org-left">April Price</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18001310</td>
<td class="org-left">April Graham</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17582640</td>
<td class="org-left">Meghan Taylor</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18774356</td>
<td class="org-left">Elizabeth Young</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18899505</td>
<td class="org-left">Kathleen Ross</td>
<td class="org-left">Programming Fundamentals</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18041686</td>
<td class="org-left">Elizabeth Evans</td>
<td class="org-left">Object Oriented Analysis</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17699458</td>
<td class="org-left">Courtney Smith</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17383582</td>
<td class="org-left">Amber Rose</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18753548</td>
<td class="org-left">Sarah Bennett</td>
<td class="org-left">Big Data</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18030119</td>
<td class="org-left">Ashley Knight</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18176079</td>
<td class="org-left">Kathleen Gray</td>
<td class="org-left">Network Technologies</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17713866</td>
<td class="org-left">Ashley Clarke</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17713866</td>
<td class="org-left">Ashley Clarke</td>
<td class="org-left">Big Data</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18508757</td>
<td class="org-left">Brittany Thomas</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17847187</td>
<td class="org-left">Kristina Simpson</td>
<td class="org-left">Network Technologies</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18581352</td>
<td class="org-left">Stacy Richardson</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17844194</td>
<td class="org-left">Rebecca Morris</td>
<td class="org-left">Network Technologies</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17267976</td>
<td class="org-left">Erin Phillips</td>
<td class="org-left">Network Technologies</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18183025</td>
<td class="org-left">Lindsey Mitchell</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18306683</td>
<td class="org-left">Cynthia Thomas</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18395645</td>
<td class="org-left">Shannon Evans</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17014005</td>
<td class="org-left">Kathryn Roberts</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17482984</td>
<td class="org-left">Allison Jones</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17267372</td>
<td class="org-left">Kristen Hughes</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17435628</td>
<td class="org-left">Stephanie Jones</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18233557</td>
<td class="org-left">Christina Jones</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17504162</td>
<td class="org-left">Amanda Evans</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18422958</td>
<td class="org-left">Lisa Bennett</td>
<td class="org-left">Network Technologies</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18435634</td>
<td class="org-left">Chelsea Russell</td>
<td class="org-left">Programming Fundamentals</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18435634</td>
<td class="org-left">Chelsea Russell</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18025468</td>
<td class="org-left">Sarah Williams</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17653287</td>
<td class="org-left">Jessica Reid</td>
<td class="org-left">Big Data</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18026521</td>
<td class="org-left">Danielle Williams</td>
<td class="org-left">Big Data</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18958966</td>
<td class="org-left">Jennifer Wilson</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18174160</td>
<td class="org-left">Lisa Jones</td>
<td class="org-left">Big Data</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17864868</td>
<td class="org-left">Lauren Hill</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17921398</td>
<td class="org-left">Jessica Wilson</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18740585</td>
<td class="org-left">April Price</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18001310</td>
<td class="org-left">April Graham</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17582640</td>
<td class="org-left">Meghan Taylor</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18774356</td>
<td class="org-left">Elizabeth Young</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18899505</td>
<td class="org-left">Kathleen Ross</td>
<td class="org-left">Programming Fundamentals</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18041686</td>
<td class="org-left">Elizabeth Evans</td>
<td class="org-left">Object Oriented Analysis</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17699458</td>
<td class="org-left">Courtney Smith</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17383582</td>
<td class="org-left">Amber Rose</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18753548</td>
<td class="org-left">Sarah Bennett</td>
<td class="org-left">Big Data</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18030119</td>
<td class="org-left">Ashley Knight</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18176079</td>
<td class="org-left">Kathleen Gray</td>
<td class="org-left">Network Technologies</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17713866</td>
<td class="org-left">Ashley Clarke</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17713866</td>
<td class="org-left">Ashley Clarke</td>
<td class="org-left">Big Data</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18508757</td>
<td class="org-left">Brittany Thomas</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">17847187</td>
<td class="org-left">Kristina Simpson</td>
<td class="org-left">Network Technologies</td>
<td class="org-right">100.0</td>
</tr>


<tr>
<td class="org-right">18581352</td>
<td class="org-left">Stacy Richardson</td>
<td class="org-left">Systems Analysis and Design</td>
<td class="org-right">100.0</td>
</tr>
</tbody>
</table>

Now it's simply a matter of getting the minimum as well:

    select max(Mark), Sid, Sname, Uname from  record where Sex is "F" and Uname like "%Object%Oriented%Analysis%" drop column Mark;
    select min(Mark), Sid, Sname, Uname from  record where Sex is "F" and Uname like "%Object%Oriented%Analysis%" ;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-right">100.0</td>
<td class="org-right">18041686</td>
<td class="org-left">Elizabeth Evans</td>
<td class="org-left">Object Oriented Analysis</td>
</tr>


<tr>
<td class="org-right">51.0</td>
<td class="org-right">18148368</td>
<td class="org-left">Lauren Williams</td>
<td class="org-left">Object Oriented Analysis</td>
</tr>
</tbody>
</table>

This includes the `Mark`, if we didn't want that then we could wrap the call in another `select`:

    select Sid, Sname from (select max(Mark), Sid, Sname, Uname from  record where Sex is "F" and Uname like "%Object%Oriented%Analysis%");
    select Sid, Sname from (select min(Mark), Sid, Sname, Uname from  record where Sex is "F" and Uname like "%Object%Oriented%Analysis%");

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-right">18041686</td>
<td class="org-left">Elizabeth Evans</td>
</tr>


<tr>
<td class="org-right">18148368</td>
<td class="org-left">Lauren Williams</td>
</tr>
</tbody>
</table>


<a id="org448ce4f"></a>

### Youngest vs Oldest Student

    select not DOB from record where ;

    select Distinct Sid, Sname, min(DOB) from record;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">17863769</td>
<td class="org-left">Anthony Morris</td>
<td class="org-right">1985-01-20</td>
</tr>
</tbody>
</table>


<a id="org4c863e2"></a>

### Top Performers

The trick here is to give the average mark column an alias, this way we can sort by it later:

    select distinct Sid, Sname, Sex, avg(Mark) as av_mark
    from record
    group by Sid
    order by av_mark desc
    limit 5

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">18908735</td>
<td class="org-left">Eric Green</td>
<td class="org-left">M</td>
<td class="org-right">93.5</td>
</tr>


<tr>
<td class="org-right">17582991</td>
<td class="org-left">Daniel Richards</td>
<td class="org-left">M</td>
<td class="org-right">93.25</td>
</tr>


<tr>
<td class="org-right">18555338</td>
<td class="org-left">Michael Williams</td>
<td class="org-left">M</td>
<td class="org-right">92.4</td>
</tr>


<tr>
<td class="org-right">17435628</td>
<td class="org-left">Stephanie Jones</td>
<td class="org-left">F</td>
<td class="org-right">92.2</td>
</tr>


<tr>
<td class="org-right">17713866</td>
<td class="org-left">Ashley Clarke</td>
<td class="org-left">F</td>
<td class="org-right">91.8333333333333</td>
</tr>
</tbody>
</table>


<a id="orgb00709c"></a>

## Python and SQL Questions

Test whether or not female students out perform male students in analysis units via mean and std dev analysis using sql queries.

    select distinct avg(Mark) as Mean_mark,
    	    avg(mark*mark) as  mean_sq_mark,
    	    avg(mark)*avg(mark) as mean_mark_sq,
    	    Utype, Sex
    	from record
    	where Utype
    	like "%Analysis%"
    	group by Sex
    	limit 10;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-right">79.74</td>
<td class="org-right">6461.1</td>
<td class="org-right">6358.4676</td>
<td class="org-left">Analysis</td>
<td class="org-left">F</td>
</tr>


<tr>
<td class="org-right">70.195</td>
<td class="org-right">5031.237</td>
<td class="org-right">4927.338025</td>
<td class="org-left">Analysis</td>
<td class="org-left">M</td>
</tr>
</tbody>
</table>

    select Sex, Mean_Mark, mean_sq_mark-mean_mark_sq as var from
        (select distinct avg(Mark) as Mean_mark,
    		avg(mark*mark) as  mean_sq_mark,
    		avg(mark)*avg(mark) as mean_mark_sq,
    		Utype, Sex
    	    from record
    	    where Utype
    	    like "%Analysis%"
    	    group by Sex
        )
    	limit 10;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-left">F</td>
<td class="org-right">79.74</td>
<td class="org-right">102.632400000001</td>
</tr>


<tr>
<td class="org-left">M</td>
<td class="org-right">70.195</td>
<td class="org-right">103.898975000001</td>
</tr>
</tbody>
</table>

This returns a \(\overline{x}_{1} - \overline{x}_{2} = 9\) with \(\sigma \approx 10\), indicating that the difference between male and female student performance in Analysis units is significant in favour of Female performance.

We could do this with *Python* as well by saving the results to a `csv` file:

    .mode csv
    .output ./03-sqlite-AnalysisMarks.csv
    select Sex, Mark
           from record
           where Utype like "%Analysis%"

Now This CSV File can be analysed with *Python*, so first importing the data:

    import pandas as pd
    import matplotlib.pyplot as plt
    
    # Import the Data frame
    analysis_marks = pd.read_csv("./03-sqlite-AnalysisMarks.csv")
    analysis_marks.columns()
    
    # Print the first few lines of the data frame
    print(analysis_marks[0:4])

    M  74.0
    0  M  59.0
    1  M  72.0
    2  M  56.0
    3  F  84.0

Then finding the standard deviation and mean values:

    analysis_marks.melt(variable = Sex)

    import pandas as pd
    import matplotlib.pyplot as plt
    
    # Import the Data frame
    analysis_marks = pd.read_csv("./03-sqlite-AnalysisMarks.csv")
    
    # Print the first few lines of the data frame
    print(analysis_marks[0:4])

    SELECT mark FROM record where Uid=300581;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">88.0</td>
</tr>


<tr>
<td class="org-right">79.0</td>
</tr>


<tr>
<td class="org-right">74.0</td>
</tr>


<tr>
<td class="org-right">59.0</td>
</tr>


<tr>
<td class="org-right">92.0</td>
</tr>
</tbody>
</table>


<a id="org4a91d71"></a>

## Quiz


<a id="orgc8679ef"></a>

### Inspect the Table

    PRAGMA table_info(record);

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">0</td>
<td class="org-left">Sid</td>
<td class="org-left">INTEGER</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">1</td>
<td class="org-left">Sname</td>
<td class="org-left">TEXT</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">2</td>
<td class="org-left">Sex</td>
<td class="org-left">TEXT</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">3</td>
<td class="org-left">DOB</td>
<td class="org-left">TEXT</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">4</td>
<td class="org-left">Uid</td>
<td class="org-left">INTEGER</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">5</td>
<td class="org-left">Mark</td>
<td class="org-left">REAL</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">6</td>
<td class="org-left">Uname</td>
<td class="org-left">TEXT</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>


<tr>
<td class="org-right">7</td>
<td class="org-left">Utype</td>
<td class="org-left">TEXT</td>
<td class="org-right">0</td>
<td class="org-left">&#xa0;</td>
<td class="org-right">0</td>
</tr>
</tbody>
</table>


<a id="orgab812c1"></a>

### Average Enrolments

To find the average number of classes that students are enrolled in, divide the number of students by the number of duplicates.

    select count(sid) / count(distinct sid) from record;

    5


<a id="org6a95344"></a>

### Birth year of Oldest Student

Don't forget to wrap strings:

    select Distinct Sid, Sname, Sex, min(DOB) as age from record where Sex is 'F'

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">17713866</td>
<td class="org-left">Ashley Clarke</td>
<td class="org-left">F</td>
<td class="org-right">1985-01-30</td>
</tr>
</tbody>
</table>


<a id="org7c0763b"></a>

### Birth year of Oldest Female Student

Don't forget to wrap strings:

    select Distinct Sid, Sname, Sex, min(DOB) as age from record where Sex is 'F'

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">17713866</td>
<td class="org-left">Ashley Clarke</td>
<td class="org-left">F</td>
<td class="org-right">1985-01-30</td>
</tr>
</tbody>
</table>


<a id="org5b413f6"></a>

### Family name of Youngest Male Student

Don't forget to wrap strings:

    select Distinct Sname, Sex, max(DOB) as age from record where Sex is 'M'

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-left">Andrew Lee</td>
<td class="org-left">M</td>
<td class="org-right">1995-12-12</td>
</tr>
</tbody>
</table>


<a id="org738afd1"></a>

### Age Difference between oldest youngest male students

Don't forget to wrap strings:

    select max(DOB) - min(DOB) from record where Sex is 'M';

    10


<a id="org70f5975"></a>

### Lowest Vs Highest

What is the difference between female and male student's highest total average mark?

Find the Average Marks of all Students

    select Sid, avg(Mark) as av_mark, Sex
           from record
           group by Sid
           limit 5

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-right">17002055</td>
<td class="org-right">75.8</td>
<td class="org-left">F</td>
</tr>


<tr>
<td class="org-right">17003783</td>
<td class="org-right">77.0</td>
<td class="org-left">M</td>
</tr>


<tr>
<td class="org-right">17004931</td>
<td class="org-right">72.8</td>
<td class="org-left">F</td>
</tr>


<tr>
<td class="org-right">17006515</td>
<td class="org-right">73.5</td>
<td class="org-left">F</td>
</tr>


<tr>
<td class="org-right">17007137</td>
<td class="org-right">75.2</td>
<td class="org-left">F</td>
</tr>
</tbody>
</table>

Of those return the highest male and female:

    select max(av_mark) as max_av, Sex
        from (
        select Sid, avg(mark) as av_mark, Sex
    	from record
    	group by Sid
        )
        group by Sex
        limit 5

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-right">92.2</td>
<td class="org-left">F</td>
</tr>


<tr>
<td class="org-right">93.5</td>
<td class="org-left">M</td>
</tr>
</tbody>
</table>


<a id="org296a23d"></a>

# Practical; NoSQL; MongoDB

The <./product.json>, [innvdoccnt.json](resources/invdoccnt.json) and [world bank json](file:///home/ryan/Sync/Studies/2020Spring/BigData/resources/world_bank.txt) Database will be used here.

Install the following software:

-   mongodb                             <sup><a id="fnr.1" class="footref" href="#fn.1">1</a></sup>
-   mongodb-tools (for mongoimport)     <sup><a id="fnr.2" class="footref" href="#fn.2">2</a></sup>
-   mongodb-compass (for sanity checks) <sup><a id="fnr.3" class="footref" href="#fn.3">3</a></sup>
-   robo3T                              <sup><a id="fnr.4" class="footref" href="#fn.4">4</a></sup>

First find out which server mongo is running on by running `mongo` in the terminal and then running the following in the shell:

    db.serverCmdLineOpts()

that should return some json, this is useful if you are using `mongo-compass` as discussed in &sect; [6.1.3](#compass).


<a id="org036c6f6"></a>

## Importing Data


<a id="org18c758c"></a>

### Using mongoimport

Import the DB by specifying an arbitrary Database name `arbitraryDBName` and an arbitrary collection name `arbitraryCollectionName`:

    cd /home/ryan/Dropbox/Studies/2020Spring/BigData/BigData/Assessments/Quizz3/
    systemctl start mongodb
    # install AUR mongodb and mongotools (probably also robo3T)
    mongoimport  /home/ryan/Sync/Studies/2020Spring/BigData/resources/world_bank.txt.json -d arbitraryDBName-c arbitraryCollectionName
    mongo

Inside MongoDB access the database and list the available collections

    use arbitraryDBName
    show collections

    switched to db testdb
    invwc
    wb


<a id="org94a7de0"></a>

### Loading the Database

Say you forgot what you imported it as, to list databases:

    db.adminCommand( { listDatabases: 1 } )

    {
    	"databases" : [
    		{
    			"name" : "admin",
    			"sizeOnDisk" : 40960,
    			"empty" : false
    		},
    		{
    			"name" : "config",
    			"sizeOnDisk" : 110592,
    			"empty" : false
    		},
    		{
    			"name" : "arbitraryDBName",
    			"sizeOnDisk" : 991232,
    			"empty" : false
    		},
    		{
    			"name" : "worldbank",
    			"sizeOnDisk" : 987136,
    			"empty" : false
    		}
    	],
    	"totalSize" : 3895296,
    	"ok" : 1
    }

use one of the databases by issuing:

    use arbitraryDBName

If we wanted to see the collections in that database:

    show collections

    arbitraryCollectionName

then to delete (drop) that database you could just do:

    db.dropDatabase()


<a id="compass"></a>

### Using the Mongo-compass program     :ATTACH:

1.  Open mongo-compass

2.  Connect to the mongoDB server
    1.  Probably localhost:27017
        
        1.  If you're on SystemD maybe check with `sudo systemctl status mongodb`, for me I got a different port number.
        
        ![img](_media/org-compass-Server.png)

1.  Create a new collection
    
    ![img](_media/org-compass-Collection.png)

2.  Import the JSON File

3.  Now from the terminal run `mongo` to open a shell and then `use local` to switch to that database.


<a id="orgaa029c4"></a>

## Workflow

1.  Open Emacs
2.  Open Vterm below
3.  Use a macro to copy a paragraph and send the results below:
    
        (fset 'send-below
        (kmacro-lambda-form [?v ?a ?p ?y ?\C-w ?j ?p ?\C-o ?\C-o ?\C-o ?\C-w ?k] 0 "%d"))
        (global-set-key (kbd "C-c m") 'send-below)
4.  Copy and paste the results all in place like fucking magic.


<a id="orgafd63c5"></a>

## List Movies

First see if you can list everything, if you created product underneath local, you'll need to do something like this:

    use local
    db.product.find()

In the case of <./product.json>, the following should return some output.

    db.product.find({'Type': 'Movie'})

    { "_id" : ObjectId("551668dbeb88341eb801f2d2"), "Classification" : "PG-13", "Title" : "Inception", "Price" : { "Buy" : 9.99, "Rent" : 2.99 }, "Director" : "Christopher Nolan", "Cast" : [ "Leonardo DiCaprio", "Joseph Gordon-Levitt" ], "Year" : "2010", "Genre" : [ "Drama", "Action", "Science Fiction" ], "Type" : "Movie", "Length (min)" : 148 }
    { "_id" : ObjectId("551668dbeb88341eb801f2db"), "Classification" : "R", "Title" : "Superbad", "Price" : { "Buy" : 9.99, "Rent" : 2.99 }, "Director" : "Greg Mottola", "Cast" : [ "Jonah Hill", "Michael Cera" ], "Year" : "2007", "Genre" : "Comedy", "Type" : "Movie", "Length (min)" : 113 }
    { "_id" : ObjectId("551668dbeb88341eb801f2dc"), "Title" : "Dracula", "Price" : { "Buy" : 9.99, "Rent" : 3.99 }, "Director" : "Tod Browning", "Cast" : [ "Bela Lugosi", "Helen Chandler" ], "Year" : "1931", "Genre" : [ "Classics", "Horror" ], "Type" : "Movie", "Length (min)" : 75 }
    
    ...
    ...
    ...

To query all the text, something like this might be useful:

    mongo --eval 'db.product.find()' local | fzf

To return All Movies that contain, for example, Morgan Freeman, Compass can be inspected to reveal the `cast` field and then the following can be used:

    db.product.find({'Cast': 'Morgan Freeman'})

    { "_id" : ObjectId("551668dbeb88341eb801f2de"), "Title" : "The Shawshank Redemption" }
    { "_id" : ObjectId("551668dbeb88341eb801f2e7"), "Title" : "The Dark Knight" }
    > db.product.find({'Cast': 'Morgan Freeman'})
    { "_id" : ObjectId("551668dbeb88341eb801f2de"), "Classification" : "R", "Title" : "The Shawshank Redemption", "Price" : { "Buy" : 9.99, "Rent" : 3.99 }, "Director" : "Frank Darabont", "Cast" : [ "Tim Robbins", "Morgan Freeman" ], "Year" : "1994", "Genre" : "Drama", "Type" : "Movie", "Length (min)" : 142 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e7"), "Classification" : "PG-13", "Title" : "The Dark Knight", "Price" : { "Buy" : 12.99, "Rent" : 3.99 }, "Director" : "Christopher Nolan", "Cast" : [ "Christian Bale", "Heath Ledger", "Morgan Freeman" ], "Year" : "2008", "Genre" : [ "Drama", "Action", "Science Fiction" ], "Type" : "Movie", "Length (min)" : 152 }
    >

This however returns too much information, instead we can use [projection](https://docs.mongodb.com/manual/tutorial/project-fields-from-query-results/) to filter the results:

    db.product.find({'Cast': 'Morgan Freeman'}, {Title: 1})

    { "_id" : ObjectId("551668dbeb88341eb801f2de"), "Title" : "The Shawshank Redemption" }
    { "_id" : ObjectId("551668dbeb88341eb801f2e7"), "Title" : "The Dark Knight" }


<a id="orgb0c39d9"></a>

## Find Songs

To Find the Songs in the Database the following can be used:

    db.product.find({'Type': 'Song'})

This returns far too many results, so instead projection can be used:

    db.product.find({'Type': 'Song'}, {'Title': 1, })

    { "_id" : ObjectId("551668dbeb88341eb801f2d3"), "Title" : "Someone Like You" }
    { "_id" : ObjectId("551668dbeb88341eb801f2d5"), "Title" : "Billie Jean" }
    { "_id" : ObjectId("551668dbeb88341eb801f2d6"), "Title" : "Speak to Me" }
    { "_id" : ObjectId("551668dbeb88341eb801f2d7"), "Title" : "I Will Always Love You" }
    { "_id" : ObjectId("551668dbeb88341eb801f2d9"), "Title" : "Back in Black" }
    { "_id" : ObjectId("551668dbeb88341eb801f2df"), "Title" : "2 Becomes 1" }
    { "_id" : ObjectId("551668dbeb88341eb801f2e2"), "Title" : "Enter Sandman" }
    { "_id" : ObjectId("551668dbeb88341eb801f2e4"), "Title" : "Smells Like Teen Spirit" }
    { "_id" : ObjectId("551668dbeb88341eb801f2e6"), "Title" : "Yesterday" }
    { "_id" : ObjectId("551668dbeb88341eb801f2e9"), "Title" : "When You Believe" }

In order to filter by Genre we could just add that to the `find` field, however because we want any type of rock, we'll need to use the `.*Rock.*` regex, this has an odd syntax in *MongoDB* where a regex term is denoted like this: `{ $regex: /.*Rock.*/ }`, so putting that together:

    db.product.find({'Type': 'Song', 'Genre': { $regex: /.*Rock.*/ }}, {'Title': 1, 'Artist': 1, 'Album': 1})

    { "_id" : ObjectId("551668dbeb88341eb801f2d5"), "Album" : { "Certification" : "43xPlatinium", "Title" : "Thriller" }, "Artist" : "Michael Jackson", "Title" : "Billie Jean" }
    { "_id" : ObjectId("551668dbeb88341eb801f2d6"), "Album" : { "Certification" : "23xPlatinium", "Title" : "The Dark Side of the Moon" }, "Artist" : "Pink Floyd", "Title" : "Speak to Me" }
    { "_id" : ObjectId("551668dbeb88341eb801f2d9"), "Album" : { "Certification" : "26xPlatinium", "Title" : "Back in Black" }, "Artist" : "AC/DC", "Title" : "Back in Black" }
    { "_id" : ObjectId("551668dbeb88341eb801f2e4"), "Album" : { "Certification" : "17xPlatinium", "Title" : "Nevermind" }, "Artist" : "Nirvana", "Title" : "Smells Like Teen Spirit" }
    { "_id" : ObjectId("551668dbeb88341eb801f2e6"), "Album" : { "Certification" : "22xPlatinium", "Title" : "1" }, "Artist" : "The Beatles", "Title" : "Yesterday" }

To sort thhe results, the `.sort()` method can be tacked on the end like so:

    db.product.find({'Type': 'Song', 'Genre': { $regex: /.*Rock.*/ }}, {'Title': 1, 'Artist': 1, 'Album': 1}).sort({ 'ReleaseDate': -1 })

    { "_id" : ObjectId("551668dbeb88341eb801f2e6"), "Album" : { "Certification" : "22xPlatinium", "Title" : "1" }, "Artist" : "The Beatles", "Title" : "Yesterday" }
    { "_id" : ObjectId("551668dbeb88341eb801f2e4"), "Album" : { "Certification" : "17xPlatinium", "Title" : "Nevermind" }, "Artist" : "Nirvana", "Title" : "Smells Like Teen Spirit" }
    { "_id" : ObjectId("551668dbeb88341eb801f2d5"), "Album" : { "Certification" : "43xPlatinium", "Title" : "Thriller" }, "Artist" : "Michael Jackson", "Title" : "Billie Jean" }
    { "_id" : ObjectId("551668dbeb88341eb801f2d9"), "Album" : { "Certification" : "26xPlatinium", "Title" : "Back in Black" }, "Artist" : "AC/DC", "Title" : "Back in Black" }
    { "_id" : ObjectId("551668dbeb88341eb801f2d6"), "Album" : { "Certification" : "23xPlatinium", "Title" : "The Dark Side of the Moon" }, "Artist" : "Pink Floyd", "Title" : "Speak to Me" }
    >


<a id="org0bdff3e"></a>

## Calculate the Average Price of Books

To find all books with more than 500 pages, the [And](https://docs.mongodb.com/manual/tutorial/query-documents/) operator can be used inside `find`, this amounts to just using a `,`.

Operators are, much like regex, a little odd, they require cages and `$` prefixes.

    db.product.find( { 'Type': 'Book', Pages: { $gt: 500 } } )

    { "_id" : ObjectId("551668dbeb88341eb801f2d0"), "Publisher" : "Prentice Hall", "ISBN" : "132126958", "Author" : "Andrew Tanenbaum", "Price" : 129.79, "Title" : "Computer Networks", "Shipping" : { "Weight (lb)" : 2.9, "Dimension (in)" : { "Width" : 6.6, "Depth" : 1.5, "Height" : 9.2 } }, "Edition" : "5", "Year" : "2010", "Type" : "Book", "Pages" : 960 }
    { "_id" : ObjectId("551668dbeb88341eb801f2d4"), "Publisher" : "Pearson", "ISBN" : "032182573X", "Author" : "Peter Tanenbaum", "Price" : 153.16, "Title" : "Excursions in Modern Mathematics", "Shipping" : { "Weight (lb)" : 3.2, "Dimension (in)" : { "Width" : 8.8, "Depth" : 1.1, "Height" : 10.9 } }, "Edition" : "8", "Year" : "2012", "Type" : "Book", "Pages" : 608 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e0"), "Publisher" : "Prentice Hall", "ISBN" : "013359162X", "Author" : "Andrew Tanenbaum, Herbert Bos", "Price" : 153.09, "Title" : "Modern Operating Systems", "Shipping" : { "Weight (lb)" : NaN, "Dimension (in)" : { "Width" : 7.1, "Depth" : 1.6, "Height" : 9.1 } }, "Edition" : "4", "Year" : "2014", "Type" : "Book", "Pages" : 1136 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e3"), "Publisher" : "Addison-Wesley", "ISBN" : "321349806", "Author" : "Ken Arnold, James Gosling", "Price" : 53.69, "Title" : "The Java Programming Language", "Shipping" : { "Weight (lb)" : NaN, "Dimension (in)" : { "Width" : 7.4, "Depth" : 1.2, "Height" : 9.2 } }, "Edition" : "4", "Year" : "2005", "Type" : "Book", "Pages" : 928 }
    { "_id" : ObjectId("551668dbeb88341eb801f2ea"), "Publisher" : "Addison Wesley", "ISBN" : "321500245", "Author" : "Mario Triola", "Price" : 28.99, "Title" : "Elementary Statistics", "Shipping" : { "Weight (lb)" : 4.7, "Dimension (in)" : { "Width" : 8.5, "Depth" : 1.4, "Height" : 11.2 } }, "Edition" : "11", "Year" : "2009", "Type" : "Book", "Pages" : 896 }
    > db.product.find( { 'Type': 'Book', Pages: { $gt: 500 } } )

To Average the price first use [projection](https://docs.mongodb.com/manual/tutorial/project-fields-from-query-results/) to return only the price values:

    db.product.find( { 'Type': 'Book', Pages: { $gt: 100 } }, { 'Price': 1} )

    { "_id" : ObjectId("551668dbeb88341eb801f2d0"), "Price" : 129.79 }
    { "_id" : ObjectId("551668dbeb88341eb801f2d1"), "Price" : 52.89 }
    { "_id" : ObjectId("551668dbeb88341eb801f2d4"), "Price" : 153.16 }
    { "_id" : ObjectId("551668dbeb88341eb801f2d8"), "Price" : NaN }
    { "_id" : ObjectId("551668dbeb88341eb801f2da"), "Price" : NaN }
    { "_id" : ObjectId("551668dbeb88341eb801f2e0"), "Price" : 153.09 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e1"), "Price" : 37.99 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e3"), "Price" : 53.69 }
    { "_id" : ObjectId("551668dbeb88341eb801f2ea"), "Price" : 28.99 }
    { "_id" : ObjectId("551668dbeb88341eb801f2eb"), "Price" : 27.68 }
    >

Next drop any results with missing values by [not equal (`$ne`)](https://docs.mongodb.com/manual/reference/operator/query/) operator:

    db.product.find( { 'Type': 'Book', Pages: { $gt: 100 }, Price: { $ne: NaN } }, { 'Price': 1} )

    { "_id" : ObjectId("551668dbeb88341eb801f2d0"), "Price" : 129.79 }
    { "_id" : ObjectId("551668dbeb88341eb801f2d1"), "Price" : 52.89 }
    { "_id" : ObjectId("551668dbeb88341eb801f2d4"), "Price" : 153.16 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e0"), "Price" : 153.09 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e1"), "Price" : 37.99 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e3"), "Price" : 53.69 }
    { "_id" : ObjectId("551668dbeb88341eb801f2ea"), "Price" : 28.99 }
    { "_id" : ObjectId("551668dbeb88341eb801f2eb"), "Price" : 27.68 }

To do this we'll create a variable, note however that `find` is such that [any variable returned is a temporary cursor](https://stackoverflow.com/a/21285674/12843551), which means that after the variable is called again it is cleared:

    var price = db.product.find( { 'Type': 'Book', Pages: { $gt: 100 }, Price: { $ne: NaN } }, { 'Price': 1} )
    price

    { "_id" : ObjectId("551668dbeb88341eb801f2d0"), "Price" : 129.79 }
    { "_id" : ObjectId("551668dbeb88341eb801f2d1"), "Price" : 52.89 }
    { "_id" : ObjectId("551668dbeb88341eb801f2d4"), "Price" : 153.16 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e0"), "Price" : 153.09 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e1"), "Price" : 37.99 }
    { "_id" : ObjectId("551668dbeb88341eb801f2e3"), "Price" : 53.69 }
    { "_id" : ObjectId("551668dbeb88341eb801f2ea"), "Price" : 28.99 }
    { "_id" : ObjectId("551668dbeb88341eb801f2eb"), "Price" : 27.68 }

but then calling `price` again would return no output:

    price

    

To overcome this make the result an array first:

    var price = db.product.find( { 'Type': 'Book', Pages: { $gt: 500 }, Price: { $ne: NaN } }, { 'Price': 1} ).toArray()
    price

    [
    	{
    		"_id" : ObjectId("551668dbeb88341eb801f2d0"),
    		"Price" : 129.79
    	},
    	{
    		"_id" : ObjectId("551668dbeb88341eb801f2d4"),
    		"Price" : 153.16
    	},
    	{
    		"_id" : ObjectId("551668dbeb88341eb801f2e0"),
    		"Price" : 153.09
    	},
    	{
    		"_id" : ObjectId("551668dbeb88341eb801f2e3"),
    		"Price" : 53.69
    	},
    	{
    		"_id" : ObjectId("551668dbeb88341eb801f2ea"),
    		"Price" : 28.99
    	}
    ]


<a id="orgd90930c"></a>

### Aggregate

Unfoututately we can't just grab the results and average, we need to use the aggregate method with `$group` and `$match` functions.

So for example, to average all the prices period, we could do something like this:

    db.product.aggregate([
        {$group: {_id:null, "AveragePrice": {$avg:"$Price"} } }
    ]);

    { "_id" : null, "AveragePrice" : NaN }

This returns `NaN` because some of the prices were missing, we'll fix this later.

The `$_id` variable denotes grouping, in this case we just want to average everything so we set it to `null`.

In order to aggregate the matches to our `.find()`, the values can be put inside a `match` group like so:

    db.product.aggregate([
        { "$match": { 'Type': 'Book', Pages: { $gt: 500 }, Price: { $ne: NaN } } },
        {$group: {_id:null, "AveragePrice": {$avg:"$Price"} } }
    ]);

This will then return:

    { "_id" : null, "AveragePrice" : 103.744 }

So the Average price of books with more than 500 pages is \\$103.75


<a id="orgd45588b"></a>

## Quizz 3


<a id="org5dfa72e"></a>

### Inverse Word Count

Import the DB:

    cd /home/ryan/Dropbox/Studies/2020Spring/BigData/BigData/Assessments/Quizz3/
    systemctl start mongodb
    # install AUR mongodb and mongotools (probably also robo3T)
    mongoimport invdoccnt.json -d testdb -c invwc  --jsonArray
    mongo

Inside MongoDB access the database and list the available collections

    use testdb
    show collections

    switched to db testdb
    invwc
    wb

the `invwc` collection is available so use find to list that:

    db.invwc.find({})

    { "_id" : ObjectId("5f757aef0beda69afb36f5b2"), "count" : 2, "word" : "Killers" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5b3"), "count" : 27, "word" : "four" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5b4"), "count" : 3, "word" : "gag" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5b5"), "count" : 1, "word" : "Marner" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5b6"), "count" : 3, "word" : "Does" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5b7"), "count" : 1, "word" : "friend's" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5b8"), "count" : 7, "word" : "hanging" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5b9"), "count" : 2, "word" : "Hopefully" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5ba"), "count" : 1, "word" : "Until" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5bb"), "count" : 1, "word" : "aggression" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5bc"), "count" : 2, "word" : "conjure" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5bd"), "count" : 1, "word" : "fairy-tale-like" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5be"), "count" : 2, "word" : "Foundation" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5bf"), "count" : 4, "word" : "Sumpter" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5c0"), "count" : 1, "word" : "humming" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5c1"), "count" : 1, "word" : "self-pity" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5c2"), "count" : 1, "word" : "Barky" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5c3"), "count" : 3, "word" : "Septimus" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5c4"), "count" : 2, "word" : "Kinear" }
    { "_id" : ObjectId("5f757aef0beda69afb36f5c5"), "count" : 2, "word" : "Lately" }
    Type "it" for more

Then to find the maximum count do one of these:

    // db.getCollection('invwc').find()
    // db.collection.find().sort({word:-1}).limit(1)
    db.invwc.find().sort({count:-1}).limit(9)

    { "_id" : ObjectId("5f757aef0beda69afb370de0"), "count" : 988, "word" : "the" }
    { "_id" : ObjectId("5f757aef0beda69afb371582"), "count" : 961, "word" : "a" }
    { "_id" : ObjectId("5f757aef0beda69afb373a95"), "count" : 960, "word" : "and" }
    { "_id" : ObjectId("5f757aef0beda69afb373cbd"), "count" : 943, "word" : "of" }
    { "_id" : ObjectId("5f757aef0beda69afb37001d"), "count" : 919, "word" : "to" }
    { "_id" : ObjectId("5f757aef0beda69afb372259"), "count" : 909, "word" : "is" }
    { "_id" : ObjectId("5f757aef0beda69afb372256"), "count" : 881, "word" : "in" }
    { "_id" : ObjectId("5f757aef0beda69afb37060d"), "count" : 796, "word" : "this" }
    { "_id" : ObjectId("5f757aef0beda69afb37224b"), "count" : 795, "word" : "it" }

or using the `aggregate` approach (which is slower):


<a id="org0706db8"></a>

### World Bank

Load the data base

    cd /home/ryan/Dropbox/Studies/2020Spring/BigData/BigData/Assessments/Quizz3/
    systemctl start mongodb
    # install AUR mongodb and mongotools (probably also robo3T)
    mongoimport word_bank.json -d testdb -c invwc  --jsonArray
    mongo

1.  Using Aggregate

    The general form for aggregate is:
    
        db.wb.aggregate([
        
        {$match: {your matching conditions}},
        
        {$group:{group expression and functions}},
        
        {$sort: {sorting expression}}
        
        ])

2.  Number of Chinese Projects

    Load the
    
    show the keys in a document of the collection: <sup><a id="fnr.5" class="footref" href="#fn.5">5</a></sup>
    
        doc=db.bank.findOne();
        for (key in doc) print(key);
    
    This produces far to much output though so just use python
    
        import pymongo as mg
        client = mg.MongoClient()
        db = client["worldbank"]
        collection = db['bank']
        vals = []
        for doc in collection.find():
            vals.append(doc.keys())
        vals =  [item for sublist in vals for item in sublist]
        vals = set(vals)
        print(vals)
    
        {'impagency', 'theme_namecode', 'themecode', 'country_namecode', 'sector', 'source', 'mjsector_namecode', '_id', 'sector4', 'mjtheme_namecode', 'sector2', 'projectstatusdisplay', 'countryname', 'project_abstract', 'sectorcode', 'approvalfy', 'sector_namecode', 'grantamt', 'closingdate', 'totalcommamt', 'productlinetype', 'mjthemecode', 'countryshortname', 'lendinginstr', 'id', 'mjtheme', 'envassesmentcategorycode', 'url', 'sector3', 'majorsector_percent', 'projectdocs', 'ibrdcommamt', 'supplementprojectflg', 'docty', 'project_name', 'projectfinancialtype', 'theme1', 'lendinginstrtype', 'borrower', 'prodline', 'prodlinetext', 'boardapprovaldate', 'idacommamt', 'totalamt', 'countrycode', 'regionname', 'sector1', 'status', 'lendprojectcost', 'board_approval_month'}
    
    This can be combined with:
    
        # Fucking Life saver
        mongo --eval 'db.bank.find()' worldbank | fzf
    
    This provides us with `boardapprovaldate` so we'll use that to get the year and we'll use `countryname` to get the country name. To find out what the country name is listed as use `distinct`:
    
        db.bank.distinct('countryname')
    
        [
        ...
        	"Lebanese Republic",
        	"Macedonia, former Yugoslav Republic of",
        	"Middle East and North Africa",
        	"Mongolia",
        	"Nepal",
        	"Oriental Republic of Uruguay",
        	"Pacific Islands",
        	"People's Republic of Angola",
        	"People's Republic of Bangladesh",
        	"People's Republic of China",
        	"Plurinational State of Bolivia",
        	"Republic of Albania",
        	"Republic of Armenia",
            ...
        ]
    
    This provides us with the *People's Republic of China*, this can also be used with regex.
    
    To find the number of projects in 2013, just use `find()` and `count()` like so:
    
        db.bank.find({
         countryname:       { $regex: /.*China.*/},
         approvalfy: { $regex: /.*2013.*/ }
         }
        ).count()
    
        18
    
    If you're talking about financial year though
    
        db.bank.find({
         countryname:       { $regex: /.*China.*/},
         approvalfy: { $regex: /.*2014.*/ }
         }
        ).count()
    
        1
    
    1.  Projects worth
    
        Now if we look at the output in [88](#org1ae6533) `lendprojectcost` looks like a good contender, issue is though that the output like it is can't be used.
        
        So instead use `aggregate` to make it all work, it will be possible to just
        throw the contents from the previous call to `find` in there, so using emacs is
        justified.
        
        Observe the use of `"$key"` when using aggregate:
        
            // 2013 projects cost
            db.bank.aggregate([
            { $match: {
                 countryshortname: "China",
             approvalfy: "2013"
            
                }},
            {$group: {_id:null, "amount": {$sum: "$lendprojectcost"}}}
            ])
            
            //2014 projects cost
            db.bank.aggregate([
            { $match: {
                 countryshortname:       { $regex: /.*China.*/},
             approvalfy: "2014"
            
                }},
            {$group: {_id:null, "amount": {$sum: "$lendprojectcost"}}}
            ])
        
            { "_id" : null, "amount" : NumberLong("6291190000") }
            { "_id" : null, "amount" : 27280000 }
    
    2.  Projects in 2014
    
        The number of projects in 2014 for south east asia. Using the *Python* script in listing [88](#org1ae6533) with `./printKeys.py | sed 's/,/\n/g' | fzf` makes it easy to find `regionname`.
        
        First list all regions:
        
            db.bank.distinct('regionname')
        
            [
            	"Africa",
            	"East Asia and Pacific",
            	"Europe and Central Asia",
            	"Latin America and Caribbean",
            	"Middle East and North Africa",
            	"Other",
            	"South Asia"
            ]
        
        This gives us the `South Asia` value to use with `.find()`:
        
            db.bank.find({regionname: "South Asia", approvalfy: "2014"}).count()
        
            7
        
        The total cost of these projects:
        
            db.bank.aggregate([
                {$match: {regionname: "South Asia", approvalfy: "2014"}}, // Find the Region Names
                {$group: {_id:null, "Total_Cost": { $sum: "$lendprojectcost"} }}, // only have ID and Total Cost
                {$sort: {"Total_Cost": -1}} // i.e. by descending
            ])
        
            { "_id" : null, "Total_Cost" : NumberLong("2207510000") }
        
        How much is that per project (i.e. the average):
        
            db.bank.aggregate([
                {$match: {regionname: "South Asia", approvalfy: "2014"}},
                {$group: {_id:null, "Average": { $avg: "$lendprojectcost"}}},
                {$sort: {"Average": -1}}
            ])
        
            { "_id" : null, "Average" : 315358571.4285714 }
        
        If the regions were ranked, where in that rank would South Asia be, to return only some keys use `find({}, {keyname: 1})`:
        
            //db.bank.find({}, {"regionname": 1, "lendprojectcost": 1})
            // This doesn't work because it doesn't add them
            db.bank.find({}, {"regionname": 1, "lendprojectcost": 1}).sort({"lendprojectcost":-1}).limit(9)
        
            { "_id" : ObjectId("52b213b38594d8a2be17c882"), "lendprojectcost" : NumberLong("5170000000"), "regionname" : "South Asia" }
            { "_id" : ObjectId("52b213b38594d8a2be17c94f"), "lendprojectcost" : NumberLong("4887090000"), "regionname" : "Africa" }
            { "_id" : ObjectId("52b213b38594d8a2be17c8f9"), "lendprojectcost" : NumberLong("4500000000"), "regionname" : "East Asia and Pacific" }
            { "_id" : ObjectId("52b213b38594d8a2be17c8a0"), "lendprojectcost" : NumberLong("2700000000"), "regionname" : "South Asia" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7ee"), "lendprojectcost" : NumberLong("2672000000"), "regionname" : "South Asia" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7f9"), "lendprojectcost" : NumberLong("2571230000"), "regionname" : "East Asia and Pacific" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7e5"), "lendprojectcost" : NumberLong("2404400000"), "regionname" : "Middle East and North Africa" }
            { "_id" : ObjectId("52b213b38594d8a2be17c840"), "lendprojectcost" : 1718300000, "regionname" : "South Asia" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7cd"), "lendprojectcost" : 1684160000, "regionname" : "Latin America and Caribbean" }
        
        To list them in order, the `id` for the `$group` must be given as `regionname`:
        
            db.bank.aggregate([
                {$match: {approvalfy: "2014", lendprojectcost: { $gt: 0}}}, // Negative Values Haven't bee Considered
                { $group: { _id: "$regionname", "Total_Cost": { $sum: "$lendprojectcost"} }}, //Group by Region Name, give back Total Cost
                {$sort: {"Total_Cost": -1}} // i.e. by descending
            ])
        
            { "_id" : "South Asia", "Total_Cost" : NumberLong("2207510000") }
            { "_id" : "Africa", "Total_Cost" : 1446990000 }
            { "_id" : "Latin America and Caribbean", "Total_Cost" : 733310000 }
            { "_id" : "Middle East and North Africa", "Total_Cost" : 372550000 }
            { "_id" : "East Asia and Pacific", "Total_Cost" : 341910000 }
            { "_id" : "Europe and Central Asia", "Total_Cost" : 331620000 }
            { "_id" : "Other", "Total_Cost" : 18890000 }
        
        How many projects did Eas Asia have provided:
        
            db.bank.find({regionname: "East Asia and Pacific", approvalfy: "2014"}).count()
        
        To return the number of projects for each group (i.e. the number of documents per each group), use the somewhat tricky `{$sum: 1}`, and change the order:
        
            db.bank.aggregate([
                {$match: {approvalfy: "2014", lendprojectcost: { $gt: 0}}}, // Negative Values Haven't bee Considered
                { $group: { _id: "$regionname", "No_Projects": { $sum: 1 }, "Total_Cost": { $sum: "$lendprojectcost"} }}, //Group by Region Name, give back Total Cost
                {$sort: {"No_Projects": -1}} // i.e. by descending
            ])
        
            { "_id" : "Africa", "No_Projects" : 24, "Total_Cost" : 1446990000 }
            { "_id" : "East Asia and Pacific", "No_Projects" : 15, "Total_Cost" : 341910000 }
            { "_id" : "Middle East and North Africa", "No_Projects" : 8, "Total_Cost" : 372550000 }
            { "_id" : "South Asia", "No_Projects" : 7, "Total_Cost" : NumberLong("2207510000") }
            { "_id" : "Europe and Central Asia", "No_Projects" : 6, "Total_Cost" : 331620000 }
            { "_id" : "Latin America and Caribbean", "No_Projects" : 5, "Total_Cost" : 733310000 }
            { "_id" : "Other", "No_Projects" : 1, "Total_Cost" : 18890000 }
        
        Africa (region) had the most number of projects, which country of Africa had the most:
        
            db.bank.aggregate([
            {$match: {regionname: "Africa", approvalfy: "2014"}},
            {$group: {_id:"$countryshortname", "Total_value": {$sum: "$lendprojectcost"}, "No_Projects": {$sum: 1}}},
            {$sort: {"No_Projects": -1}}
                ])
        
            { "_id" : "Africa", "Total_value" : 510080000, "No_Projects" : 5 }
            { "_id" : "Cote d'Ivoire", "Total_value" : 115750000, "No_Projects" : 2 }
            { "_id" : "Mauritania", "Total_value" : 450000, "No_Projects" : 1 }
            { "_id" : "Angola", "Total_value" : 80000000, "No_Projects" : 1 }
            { "_id" : "Seychelles", "Total_value" : 7000000, "No_Projects" : 1 }
            { "_id" : "South Sudan", "Total_value" : 7530000, "No_Projects" : 1 }
            { "_id" : "Senegal", "Total_value" : 46000000, "No_Projects" : 1 }
            { "_id" : "Ghana", "Total_value" : 97000000, "No_Projects" : 1 }
            { "_id" : "Sao Tome and Principe", "Total_value" : 100000, "No_Projects" : 1 }
            { "_id" : "Lesotho", "Total_value" : 15000000, "No_Projects" : 1 }
            { "_id" : "Kenya", "Total_value" : 66400000, "No_Projects" : 1 }
            { "_id" : "Nigeria", "Total_value" : 300000000, "No_Projects" : 1 }
            { "_id" : "Gambia, The", "Total_value" : 5000000, "No_Projects" : 1 }
            { "_id" : "Comoros", "Total_value" : 5000000, "No_Projects" : 1 }
            { "_id" : "Mozambique", "Total_value" : 32000000, "No_Projects" : 1 }
            { "_id" : "Congo, Republic of", "Total_value" : 32000000, "No_Projects" : 1 }
            { "_id" : "Madagascar", "Total_value" : 85400000, "No_Projects" : 1 }
            { "_id" : "Tanzania", "Total_value" : 24280000, "No_Projects" : 1 }
            { "_id" : "Sierra Leone", "Total_value" : 18000000, "No_Projects" : 1 }
        
        Africa the country had the most, the largest project being worth:
        
            db.bank.aggregate([
            {$match: {regionname: "Africa", approvalfy: "2014"}},
            {$group: {_id:"$lendprojectcost"}},
            {$sort: {"_id": -1}}
                ])
        
            { "_id" : 468900000 }
            { "_id" : 300000000 }
            { "_id" : 97000000 }
            { "_id" : 85400000 }
            { "_id" : 80000000 }
            { "_id" : 66400000 }
            { "_id" : 65750000 }
            { "_id" : 50000000 }
            { "_id" : 46000000 }
            { "_id" : 32000000 }
            { "_id" : 24280000 }
            { "_id" : 22000000 }
            { "_id" : 18000000 }
            { "_id" : 15000000 }
            { "_id" : 10750000 }
            { "_id" : 7530000 }
            { "_id" : 7000000 }
            { "_id" : 5000000 }
            { "_id" : 4630000 }
            { "_id" : 3800000 }
            Type "it" for more
        
        Observe the use of the `$first` accumulator/function that needs be used to
        return a raw feature:
        
            db.bank.aggregate([
            {$match: {regionname: "Africa", approvalfy: "2014"}},
            {$group: {       _id:"$_id",
            	      "cost": { $first: "$lendprojectcost"},
            	   "country": { $first: "$countryshortname"}
            	   }
            						    },
            
            {$sort: {"cost": -1}}
                ])
        
            { "_id" : ObjectId("52b213b38594d8a2be17c7c1"), "cost" : 468900000, "country" : "Africa" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7a0"), "cost" : 300000000, "country" : "Nigeria" }
            { "_id" : ObjectId("52b213b38594d8a2be17c78c"), "cost" : 97000000, "country" : "Ghana" }
            { "_id" : ObjectId("52b213b38594d8a2be17c791"), "cost" : 85400000, "country" : "Madagascar" }
            { "_id" : ObjectId("52b213b38594d8a2be17c79e"), "cost" : 80000000, "country" : "Angola" }
            { "_id" : ObjectId("52b213b38594d8a2be17c785"), "cost" : 66400000, "country" : "Kenya" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7bd"), "cost" : 65750000, "country" : "Cote d'Ivoire" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7b5"), "cost" : 50000000, "country" : "Cote d'Ivoire" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7a3"), "cost" : 46000000, "country" : "Senegal" }
            { "_id" : ObjectId("52b213b38594d8a2be17c79d"), "cost" : 32000000, "country" : "Mozambique" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7a9"), "cost" : 32000000, "country" : "Congo, Republic of" }
            { "_id" : ObjectId("52b213b38594d8a2be17c79f"), "cost" : 24280000, "country" : "Tanzania" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7ae"), "cost" : 22000000, "country" : "Africa" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7b6"), "cost" : 18000000, "country" : "Sierra Leone" }
            { "_id" : ObjectId("52b213b38594d8a2be17c784"), "cost" : 15000000, "country" : "Lesotho" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7ad"), "cost" : 10750000, "country" : "Africa" }
            { "_id" : ObjectId("52b213b38594d8a2be17c78a"), "cost" : 7530000, "country" : "South Sudan" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7a1"), "cost" : 7000000, "country" : "Seychelles" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7a7"), "cost" : 5000000, "country" : "Gambia, The" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7b0"), "cost" : 5000000, "country" : "Comoros" }
            Type "it" for more
        
            db.bank.aggregate([
            {$match: {regionname: "Africa", approvalfy: "2014"}},
            {$group: {       _id:"$_id",
            	      "cost": { $first: "$lendprojectcost"},
            	   "country": { $first: "$countryshortname"}
            	   }
            						    },
            
            {$sort: {"cost": -1}}
                ])
        
            { "_id" : ObjectId("52b213b38594d8a2be17c7c1"), "cost" : 468900000, "country" : "Africa" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7a0"), "cost" : 300000000, "country" : "Nigeria" }
            { "_id" : ObjectId("52b213b38594d8a2be17c78c"), "cost" : 97000000, "country" : "Ghana" }
            { "_id" : ObjectId("52b213b38594d8a2be17c791"), "cost" : 85400000, "country" : "Madagascar" }
            { "_id" : ObjectId("52b213b38594d8a2be17c79e"), "cost" : 80000000, "country" : "Angola" }
            { "_id" : ObjectId("52b213b38594d8a2be17c785"), "cost" : 66400000, "country" : "Kenya" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7bd"), "cost" : 65750000, "country" : "Cote d'Ivoire" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7b5"), "cost" : 50000000, "country" : "Cote d'Ivoire" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7a3"), "cost" : 46000000, "country" : "Senegal" }
            { "_id" : ObjectId("52b213b38594d8a2be17c79d"), "cost" : 32000000, "country" : "Mozambique" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7a9"), "cost" : 32000000, "country" : "Congo, Republic of" }
            { "_id" : ObjectId("52b213b38594d8a2be17c79f"), "cost" : 24280000, "country" : "Tanzania" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7ae"), "cost" : 22000000, "country" : "Africa" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7b6"), "cost" : 18000000, "country" : "Sierra Leone" }
            { "_id" : ObjectId("52b213b38594d8a2be17c784"), "cost" : 15000000, "country" : "Lesotho" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7ad"), "cost" : 10750000, "country" : "Africa" }
            { "_id" : ObjectId("52b213b38594d8a2be17c78a"), "cost" : 7530000, "country" : "South Sudan" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7a1"), "cost" : 7000000, "country" : "Seychelles" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7a7"), "cost" : 5000000, "country" : "Gambia, The" }
            { "_id" : ObjectId("52b213b38594d8a2be17c7b0"), "cost" : 5000000, "country" : "Comoros" }
            Type "it" for more
        
            db.wb.aggregate([
            
            {$match: {your matching conditions}},
            
            {$group:{group expression and functions}},
            
            {$sort: {sorting expression}}
            
            ])


<a id="org3bacfad"></a>

# Predictive Modelling

It appears that in the past the training data splitting libraries were contained in:

> `sklearn.cross_validation`

It seems they are now in: <sup><a id="fnr.6" class="footref" href="#fn.6">6</a></sup>

    ~from sklearn.model_selection ~

-   Using SVM in python
    -   p. 21
        -   lecture slides 09
-   Using Trees in *Python*
    -   Lecture Slides 10
        -   P. 11
-   Using Random Forest


<a id="orgc676527"></a>

## Classification


<a id="org630bc73"></a>

### SVM

    import numpy as np
    from sklearn import svm, datasets
    
    # Import some data ------------------------------------------
    random.seed(3823)
    iris = datasets.load_iris()
    
    # Test and Training Split Manually --------------------------
    trainidx = np.random.choice(iris['data'].shape[0], int(iris['data'].shape[0]*0.7))
    testidx = list(set(range(iris['data'].shape[0])) - set(trainidx))
    
     # Training...................................................
       # Input Variables
    trainX = iris.data[trainidx, :2]
       # Output Classification Variable
    trainy = iris.target[trainidx]
    
     # Testing ...................................................
       # Input Variables
    testX = iris.data[testidx, :2]
       # Output Classification Variable
    testy = iris.target[testidx]
    
    # Create an SVM ----------------------------------------------
    # Create the Model
    C = 1.0 # Regularization Parameter
    svc = svm.SVC(kernel = 'linear', C = C)
    # Fit the Model
    svc.fit(trainX, trainy)
    # lin_svc = svm.LinearSVC(C = C).fit(trainX, trainy) # This scales better
    
    # Test the Model---------------------------------------------
    Z = svc.predict(testX)
    print("Percentage of Correct Predictions:")
    print(sum(Z==testy)/len(Z)*100)
    
    ## This should return 79.710 %


<a id="org6cb4119"></a>

### Trees

See figure [tree_moon_class](#tree_moon_class).

![img](_media/Tree_Classification_Moon.png "Moon Data With a Tree Classification")

In descending order, typically, the fastest classification algorithms are: <sup><a id="fnr.7" class="footref" href="#fn.7">7</a></sup>

1.  Decision Tree
2.  Random Forrest
3.  Linear SVM
4.  Non-Linear SVM

With respect to choosing a classification Model:

-   If the data is non linear and model accuracy is paramount:
    -   Non Linear SVM
        -   This will Require a lot of computing power though
-   If there is really big data, whith a lot of features and speed is the priority
    -   Linear SVM
-   If the data is non-linear and an interpretable model is required
    -   Random Forest.


<a id="org620782e"></a>

### Classification Score

To see what `score` actually measures, perform `help(clf.score)`, it seems Classification in SciKitLearn is usually Accuracy: <sup><a id="fnr.8" class="footref" href="#fn.8">8</a></sup>

\[
\mathrm{ACC} = \frac{\mathrm{TP} + \mathrm{TN}}{\mathrm{P} + \mathrm{N}}
\]


<a id="org3c62bc2"></a>

### Decision Tree

Adapted from p. 280 of 344 of [Lecture Slides](BigData/00_Slides_BigData.pdf)

    #-- Import Packages -------------------------------------------
    import numpy as np
    import sklearn
    from sklearn.model_selection import train_test_split
    from sklearn import datasets
    
    #-- Generate Two Moons Data -----------------------------------
    X, y = datasets.make_moons(n_samples = 1000, noise = 0.3, random_state = 0)
    
    #-- Split data into Training and Test Sets --------------------
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.4)
    
    #  Define a Decision Tree Classifier -------------------------
    d = 4
    clf = sklearn.tree.DecisionTreeClassifier(max_depth = d)
    
      #. Train the Model ..........................................
      clf.fit(X_train, y_train)
    
      #. Test the Model
      score = clf.score(X_test, y_test)
      print("The performance is:\n" + str(score*100) + "%")
      #  help(clf.score)
          # This returns the mean accuracy
    	  # (TP+TN)/(P+N)


<a id="org398f095"></a>

### Random Forrest

Adapted from p. 280 of 344 of [Lecture Slides](Material/lectures/00_Slides_BigData.pdf)

    #-- Import Packages -------------------------------------------
    import numpy as np
    from sklearn.ensemble import RandomForestClassifier
    from sklearn.model_selection import train_test_split
    
    
    
    #-- Generate Two Moons Data -----------------------------------
    X, y = datasets.make_moons(n_samples = 1000, noise = 0.3, random_state = 0)
    
    #-- Split data into Training and Test Sets --------------------
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.4)
    
    #  Define a Decision Tree Classifier -------------------------
    clf = RandomForestClassifier(
      n_estimators = 10,
      max_depth = 16
    )
      #. Train the Model ..........................................
      clf.fit(X_train, y_train)
    
      #. Test the Model
      score = clf.score(X_test, y_test)
      print("The performance is:\n" + str(score*100) + "%")
      #  help(clf.score)
          # This returns the mean accuracy
    	  # (TP+TN)/(P+N)


<a id="org0b63fc9"></a>

## Regression

Implementing Linear Regression in Python

First let's get some data with ***R***:

    #!/usr/bin/R
    write.csv(cars, file = "cars.csv")
    list.files()

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">BigData.org</td>
</tr>


<tr>
<td class="org-left">cars.csv</td>
</tr>


<tr>
<td class="org-left">Material</td>
</tr>


<tr>
<td class="org-left">style.css</td>
</tr>
</tbody>
</table>


<a id="org22590ed"></a>

### Linear Regression (Ordinary Least Squares)

Observe:

-   it is necessary to load `matplotlib.pyplot` not just `matplotlib`, the `pyplot` submodule will not not be pulled in and must be pulled in explicitly.
-   `x` is a `(20,)` numpy array, it is like a vector, the output of `train_test_split` outputs what it got in. The `SciKit` package expects matrices (rows as observations, columns as factors), by calling `x.reshape(-1, 1)` the numpy array can be reshaped to be a \(n\times 1\) matrix of size `(n, 1)`.

    from sklearn import linear_model
    from sklearn.model_selection import train_test_split
    import numpy as np
    import pandas as pd
    import matplotlib.pyplot as plt
    
    # Load the Data (Generate from Shell with R) ----------------
    #! R -e 'write.csv(cars, file = "cars.csv")'
    cars = pd.read_csv("./cars.csv")
    
    # Assign Variables
    y = np.array(cars['dist'].astype('float'))
    x = np.array(cars['speed'].astype('float'))
    
    # Test Training Split ---------------------------------------
    x_train, x_test, y_train, y_test = train_test_split(
    		    x, y,
    		    test_size = 0.4, random_state = 42
    )
    
    
    # Create the Linear Model ------------------------------------
    reg = linear_model.LinearRegression(fit_intercept=True)
    
    # Fit the Model ---------------------------------------------
    reg.fit(x_train.reshape(-1, 1), y_train)
    
    # Test the Model --------------------------------------------
    y_pred = reg.predict(x_test.reshape(-1, 1))

    None

1.  Plotting Linear Regression     :plot:

    1.  MatPlotlib
    
        A plot of this model can be produced with MatPlotLib: <a id="orgf60b1fd"></a>
        
            import matplotlib.pyplot as plt
            
            # Make an empty figure
            p = plt.figure()
            
            # Create the Scatter Plot
            plt.scatter(x_test, y_test)
            
            # Add the Predictions as a line
            plt.plot(x_test, y_pred)
            
            # Labels
            plt.xlabel("Speed")
            plt.ylabel("Distance")
            plt.title("Plot of Linear Regression of Distance given Speed")
            
            # Save the Plot
            # Save it before previewing or the image is blank
            plt.savefig('_media/cars.png', format = 'png')
            plt.show()
        
        ![img](_media/cars.png)
        
        -   the `scatter` method adds points and the `plot` method adds a line.
        -   Observe also that the `pyplot` submodule was loaded in.
    
    2.  Plotnine GGPlot
    
        Or my Using Plotnine:
        
            data = {'distance': x_test,
            	'speed': y_test,
            	'speed_model': y_pred
            }
            df = pd.DataFrame(data, columns = ['distance', 'speed', 'speed_model'])
            
            print(df.iloc[1:6,:])
        
               distance  speed  speed_model
            1      20.0   48.0    56.286565
            2      17.0   50.0    46.314626
            3      24.0   70.0    69.582483
            4      13.0   34.0    33.018707
            5      24.0  120.0    69.582483
        
        And finially Plot the Data:
        
            from plotnine import *
            import copy
            
            p = (
                ggplot(df, aes(x = 'distance')) +
            	geom_point(aes(y = 'speed')) +
            	geom_smooth(aes(y = 'speed_model')) +
            	theme_bw() +
            	labs(x = "Distance", y = "Speed") +
            	ggtitle('Magnitude of Determinant Given Matrix Size')
            
            )
            p.save(filename = '_media/cars_ggplotnine.png', format = 'png',
                   width = 4, height = 4, units = 'in', dpi = 500)
        
        ![img](./_media/cars_ggplotnine.png)
        
        Ideally however the modelled data and the observed data should both be in the
        speed column but with a different label (say model/obs), this can be acheived by
        using `pandas.wide_to_long`:
        
        First melt the data down:
        
            # Melt the data down
            df_melt = pd.melt(df, id_vars = ['distance'], value_vars = ['speed', 'speed_model'], var_name = "data_type", value_name = "speed")
            print(df_melt.head(3))
        
               distance data_type  speed
            0      12.0     speed   24.0
            1      20.0     speed   48.0
            2      17.0     speed   50.0
        
        Then Rename the Factors
        
            # Melt the data down
            df_melt = df_melt.replace(to_replace=['speed','speed_model'], value=['observed', 'model'])
            print(df_melt.head(3))
        
               distance data_type  speed
            0      12.0  observed   24.0
            1      20.0  observed   48.0
            2      17.0  observed   50.0
        
        Inspect the variable names and the data:
        
            df_melt.head()
            df_melt.columns
        
               distance data_type  speed
            0      12.0  observed   24.0
            1      20.0  observed   48.0
            2      17.0  observed   50.0
            3      24.0  observed   70.0
            4      13.0  observed   34.0
            
            >>> df_melt.columns
            
            Index(['distance', 'data_type', 'speed'], dtype='object')
        
        Now the Data Can be plotted, but notice in `geom_smooth` we only plotted
        the line for the 'observed'data:
        
            p = (
              ggplot(df_melt, aes(x = 'distance', color = 'data_type', y = 'speed')) +
            	geom_point() +
            	geom_smooth(data = df_melt[df_melt['data_type']=='observed']) +
            	theme_bw()  +
            	labs(x = "Distance", y = "Speed")  +
            	ggtitle('Linear Model of Distance Given Speed')    +
            #        guides(color = guide_legend("Data Type"))
            	scale_color_discrete(labels = ["Observation", "Prediction"])
            )
            p.save(filename = '_media/cars_ggplotnine_melt.png', format = 'png',
                   width = 4, height = 4, units = 'in', dpi = 500)
        
        ![img](_media/cars_ggplotnine_melt.png)


<a id="org117d367"></a>

### Sparse Linear Regression

When given many variables in a regression problem, where not all variables will be useful, a *variable selection* problem presents itself.

Variable Selection is **NP** hard with \(O(2^{N})\) complexity, to address it:

-   Greedy Selection
    -   Forward / Backward Selection <sup><a id="fnr.9" class="footref" href="#fn.9">9</a></sup>
-   Sparse Linear Regression
    -   LASSO and Ridge
    -   Elastic Net
    -   Theres plenty of them.

1.  LASSO

    The *Least Absolute Shrinkage and Selection Operator*, given the model:
    
    \begin{align}
    y_{\mathrm{model}} = b_1x_1 +  b_2x_2 +  b_3x_3 +  \ldots b_px_p
    \end{align}
    
    find the vector \(\mathbf{b} = \left\langle b1, b2, b3, ..., b_p
    \right\rangle \)
    
    such that:
    
    \begin{align}
          \mathrm{minimize} \enspace \left( y_{\mathrm{data}}- y_{\mathrm{model}}
          \right)^2 \enspace \mathrm{subject to:} \sum^{p}_{i= 1}
    \left\lvert b_k \right\rvert \leq t
    \end{align}
    
    Implementing lasso regression in *Python*:
    
        from sklearn import datasets
        from sklearn import linear_model
        from sklearn.model_selection import train_test_split
        diabetes = datasets.load_diabetes()
        
        # Assign Variables ------------------------------------------
        X = diabetes.data      # ; print(X)
        y = diabetes.target    # ; print(y)
        
        # Test Train Split ------------------------------------------
        X_train, X_test, y_train, y_test = train_test_split(X, y,
            test_size = 0.4, random_state = 42)
        
        # Create the Model ------------------------------------------
        reg = linear_model.Lasso(alpha = 1.5, normalize = True)
        
        # Fit the Model ---------------------------------------------
        reg.fit(X_train, y_train)
        
        # Print the Selected Variables ------------------------------
        varnames = diabetes.feature_names
        selected_features =  [ varnames[i] for i in np.where(reg.coef_!=0)[0] ]
        
        print("The variables selected are:")
        print(selected_features)
    
        >>> print(selected_features)
        ['bmi', 's5']
    
    The tricky part with *sparse linear regressin* is choosing the *tuning parameter* also known as the *regularisation parameter* denoted by \(\lambda\) (and ocassionaly by \(\alpha\) and \(\beta\)), to choose this the following are used:
    
    -   Path Algorithms
    -   Least Angle Regression (LARS)
    
    1.  Least Angle Regression LARS
    
            import numpy as np
            import matplotlib.pyplot as plt
            from sklearn import linear_model
            from sklearn impoirt datasets
            diabetes = datasets.load_diabetes()
            varnames = diabetes.feature_names
            
            
            # Assign the Variables --------------------------------------
            X = diabetes.data  # These are  numpy arrays
            y = diabetes.target
            
            
            # Perform the LARS -------------------------------------------
            alphas, index, coefs = linear_model.lars_path(X, y, method = 'lasso', verbose = True)
            
            xx = np.sum(np.abs(coefs.T), axis = 1)   # x /= 5 means x = x/5
            xx = xx/xx[-1] # Scale to 1
        
        To plot this:
        
            import matplotlib.pyplot as plt
            plt.plot(xx, coefs.T)
            ymin, ymax = plt.ylim()
            plt.vlines(xx, ymin, ymax, linestyles='dashed')
            plt.xlabel('|coef| / max|coef|')
            plt.ylabel('Coefficients')
            plt.title('LASSO Path')
            plt.axis('tight')
            plt.savefig('_media/lars_plot.png', format = 'png')
            plt.show()
        
        ![img](_media/lars_plot.png)


<a id="orgac0ac1a"></a>

# Exam Preparation


<a id="org9eacb89"></a>

## Plot a CSV


<a id="org432b8bb"></a>

### Chosen approach

    import pandas as pd
    
    ## Load the Data
    df_x = pd.read_csv(r'./300580_new.csv', header = None)
    df_y = pd.read_csv(r'./300581_new.csv', header = None)
    
    ## Print the Data
    data = pd.concat([df_x, df_y], axis = 1)
    data.columns = ["x", "y"]
    print(data)
    
    ## Plot the Data
    from plotnine import *
    
    p = (
        ggplot(data, aes(x = 'x')) +
    	geom_point(aes(y = 'y')) +
    #        geom_smooth(aes(y = 'speed_model')) +
    	theme_bw() +
    	labs(x = "Distance", y = "Speed") +
    	ggtitle('Magnitude of Determinant Given Matrix Size')
    
    )
    p


<a id="org69b96d6"></a>

### Import a CSV

1.  Using lists

    The real trick here is using [`reshape`](file:///home/ryan/Sync/Notes/Org/roam/20201103164705-reshaping_arrays_using_numpy.md) to fix the CSV:
    
        import csv
        import numpy as np
        
        with open('./300580_new.csv') as f:
            reader = csv.reader(f)
            l1 = np.array(list(reader)).reshape(1, -1).tolist()[0]
        with open('./300581_new.csv') as f:
            reader = csv.reader(f)
            l2 = np.array(list(reader)).reshape(1, -1).tolist()[0]
        
        print('\n')
        for i in range(len(l1)):
            print(str(float(l1[i])) + '\t' + str(float(l2[i])))

2.  Using Pandas

    You essentially want to follow the approach taken in &sect; [7.2.1.1.1](#orgf60b1fd).
    
    First import the CSV file as a `pandas`, specify the `header` accordingly:
    
        import pandas as pd
        
        df_x = pd.read_csv(r'./300580_new.csv', header = None)
        df_y = pd.read_csv(r'./300581_new.csv', header = None)
    
    Print the contents by creating a pandas data frame:
    
        print(df_x)
        print(df_y)
        data = pd.concat([df_x, df_y], axis = 1)
        data.columns = ["x", "y"]
        print(data)
    
        >>> pd.concat([df_x, df_y], axis = 1) # NOTE
               0     0
        0   88.0  79.0
        1   76.0  62.0
        2   90.0  76.0
        3   96.0  94.0
    
    To extract this data again we can use the `iloc` method, similar to ***R*** but with a `:` character:
    
        df_x = data.iloc[:,1]
        df_y = data.iloc[:,2]


<a id="orge1788bf"></a>

### Plot the Data

1.  Pandas Plot Method

    Pandas can call matplotlib directly like so:
    
        data.plot.scatterplot(x = 'x', y = 'y')
    
    ![img](_media/matplotlib_pyplot_scatterplot_example.png)

2.  MatPlotLib

    The advantage to using matplotlib is that it can be used on lists and pandas, so this is convenient if the list method was used.
    
    To plot this directly with matplotlib (as in [7.2.1.1.1](#orgf60b1fd)):
    
        # Make an empty figure
        p = plt.figure()
        
        ## Make a Scatter Plot
        plt.scatter(df_x, df_y)
        
        # Labels
        plt.xlabel("Speed")
        plt.ylabel("Distance")
        plt.title("Plot of Linear Regression of Distance given Speed")
        
        # Save the Plot
        # Save it before previewing or the image is blank
        # plt.savefig('/home/ryan/Sync/Studies/2020Spring/BigData/_media/matplotlib_pyplot_scatterplot_example.png')
        plt.show()
    
    ![img](_media/matplotlib_pyplot_scatterplot_example.png)

3.  Plotnine     :plotnine:

    This could also be done in `plotnine` for the sake of ggplot syntax:
    
        from plotnine import *
        
        p = (
            ggplot(data, aes(x = 'x')) +
        	geom_point(aes(y = 'y')) +
        #        geom_smooth(aes(y = 'speed_model')) +
        	theme_bw() +
        	labs(x = "Distance", y = "Speed") +
        	ggtitle('Magnitude of Determinant Given Matrix Size')
        
        )
        p
        p.save(filename = '_media/cars_ggplotnine.png', format = 'png',
               width = 4, height = 4, units = 'in', dpi = 500)


<a id="orgd7a8b78"></a>

## SQL

The file is located at `./Exam/Sample/testdb.sqlite` so if you wanted to run this in the terminal:

    sqlite3

then inside sql:

    .open "/home/ryan/Sync/Studies/2020Spring/BigData/Exam/Sample/testdb.sqlite"

First we need to find out the tables contained in the database:

    .tables

    record

now that we know that it has a table called record we can get column names from it using `.schema`:

    .schema record

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">CREATE TABLE record (</td>
</tr>


<tr>
<td class="org-left">[Sid] INTEGER</td>
</tr>


<tr>
<td class="org-left">[Sname] TEXT</td>
</tr>


<tr>
<td class="org-left">[Sex] TEXT</td>
</tr>


<tr>
<td class="org-left">[DOB] TEXT</td>
</tr>


<tr>
<td class="org-left">[Uid] INTEGER</td>
</tr>


<tr>
<td class="org-left">[Mark] REAL</td>
</tr>


<tr>
<td class="org-left">[Uname] TEXT</td>
</tr>


<tr>
<td class="org-left">[Utype] TEXT</td>
</tr>


<tr>
<td class="org-left">);</td>
</tr>
</tbody>
</table>


<a id="org4073bc7"></a>

### (1) How many students are in the database?

    .schema record

    select count(*) from
           (select Distinct Sid from record)
           ;

    1000

1.  How many female students are in the database?

    First we need to inspect the first couple values of the `Sex` column:
    
        select Sid, Sex, Sname, avg(Mark) as av_mark
               from record
               group by Sid
               limit 9
               ;
    
    <table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
    
    
    <colgroup>
    <col  class="org-right" />
    
    <col  class="org-left" />
    
    <col  class="org-left" />
    
    <col  class="org-right" />
    </colgroup>
    <tbody>
    <tr>
    <td class="org-right">17002055</td>
    <td class="org-left">F</td>
    <td class="org-left">Kimberly Thomas</td>
    <td class="org-right">75.8</td>
    </tr>
    
    
    <tr>
    <td class="org-right">17003783</td>
    <td class="org-left">M</td>
    <td class="org-left">James Richardson</td>
    <td class="org-right">77.0</td>
    </tr>
    
    
    <tr>
    <td class="org-right">17004931</td>
    <td class="org-left">F</td>
    <td class="org-left">Melanie Knight</td>
    <td class="org-right">72.8</td>
    </tr>
    
    
    <tr>
    <td class="org-right">17006515</td>
    <td class="org-left">F</td>
    <td class="org-left">Elizabeth Robertson</td>
    <td class="org-right">73.5</td>
    </tr>
    
    
    <tr>
    <td class="org-right">17007137</td>
    <td class="org-left">F</td>
    <td class="org-left">Erin Murray</td>
    <td class="org-right">75.2</td>
    </tr>
    
    
    <tr>
    <td class="org-right">17009377</td>
    <td class="org-left">M</td>
    <td class="org-left">Bryan Thomson</td>
    <td class="org-right">71.8</td>
    </tr>
    
    
    <tr>
    <td class="org-right">17011808</td>
    <td class="org-left">F</td>
    <td class="org-left">Megan Butler</td>
    <td class="org-right">72.6666666666667</td>
    </tr>
    
    
    <tr>
    <td class="org-right">17012981</td>
    <td class="org-left">F</td>
    <td class="org-left">Latoya Lee</td>
    <td class="org-right">76.0</td>
    </tr>
    
    
    <tr>
    <td class="org-right">17013056</td>
    <td class="org-left">M</td>
    <td class="org-left">Michael Thompson</td>
    <td class="org-right">76.8</td>
    </tr>
    </tbody>
    </table>
    
    This indicates that gender is stored as "M" or "F", so the number of female students is given by:
    
    -   Counting the number of observations, where:
        -   Sex is "F"
        -   Sid is a `Distinct` value
    
    This can be implemented like so:
    
        select count(*) from
               (select Distinct Sid from record where Sex is "F")
               ;
    
        500


<a id="orgfa149b4"></a>

### (2) List the Unique Unit IDS in the Database

The <del><del>unique</del></del> Distinct unit IDs in the database can be listed like so:

    select Uid
           from record
           group by Uid
           ;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">300144</td>
</tr>


<tr>
<td class="org-right">300580</td>
</tr>


<tr>
<td class="org-right">300581</td>
</tr>


<tr>
<td class="org-right">300585</td>
</tr>


<tr>
<td class="org-right">300695</td>
</tr>


<tr>
<td class="org-right">301046</td>
</tr>
</tbody>
</table>

The number of Distinct Uid can be returned like so:

    select count(Distinct Uid)
           from record
           ;

    6

The number of different students for each unit, in this data base, rounded to 2dp:

    select Uid, count(*), round(avg(Mark), 2) as av_mark
           from (select Uid, Mark from record)
           group by Uid
           ;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />
</colgroup>
<tbody>
<tr>
<td class="org-right">300144</td>
<td class="org-right">1000</td>
<td class="org-right">70.05</td>
</tr>


<tr>
<td class="org-right">300580</td>
<td class="org-right">1000</td>
<td class="org-right">80.18</td>
</tr>


<tr>
<td class="org-right">300581</td>
<td class="org-right">1000</td>
<td class="org-right">70.01</td>
</tr>


<tr>
<td class="org-right">300585</td>
<td class="org-right">1000</td>
<td class="org-right">79.88</td>
</tr>


<tr>
<td class="org-right">300695</td>
<td class="org-right">504</td>
<td class="org-right">75.45</td>
</tr>


<tr>
<td class="org-right">301046</td>
<td class="org-right">502</td>
<td class="org-right">74.67</td>
</tr>
</tbody>
</table>


<a id="org4fdab51"></a>

### 3. Which Unit has the lowest Mark in the database?

The minimum marks across the units are given by:

    select Min(Mark) as min, Uid, count(*), round(avg(Mark), 2) as av_mark, Uname
           from (select Uid, Mark, Uname from record)
           group by Uid
           order by Min asc /* or desc */
           ;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-right">32.0</td>
<td class="org-right">300695</td>
<td class="org-right">504</td>
<td class="org-right">75.45</td>
<td class="org-left">Network Technologies</td>
</tr>


<tr>
<td class="org-right">34.0</td>
<td class="org-right">300581</td>
<td class="org-right">1000</td>
<td class="org-right">70.01</td>
<td class="org-left">Programming Techniques</td>
</tr>


<tr>
<td class="org-right">41.0</td>
<td class="org-right">300144</td>
<td class="org-right">1000</td>
<td class="org-right">70.05</td>
<td class="org-left">Object Oriented Analysis</td>
</tr>


<tr>
<td class="org-right">41.0</td>
<td class="org-right">300580</td>
<td class="org-right">1000</td>
<td class="org-right">80.18</td>
<td class="org-left">Programming Fundamentals</td>
</tr>


<tr>
<td class="org-right">43.0</td>
<td class="org-right">301046</td>
<td class="org-right">502</td>
<td class="org-right">74.67</td>
<td class="org-left">Big Data</td>
</tr>


<tr>
<td class="org-right">45.0</td>
<td class="org-right">300585</td>
<td class="org-right">1000</td>
<td class="org-right">79.88</td>
<td class="org-left">Systems Analysis and Design</td>
</tr>
</tbody>
</table>

Only the minimum value result can be returned thusly:

    select Min(Mark) as min, Uid, Uname
           from record ;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-right">32.0</td>
<td class="org-right">300695</td>
<td class="org-left">Network Technologies</td>
</tr>
</tbody>
</table>


<a id="org671fa7f"></a>

### 4. Which unit has the lowest average mark in the database?

So first we need to list the average marks and unit id values:

    select Uid, avg(Mark) as av_mark, Uname
           from (select Uid, Mark, Uname from record)
           group by Uid
           ;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-right">300144</td>
<td class="org-right">70.054</td>
<td class="org-left">Object Oriented Analysis</td>
</tr>


<tr>
<td class="org-right">300580</td>
<td class="org-right">80.177</td>
<td class="org-left">Programming Fundamentals</td>
</tr>


<tr>
<td class="org-right">300581</td>
<td class="org-right">70.011</td>
<td class="org-left">Programming Techniques</td>
</tr>


<tr>
<td class="org-right">300585</td>
<td class="org-right">79.881</td>
<td class="org-left">Systems Analysis and Design</td>
</tr>


<tr>
<td class="org-right">300695</td>
<td class="org-right">75.4523809523809</td>
<td class="org-left">Network Technologies</td>
</tr>


<tr>
<td class="org-right">301046</td>
<td class="org-right">74.6713147410359</td>
<td class="org-left">Big Data</td>
</tr>
</tbody>
</table>

Now from this we need to select the minimum `av_mark` value, observe that no `;` is used inside the brackets corresponding to `from`, this is an easy mistake to make:

    select Min(av_mark) as min_av, Uid, Uname
        from (select Uid, Uname, avg(Mark) as av_mark
    	from (select Uid, Uname, Mark from record) group by Uid)
           ;

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-right" />

<col  class="org-right" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-right">70.011</td>
<td class="org-right">300581</td>
<td class="org-left">Programming Techniques</td>
</tr>
</tbody>
</table>

Hence the minimum mark is 70.011 corresponding to 300581


<a id="org628bcb1"></a>

### Which is the hardest unit

*Programming Techniques* has the lowest average mark of 70.054, suggesting that for the majority of students it is more difficult.

A case could be made for *Network Technologies* in the sense that it has a reasonably high average mark (75.5) and the lowest minimum (32), this suggests that there may be a knowledge gap for some students making it significantly more difficult for a select few students.

Charecteristics of students who do poorly in Network Technologies should be investigated to find a pattern.


<a id="orge0d1e5f"></a>

## Create Moons Data


<a id="org6603231"></a>

### Summary

    #-- Import Packages -------------------------------------------
    import numpy as np
    import sklearn
    from sklearn.model_selection import train_test_split
    from sklearn import datasets
    from sklearn.model_selection import train_test_split
    
    #-- Generate Two Moons Data -----------------------------------
    X, y = datasets.make_moons(n_samples = 1000, noise = 0.3, random_state = 0)
    
    #-- Split data into Training and Test Sets --------------------
    X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.4)
    
    import pandas as pd
    from plotnine import *
    
    ## Make a dataframe
    
    data = pd.DataFrame()
    data['x1'] = X[:,0]
    data['x2'] = X[:,1]
    data['y']  = y
    
    ## Make a plot
    
    (
        ggplot(data, aes(x = 'x1', y = 'x2', color = 'y')) +
    	geom_point() +
    	theme_bw()
    
    )


<a id="orgcff832f"></a>

### In Detail

1.  Generate and split the Data

        #-- Import Packages -------------------------------------------
        import numpy as np
        import sklearn
        from sklearn.model_selection import train_test_split
        from sklearn import datasets
        from sklearn.model_selection import train_test_split
        
        #-- Generate Two Moons Data -----------------------------------
        X, y = datasets.make_moons(n_samples = 1000, noise = 0.3, random_state = 0)
        
        #-- Split data into Training and Test Sets --------------------
        X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 0.4)

2.  Split Manually

    The data can also be split manually:
    
        # Test and Training Split Manually --------------------------
        # Create the
        train_id = random.sample(range(N), int(0.7*N))
        test_id  = [i for i in range(N) if i not in train_id]
        
        # Seperate the training data
        X_train = X[train_id, :]
        X_test = X[test_id, :]
        
        # Seperate the Output or response Variables
        y_train = [y[i] for i in train_id]
        y_test = [y[i] for i in test_id]

3.  Plot with Plotnine

    This could also be don with plotnine, which is arguably significantly easier:
    
        import pandas as pd
        from plotnine import *
        
        ## Make a dataframe
        
        data = pd.DataFrame()
        data['x1'] = X[:,0]
        data['x2'] = X[:,1]
        data['y']  = y
        
        ## Make a plot
        
        (
            ggplot(data, aes(x = 'x1', y = 'x2', color = 'y')) +
        	geom_point() +
        	theme_bw()
        
        )
    
    ![img](_media/ggplot_two_moons_plot.png)

4.  Plot with Matplotlib

    To plot the data with matplotlib:
    
        #!/usr/bin/env python3
        
        #-- Import Packages -------------------------------------------
        from sklearn import datasets
        from sklearn.model_selection import train_test_split
        import matplotlib.pyplot as plt
        
        #-- Generate Two Moons Data -----------------------------------
        X, y = datasets.make_moons(n_samples = 700, noise = 0.3, random_state = 0)
        
        #-- Split data into Training and Test Sets --------------------
        X_train, X_test, y_train, y_test = train_test_split(X, y, test_size = 200) #TODO how to make exactly 200
        
        x1_list = X[:, 0].reshape(1, -1)[0]
        x2_list = X[:, 1].reshape(1, -1)[0]
        
        ## Make a Scatter Plot
        plt.scatter(x1_list, x2_list, c = y)
        plt.show()
    
    ![img](_media/two_moons_matplotlib.png)


<a id="orgc5e7924"></a>

## Fit a KNN Classifier


<a id="orgbb7e0e5"></a>

### Documentation

For these questions you really just want to look at the documentation:

-   [KNN Model](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
-   [Neural Network](https://scikit-learn.org/stable/modules/neural_networks_supervised.html)
-   [Decision Tree](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html?highlight=decision%20tree#sklearn.tree.DecisionTreeClassifier)
-   [Random Forest](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html?highlight=random%20forest#sklearn.ensemble.RandomForestClassifier)


<a id="org9e9dafd"></a>

### Fit the Model

A Knn Model can be fit to the data thusly:

    
    ## Fit the Model
    from sklearn.neighbors import KNeighborsClassifier
    ng = KNeighborsClassifier(n_neighbors=10)
    ng .fit(X_train, y_train)
    
    ## Look at a couple Predictions
    print("Given the Input variables:")
    print(X_train[0:5,:])
    
    print("The Model Predicts that the output will be:")
    ng.predict(X_train[0:5,:])
    
    print("The output was:")
    print(y[0:5])


<a id="orgef60a21"></a>

### Measure the score

To see what `score` actually measures, perform `help(clf.score)`, it seems Classification in SciKitLearn is usually Accuracy: <sup><a id="fnr.10" class="footref" href="#fn.10">10</a></sup>

\[
\mathrm{ACC} = \frac{\mathrm{TP} + \mathrm{TN}}{\mathrm{P} + \mathrm{N}}
\]

This can be returned by using the `score` method with the training and test data given:

    ## Consider the Accuracy of the model
    ng.score(X_test, y_test)

In this case the score was 90%, indicating that the performance of knn is very good on this type of data.

Using Cross Validation can provide a more accurate score, particularly when data is limited:

    ## If data were limited cross validation may be more accurate
    from sklearn.model_selection import cross_val_score
    print(np.mean(cross_val_score(ng, X, y, cv=10)))


<a id="orge781a1d"></a>

## Creating Datasets with Scikit learn

There are many diffferent methods to make data in python using [Sci Kit Learn Make\_](https://scikit-learn.org/stable/search.html?q=sklearn+datasets+make) functions, see also [This link here](https://machinelearningmastery.com/generate-test-datasets-python-scikit-learn/).


<a id="org1073649"></a>

### Make Blobs

    #!/usr/bin/env python
    
    from matplotlib import pyplot as plt
    from pandas import DataFrame
    
    # generate 2d classification dataset
    X, y = make_blobs(n_samples=100, centers=3, n_features=2)
    
    # scatter plot, dots colored by class value
    df = DataFrame(dict(x=X[:,0], y=X[:,1], label=y))
    
    colors = {0:'red', 1:'blue', 2:'green'}
    
    fig, ax = pyplot.subplots()
    
    grouped = df.groupby('label')
    for key, group in grouped:
        group.plot(ax=ax, kind='scatter', x='x', y='y', label=key, color=colors[key])
    pyplot.show()


<a id="orgc821d5a"></a>

# Sqlite as a Text Searching tool

    create virtual table notes using FTS5(path, contents);
    insert into notes values('./filename', 'some text interesting');
    insert into notes values('./other', 'blah');
    select * from notes where notes match 'text';

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<tbody>
<tr>
<td class="org-left">./filename</td>
<td class="org-left">some text interesting</td>
</tr>


<tr>
<td class="org-left">./other</td>
<td class="org-left">blah</td>
</tr>
</tbody>
</table>


# Footnotes

<sup><a id="fn.1" href="#fnr.1">1</a></sup> <https://aur.archlinux.org/packages/mongodb/>

<sup><a id="fn.2" href="#fnr.2">2</a></sup> <https://aur.archlinux.org/packages/mongodb-tools/>

<sup><a id="fn.3" href="#fnr.3">3</a></sup> <https://aur.archlinux.org/packages/mongodb-compass/>

<sup><a id="fn.4" href="#fnr.4">4</a></sup> <https://aur.archlinux.org/packages/robo3t-bin/>

<sup><a id="fn.5" href="#fnr.5">5</a></sup> Different documents in a collection may have different values so be careful with this one.

<sup><a id="fn.6" href="#fnr.6">6</a></sup> <https://scikit-learn.org/stable/modules/cross_validation.html>

<sup><a id="fn.7" href="#fnr.7">7</a></sup> p. 285/344 of  [Lecture Slides](Material/lectures/00_Slides_BigData.pdf)

<sup><a id="fn.8" href="#fnr.8">8</a></sup> See the [Wikipedia :Sensitivity and Specificity](https://en.wikipedia.org/wiki/Sensitivity_and_specificity)

<sup><a id="fn.9" href="#fnr.9">9</a></sup> See [Intro Stat Learning](file:///home/ryan/Sync/Books/Textbooks/Data Science/Introduction to statistical learning.pdf)

<sup><a id="fn.10" href="#fnr.10">10</a></sup> See the [Wikipedia :Sensitivity and Specificity](https://en.wikipedia.org/wiki/Sensitivity_and_specificity)
