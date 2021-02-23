---
title: Applications of Big Data
description: Notes from the UWS unit on SQL, NoSQL and Hadoop.
published: true
date: 2021-02-23T00:24:53.977Z
tags: 
editor: markdown
dateCreated: 2021-02-23T00:20:49.656Z
---

<link rel="stylesheet" type="text/css" href="style.css">

# Links

- [Learning Guide](Material/301110_2020_Spring_Day_Learning_Guide.pdf)
- [First Practical
  (Python)](~/Dropbox/DataSci/BigData/Practicals/02_Practical_2-Python_Basics-II.org::*Calculate Data Statistics)
  - [SQL and NoSQL
    Practical](~/Sync/DataSci/BigData/Practicals/04-MongoDB.org)
- [Lectures](Material/00_Slides_BigData.pdf)
- [Practice Exam](bigdata_practice_exam.pdf)

Start Recoll for Material:

```bash
recoll -c '/home/ryan/Sync/Studies/2020Spring/BigData/Material/.recoll' & disown
```

# 1-2 Intro to Python

Basically just refer to the [First
Practical](~/Dropbox/DataSci/BigData/Practicals/02_Practical_2-Python_Basics-II.org::*Calculate Data Statistics).

# SQLite

- [Lecture
  Slides](pdf:~/Dropbox/Studies/2020Spring/BigData/BigData/lectures/04-Lecture-Slides.pdf.pdf::8++0.00)
- [Practical 03 - SQL-Lite](BigData/Practicals/PDF/03-Practical.pdf)
  - [Working
    Org-File](~/Dropbox/DataSci/BigData/Practicals/04-MongoDB.org)

## Lecture

### OverView

1. Relational Databases
   
   RDBMS (Relational Database Managent Systems) include software such
   as:
   
   - Oracle
   - MS SQL
   - MySQL
   - SQL-Lite
   
   They all implement some version of the *Structured Query Language*
   (SQL).
   
   This unit will be concerned with SQLite, it is a simple standalone
   application with no need for installation.

### SQL

1. Why SQL
   
   SQL is widely implemented language for databases, it scales
   ****up**** to large systems quite well but not out to parallel
   systems easily.

2. Working with SQLite
   
   In org-mode the `ob-sqlite` package ([See this
   example](https://orgmode.org/worg/org-contrib/babel/languages/ob-doc-sqlite.org.html)
   ) can be quite handy, just specify the `:dir /path/to/dir` and
   `:db /path/to/file.sqlite` and sqlite databases can be manipulated
   from within `org-mode` like so:
   
   ```example
   #+begin_src sqlite :dir /tmp/ :db test-sqlite.db
   create table greeting(one varchar(10), two varchar(10));
   insert into greeting values('Hello', 'world!');
   select * from greeting
   #+end_src
   ```
   
   Which can be embedded in `org-mode` like so:
   
   ```sql
   create table greeting(one varchar(10), two varchar(10));
   insert into greeting values('Hello', 'world!');
   select * from greeting
   ```
   
   This however means we don't need to open databases, so if you're
   ever at the shell, you can open a database with
   `.open /path/to/db.sqlite` like this:
   
   ```sql
   .open ./BigData/Practicals/Resources :db testdb.sqlite
   ```
   
   In this unit we have the `test.db.sqlite` file, in `SQL` we could
   show all the tables with `show tables;`, but in `sqlite` we just use
   `.tables` like so:
   
   ```sql
   .tables
   ```
   
   This shows that the only table is a table ambiguously called record,
   we can investiage each row (also referred to as records)
   
   ```sql
   select * from record;
   ```
   
   There are a bunch of examples [here on pages
   9-16](pdf:~/Dropbox/Studies/2020Spring/BigData/BigData/lectures/04-Lecture-Slides.pdf.pdf::11++0.00)
   that we could use for the tutorial questions

### Data Analysis with SQL and Python

1. <span class="done DONE">DONE</span> How to Derive the Correlation
   Coefficient
   
   [This
   Paper](~/Dropbox/Studies/2020Autumn/ThinkingAboutData/correlation.pdf)
   The Correlation coefficient can be interpreted in one of two ways:
   
   - The covariance scaled relative to the $x$ and $y$ variance
     - $\rho = \frac{S_{x, y}}{s_x \cdot s_y}$
   - The rate of change of the line of best fit of the standardised
     data
     - This is equivalent to the rate of change of the line of best
       fit divided by $(\frac{s_y}{s_x})$:
       - $\rho = b \cdot \frac{s_x}{s_y} \quad \iff \quad  \hat{y_i}=bx_i + c$
   
   This can be seen by performing linear regression in *****R*****:
   
   ```r
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
   ```
   
   ```example
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
   ```
   
   ```r
   #+BEGIN_SRC R :cache yes :exports both :results output graphics :file ./test.png
     library("ggplot2")
     cars_std <- as.data.frame(scale(cars))
   
     ggplot(cars_std, aes(x = speed, y = dist)) +
     geom_point() +
     geom_smooth(method = "lm") +
     theme_bw()
   ```
   
   ![](./Attachments/Thinking_About_Data/correlation_lm.png)
   
   This shows that despite noise data can still have a correlation
   coefficient of 1 if the noise is evenly distributed in a way that
   the correlation coefficient can have a rate of change of 1.

# NoSQL (MongoDB)

- [Lecture
  Slides](pdf:~/Dropbox/Studies/2020Spring/BigData/BigData/lectures/05-Lecture-Slides.pdf)
- [Practical 04 - Mongo DB
  PDF](BigData/Practicals/PDF/04-Practical.pdf)
  - [Working
    Org-File](~/Dropbox/DataSci/BigData/Practicals/04-MongoDB.org)

## Lecture

## Practical

### Using ob-MongoDB

1. Org Babel Mongo
   
   Support for MongoDB queries in org-mode blocks, like so:
   
   ```example
   #+BEGIN_SRC mongo :db staff
   db.employees.count({country: "gb"});
   #+END_SRC
   
   #+RESULTS:
   : 15
   ```
   
   1. Installation
      
      If you're hooked up to [MELPA](http://melpa.milkbox.net/):
      
      ```example
      M-x package-refresh-contents
      M-x package-install RET ob-mongo
      ```
      
      Alternatively just grab the single `ob-mongo.el` file and
      install that in your preferred way.
   
   2. Status
      
      Alpha. Safe to use, but feature-poor. It's still better than it
      not existing at all. ;-)
   
   3. Options
      
      Each block supports the following arguments:
      
      | Argument     | Description      | Example                                 | Default |
      | ------------ | ---------------- | --------------------------------------- | ------- |
      | `:db`        | Database name.   | `#+BEGIN_SRC mongo :db staff`           | None.   |
      | `:host`      | Host             | `#+BEGIN_SRC mongo :host localhost`     | None.   |
      | `:port`      | Port             | `#+BEGIN_SRC mongo :port 27018`         | None.   |
      | `:user`      | Username         | `#+BEGIN_SRC mongo :user root`          | None.   |
      | `:password`  | Password         | `#+BEGIN_SRC mongo :password superword` | None.   |
      | `:mongoexec` | Mongo executable | `#+BEGIN_SRC mongo :mongoexec mongo26`  | "mongo" |
      
      All defaults are customizable with
      `M-x customize-group RET ob-mongo`.

## Notes

| SQL Terms/Syntax | MongoDB Terms/Syntax      |
| ---------------- | ------------------------- |
| Database         | Database                  |
| Table            | Collection                |
| Row              | Document                  |
| Column           | Field                     |
| Index            | Index                     |
| Table            | \$lookup or embedded docs |
| Primary key      | Primary key               |
| Transactions     | Transactions              |

# Practical; SQLite

## Export

The code blocks MUST be `begin_src sqlite` in order for the evaluation
to work, however to export to minted they MUST be `begin_src sql` so
I'll just have to use `sed` clean it up.

```bash
sd -s '_src sqlite' '_src sqlite' 04-MongoDB.org
```

```bash
sd -s '_src sqlite' '_src sqliteite'  04-MongoDB.org
```

## Introduction

The database is [./testdb.sqlite](./testdb.sqlite), we can investigate
it like this:

```sql
.tables
```

now that we know that it has a table called record we can get column
names from it using `.schema`:

```sql
.schema record
```

Alternatively the following could be used:

```sql
PRAGMA table_info(record);
```

```sql
select * from record limit 4
```

## SQL Exercises

### Count the Number of Records

```sql
select count(*) from record;
```

### Count the number of students

```sql
select count(*) from
       (select Distinct Sid from record)
       ;
```

### Count the number of female students

```sql
select count(*) from
       (select Distinct Sid from record where Sex is "F")
       ;
```

### Male Students that Fail a Programming Class

Return a list of the male students who failed *Programming Techniques
(300581)*, Display:

- student IDs
- Names
- Marks

The `like` operator could be used:

```sql
select Sname, Sid, Mark from record where Sex is "M" and Mark < 50 and Uname like "%prog%tech%";
```

### Lowest Vs Highest

Display:

- Student IDs
- Names

of students that are:

- Female
- Highest or Lowest mark in OOA

Notice that this seems wrong:

```sql
select Sname, Sid, Uname, max(Mark), min(Mark) from record where Sex is "F" ;
select Sname, Sid, Uname, min(Mark), min(Mark) from record where Sex is "F" ;
```

And that this simply doesn't evaluate:

```sql
select Sid, Sname from record where Sex = "F" and Mark = Max(Mark);
```

Instead you need to wrap the `Max(Mark)` call in a `(select )`
statement.

```sql
select Sid, Sname, Uname, Mark from  record where Sex is "F" and Mark = (select max(Mark) from record);
select Sid, Sname, Uname, Mark from  record where Sex is "F" and Mark in (select max(Mark) from record);
```

|          |                  |                             |       |
| -------- | ---------------- | --------------------------- | ----- |
| 17844194 | Rebecca Morris   | Network Technologies        | 100.0 |
| 17267976 | Erin Phillips    | Network Technologies        | 100.0 |
| 18183025 | Lindsey Mitchell | Systems Analysis and Design | 100.0 |
|          |                  |                             |       |
|          |                  |                             |       |

Now it's simply a matter of getting the minimum as well:

```sql
select max(Mark), Sid, Sname, Uname from  record where Sex is "F" and Uname like "%Object%Oriented%Analysis%" drop column Mark;
select min(Mark), Sid, Sname, Uname from  record where Sex is "F" and Uname like "%Object%Oriented%Analysis%" ;
```

This includes the `Mark`, if we didn't want that then we could wrap the
call in another `select`:

```sql
select Sid, Sname from (select max(Mark), Sid, Sname, Uname from  record where Sex is "F" and Uname like "%Object%Oriented%Analysis%");
select Sid, Sname from (select min(Mark), Sid, Sname, Uname from  record where Sex is "F" and Uname like "%Object%Oriented%Analysis%");
```

### Youngest vs Oldest Student

```sql
select not DOB from record where ;
```

```sql
select Distinct Sid, Sname, min(DOB) from record;
```

### Top Performers

The trick here is to give the average mark column an alias, this way we
can sort by it later:

```sql
select distinct Sid, Sname, Sex, avg(Mark) as av_mark
from record
group by Sid
order by av_mark desc
limit 5
```

## Python and SQL Questions

Test whether or not female students out perform male students in
analysis units via mean and std dev analysis using sql queries.

```sql
select distinct avg(Mark) as Mean_mark,
            avg(mark*mark) as  mean_sq_mark,
            avg(mark)*avg(mark) as mean_mark_sq,
            Utype, Sex
        from record
        where Utype
        like "%Analysis%"
        group by Sex
        limit 10;
```

```sql
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
```

This returns a $\overline{x}_{1} - \overline{x}_{2} = 9$ with
$\sigma \approx 10$, indicating that the difference between male and
female student performance in Analysis units is significant in favour of
Female performance.

We could do this with *Python* as well by saving the results to a `csv`
file:

```sql
.mode csv
.output ./03-sqlite-AnalysisMarks.csv
select Sex, Mark
       from record
       where Utype like "%Analysis%"
```

Now This CSV File can be analysed with *Python*, so first importing the
data:

```python
import pandas as pd
import matplotlib.pyplot as plt

# Import the Data frame
analysis_marks = pd.read_csv("./03-sqlite-AnalysisMarks.csv")
analysis_marks.columns()

# Print the first few lines of the data frame
print(analysis_marks[0:4])
```

```example
M  74.0
0  M  59.0
1  M  72.0
2  M  56.0
3  F  84.0
```

Then finding the standard deviation and mean values:

```python
analysis_marks.melt(variable = Sex)
```

```python
import pandas as pd
import matplotlib.pyplot as plt

# Import the Data frame
analysis_marks = pd.read_csv("./03-sqlite-AnalysisMarks.csv")

# Print the first few lines of the data frame
print(analysis_marks[0:4])
```

```sql
SELECT mark FROM record where Uid=300581;
```

## Quiz

### Inspect the Table

```sql
PRAGMA table_info(record);
```

### Average Enrolments

To find the average number of classes that students are enrolled in,
divide the number of students by the number of duplicates.

```sql
select count(sid) / count(distinct sid) from record;
```

### Birth year of Oldest Student

Don't forget to wrap strings:

```sql
select Distinct Sid, Sname, Sex, min(DOB) as age from record where Sex is 'F'
```

### Birth year of Oldest Female Student

Don't forget to wrap strings:

```sql
select Distinct Sid, Sname, Sex, min(DOB) as age from record where Sex is 'F'
```

### Family name of Youngest Male Student

Don't forget to wrap strings:

```sql
select Distinct Sname, Sex, max(DOB) as age from record where Sex is 'M'
```

### Age Difference between oldest youngest male students

Don't forget to wrap strings:

```sql
select max(DOB) - min(DOB) from record where Sex is 'M';
```

### Lowest Vs Highest

What is the difference between female and male student's highest total
average mark?

Find the Average Marks of all Students

```sql
select Sid, avg(Mark) as av_mark, Sex
       from record
       group by Sid
       limit 5
```

Of those return the highest male and female:

```sql
select max(av_mark) as max_av, Sex
    from (
    select Sid, avg(mark) as av_mark, Sex
        from record
        group by Sid
    )
    group by Sex
    limit 5
```

# Practical; NoSQL; MongoDB

The [./product.json](./product.json),
[innvdoccnt.json](resources/invdoccnt.json) and [world bank
json](file:///home/ryan/Sync/Studies/2020Spring/BigData/resources/world_bank.txt)
Database will be used here.

Install the following software:

- mongodb [1]
- mongodb-tools (for mongoimport) [2]
- mongodb-compass (for sanity checks) [3]
- robo3T [4]

First find out which server mongo is running on by running `mongo` in
the terminal and then running the following in the shell:

```javascript
db.serverCmdLineOpts()
```

that should return some json, this is useful if you are using
`mongo-compass` as discussed in § [\#compass](#compass).

## Importing Data

### Using mongoimport

Import the DB by specifying an arbitrary Database name `arbitraryDBName`
and an arbitrary collection name `arbitraryCollectionName`:

```bash
cd /home/ryan/Dropbox/Studies/2020Spring/BigData/BigData/Assessments/Quizz3/
systemctl start mongodb
# install AUR mongodb and mongotools (probably also robo3T)
mongoimport  /home/ryan/Sync/Studies/2020Spring/BigData/resources/world_bank.txt.json -d arbitraryDBName-c arbitraryCollectionName
mongo
```

Inside MongoDB access the database and list the available collections

```mongo
use arbitraryDBName
show collections
```

### Loading the Database

Say you forgot what you imported it as, to list databases:

```json
db.adminCommand( { listDatabases: 1 } )
```

```json
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
```

use one of the databases by issuing:

```javascript
use arbitraryDBName
```

If we wanted to see the collections in that database:

    show collections

```example
arbitraryCollectionName
```

then to delete (drop) that database you could just do:

    db.dropDatabase()

### Using the Mongo-compass program <span class="tag" tag-name="ATTACH"><span class="smallcaps">ATTACH</span></span>

1. Open mongo-compass

2. Connect to the mongoDB server
   
   1. Probably localhost:27017
      
      1. If you're on SystemD maybe check with
         `sudo systemctl status mongodb`, for me I got a different
         port number.
      
      <img src="_media/org-compass-Server.png" width="400" />

3. Create a new collection
   
   <img src="_media/org-compass-Collection.png" width="400" />

4. Import the JSON File

5. Now from the terminal run `mongo` to open a shell and then
   `use local` to switch to that database.

## Workflow

1. Open Emacs

2. Open Vterm below

3. Use a macro to copy a paragraph and send the results below:
   
   ```elisp
   (fset 'send-below
   (kmacro-lambda-form [?v ?a ?p ?y ?\C-w ?j ?p ?\C-o ?\C-o ?\C-o ?\C-w ?k] 0 "%d"))
   (global-set-key (kbd "C-c m") 'send-below)
   ```

4. Copy and paste the results all in place like fucking magic.

## List Movies

First see if you can list everything, if you created product underneath
local, you'll need to do something like this:

```javascript
use local
db.product.find()
```

In the case of [./product.json](./product.json), the following should
return some output.

```javascript
db.product.find({'Type': 'Movie'})
```

```json
{ "_id" : ObjectId("551668dbeb88341eb801f2d2"), "Classification" : "PG-13", "Title" : "Inception", "Price" : { "Buy" : 9.99, "Rent" : 2.99 }, "Director" : "Christopher Nolan", "Cast" : [ "Leonardo DiCaprio", "Joseph Gordon-Levitt" ], "Year" : "2010", "Genre" : [ "Drama", "Action", "Science Fiction" ], "Type" : "Movie", "Length (min)" : 148 }
{ "_id" : ObjectId("551668dbeb88341eb801f2db"), "Classification" : "R", "Title" : "Superbad", "Price" : { "Buy" : 9.99, "Rent" : 2.99 }, "Director" : "Greg Mottola", "Cast" : [ "Jonah Hill", "Michael Cera" ], "Year" : "2007", "Genre" : "Comedy", "Type" : "Movie", "Length (min)" : 113 }
{ "_id" : ObjectId("551668dbeb88341eb801f2dc"), "Title" : "Dracula", "Price" : { "Buy" : 9.99, "Rent" : 3.99 }, "Director" : "Tod Browning", "Cast" : [ "Bela Lugosi", "Helen Chandler" ], "Year" : "1931", "Genre" : [ "Classics", "Horror" ], "Type" : "Movie", "Length (min)" : 75 }

...
...
...
```

To query all the text, something like this might be useful:

```bash
mongo --eval 'db.product.find()' local | fzf
```

To return All Movies that contain, for example, Morgan Freeman, Compass
can be inspected to reveal the `cast` field and then the following can
be used:

```javascript
db.product.find({'Cast': 'Morgan Freeman'})
```

```json
{ "_id" : ObjectId("551668dbeb88341eb801f2de"), "Title" : "The Shawshank Redemption" }
{ "_id" : ObjectId("551668dbeb88341eb801f2e7"), "Title" : "The Dark Knight" }
> db.product.find({'Cast': 'Morgan Freeman'})
{ "_id" : ObjectId("551668dbeb88341eb801f2de"), "Classification" : "R", "Title" : "The Shawshank Redemption", "Price" : { "Buy" : 9.99, "Rent" : 3.99 }, "Director" : "Frank Darabont", "Cast" : [ "Tim Robbins", "Morgan Freeman" ], "Year" : "1994", "Genre" : "Drama", "Type" : "Movie", "Length (min)" : 142 }
{ "_id" : ObjectId("551668dbeb88341eb801f2e7"), "Classification" : "PG-13", "Title" : "The Dark Knight", "Price" : { "Buy" : 12.99, "Rent" : 3.99 }, "Director" : "Christopher Nolan", "Cast" : [ "Christian Bale", "Heath Ledger", "Morgan Freeman" ], "Year" : "2008", "Genre" : [ "Drama", "Action", "Science Fiction" ], "Type" : "Movie", "Length (min)" : 152 }
>
```

This however returns too much information, instead we can use
[projection](https://docs.mongodb.com/manual/tutorial/project-fields-from-query-results/)
to filter the results:

```javascript
db.product.find({'Cast': 'Morgan Freeman'}, {Title: 1})
```

```json
{ "_id" : ObjectId("551668dbeb88341eb801f2de"), "Title" : "The Shawshank Redemption" }
{ "_id" : ObjectId("551668dbeb88341eb801f2e7"), "Title" : "The Dark Knight" }
```

## Find Songs

To Find the Songs in the Database the following can be used:

```javascript
db.product.find({'Type': 'Song'})
```

This returns far too many results, so instead projection can be used:

```javascript
db.product.find({'Type': 'Song'}, {'Title': 1, })
```

```json
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
```

In order to filter by Genre we could just add that to the `find` field,
however because we want any type of rock, we'll need to use the
`.*Rock.*` regex, this has an odd syntax in *MongoDB* where a regex term
is denoted like this: `{ $regex: /.*Rock.*/ }`, so putting that
together:

```javascript
db.product.find({'Type': 'Song', 'Genre': { $regex: /.*Rock.*/ }}, {'Title': 1, 'Artist': 1, 'Album': 1})
```

```json
{ "_id" : ObjectId("551668dbeb88341eb801f2d5"), "Album" : { "Certification" : "43xPlatinium", "Title" : "Thriller" }, "Artist" : "Michael Jackson", "Title" : "Billie Jean" }
{ "_id" : ObjectId("551668dbeb88341eb801f2d6"), "Album" : { "Certification" : "23xPlatinium", "Title" : "The Dark Side of the Moon" }, "Artist" : "Pink Floyd", "Title" : "Speak to Me" }
{ "_id" : ObjectId("551668dbeb88341eb801f2d9"), "Album" : { "Certification" : "26xPlatinium", "Title" : "Back in Black" }, "Artist" : "AC/DC", "Title" : "Back in Black" }
{ "_id" : ObjectId("551668dbeb88341eb801f2e4"), "Album" : { "Certification" : "17xPlatinium", "Title" : "Nevermind" }, "Artist" : "Nirvana", "Title" : "Smells Like Teen Spirit" }
{ "_id" : ObjectId("551668dbeb88341eb801f2e6"), "Album" : { "Certification" : "22xPlatinium", "Title" : "1" }, "Artist" : "The Beatles", "Title" : "Yesterday" }
```

To sort thhe results, the `.sort()` method can be tacked on the end like
so:

```javascript
db.product.find({'Type': 'Song', 'Genre': { $regex: /.*Rock.*/ }}, {'Title': 1, 'Artist': 1, 'Album': 1}).sort({ 'ReleaseDate': -1 })
```

```json
{ "_id" : ObjectId("551668dbeb88341eb801f2e6"), "Album" : { "Certification" : "22xPlatinium", "Title" : "1" }, "Artist" : "The Beatles", "Title" : "Yesterday" }
{ "_id" : ObjectId("551668dbeb88341eb801f2e4"), "Album" : { "Certification" : "17xPlatinium", "Title" : "Nevermind" }, "Artist" : "Nirvana", "Title" : "Smells Like Teen Spirit" }
{ "_id" : ObjectId("551668dbeb88341eb801f2d5"), "Album" : { "Certification" : "43xPlatinium", "Title" : "Thriller" }, "Artist" : "Michael Jackson", "Title" : "Billie Jean" }
{ "_id" : ObjectId("551668dbeb88341eb801f2d9"), "Album" : { "Certification" : "26xPlatinium", "Title" : "Back in Black" }, "Artist" : "AC/DC", "Title" : "Back in Black" }
{ "_id" : ObjectId("551668dbeb88341eb801f2d6"), "Album" : { "Certification" : "23xPlatinium", "Title" : "The Dark Side of the Moon" }, "Artist" : "Pink Floyd", "Title" : "Speak to Me" }
>
```

## Calculate the Average Price of Books

To find all books with more than 500 pages, the
[And](https://docs.mongodb.com/manual/tutorial/query-documents/)
operator can be used inside `find`, this amounts to just using a `,`.

Operators are, much like regex, a little odd, they require cages and `$`
prefixes.

```javascript
db.product.find( { 'Type': 'Book', Pages: { $gt: 500 } } )
```

```json
{ "_id" : ObjectId("551668dbeb88341eb801f2d0"), "Publisher" : "Prentice Hall", "ISBN" : "132126958", "Author" : "Andrew Tanenbaum", "Price" : 129.79, "Title" : "Computer Networks", "Shipping" : { "Weight (lb)" : 2.9, "Dimension (in)" : { "Width" : 6.6, "Depth" : 1.5, "Height" : 9.2 } }, "Edition" : "5", "Year" : "2010", "Type" : "Book", "Pages" : 960 }
{ "_id" : ObjectId("551668dbeb88341eb801f2d4"), "Publisher" : "Pearson", "ISBN" : "032182573X", "Author" : "Peter Tanenbaum", "Price" : 153.16, "Title" : "Excursions in Modern Mathematics", "Shipping" : { "Weight (lb)" : 3.2, "Dimension (in)" : { "Width" : 8.8, "Depth" : 1.1, "Height" : 10.9 } }, "Edition" : "8", "Year" : "2012", "Type" : "Book", "Pages" : 608 }
{ "_id" : ObjectId("551668dbeb88341eb801f2e0"), "Publisher" : "Prentice Hall", "ISBN" : "013359162X", "Author" : "Andrew Tanenbaum, Herbert Bos", "Price" : 153.09, "Title" : "Modern Operating Systems", "Shipping" : { "Weight (lb)" : NaN, "Dimension (in)" : { "Width" : 7.1, "Depth" : 1.6, "Height" : 9.1 } }, "Edition" : "4", "Year" : "2014", "Type" : "Book", "Pages" : 1136 }
{ "_id" : ObjectId("551668dbeb88341eb801f2e3"), "Publisher" : "Addison-Wesley", "ISBN" : "321349806", "Author" : "Ken Arnold, James Gosling", "Price" : 53.69, "Title" : "The Java Programming Language", "Shipping" : { "Weight (lb)" : NaN, "Dimension (in)" : { "Width" : 7.4, "Depth" : 1.2, "Height" : 9.2 } }, "Edition" : "4", "Year" : "2005", "Type" : "Book", "Pages" : 928 }
{ "_id" : ObjectId("551668dbeb88341eb801f2ea"), "Publisher" : "Addison Wesley", "ISBN" : "321500245", "Author" : "Mario Triola", "Price" : 28.99, "Title" : "Elementary Statistics", "Shipping" : { "Weight (lb)" : 4.7, "Dimension (in)" : { "Width" : 8.5, "Depth" : 1.4, "Height" : 11.2 } }, "Edition" : "11", "Year" : "2009", "Type" : "Book", "Pages" : 896 }
> db.product.find( { 'Type': 'Book', Pages: { $gt: 500 } } )
```

To Average the price first use
[projection](https://docs.mongodb.com/manual/tutorial/project-fields-from-query-results/)
to return only the price values:

```javascript
db.product.find( { 'Type': 'Book', Pages: { $gt: 100 } }, { 'Price': 1} )
```

```json
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
```

Next drop any results with missing values by [not equal
(`$ne`)](https://docs.mongodb.com/manual/reference/operator/query/)
operator:

```javascript
db.product.find( { 'Type': 'Book', Pages: { $gt: 100 }, Price: { $ne: NaN } }, { 'Price': 1} )
```

```json
{ "_id" : ObjectId("551668dbeb88341eb801f2d0"), "Price" : 129.79 }
{ "_id" : ObjectId("551668dbeb88341eb801f2d1"), "Price" : 52.89 }
{ "_id" : ObjectId("551668dbeb88341eb801f2d4"), "Price" : 153.16 }
{ "_id" : ObjectId("551668dbeb88341eb801f2e0"), "Price" : 153.09 }
{ "_id" : ObjectId("551668dbeb88341eb801f2e1"), "Price" : 37.99 }
{ "_id" : ObjectId("551668dbeb88341eb801f2e3"), "Price" : 53.69 }
{ "_id" : ObjectId("551668dbeb88341eb801f2ea"), "Price" : 28.99 }
{ "_id" : ObjectId("551668dbeb88341eb801f2eb"), "Price" : 27.68 }
```

To do this we'll create a variable, note however that `find` is such
that [any variable returned is a temporary
cursor](https://stackoverflow.com/a/21285674/12843551), which means that
after the variable is called again it is cleared:

```javascript
var price = db.product.find( { 'Type': 'Book', Pages: { $gt: 100 }, Price: { $ne: NaN } }, { 'Price': 1} )
price
```

```json
{ "_id" : ObjectId("551668dbeb88341eb801f2d0"), "Price" : 129.79 }
{ "_id" : ObjectId("551668dbeb88341eb801f2d1"), "Price" : 52.89 }
{ "_id" : ObjectId("551668dbeb88341eb801f2d4"), "Price" : 153.16 }
{ "_id" : ObjectId("551668dbeb88341eb801f2e0"), "Price" : 153.09 }
{ "_id" : ObjectId("551668dbeb88341eb801f2e1"), "Price" : 37.99 }
{ "_id" : ObjectId("551668dbeb88341eb801f2e3"), "Price" : 53.69 }
{ "_id" : ObjectId("551668dbeb88341eb801f2ea"), "Price" : 28.99 }
{ "_id" : ObjectId("551668dbeb88341eb801f2eb"), "Price" : 27.68 }
```

but then calling `price` again would return no output:

```javascript
price
```

```json

```

To overcome this make the result an array first:

```javascript
var price = db.product.find( { 'Type': 'Book', Pages: { $gt: 500 }, Price: { $ne: NaN } }, { 'Price': 1} ).toArray()
price
```

```json
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
```

### Aggregate

Unfoututately we can't just grab the results and average, we need to use
the aggregate method with `$group` and `$match` functions.

So for example, to average all the prices period, we could do something
like this:

```javascript
db.product.aggregate([
    {$group: {_id:null, "AveragePrice": {$avg:"$Price"} } }
]);
```

```json
{ "_id" : null, "AveragePrice" : NaN }
```

This returns `NaN` because some of the prices were missing, we'll fix
this later.

The `$_id` variable denotes grouping, in this case we just want to
average everything so we set it to `null`.

In order to aggregate the matches to our `.find()`, the values can be
put inside a `match` group like so:

```javascript
db.product.aggregate([
    { "$match": { 'Type': 'Book', Pages: { $gt: 500 }, Price: { $ne: NaN } } },
    {$group: {_id:null, "AveragePrice": {$avg:"$Price"} } }
]);
```

This will then return:

```json
{ "_id" : null, "AveragePrice" : 103.744 }
```

So the Average price of books with more than 500 pages is \\\$103.75

## Quizz 3

### Inverse Word Count

Import the DB:

```bash
cd /home/ryan/Dropbox/Studies/2020Spring/BigData/BigData/Assessments/Quizz3/
systemctl start mongodb
# install AUR mongodb and mongotools (probably also robo3T)
mongoimport invdoccnt.json -d testdb -c invwc  --jsonArray
mongo
```

Inside MongoDB access the database and list the available collections

```mongo
use testdb
show collections
```

the `invwc` collection is available so use find to list that:

```mongo
db.invwc.find({})
```

Then to find the maximum count do one of these:

```mongo
// db.getCollection('invwc').find()
// db.collection.find().sort({word:-1}).limit(1)
db.invwc.find().sort({count:-1}).limit(9)
```

or using the `aggregate` approach (which is slower):

### World Bank

Load the data base

```bash
cd /home/ryan/Dropbox/Studies/2020Spring/BigData/BigData/Assessments/Quizz3/
systemctl start mongodb
# install AUR mongodb and mongotools (probably also robo3T)
mongoimport word_bank.json -d testdb -c invwc  --jsonArray
mongo
```

1. Using Aggregate
   
   The general form for aggregate is:
   
   ```mongo
   db.wb.aggregate([
   
   {$match: {your matching conditions}},
   
   {$group:{group expression and functions}},
   
   {$sort: {sorting expression}}
   
   ])
   ```

2. Number of Chinese Projects
   
   Load the
   
   show the keys in a document of the collection: [5]
   
   ```mongo
   doc=db.bank.findOne();
   for (key in doc) print(key);
   ```
   
   This produces far to much output though so just use python
   
   <div>
   
   <span class="label">Key Values output by using *Python* and
   `pymongo`</span>
   
   ```python
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
   ```
   
   </div>
   
   ```example
   {'impagency', 'theme_namecode', 'themecode', 'country_namecode', 'sector', 'source', 'mjsector_namecode', '_id', 'sector4', 'mjtheme_namecode', 'sector2', 'projectstatusdisplay', 'countryname', 'project_abstract', 'sectorcode', 'approvalfy', 'sector_namecode', 'grantamt', 'closingdate', 'totalcommamt', 'productlinetype', 'mjthemecode', 'countryshortname', 'lendinginstr', 'id', 'mjtheme', 'envassesmentcategorycode', 'url', 'sector3', 'majorsector_percent', 'projectdocs', 'ibrdcommamt', 'supplementprojectflg', 'docty', 'project_name', 'projectfinancialtype', 'theme1', 'lendinginstrtype', 'borrower', 'prodline', 'prodlinetext', 'boardapprovaldate', 'idacommamt', 'totalamt', 'countrycode', 'regionname', 'sector1', 'status', 'lendprojectcost', 'board_approval_month'}
   ```
   
   This can be combined with:
   
   ```bash
   # Fucking Life saver
   mongo --eval 'db.bank.find()' worldbank | fzf
   ```
   
   This provides us with `boardapprovaldate` so we'll use that to get
   the year and we'll use `countryname` to get the country name. To
   find out what the country name is listed as use `distinct`:
   
   ```mongo
   db.bank.distinct('countryname')
   ```
   
   ```example
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
   ```
   
   This provides us with the *People's Republic of China*, this can
   also be used with regex.
   
   To find the number of projects in 2013, just use `find()` and
   `count()` like so:
   
   ```mongo
   db.bank.find({
    countryname:       { $regex: /.*China.*/},
    approvalfy: { $regex: /.*2013.*/ }
    }
   ).count()
   ```
   
   If you're talking about financial year though
   
   ```mongo
   db.bank.find({
    countryname:       { $regex: /.*China.*/},
    approvalfy: { $regex: /.*2014.*/ }
    }
   ).count()
   ```
   
   1. Projects worth
      
      Now if we look at the output in <span class="spurious-link"
      target="KeyVals">*KeyVals*</span> `lendprojectcost` looks like a
      good contender, issue is though that the output like it is can't
      be used.
      
      So instead use `aggregate` to make it all work, it will be
      possible to just throw the contents from the previous call to
      `find` in there, so using emacs is justified.
      
      Observe the use of `"$key"` when using aggregate:
      
      ```mongo
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
      ```
   
   2. Projects in 2014
      
      The number of projects in 2014 for south east asia. Using the
      *Python* script in listing <span class="spurious-link"
      target="KeyVals">*KeyVals*</span> with
      `./printKeys.py | sed 's/,/\n/g' | fzf` makes it easy to find
      `regionname`.
      
      First list all regions:
      
      ```mongo
      db.bank.distinct('regionname')
      ```
      
      This gives us the `South Asia` value to use with `.find()`:
      
      ```mongo
      db.bank.find({regionname: "South Asia", approvalfy: "2014"}).count()
      ```
      
      The total cost of these projects:
      
      ```mongo
      db.bank.aggregate([
          {$match: {regionname: "South Asia", approvalfy: "2014"}}, // Find the Region Names
          {$group: {_id:null, "Total_Cost": { $sum: "$lendprojectcost"} }}, // only have ID and Total Cost
          {$sort: {"Total_Cost": -1}} // i.e. by descending
      ])
      ```
      
      How much is that per project (i.e. the average):
      
      ```mongo
      db.bank.aggregate([
          {$match: {regionname: "South Asia", approvalfy: "2014"}},
          {$group: {_id:null, "Average": { $avg: "$lendprojectcost"}}},
          {$sort: {"Average": -1}}
      ])
      ```
      
      If the regions were ranked, where in that rank would South Asia
      be, to return only some keys use `find({}, {keyname: 1})`:
      
      ```mongo
      //db.bank.find({}, {"regionname": 1, "lendprojectcost": 1})
      // This doesn't work because it doesn't add them
      db.bank.find({}, {"regionname": 1, "lendprojectcost": 1}).sort({"lendprojectcost":-1}).limit(9)
      ```
      
      To list them in order, the `id` for the `$group` must be given
      as `regionname`:
      
      ```mongo
      db.bank.aggregate([
          {$match: {approvalfy: "2014", lendprojectcost: { $gt: 0}}}, // Negative Values Haven't bee Considered
          { $group: { _id: "$regionname", "Total_Cost": { $sum: "$lendprojectcost"} }}, //Group by Region Name, give back Total Cost
          {$sort: {"Total_Cost": -1}} // i.e. by descending
      ])
      ```
      
      How many projects did Eas Asia have provided:
      
      ```mongo
      db.bank.find({regionname: "East Asia and Pacific", approvalfy: "2014"}).count()
      ```
      
      To return the number of projects for each group (i.e. the number
      of documents per each group), use the somewhat tricky
      `{$sum: 1}`, and change the order:
      
      ```mongo
      db.bank.aggregate([
          {$match: {approvalfy: "2014", lendprojectcost: { $gt: 0}}}, // Negative Values Haven't bee Considered
          { $group: { _id: "$regionname", "No_Projects": { $sum: 1 }, "Total_Cost": { $sum: "$lendprojectcost"} }}, //Group by Region Name, give back Total Cost
          {$sort: {"No_Projects": -1}} // i.e. by descending
      ])
      ```
      
      Africa (region) had the most number of projects, which country
      of Africa had the most:
      
      ```mongo
      db.bank.aggregate([
      {$match: {regionname: "Africa", approvalfy: "2014"}},
      {$group: {_id:"$countryshortname", "Total_value": {$sum: "$lendprojectcost"}, "No_Projects": {$sum: 1}}},
      {$sort: {"No_Projects": -1}}
          ])
      ```
      
      Africa the country had the most, the largest project being
      worth:
      
      ```mongo
      db.bank.aggregate([
      {$match: {regionname: "Africa", approvalfy: "2014"}},
      {$group: {_id:"$lendprojectcost"}},
      {$sort: {"_id": -1}}
          ])
      ```
      
      Observe the use of the `$first` accumulator/function that needs
      be used to return a raw feature:
      
      ```mongo
      db.bank.aggregate([
      {$match: {regionname: "Africa", approvalfy: "2014"}},
      {$group: {       _id:"$_id",
                    "cost": { $first: "$lendprojectcost"},
                 "country": { $first: "$countryshortname"}
                 }
                                                          },
      
      {$sort: {"cost": -1}}
          ])
      ```
      
      ```mongo
      db.bank.aggregate([
      {$match: {regionname: "Africa", approvalfy: "2014"}},
      {$group: {       _id:"$_id",
                    "cost": { $first: "$lendprojectcost"},
                 "country": { $first: "$countryshortname"}
                 }
                                                          },
      
      {$sort: {"cost": -1}}
          ])
      ```
      
      ```example
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
      ```
      
      ```mongo
      db.wb.aggregate([
      
      {$match: {your matching conditions}},
      
      {$group:{group expression and functions}},
      
      {$sort: {sorting expression}}
      
      ])
      ```

# Predictive Modelling

It appears that in the past the training data splitting libraries were
contained in:

> `sklearn.cross_validation`

It seems they are now in: [6]

    ~from sklearn.model_selection ~

- Using SVM in python
  - p\. 21
    - lecture slides 09
- Using Trees in *Python*
  - Lecture Slides 10
    - P. 11
- Using Random Forest

## Classification

### SVM

```python
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
```

### Trees

See figure ref:tree<sub>moonclass</sub>.

<figure>
<img src="_media/Tree_Classification_Moon.png" title="tree_moon_class" width="400" alt="Moon Data With a Tree Classification" /><figcaption aria-hidden="true">Moon Data With a Tree Classification</figcaption>
</figure>

In descending order, typically, the fastest classification algorithms
are: [7]

1. Decision Tree
2. Random Forrest
3. Linear SVM
4. Non-Linear SVM

With respect to choosing a classification Model:

- If the data is non linear and model accuracy is paramount:
  - Non Linear SVM
    - This will Require a lot of computing power though
- If there is really big data, whith a lot of features and speed is
  the priority
  - Linear SVM
- If the data is non-linear and an interpretable model is required
  - Random Forest.

### Classification Score

To see what `score` actually measures, perform `help(clf.score)`, it
seems Classification in SciKitLearn is usually Accuracy: [8]

$$
\mathrm{ACC} = \frac{\mathrm{TP} + \mathrm{TN}}{\mathrm{P} + \mathrm{N}}
$$

### Decision Tree

Adapted from p. 280 of 344 of [Lecture
Slides](BigData/00_Slides_BigData.pdf)

```python
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
```

### Random Forrest

Adapted from p. 280 of 344 of [Lecture
Slides](Material/lectures/00_Slides_BigData.pdf)

```python
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
```

## Regression

Implementing Linear Regression in Python

First let's get some data with ***R***:

```r
#!/usr/bin/R
write.csv(cars, file = "cars.csv")
list.files()
```

### Linear Regression (Ordinary Least Squares)

Observe:

- it is necessary to load `matplotlib.pyplot` not just `matplotlib`,
  the `pyplot` submodule will not not be pulled in and must be pulled
  in explicitly.
- `x` is a `(20,)` numpy array, it is like a vector, the output of
  `train_test_split` outputs what it got in. The `SciKit` package
  expects matrices (rows as observations, columns as factors), by
  calling `x.reshape(-1, 1)` the numpy array can be reshaped to be a
  $n\times 1$ matrix of size `(n, 1)`.

```python
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
```

1. Plotting Linear Regression <span class="tag" tag-name="plot"><span
   class="smallcaps">plot</span></span>
   
   1. MatPlotlib
      
      A plot of this model can be produced with MatPlotLib: <span
      id="plt"></span>
      
      ```python
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
      ```
      
      ![](_media/cars.png)
      
      - the `scatter` method adds points and the `plot` method adds
        a line.
      - Observe also that the `pyplot` submodule was loaded in.
   
   2. Plotnine GGPlot
      
      Or my Using Plotnine:
      
      ```python
      data = {'distance': x_test,
              'speed': y_test,
              'speed_model': y_pred
      }
      df = pd.DataFrame(data, columns = ['distance', 'speed', 'speed_model'])
      
      print(df.iloc[1:6,:])
      ```
      
      ```example
         distance  speed  speed_model
      1      20.0   48.0    56.286565
      2      17.0   50.0    46.314626
      3      24.0   70.0    69.582483
      4      13.0   34.0    33.018707
      5      24.0  120.0    69.582483
      ```
      
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
      
      <img src="./_media/cars_ggplotnine.png" width="400" />
      
      Ideally however the modelled data and the observed data should
      both be in the speed column but with a different label (say
      model/obs), this can be acheived by using `pandas.wide_to_long`:
      
      First melt the data down:
      
      ```python
      # Melt the data down
      df_melt = pd.melt(df, id_vars = ['distance'], value_vars = ['speed', 'speed_model'], var_name = "data_type", value_name = "speed")
      print(df_melt.head(3))
      ```
      
      ```example
         distance data_type  speed
      0      12.0     speed   24.0
      1      20.0     speed   48.0
      2      17.0     speed   50.0
      ```
      
      Then Rename the Factors
      
          # Melt the data down
          df_melt = df_melt.replace(to_replace=['speed','speed_model'], value=['observed', 'model'])
          print(df_melt.head(3))
      
      ```example
         distance data_type  speed
      0      12.0  observed   24.0
      1      20.0  observed   48.0
      2      17.0  observed   50.0
      ```
      
      Inspect the variable names and the data:
      
          df_melt.head()
          df_melt.columns
      
      ```example
         distance data_type  speed
      0      12.0  observed   24.0
      1      20.0  observed   48.0
      2      17.0  observed   50.0
      3      24.0  observed   70.0
      4      13.0  observed   34.0
      
      >>> df_melt.columns
      
      Index(['distance', 'data_type', 'speed'], dtype='object')
      ```
      
      Now the Data Can be plotted, but notice in `geom_smooth` we only
      plotted the line for the 'observed'data:
      
      ```python
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
      ```
      
      <img src="_media/cars_ggplotnine_melt.png" width="400" />

### Sparse Linear Regression

When given many variables in a regression problem, where not all
variables will be useful, a *variable selection* problem presents
itself.

Variable Selection is **NP** hard with $O(2^{N})$ complexity, to address
it:

- Greedy Selection
  
  - Forward / Backward Selection [9]

- Sparse Linear Regression
  
  - LASSO and Ridge
  - Elastic Net
  - Theres plenty of them.
1. LASSO
   
   The *Least Absolute Shrinkage and Selection Operator*, given the
   model:
   
   find the vector $\mathbf{b} = \left\langle b1, b2, b3, ..., b_p
   \right\rangle $
   
   such that:
   
   Implementing lasso regression in *Python*:
   
   ```python
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
   ```
   
   ```example
   >>> print(selected_features)
   ['bmi', 's5']
   ```
   
   The tricky part with *sparse linear regressin* is choosing the
   *tuning parameter* also known as the *regularisation parameter*
   denoted by $\lambda$ (and ocassionaly by $\alpha$ and $\beta$), to
   choose this the following are used:
   
   - Path Algorithms
   
   - Least Angle Regression (LARS)
   1. Least Angle Regression LARS
      
      ```python
      import numpy as np
      import matplotlib.pyplot as plt
      from sklearn import linear_model
      from sklearn impoirt datasets
      diabetes = datasets.load_diabetes()
      varnames = diabetes.feature_names
      ```
      
      # Assign the Variables --------------------------------------
      
        X = diabetes.data  # These are  numpy arrays
        y = diabetes.target

        # Perform the LARS -------------------------------------------
        alphas, index, coefs = linear_model.lars_path(X, y, method = 'lasso', verbose = True)
    
        xx = np.sum(np.abs(coefs.T), axis = 1)   # x /= 5 means x = x/5
        xx = xx/xx[-1] # Scale to 1
        ```
    
        To plot this:
    
        ``` python
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
        ```
    
        ![](_media/lars_plot.png)

# Exam Preparation

## Plot a CSV

### Chosen approach

```python
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
```

### Import a CSV

1. Using lists
   
   The real trick here is using
   [`reshape`](~/Sync/Notes/Org/roam/20201103164705-reshaping_arrays_using_numpy.org)
   to fix the CSV:
   
   ```python
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
   ```

2. Using Pandas
   
   You essentially want to follow the approach taken in § [plt](#plt).
   
   First import the CSV file as a `pandas`, specify the `header`
   accordingly:
   
   ```python
   import pandas as pd
   
   df_x = pd.read_csv(r'./300580_new.csv', header = None)
   df_y = pd.read_csv(r'./300581_new.csv', header = None)
   ```
   
   Print the contents by creating a pandas data frame:
   
   ```python
   print(df_x)
   print(df_y)
   data = pd.concat([df_x, df_y], axis = 1)
   data.columns = ["x", "y"]
   print(data)
   ```
   
   ```example
   >>> pd.concat([df_x, df_y], axis = 1) # NOTE
          0     0
   0   88.0  79.0
   1   76.0  62.0
   2   90.0  76.0
   3   96.0  94.0
   ```
   
   To extract this data again we can use the `iloc` method, similar to
   ***R*** but with a `:` character:
   
   ```python
   df_x = data.iloc[:,1]
   df_y = data.iloc[:,2]
   ```

### Plot the Data

1. Pandas Plot Method
   
   Pandas can call matplotlib directly like so:
   
   ```python
   data.plot.scatterplot(x = 'x', y = 'y')
   ```
   
   <img src="_media/matplotlib_pyplot_scatterplot_example.png" width="400" />

2. MatPlotLib
   
   The advantage to using matplotlib is that it can be used on lists
   and pandas, so this is convenient if the list method was used.
   
   To plot this directly with matplotlib (as in [plt](#plt)):
   
   ```python
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
   ```
   
   <img src="_media/matplotlib_pyplot_scatterplot_example.png" width="400" />

3. Plotnine <span class="tag" tag-name="plotnine"><span
   class="smallcaps">plotnine</span></span>
   
   This could also be done in `plotnine` for the sake of ggplot syntax:
   
   ```python
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
   ```

## SQL

The file is located at `./Exam/Sample/testdb.sqlite` so if you wanted to
run this in the terminal:

```bash
sqlite3
```

then inside sql:

```bash
.open "/home/ryan/Sync/Studies/2020Spring/BigData/Exam/Sample/testdb.sqlite"
```

First we need to find out the tables contained in the database:

```sql
.tables
```

```example
record
```

now that we know that it has a table called record we can get column
names from it using `.schema`:

```sql
.schema record
```

|                       |
| --------------------- |
| CREATE TABLE record ( |
| \[Sid\] INTEGER       |
| \[Sname\] TEXT        |
| \[Sex\] TEXT          |
| \[DOB\] TEXT          |
| \[Uid\] INTEGER       |
| \[Mark\] REAL         |
| \[Uname\] TEXT        |
| \[Utype\] TEXT        |
| );                    |

### (1) How many students are in the database?

```sql
.schema record
```

```sql
select count(*) from
       (select Distinct Sid from record)
       ;
```

```example
1000
```

1. How many female students are in the database?
   
   First we need to inspect the first couple values of the `Sex`
   column:
   
   ```sql
   select Sid, Sex, Sname, avg(Mark) as av_mark
          from record
          group by Sid
          limit 9
          ;
   ```
   
   |          |     |                     |                  |
   | -------- | --- | ------------------- | ---------------- |
   | 17002055 | F   | Kimberly Thomas     | 75.8             |
   | 17003783 | M   | James Richardson    | 77.0             |
   | 17004931 | F   | Melanie Knight      | 72.8             |
   | 17006515 | F   | Elizabeth Robertson | 73.5             |
   | 17007137 | F   | Erin Murray         | 75.2             |
   | 17009377 | M   | Bryan Thomson       | 71.8             |
   | 17011808 | F   | Megan Butler        | 72.6666666666667 |
   | 17012981 | F   | Latoya Lee          | 76.0             |
   | 17013056 | M   | Michael Thompson    | 76.8             |
   
   This indicates that gender is stored as "M" or "F", so the number of
   female students is given by:
   
   - Counting the number of observations, where:
     - Sex is "F"
     - Sid is a `Distinct` value
   
   This can be implemented like so:
   
   ```sql
   select count(*) from
          (select Distinct Sid from record where Sex is "F")
          ;
   ```
   
   ```example
   500
   ```

### (2) List the Unique Unit IDS in the Database

The ~~~~unique~~~~ Distinct unit IDs in the database can be listed like
so:

```sql
select Uid
       from record
       group by Uid
       ;
```

|        |
| ------ |
| 300144 |
| 300580 |
| 300581 |
| 300585 |
| 300695 |
| 301046 |

The number of Distinct Uid can be returned like so:

```sql
select count(Distinct Uid)
       from record
       ;
```

```example
6
```

The number of different students for each unit, in this data base,
rounded to 2dp:

```sql
select Uid, count(*), round(avg(Mark), 2) as av_mark
       from (select Uid, Mark from record)
       group by Uid
       ;
```

|        |      |       |
| ------ | ---- | ----- |
| 300144 | 1000 | 70.05 |
| 300580 | 1000 | 80.18 |
| 300581 | 1000 | 70.01 |
| 300585 | 1000 | 79.88 |
| 300695 | 504  | 75.45 |
| 301046 | 502  | 74.67 |

### 3. Which Unit has the lowest Mark in the database?

The minimum marks across the units are given by:

```sql
select Min(Mark) as min, Uid, count(*), round(avg(Mark), 2) as av_mark, Uname
       from (select Uid, Mark, Uname from record)
       group by Uid
       order by Min asc /* or desc */
       ;
```

|      |        |      |       |                             |
| ---- | ------ | ---- | ----- | --------------------------- |
| 32.0 | 300695 | 504  | 75.45 | Network Technologies        |
| 34.0 | 300581 | 1000 | 70.01 | Programming Techniques      |
| 41.0 | 300144 | 1000 | 70.05 | Object Oriented Analysis    |
| 41.0 | 300580 | 1000 | 80.18 | Programming Fundamentals    |
| 43.0 | 301046 | 502  | 74.67 | Big Data                    |
| 45.0 | 300585 | 1000 | 79.88 | Systems Analysis and Design |

Only the minimum value result can be returned thusly:

```sql
select Min(Mark) as min, Uid, Uname
       from record ;
```

|      |        |                      |
| ---- | ------ | -------------------- |
| 32.0 | 300695 | Network Technologies |

### 4. Which unit has the lowest average mark in the database?

So first we need to list the average marks and unit id values:

```sql
select Uid, avg(Mark) as av_mark, Uname
       from (select Uid, Mark, Uname from record)
       group by Uid
       ;
```

|        |                  |                             |
| ------ | ---------------- | --------------------------- |
| 300144 | 70.054           | Object Oriented Analysis    |
| 300580 | 80.177           | Programming Fundamentals    |
| 300581 | 70.011           | Programming Techniques      |
| 300585 | 79.881           | Systems Analysis and Design |
| 300695 | 75.4523809523809 | Network Technologies        |
| 301046 | 74.6713147410359 | Big Data                    |

Now from this we need to select the minimum `av_mark` value, observe
that no `;` is used inside the brackets corresponding to `from`, this is
an easy mistake to make:

```sql
select Min(av_mark) as min_av, Uid, Uname
    from (select Uid, Uname, avg(Mark) as av_mark
        from (select Uid, Uname, Mark from record) group by Uid)
       ;
```

|        |        |                        |
| ------ | ------ | ---------------------- |
| 70.011 | 300581 | Programming Techniques |

Hence the minimum mark is 70.011 corresponding to 300581

### Which is the hardest unit

*Programming Techniques* has the lowest average mark of 70.054,
suggesting that for the majority of students it is more difficult.

A case could be made for *Network Technologies* in the sense that it has
a reasonably high average mark (75.5) and the lowest minimum (32), this
suggests that there may be a knowledge gap for some students making it
significantly more difficult for a select few students.

Charecteristics of students who do poorly in Network Technologies should
be investigated to find a pattern.

## Create Moons Data

### Summary

```python
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
```

### In Detail

1. Generate and split the Data
   
   ```python
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
   ```

2. Split Manually
   
   The data can also be split manually:
   
   ```python
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
   ```

3. Plot with Plotnine
   
   This could also be don with plotnine, which is arguably
   significantly easier:
   
   ```python
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
   ```
   
   <img src="_media/ggplot_two_moons_plot.png" width="400" />

4. Plot with Matplotlib
   
   To plot the data with matplotlib:
   
   ```python
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
   ```
   
   <img src="_media/two_moons_matplotlib.png" width="400" />

## Fit a KNN Classifier

### Documentation

For these questions you really just want to look at the documentation:

- [KNN
  Model](https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html)
- [Neural
  Network](https://scikit-learn.org/stable/modules/neural_networks_supervised.html)
- [Decision
  Tree](https://scikit-learn.org/stable/modules/generated/sklearn.tree.DecisionTreeClassifier.html?highlight=decision%20tree#sklearn.tree.DecisionTreeClassifier)
- [Random
  Forest](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.RandomForestClassifier.html?highlight=random%20forest#sklearn.ensemble.RandomForestClassifier)

### Fit the Model

A Knn Model can be fit to the data thusly:

```python
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
```

### Measure the score

To see what `score` actually measures, perform `help(clf.score)`, it
seems Classification in SciKitLearn is usually Accuracy: [10]

$$
\mathrm{ACC} = \frac{\mathrm{TP} + \mathrm{TN}}{\mathrm{P} + \mathrm{N}}
$$

This can be returned by using the `score` method with the training and
test data given:

```python
## Consider the Accuracy of the model
ng.score(X_test, y_test)
```

In this case the score was 90%, indicating that the performance of knn
is very good on this type of data.

Using Cross Validation can provide a more accurate score, particularly
when data is limited:

```python
## If data were limited cross validation may be more accurate
from sklearn.model_selection import cross_val_score
print(np.mean(cross_val_score(ng, X, y, cv=10)))
```

## Creating Datasets with Scikit learn

There are many diffferent methods to make data in python using [Sci Kit
Learn
Make\_](https://scikit-learn.org/stable/search.html?q=sklearn+datasets+make)
functions, see also [This link
here](https://machinelearningmastery.com/generate-test-datasets-python-scikit-learn/).

### Make Blobs

```python
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
```

# Sqlite as a Text Searching tool

```sql
create virtual table notes using FTS5(path, contents);
insert into notes values('./filename', 'some text interesting');
insert into notes values('./other', 'blah');
select * from notes where notes match 'text';
```

[1] <https://aur.archlinux.org/packages/mongodb/>

[2] <https://aur.archlinux.org/packages/mongodb-tools/>

[3] <https://aur.archlinux.org/packages/mongodb-compass/>

[4] <https://aur.archlinux.org/packages/robo3t-bin/>

[5] Different documents in a collection may have different values so be
careful with this one.

[6] <https://scikit-learn.org/stable/modules/cross_validation.html>

[7] p\. 285/344 of [Lecture
Slides](Material/lectures/00_Slides_BigData.pdf)

[8] See the [Wikipedia :Sensitivity and
Specificity](https://en.wikipedia.org/wiki/Sensitivity_and_specificity)

[9] See [Intro Stat
Learning](~/Sync/Books/Textbooks/Data Science/Introduction to statistical learning.pdf)

[10] See the [Wikipedia :Sensitivity and
Specificity](https://en.wikipedia.org/wiki/Sensitivity_and_specificity)
