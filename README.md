Download Link: https://assignmentchef.com/product/solved-csci3901-lab9-database-design
<br>
In this lab, you will practice designing databases with key constraints.

<h1>Preparation</h1>

<ul>

 <li>Make sure that you are using your own private database on db.cs.dal.ca.

  <ul>

   <li>To do so, execute the command use USERID; where USERID is your CSID.</li>

  </ul></li>

 <li>Ensure that MySQLWorkbench is allowing you to do updates and deletions.

  <ul>

   <li>To do this, you may execute the command set SQL SAFE UPDATES=0;</li>

   <li>Alternatively, you can go into the MySQLWorkbench Preferences, then the SQL Editor tab and uncheck the Safe Updates box.</li>

  </ul></li>

</ul>

<strong>Resources</strong>

<ul>

 <li>MySQLWorkbench</li>

</ul>

<h1>Procedure</h1>

<h2>Set-up</h2>

<ol>

 <li>Create two tables in your database and include some basic information into the tables using the following commands:</li>

</ol>

create table web ( web_id int primary key, URL varchar(50)

);

create table course ( course_key int primary key, name varchar(10), web_id int );

insert into web values

(1, “cs.dal.ca”),

(2, “google.com”),

(3, “dal.ca”); insert into course values

(1, “csci3901”, 1),

(2, “csci5100”, 1),

(3, “math1000”, 3);

<h2>Lab steps</h2>

In part 1 you will execute a sequence of steps to modify the database you just created. In part 2, you will design a database given an ER diagram.

<strong>Part 1 – Key constraints</strong>

<ol>

 <li>Make the following changes to the database and report on their success or failure:

  <ul>

   <li>Add an entry to course with web id of NULL</li>

   <li>Add an entry to course with web id of 2</li>

   <li>Add an entry to course with web id of 4</li>

   <li>Add an entry to web with web id of 5</li>

  </ul></li>

 <li>Explain how you could identify all the entries in course with bad web id</li>

 <li>A foreign key constraint can be added to the course table with the command alter table course add foreign key (web_id) references web (web_id);</li>

</ol>

Determine whether the foreign key constraint can be successfully added with the above command in each of the following cases:

<ul>

 <li>course contains a webid that is a bad foreign key</li>

 <li>course contains a webid that is NULL</li>

 <li>course contains only web ids that are in web</li>

</ul>

<ol start="4">

 <li>Add web id as a foreign key in course, making any changes to either table necessary to do so.</li>

 <li>Explain what it means if you allow a foreign key column to be NULL</li>

 <li>Explain what it means if you <strong>do not </strong>allow a foreign key column to be NULL</li>

 <li>Make the following changes to the database and report on their success or failure:

  <ul>

   <li>Delete course key 2 in course</li>

   <li>Delete web id 3 in web</li>

   <li>Delete web (i.e. using drop table web;) (d) Delete course (i.e. using drop table course;)</li>

  </ul></li>

 <li>Explain why the previous commands succeeded or failed.</li>

</ol>

Figure 1: Entity relationship diagram

<strong>Part 2 – Database design </strong>Translate the ERD from fig. 1 to a set of tables in your database. Use the prefix ds  (for “dining service”) in your table names to let you group all the tables from this exercise.

In the figure, underlined attributes represent primary keys and attributes in curly braces {} represent multi-valued fields.

<h1>Questions</h1>

<ol>

 <li>How can foreign key constraints help to maintain the integrity of data in your database?</li>

 <li>Is there only one valid design for a database with a given ER diagram?</li>

</ol>