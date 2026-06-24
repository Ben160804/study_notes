======================================================================
DBMS UNIT-WISE QUESTION BANK (Organizer)
======================================================================

Years covered: 
Total lines in raw OCR: 4603


======================================================================
  UNIT-1: Intro & Architecture
======================================================================

  Q1: 1. Describe the three-schema i
archltectu(r)elgz [WBUT 2006]
Expiain in brief 3-schema architecture of DBMS. | [WBUT 2013]
a o)
Describe three layer architecture of DBMsR' . |
_ Oli [WBUT 2013]
Describe Three-Schem ; :
. a architectu
4
DBMSCS-2
DATABASE MANAGEMENT SYSTEMS
Answer:
Three Schema Architecture of DBMS
! Mapping supplied by.
CONCEPTUAL L...

  Q2: 2. What are the main functions of a database manager? List five major functions of
Data Base Administrator. [WBUT 2006]
OR,
Explain the roles of a database administrator (DBA). [WBUT 20089]
OR,
Discuss the role of DBA. | [WBUT 2017]
OR,
Explain the role of database administrator? [WBUT 2018]
Answer: . .
The functions of the DBA include the followin...

  Q3: 8. What separates the ‘h sical :
data representation? physical aspects of data storage from the logical aspects of
a) Data b) Schem : [WBUT 2010]
Answer: (b) ) 3 ¢) Constraints d) Relationship
DBMSCS-8
.
’ DATABASE MANAGEMENT SYSTEMS
9i What7schema defines how and where the data are organized in a physical data
storage? [WBUT 2010]
% a) Exze;nal b)...

  Q4: 1. What is the difference between logical data independence and physical data
independence? iy [WBUT 2006]
Défine physical data independence and logical data independence. [WBUT 2015]
Answer: )
Logical data independence: The ability to change the logxca}l (conceptual) schema
without changing the External schema (User View) is callgd logical data. m...

  Q5: 2. Explain the terms Candidate key, Primary key g [WBUT 2006, 2017]
OR,
in wi le super key, candidate key and primary key.
Explain with examp p y [WBUT 2013, 2019]
‘ OR, '
Explain with examples the term super key, candidate key, primary key and
~ alternate key. [WBUT 2015]
Answer: ‘
: Candidate key
In the relational model of databases, a candidate...

  Q6: 11. What do you mean by data abstraction? Explain three levels of data
. abstraction? [WBUT 2015]
Answer: '
The database Management system provides users an abstract view of data. Fo_r users
simplicity DBMS provides different levels of abstraction. The following are different
levels of abstraction.
1. Physical Level
2. Logical Level
3. View Level '...

  Q7: 8. Write short note on Data Dictionary. [WBUT 2013]
Answer: ;
* Refer to Question No. 4(b) of Short Answer Type Questions. .!
]
:
_ DBMSCS-24
r’
l
F DATABASE MANAGEMENT SYSTEMS
; e —————————————————————————
E Multiple Choice Type Questions
\
| 1. Relational algebra is a [WBUT 2007, 2019]
'; a) procedural language b) non-procedural language
i c) que...

  Q8: 3. Write short notes on the following: -
a) Theta (0) join [WBUT 2009] ,
b) Database models [WBUT 2016]
c) Inner join and Quter join [WBUT 2016]
d) Tuple Relational Calculus [MODEL QUESTION]
e) Degree of relationship ‘ [MODEL QUESTION]
Answer: : :
a) Theta (0) join: ‘ ~
The theta join operation is an extension to the natural-join operation that all...

  Q9: 2. List two reasons why ‘null’ values might be int (wBUT mq
PRSI . . : . value in a column is unknown q‘:‘
A null value in a relational database is used when the vait time data types) N
missing. A null is neither an empty string (for character of date U i 3
zero value (for numeric data types). : own It ‘i
NULL is often used in places where a value...

  Q10: 7. Consider the employee database:
: BU
Employee (emp_name, street, emp_id) [WBUT 2016, 2588
Works (emp_name, company_name, salary)
Company (company_name, city)
yv:i'::s:zs (emp_name, manager_name)
e appropriate SQL statemen i
a) Find the names and cities of resitdoe?'nct:ge ?aslns of the above table:
b) Find the names, street addresses and giti:s|...

  Q11: 4. Consider the schema R=(S, T, U, V) and the dependencies |
S>T.T->UU—-VandV —>S. Let R= (Rl and R2) be a decomposition such |
that R1NR2 = 6. The decomposition is: [WBUT 2011] |
a) Not in 2NF b) In 2NF but not in 3NF
c) In 3NF but not in 2NF d) In both 2NF and 3NF
Answer: (c) |
5. R={1,J,K,L},F ={I > K,IL>J,JK - L, L — K}. The candidate keys are...

  Q12: 2. Define BCNF. How does it differ from 3NF? Why is it considered a stronger from
3 NF? [WBUT 2007, 2009, 2010, 2011, 2012, 2019]
OR,
Explain with example “BCNF is stricter than 3NF”. [WBUT 2015] 1
OR, \
How does BCNF differ from 3rd normal form? , [WBUT 2016]
Answer: 1
| Boyce-Codd normal form (or BCNF or 3.5NF) is a normal form used in database ‘...

  Q13: 8. What do you mean by closure? : [WBUT 2013]
Answer: ‘
Thc? closu.re ot_‘ a set I of functional dependencies is the set of all functional dependencies
logically implied by F. We denote the closure of F by F+.
9. Suppose that we decompose the schema, :
R=(4,B,C,D) into (4,B,C) and (4,D,F). [WBUT 2013]
Show that this d ition i 9 . |
i s B ecompositi...

  Q14: 10. Discuss the properties of decomposition including attribute preservation,
dependency preservation and lossless join with example. [WBUT 2014]
. Answer:
’ Aftribute preservation condition:
' Each attribute in R will appear in at least one relation schema Ri in the decomposition s0
that no attributes are “lost”.
- Another goal of decomposition is...

  Q15: 8. Given a database schema named PLANE_INFO (flight_no, date, plane, airline, :
from, to, miles), the functional dependency diagram is given below:
-
[
from
E \-E
Decompose it up to Boyce-Codd Normal Form (BCNF). [WBUT 2009, 2010]
Answer:
Flight_no,date->Plane (1) '
Flight No->airline,from,to,miles (2) ' i
Fl'<>m3to-9miles (3) th
IS{elatlon (?) hol...

  Q16: 1. Explain the importance of view in providing security to the database. What are
the importance of GRANT and REVOKE commands? [MODEL QUESTION]
Answer: , ‘
1* Part: .
: Views can serve as security mechanisms by restricting the data available to users. Some
data can be accessible to users for query and modification, while the rest of the table or
da...

  Q17: 7. Define Data Warehouse and briefly describe its characteristics.
[MODEL QUESTION]
Answer; y f
A data warehouse consists of a computer database responsible for the collection and
storage of information for a specific organization. This collection of information is then {
Used to manage information efficiently and analyze the collected data. Althou...

  Q18: 6. What is Weak entity set? Explain with suitable example. ot 5}55’\\ 353
e ’ on o, . N NN
Ses Topiés ENTFTY-RELATIONSHIP MODEL, Short Ans#er TyRE SECc R
DBMSCS-149 X2
) See Topic: TRANSAC PROCESSING, Short Answer Type Question No. 2. PIIII
a) File indexing "figt?’i}:l?ﬁ
¢) Advantages of DBMS 209834
d) Database models A\};A 22
e) Inner join and Out...

  Q19: 3. Consider the following database with primary keys underlined 3{:%\;}5
Project (P — No, P — Name, P — incharge) 23 WD
Employee (E — no, E — Name) )\: e
Assigned-To (E — no, P.— no) {
Wirite relational algebra expression for the following: , , QA
(a) List detail of employee working on all projects. N
(b) List E — no, E — name of employee who do no...


======================================================================
  UNIT-2: ER & Relational Model
======================================================================

  Q1: 2. What are the main functions of a database manager? List five major functions of
Data Base Administrator. [WBUT 2006]
OR,
Explain the roles of a database administrator (DBA). [WBUT 20089]
OR,
Discuss the role of DBA. | [WBUT 2017]
OR,
Explain the role of database administrator? [WBUT 2018]
Answer: . .
The functions of the DBA include the followin...

  Q2: 4. What is the difference between a database and a table? [(WBUT 2009, 2011]
Answer:
El);tat?ase is a Pool of data. Tables are the containers .of holding the data. As per relational
o retlicail;:ti (r)rrlla;?dg/emenifslysmr?, tables Iare organized following the rules of total
or partial participation. Implementation is done wi i
| Key and foreign k...

  Q3: 6. What is the smallest unil_t of data in a relational model? [WBUT 2010, 2012]
a) Data type b) Field c) Data value d) None of these
Answer: (c) .
7. The word ‘loss’ in lossless refers to [WBUT 2010]
a) loss of information b) loss of attributes
c) loss of relations d) none of these ‘
Answer: (c)

  Q4: 8. What separates the ‘h sical :
data representation? physical aspects of data storage from the logical aspects of
a) Data b) Schem : [WBUT 2010]
Answer: (b) ) 3 ¢) Constraints d) Relationship
DBMSCS-8
.
’ DATABASE MANAGEMENT SYSTEMS
9i What7schema defines how and where the data are organized in a physical data
storage? [WBUT 2010]
% a) Exze;nal b)...

  Q5: 11. What is the cardinality of a table with 1000 rows & 10 columns? [WBUT 201 2]
‘ p a) 10( ) b) 100 c) 1000 d) none of these
nswer: (c .
12. In the relational modes, cardinality is termed as [WBUT 2013, 2019]
a) number of tuples b) number of attributes
) number of tables d) number of constraints
Answer: (a)
13. The different levels of data abstrac...

  Q6: 1. What is the difference between logical data independence and physical data
independence? iy [WBUT 2006]
Défine physical data independence and logical data independence. [WBUT 2015]
Answer: )
Logical data independence: The ability to change the logxca}l (conceptual) schema
without changing the External schema (User View) is callgd logical data. m...

  Q7: 2. Explain the terms Candidate key, Primary key g [WBUT 2006, 2017]
OR,
in wi le super key, candidate key and primary key.
Explain with examp p y [WBUT 2013, 2019]
‘ OR, '
Explain with examples the term super key, candidate key, primary key and
~ alternate key. [WBUT 2015]
Answer: ‘
: Candidate key
In the relational model of databases, a candidate...

  Q8: 6. Explain candidate key with an example. [WBUT 2011]
Answer:
Refer to Question No. 2 of Short Answer Type Questions.

  Q9: 7. Define super key, candidate key and primary key. [WBUT 2012]
Answer:
Refer to Question No. 2 of Short Answer Type Questions.

  Q10: 8. What is cardinality ratio? [WBUT 2013, 2017]
Answer: : ; '
Cardinality: Cardinality is the specification of the number of occurrences of one object
that can be related to the number of occurrences of another object. \ o 1 .
For example, one object can relate to only one other object (1:1 relationship); one object
: can relate to many objects (1:...

  Q11: 10. What do you mean by degree, cardinality of relationship? [WBUT 2015]
Answer: AT :
The degree of relationship (also known as cardinality) is the number (?f occurrences in
one entity which are associated (or linked) to the number of occurrences in another.
. There are three degrees of relationship, known as:
1. one-to-one (1:1)
- 2. one-to-many (...

  Q12: 12. What is Weak entity set? Explain with suitable example. [WBUT 2016]
Answer:
An entity set is called a weak entity set if its existence depends on other entities (called
strong entities). Thus a weak entity set does not have sufficient attributes to form a
primary key.
As shown in -ﬁg.. the entity set Departures which has the only attribute date...

  Q13: 13. Describe different types of attribute. [WBUT 2017]
Answer:
Types of Attribute are: '
Single valued Attributes: An attribute, that has a single value for a particular entity. For
example, age of a employee entity. -
Multi valued Attributes: An attributes that may have multipie values for the same entity.
For example colors of a car entity. A
Com...

  Q14: 15. Explain with example the difference between strong and weak entity sets.
[WBUT 2019]
Answer: Refer to Question No. 3 (I°' Part) of Short Answer Type Questions.
Example of Strong entity set & Weak entity set:
Flight is a strong entity. @
P
Departures is a weak entity.
|
1. Design a Generalization-Specialization hierarchy for a motor-vehicle sale...

  Q15: 8. Write short note on Data Dictionary. [WBUT 2013]
Answer: ;
* Refer to Question No. 4(b) of Short Answer Type Questions. .!
]
:
_ DBMSCS-24
r’
l
F DATABASE MANAGEMENT SYSTEMS
; e —————————————————————————
E Multiple Choice Type Questions
\
| 1. Relational algebra is a [WBUT 2007, 2019]
'; a) procedural language b) non-procedural language
i c) que...

  Q16: 2. Discuss the entity integrit ial i : :
considered importan¥? Expgair)ll ;irt‘g sr:ift(;rtflr::)i lntelgnty . W
Answer: ample. [WBUT 2008, 2010, 2012]
Entity Integrity: In a relational d ity i
: atabase, entit s ority T
records are duplicated and that no attributes thzlln“fm) 'S a property that ensures thatno
one‘ot the properties necessary (o ens...

  Q17: 9. Define the following: [MODEL QUESTION]
i) Derived attribute [
ii) Domain 4
iii) 1 to Many relationship ‘ :
iv) Projection |
v) Union compatibility E
Answer: :
i) Derived Attribute: a
The attribute values which are not a part of the entity but can be computed in association |
with some other stored attributes. It is not stored but can be computed...

  Q18: 2. Consider the relational database as given below and write down expressions in |
relational algebra for the following queries.
Material_Master (item_id, item name, reorder level) :
Material_Dts (item_id, Supplier_id, Pharchase_date, Qty, Utcost) |
i) Select the quantities of each purchased material alphabetically.
ii) Select the names of material...

  Q19: 3. Write short notes on the following: -
a) Theta (0) join [WBUT 2009] ,
b) Database models [WBUT 2016]
c) Inner join and Quter join [WBUT 2016]
d) Tuple Relational Calculus [MODEL QUESTION]
e) Degree of relationship ‘ [MODEL QUESTION]
Answer: : :
a) Theta (0) join: ‘ ~
The theta join operation is an extension to the natural-join operation that all...

  Q20: 13. What is the name of a trigger that triggers that triggers itself?
: . : ‘ [WBUT 2014, 2017}
\ a) Triggering trigger b) Cascading trigger
c) Mutating trigger d) None of the above
Answer: (b)
14, DML stands'for ' [WBUT 2015]
a) Data Manipulation Language b) Data Media Language
c) both (a) & (b) d) none of these
‘ Answer: (a)
15. Which data type c...

  Q21: 5. What is a trigger? How many types of trigger are there? [WBUT 2012]
| Answer:
| (% Part: Refer to Question No. 1(a) of Long Answer Type Questions.
2 Part:
In SQL Server we can create four types of triggers Data Definition Language (DDL)
triggers, Data Manipulation Language (DML) triggers, CLR triggers and Logon triggers.
1. DDL Triggers '
In SQL...

  Q22: 2. List two reasons why ‘null’ values might be int (wBUT mq
PRSI . . : . value in a column is unknown q‘:‘
A null value in a relational database is used when the vait time data types) N
missing. A null is neither an empty string (for character of date U i 3
zero value (for numeric data types). : own It ‘i
NULL is often used in places where a value...

  Q23: 6. Consider the following employee database, primary keys are underlined.
Employee(employee-name, street, city)
Works(employee-name, company-name, salary)
Company(company-name, city)
Manages(employee-name, manager-name)
:;r;:til:‘ c?CtJL’s for the queries given below: |
i Findhe names of all employees who work for )SYZ._ T T
o all empl_oyees in the...

  Q24: 7. Consider the employee database:
: BU
Employee (emp_name, street, emp_id) [WBUT 2016, 2588
Works (emp_name, company_name, salary)
Company (company_name, city)
yv:i'::s:zs (emp_name, manager_name)
e appropriate SQL statemen i
a) Find the names and cities of resitdoe?'nct:ge ?aslns of the above table:
b) Find the names, street addresses and giti:s|...

  Q25: 4. Consider the schema R=(S, T, U, V) and the dependencies |
S>T.T->UU—-VandV —>S. Let R= (Rl and R2) be a decomposition such |
that R1NR2 = 6. The decomposition is: [WBUT 2011] |
a) Not in 2NF b) In 2NF but not in 3NF
c) In 3NF but not in 2NF d) In both 2NF and 3NF
Answer: (c) |
5. R={1,J,K,L},F ={I > K,IL>J,JK - L, L — K}. The candidate keys are...


======================================================================
  UNIT-3: SQL & Queries
======================================================================

  Q1: 1. Describe the three-schema i
archltectu(r)elgz [WBUT 2006]
Expiain in brief 3-schema architecture of DBMS. | [WBUT 2013]
a o)
Describe three layer architecture of DBMsR' . |
_ Oli [WBUT 2013]
Describe Three-Schem ; :
. a architectu
4
DBMSCS-2
DATABASE MANAGEMENT SYSTEMS
Answer:
Three Schema Architecture of DBMS
! Mapping supplied by.
CONCEPTUAL L...

  Q2: 2. What are the main functions of a database manager? List five major functions of
Data Base Administrator. [WBUT 2006]
OR,
Explain the roles of a database administrator (DBA). [WBUT 20089]
OR,
Discuss the role of DBA. | [WBUT 2017]
OR,
Explain the role of database administrator? [WBUT 2018]
Answer: . .
The functions of the DBA include the followin...

  Q3: 4. What is the difference between a database and a table? [(WBUT 2009, 2011]
Answer:
El);tat?ase is a Pool of data. Tables are the containers .of holding the data. As per relational
o retlicail;:ti (r)rrlla;?dg/emenifslysmr?, tables Iare organized following the rules of total
or partial participation. Implementation is done wi i
| Key and foreign k...

  Q4: 11. What is the cardinality of a table with 1000 rows & 10 columns? [WBUT 201 2]
‘ p a) 10( ) b) 100 c) 1000 d) none of these
nswer: (c .
12. In the relational modes, cardinality is termed as [WBUT 2013, 2019]
a) number of tuples b) number of attributes
) number of tables d) number of constraints
Answer: (a)
13. The different levels of data abstrac...

  Q5: 1. What is the difference between logical data independence and physical data
independence? iy [WBUT 2006]
Défine physical data independence and logical data independence. [WBUT 2015]
Answer: )
Logical data independence: The ability to change the logxca}l (conceptual) schema
without changing the External schema (User View) is callgd logical data. m...

  Q6: 2. Explain the terms Candidate key, Primary key g [WBUT 2006, 2017]
OR,
in wi le super key, candidate key and primary key.
Explain with examp p y [WBUT 2013, 2019]
‘ OR, '
Explain with examples the term super key, candidate key, primary key and
~ alternate key. [WBUT 2015]
Answer: ‘
: Candidate key
In the relational model of databases, a candidate...

  Q7: 9. What is disjointless constraint? [WBUT 2013]
Answer: ' . _
Disjoint Constraints: One or more sub collections of a given super collection may be
declared to be disjoint. It implies that no object may occur in more than one of these sub
DBMSCS-13
collections. E.g. Employees and Customers may be declared to be disjoint sub collections
of Persons. S...

  Q8: 11. What do you mean by data abstraction? Explain three levels of data
. abstraction? [WBUT 2015]
Answer: '
The database Management system provides users an abstract view of data. Fo_r users
simplicity DBMS provides different levels of abstraction. The following are different
levels of abstraction.
1. Physical Level
2. Logical Level
3. View Level '...

  Q9: 13. Describe different types of attribute. [WBUT 2017]
Answer:
Types of Attribute are: '
Single valued Attributes: An attribute, that has a single value for a particular entity. For
example, age of a employee entity. -
Multi valued Attributes: An attributes that may have multipie values for the same entity.
For example colors of a car entity. A
Com...

  Q10: 15. Explain with example the difference between strong and weak entity sets.
[WBUT 2019]
Answer: Refer to Question No. 3 (I°' Part) of Short Answer Type Questions.
Example of Strong entity set & Weak entity set:
Flight is a strong entity. @
P
Departures is a weak entity.
|
1. Design a Generalization-Specialization hierarchy for a motor-vehicle sale...

  Q11: 8. Write short note on Data Dictionary. [WBUT 2013]
Answer: ;
* Refer to Question No. 4(b) of Short Answer Type Questions. .!
]
:
_ DBMSCS-24
r’
l
F DATABASE MANAGEMENT SYSTEMS
; e —————————————————————————
E Multiple Choice Type Questions
\
| 1. Relational algebra is a [WBUT 2007, 2019]
'; a) procedural language b) non-procedural language
i c) que...

  Q12: 2. Discuss the entity integrit ial i : :
considered importan¥? Expgair)ll ;irt‘g sr:ift(;rtflr::)i lntelgnty . W
Answer: ample. [WBUT 2008, 2010, 2012]
Entity Integrity: In a relational d ity i
: atabase, entit s ority T
records are duplicated and that no attributes thzlln“fm) 'S a property that ensures thatno
one‘ot the properties necessary (o ens...

  Q13: 9. Define the following: [MODEL QUESTION]
i) Derived attribute [
ii) Domain 4
iii) 1 to Many relationship ‘ :
iv) Projection |
v) Union compatibility E
Answer: :
i) Derived Attribute: a
The attribute values which are not a part of the entity but can be computed in association |
with some other stored attributes. It is not stored but can be computed...

  Q14: 2. Consider the relational database as given below and write down expressions in |
relational algebra for the following queries.
Material_Master (item_id, item name, reorder level) :
Material_Dts (item_id, Supplier_id, Pharchase_date, Qty, Utcost) |
i) Select the quantities of each purchased material alphabetically.
ii) Select the names of material...

  Q15: 3. Write short notes on the following: -
a) Theta (0) join [WBUT 2009] ,
b) Database models [WBUT 2016]
c) Inner join and Quter join [WBUT 2016]
d) Tuple Relational Calculus [MODEL QUESTION]
e) Degree of relationship ‘ [MODEL QUESTION]
Answer: : :
a) Theta (0) join: ‘ ~
The theta join operation is an extension to the natural-join operation that all...

  Q16: 8. What operator performs pattern matching is SC_IL? [‘:IV Bfutz :g;z’ 2017]
a) Except b) Intersect c) Like d) All o
Answer: (d)
- 9. DML is provided for [WBUT 2013, 2019]
a) description of logical structure of database
b) addition of new structures in the database system
¢) manipulation & processing of database
d) definition of physical structure...

  Q17: 11. Consider the following SQL statements: . [WBUT 2014]
A. Select * from student where year = 2"" or year = 3’
B. Select * from student where year in (2", 3%
a) A is correct while B is not
b) B is correct while A is not
c) Both will generate same result set :
d) A and B will generate different result sets
Answer: (¢)

  Q18: 12. Consider the following query:
(((P WHERE _COLOUR=’RED’)’RED’)[P#]JOIN SP)[S#]JOIN S) MEVES
[SNAME]Which one of the following set of o i
involve? perations does the above Query
a) 1 selection, 2 joins, 3 projections
| c) 2 selections, 2 joins, 3 projections d; : ;’;‘,’fﬁt'”’ 2joins, 3 selections
Answer: (b) ction, 2 joins, 3 intersections
; DBMS...

  Q19: 13. What is the name of a trigger that triggers that triggers itself?
: . : ‘ [WBUT 2014, 2017}
\ a) Triggering trigger b) Cascading trigger
c) Mutating trigger d) None of the above
Answer: (b)
14, DML stands'for ' [WBUT 2015]
a) Data Manipulation Language b) Data Media Language
c) both (a) & (b) d) none of these
‘ Answer: (a)
15. Which data type c...

  Q20: 1. Explain the terms View. [WBUT 2006, 2008, 2012]
Answer:
A view is a relation (virtual rather than base) and can be used in query expressions, that
is, queries can be written-using the view as a relation. In other words, a view is a named
table that is represented, not by its own physically separate stored data. but by its
definition in terms of...

  Q21: 5. What is a trigger? How many types of trigger are there? [WBUT 2012]
| Answer:
| (% Part: Refer to Question No. 1(a) of Long Answer Type Questions.
2 Part:
In SQL Server we can create four types of triggers Data Definition Language (DDL)
triggers, Data Manipulation Language (DML) triggers, CLR triggers and Logon triggers.
1. DDL Triggers '
In SQL...

  Q22: 2. List two reasons why ‘null’ values might be int (wBUT mq
PRSI . . : . value in a column is unknown q‘:‘
A null value in a relational database is used when the vait time data types) N
missing. A null is neither an empty string (for character of date U i 3
zero value (for numeric data types). : own It ‘i
NULL is often used in places where a value...

  Q23: 6. Consider the following employee database, primary keys are underlined.
Employee(employee-name, street, city)
Works(employee-name, company-name, salary)
Company(company-name, city)
Manages(employee-name, manager-name)
:;r;:til:‘ c?CtJL’s for the queries given below: |
i Findhe names of all employees who work for )SYZ._ T T
o all empl_oyees in the...

  Q24: 7. Consider the employee database:
: BU
Employee (emp_name, street, emp_id) [WBUT 2016, 2588
Works (emp_name, company_name, salary)
Company (company_name, city)
yv:i'::s:zs (emp_name, manager_name)
e appropriate SQL statemen i
a) Find the names and cities of resitdoe?'nct:ge ?aslns of the above table:
b) Find the names, street addresses and giti:s|...

  Q25: 4. Consider the schema R=(S, T, U, V) and the dependencies |
S>T.T->UU—-VandV —>S. Let R= (Rl and R2) be a decomposition such |
that R1NR2 = 6. The decomposition is: [WBUT 2011] |
a) Not in 2NF b) In 2NF but not in 3NF
c) In 3NF but not in 2NF d) In both 2NF and 3NF
Answer: (c) |
5. R={1,J,K,L},F ={I > K,IL>J,JK - L, L — K}. The candidate keys are...


======================================================================
  UNIT-4: Normalization
======================================================================

  Q1: 4. What is the difference between a database and a table? [(WBUT 2009, 2011]
Answer:
El);tat?ase is a Pool of data. Tables are the containers .of holding the data. As per relational
o retlicail;:ti (r)rrlla;?dg/emenifslysmr?, tables Iare organized following the rules of total
or partial participation. Implementation is done wi i
| Key and foreign k...

  Q2: 2. Explain the terms Candidate key, Primary key g [WBUT 2006, 2017]
OR,
in wi le super key, candidate key and primary key.
Explain with examp p y [WBUT 2013, 2019]
‘ OR, '
Explain with examples the term super key, candidate key, primary key and
~ alternate key. [WBUT 2015]
Answer: ‘
: Candidate key
In the relational model of databases, a candidate...

  Q3: 8. Write short note on Data Dictionary. [WBUT 2013]
Answer: ;
* Refer to Question No. 4(b) of Short Answer Type Questions. .!
]
:
_ DBMSCS-24
r’
l
F DATABASE MANAGEMENT SYSTEMS
; e —————————————————————————
E Multiple Choice Type Questions
\
| 1. Relational algebra is a [WBUT 2007, 2019]
'; a) procedural language b) non-procedural language
i c) que...

  Q4: 13. What is the name of a trigger that triggers that triggers itself?
: . : ‘ [WBUT 2014, 2017}
\ a) Triggering trigger b) Cascading trigger
c) Mutating trigger d) None of the above
Answer: (b)
14, DML stands'for ' [WBUT 2015]
a) Data Manipulation Language b) Data Media Language
c) both (a) & (b) d) none of these
‘ Answer: (a)
15. Which data type c...

  Q5: 7. Consider the employee database:
: BU
Employee (emp_name, street, emp_id) [WBUT 2016, 2588
Works (emp_name, company_name, salary)
Company (company_name, city)
yv:i'::s:zs (emp_name, manager_name)
e appropriate SQL statemen i
a) Find the names and cities of resitdoe?'nct:ge ?aslns of the above table:
b) Find the names, street addresses and giti:s|...

  Q6: 4. Consider the schema R=(S, T, U, V) and the dependencies |
S>T.T->UU—-VandV —>S. Let R= (Rl and R2) be a decomposition such |
that R1NR2 = 6. The decomposition is: [WBUT 2011] |
a) Not in 2NF b) In 2NF but not in 3NF
c) In 3NF but not in 2NF d) In both 2NF and 3NF
Answer: (c) |
5. R={1,J,K,L},F ={I > K,IL>J,JK - L, L — K}. The candidate keys are...

  Q7: 2. Define BCNF. How does it differ from 3NF? Why is it considered a stronger from
3 NF? [WBUT 2007, 2009, 2010, 2011, 2012, 2019]
OR,
Explain with example “BCNF is stricter than 3NF”. [WBUT 2015] 1
OR, \
How does BCNF differ from 3rd normal form? , [WBUT 2016]
Answer: 1
| Boyce-Codd normal form (or BCNF or 3.5NF) is a normal form used in database ‘...

  Q8: 4. Draw a functional dependehc‘ di S _
BCNF. Decompose that FD diangm iz?;a;:lslio diagram) that is in 3NF but notin
Answer: ' [WBUT 2009, 2011]
Example (3NF but not BCNF):
SUPPLIER_PART (supplier no, suppl; ]
_ pplier_no,
l\;;mctional Dependenciis; _ho; supplier_name, part_no, quantity) ;'
¢ assume that supplier name' | A
candidate keys: % s are a...

  Q9: 6. Consider relation R (A, B, C) and a set of function dependencies [WBUT 201 1
F = {A>BC, B-C, A-B, AB—C} Compute the canonical cover for F.
Answer: '
A canonical cover F, for F is a set of dependencies such that E: A
Logically implies all dependencies in F. and F. logically implies all dependencies in F,
moreover ‘ :
— No functional dependency in...

  Q10: 7. Compare between 3NF and BCNF with example. WBUT 2012]
Answer: :
i) In case of 3NF all the determinant cannot | i) In case of BCNF all the determinant must
be candidate key. be candidate key.
iii) 3NF is normal form in which the table is | iii) BCNF is a normal form in which for
in 2NF and every non-prime attribute is non- | every one of a table’...

  Q11: 10. Discuss the properties of decomposition including attribute preservation,
dependency preservation and lossless join with example. [WBUT 2014]
. Answer:
’ Aftribute preservation condition:
' Each attribute in R will appear in at least one relation schema Ri in the decomposition s0
that no attributes are “lost”.
- Another goal of decomposition is...

  Q12: 12. What are the advantages of normalization? [WBUT 2016]
Answer: :
Advantages of normalization
{_ Smaller database: By eliminating duplicate data, you will be able to reduce the overall
size of the database. -
2. Better performance:
a. Narrow tables: Having more fine-tuned tables allows your tables to have less columns
and allows you to fit more r...

  Q13: 13. What is closure and minimal cover? What is inclusion dependency? ‘
[WBUT 2017]
Answer: ' )
. B part: '
Closure: Refer to Question No. 8 of Short Answer Type Questions.
Minimal Cover: |
R(ABCD), F={A—->BC,B—>C,AB->Dj} '
A — BC
AS>B, A—C, BSC, AB=D- ¥
S moiosn: i)
A" = ABCD B =BC
A"=ACD .
A' = ABCD
A'=ABC A—D 4
Thus minimal cover can be summarily...

  Q14: 1. Discuss the “insertion anomalies” b j P i Bl
anomalies” with respect to normal forn;s wi,:ga;'l?i?abimoma"es and ‘o E
- method to overcome them. ¢ example and suggest a X
An anomaly is a variation wi 4
update, insert, delete operations a?c t tofa datab‘_‘sc. maintenance. In databases when =
should be in a minimum tim pertormed, it is desirable t...

  Q15: 5. Explain the following terms ‘Fully functional dependency’ and ‘non transitive
dependency’ with examples. [WBUT 2008]
Answer:;
: An_ attribute is fully functionally dependent on a set of attributes X if it is
_ I functionally dependent on X, and
1. not functionally dependent on any proper subset of X. {Employee Address} has a
functional dependenc...

  Q16: 6. What is MVDs? i - 8,
ean by lossless (or non-additive) join property of decomposition?
What do you m y [WBUT 2008]
Answer: ]
1* Part: Refer to Question No. 2(a) of Long Answer T ype Questions.
2" part:
Lossless Decomposition: _ ,
Let R having the decompositions R1 and R2 With given set of FD’s say F, thgn R1 and
R2 to become lossless then at lea...

  Q17: 8. Given a database schema named PLANE_INFO (flight_no, date, plane, airline, :
from, to, miles), the functional dependency diagram is given below:
-
[
from
E \-E
Decompose it up to Boyce-Codd Normal Form (BCNF). [WBUT 2009, 2010]
Answer:
Flight_no,date->Plane (1) '
Flight No->airline,from,to,miles (2) ' i
Fl'<>m3to-9miles (3) th
IS{elatlon (?) hol...

  Q18: 24. Write short notes on the following:
a) Armstrong’s axioms [WBUT 2009, 2017]
b) Functional dependency ' [WBUT 2013]
¢) BCNF [WBUT 2018]
Answer
‘. ;) Ar mstrong’s Axioms (Inference Rules for FDs):
5 or any given relation, there can be many FDs. Let us denote F as the set of FDs of a
;{ Elven relation R. There can be many other FDs that can be der...

  Q19: 7. Define Data Warehouse and briefly describe its characteristics.
[MODEL QUESTION]
Answer; y f
A data warehouse consists of a computer database responsible for the collection and
storage of information for a specific organization. This collection of information is then {
Used to manage information efficiently and analyze the collected data. Althou...

  Q20: 3. Explain two-phase locking protocol. AN 5
See Topic: TRANSACTION PROCESSING, Short Answer Type Question No. 5. \?vﬂ
4 Consider the relation R = {A, B,C,D,E.F,G,H, ],J} and the set of functional dependencies: 4 /
| B
Pw:{AB——>C,A—>DE,B—>F,F—>GH,D—>U} 5;
v
Decompose R into 3NF. ﬁ;
See Topic: FUNCTIONAL DEPENDENCIES AND NORMALIZATION, Short Answer T...

  Q21: 6. What is Weak entity set? Explain with suitable example. ot 5}55’\\ 353
e ’ on o, . N NN
Ses Topiés ENTFTY-RELATIONSHIP MODEL, Short Ans#er TyRE SECc R
DBMSCS-149 X2
) See Topic: TRANSAC PROCESSING, Short Answer Type Question No. 2. PIIII
a) File indexing "figt?’i}:l?ﬁ
¢) Advantages of DBMS 209834
d) Database models A\};A 22
e) Inner join and Out...

  Q22: 3. Consider the following database with primary keys underlined 3{:%\;}5
Project (P — No, P — Name, P — incharge) 23 WD
Employee (E — no, E — Name) )\: e
Assigned-To (E — no, P.— no) {
Wirite relational algebra expression for the following: , , QA
(a) List detail of employee working on all projects. N
(b) List E — no, E — name of employee who do no...

  Q23: 5. Define BCNF. How does it differ from 3NF? Why is it considered a stronger than 3 NF? &&§§
- Topic: FUNCTIONAL DEPENDENCIES AND I\'ORMALIZATIO.\', Short Answer Type §§{§§
Question No- 2- A
e | RARA

  Q24: 6. What is the main difference between two-phase locking and the time stamping technique &%{%}
' concurrency control? Explain briefly. - gsigs
' See Topic: TRANSACTION PROCESSING, Short Answer Type Question No. 5. :ﬂ:m
: | RO
GROUP-C g)'%g
(Long Answer Type Questions) 2
7.a) What is mapping constraint ? Describe three-layer architecture of DBMS. q“...


======================================================================
  UNIT-5: Transaction & Concurrency
======================================================================

  Q1: 2. What are the main functions of a database manager? List five major functions of
Data Base Administrator. [WBUT 2006]
OR,
Explain the roles of a database administrator (DBA). [WBUT 20089]
OR,
Discuss the role of DBA. | [WBUT 2017]
OR,
Explain the role of database administrator? [WBUT 2018]
Answer: . .
The functions of the DBA include the followin...

  Q2: 4. What is the difference between a database and a table? [(WBUT 2009, 2011]
Answer:
El);tat?ase is a Pool of data. Tables are the containers .of holding the data. As per relational
o retlicail;:ti (r)rrlla;?dg/emenifslysmr?, tables Iare organized following the rules of total
or partial participation. Implementation is done wi i
| Key and foreign k...

  Q3: 5. What is a RDBMS terminology for a set of legal values that an attribute can
have? [WBUT 2010]
a) Tuple b) Relation c) Attribute d) Domain
Answer: (d)

  Q4: 8. What separates the ‘h sical :
data representation? physical aspects of data storage from the logical aspects of
a) Data b) Schem : [WBUT 2010]
Answer: (b) ) 3 ¢) Constraints d) Relationship
DBMSCS-8
.
’ DATABASE MANAGEMENT SYSTEMS
9i What7schema defines how and where the data are organized in a physical data
storage? [WBUT 2010]
% a) Exze;nal b)...

  Q5: 11. What is the cardinality of a table with 1000 rows & 10 columns? [WBUT 201 2]
‘ p a) 10( ) b) 100 c) 1000 d) none of these
nswer: (c .
12. In the relational modes, cardinality is termed as [WBUT 2013, 2019]
a) number of tuples b) number of attributes
) number of tables d) number of constraints
Answer: (a)
13. The different levels of data abstrac...

  Q6: 1. What is the difference between logical data independence and physical data
independence? iy [WBUT 2006]
Défine physical data independence and logical data independence. [WBUT 2015]
Answer: )
Logical data independence: The ability to change the logxca}l (conceptual) schema
without changing the External schema (User View) is callgd logical data. m...

  Q7: 11. What do you mean by data abstraction? Explain three levels of data
. abstraction? [WBUT 2015]
Answer: '
The database Management system provides users an abstract view of data. Fo_r users
simplicity DBMS provides different levels of abstraction. The following are different
levels of abstraction.
1. Physical Level
2. Logical Level
3. View Level '...

  Q8: 15. Explain with example the difference between strong and weak entity sets.
[WBUT 2019]
Answer: Refer to Question No. 3 (I°' Part) of Short Answer Type Questions.
Example of Strong entity set & Weak entity set:
Flight is a strong entity. @
P
Departures is a weak entity.
|
1. Design a Generalization-Specialization hierarchy for a motor-vehicle sale...

  Q9: 8. Write short note on Data Dictionary. [WBUT 2013]
Answer: ;
* Refer to Question No. 4(b) of Short Answer Type Questions. .!
]
:
_ DBMSCS-24
r’
l
F DATABASE MANAGEMENT SYSTEMS
; e —————————————————————————
E Multiple Choice Type Questions
\
| 1. Relational algebra is a [WBUT 2007, 2019]
'; a) procedural language b) non-procedural language
i c) que...

  Q10: 2. Discuss the entity integrit ial i : :
considered importan¥? Expgair)ll ;irt‘g sr:ift(;rtflr::)i lntelgnty . W
Answer: ample. [WBUT 2008, 2010, 2012]
Entity Integrity: In a relational d ity i
: atabase, entit s ority T
records are duplicated and that no attributes thzlln“fm) 'S a property that ensures thatno
one‘ot the properties necessary (o ens...

  Q11: 3. Write short notes on the following: -
a) Theta (0) join [WBUT 2009] ,
b) Database models [WBUT 2016]
c) Inner join and Quter join [WBUT 2016]
d) Tuple Relational Calculus [MODEL QUESTION]
e) Degree of relationship ‘ [MODEL QUESTION]
Answer: : :
a) Theta (0) join: ‘ ~
The theta join operation is an extension to the natural-join operation that all...

  Q12: 8. What operator performs pattern matching is SC_IL? [‘:IV Bfutz :g;z’ 2017]
a) Except b) Intersect c) Like d) All o
Answer: (d)
- 9. DML is provided for [WBUT 2013, 2019]
a) description of logical structure of database
b) addition of new structures in the database system
¢) manipulation & processing of database
d) definition of physical structure...

  Q13: 1. Explain the terms View. [WBUT 2006, 2008, 2012]
Answer:
A view is a relation (virtual rather than base) and can be used in query expressions, that
is, queries can be written-using the view as a relation. In other words, a view is a named
table that is represented, not by its own physically separate stored data. but by its
definition in terms of...

  Q14: 5. What is a trigger? How many types of trigger are there? [WBUT 2012]
| Answer:
| (% Part: Refer to Question No. 1(a) of Long Answer Type Questions.
2 Part:
In SQL Server we can create four types of triggers Data Definition Language (DDL)
triggers, Data Manipulation Language (DML) triggers, CLR triggers and Logon triggers.
1. DDL Triggers '
In SQL...

  Q15: 2. List two reasons why ‘null’ values might be int (wBUT mq
PRSI . . : . value in a column is unknown q‘:‘
A null value in a relational database is used when the vait time data types) N
missing. A null is neither an empty string (for character of date U i 3
zero value (for numeric data types). : own It ‘i
NULL is often used in places where a value...

  Q16: 7. Consider the employee database:
: BU
Employee (emp_name, street, emp_id) [WBUT 2016, 2588
Works (emp_name, company_name, salary)
Company (company_name, city)
yv:i'::s:zs (emp_name, manager_name)
e appropriate SQL statemen i
a) Find the names and cities of resitdoe?'nct:ge ?aslns of the above table:
b) Find the names, street addresses and giti:s|...

  Q17: 6. Consider relation R (A, B, C) and a set of function dependencies [WBUT 201 1
F = {A>BC, B-C, A-B, AB—C} Compute the canonical cover for F.
Answer: '
A canonical cover F, for F is a set of dependencies such that E: A
Logically implies all dependencies in F. and F. logically implies all dependencies in F,
moreover ‘ :
— No functional dependency in...

  Q18: 8. What do you mean by closure? : [WBUT 2013]
Answer: ‘
Thc? closu.re ot_‘ a set I of functional dependencies is the set of all functional dependencies
logically implied by F. We denote the closure of F by F+.
9. Suppose that we decompose the schema, :
R=(4,B,C,D) into (4,B,C) and (4,D,F). [WBUT 2013]
Show that this d ition i 9 . |
i s B ecompositi...

  Q19: 24. Write short notes on the following:
a) Armstrong’s axioms [WBUT 2009, 2017]
b) Functional dependency ' [WBUT 2013]
¢) BCNF [WBUT 2018]
Answer
‘. ;) Ar mstrong’s Axioms (Inference Rules for FDs):
5 or any given relation, there can be many FDs. Let us denote F as the set of FDs of a
;{ Elven relation R. There can be many other FDs that can be der...

  Q20: 1. What is the difference between Primary index, Secondary index and Clustering
index? [(WBUT 2006, 2011]
' Answer:
Primary & Secondary Index:
Refer to Question No. 3(a) of Long Answer Type Questions.
Clustering Indexes .
If records of a file are physically ordered on a nonkey field, called the clustering field.
' We can create a clustering index t...

  Q21: 3. However, the leaf node are still required to be at least half full. ‘
4. Insertion and delethn from a B +-tree file organization are handled in the same way
as that in a B +-tree index. :
5, When a B +-tree Is used for file organization, space utilization is particularly
important. We can improve the space uilization by involving more sibling no...

  Q22: 6. Consider the file with » = 3000 records (fixed length) of size R = 100 bytes stored
on a disk with block size B = 1024 bytes. Suppose each index entry in index file
takes 15 bytes (9 bytes for index value, 5 bytes for pointer). What is the number of
accessing blocks for clustering index? [WBUT 2015]
Answer: .
Block Factor bfr = (B/R) =(1024/100)...

  Q23: 7. Write short notes on the following: |
a) B-tree !
p) File indexing [WBUT 2013, 2019]
c) B+ tree [WBUT 2016]
OR, [WBUT 2016]
B+ tree file organization
d) Ordered Index [WBUT 2018]
e) Primary Index and Secondary Index : IWVISH 20373
, [WBUT 2018]
Answer:
a) B-tree: .
. et andl fhase Revs pant i TREN non- eaf npde is one less than the number
| of i...

  Q24: 1. What is two phase locking protocol? [WBUT 2008, 2012, 20
i i ili ’ ' 17]
How does it guarantee serializability?
| ) OR, [WBUT 2008, 2017)] }
griefly explain two phase locking protocol, ‘
| OR, [WBUT 2015]
pescribe different 2PL protocol in brief. [WBUT 2018]
Answer:
Two-phase locking
According 1o ‘h? two-phase lgcking protocol, a transaction han...

  Q25: 5. What is the single most significant difference between two-phase locking and
l the time-stamping technique concurrency control? Explain briefly. [WBUT 2014]
_ OR,
Explain two-phase locking protocol. ‘ [WBUT 2016]
OR,
What_is the main difference between two-phase locking and the time stamping
technique concurrency control? Explain briefly. [WBUT...


======================================================================
  UNIT-6: File Organization & Indexing
======================================================================

  Q1: 1. What is the difference between logical data independence and physical data
independence? iy [WBUT 2006]
Défine physical data independence and logical data independence. [WBUT 2015]
Answer: )
Logical data independence: The ability to change the logxca}l (conceptual) schema
without changing the External schema (User View) is callgd logical data. m...

  Q2: 2. Discuss the entity integrit ial i : :
considered importan¥? Expgair)ll ;irt‘g sr:ift(;rtflr::)i lntelgnty . W
Answer: ample. [WBUT 2008, 2010, 2012]
Entity Integrity: In a relational d ity i
: atabase, entit s ority T
records are duplicated and that no attributes thzlln“fm) 'S a property that ensures thatno
one‘ot the properties necessary (o ens...

  Q3: 9. Define the following: [MODEL QUESTION]
i) Derived attribute [
ii) Domain 4
iii) 1 to Many relationship ‘ :
iv) Projection |
v) Union compatibility E
Answer: :
i) Derived Attribute: a
The attribute values which are not a part of the entity but can be computed in association |
with some other stored attributes. It is not stored but can be computed...

  Q4: 13. What is the name of a trigger that triggers that triggers itself?
: . : ‘ [WBUT 2014, 2017}
\ a) Triggering trigger b) Cascading trigger
c) Mutating trigger d) None of the above
Answer: (b)
14, DML stands'for ' [WBUT 2015]
a) Data Manipulation Language b) Data Media Language
c) both (a) & (b) d) none of these
‘ Answer: (a)
15. Which data type c...

  Q5: 4. Consider the schema R=(S, T, U, V) and the dependencies |
S>T.T->UU—-VandV —>S. Let R= (Rl and R2) be a decomposition such |
that R1NR2 = 6. The decomposition is: [WBUT 2011] |
a) Not in 2NF b) In 2NF but not in 3NF
c) In 3NF but not in 2NF d) In both 2NF and 3NF
Answer: (c) |
5. R={1,J,K,L},F ={I > K,IL>J,JK - L, L — K}. The candidate keys are...

  Q6: 12. What are the advantages of normalization? [WBUT 2016]
Answer: :
Advantages of normalization
{_ Smaller database: By eliminating duplicate data, you will be able to reduce the overall
size of the database. -
2. Better performance:
a. Narrow tables: Having more fine-tuned tables allows your tables to have less columns
and allows you to fit more r...

  Q7: 24. Write short notes on the following:
a) Armstrong’s axioms [WBUT 2009, 2017]
b) Functional dependency ' [WBUT 2013]
¢) BCNF [WBUT 2018]
Answer
‘. ;) Ar mstrong’s Axioms (Inference Rules for FDs):
5 or any given relation, there can be many FDs. Let us denote F as the set of FDs of a
;{ Elven relation R. There can be many other FDs that can be der...

  Q8: 1. What is the difference between Primary index, Secondary index and Clustering
index? [(WBUT 2006, 2011]
' Answer:
Primary & Secondary Index:
Refer to Question No. 3(a) of Long Answer Type Questions.
Clustering Indexes .
If records of a file are physically ordered on a nonkey field, called the clustering field.
' We can create a clustering index t...

  Q9: 3. However, the leaf node are still required to be at least half full. ‘
4. Insertion and delethn from a B +-tree file organization are handled in the same way
as that in a B +-tree index. :
5, When a B +-tree Is used for file organization, space utilization is particularly
important. We can improve the space uilization by involving more sibling no...

  Q10: 6. Consider the file with » = 3000 records (fixed length) of size R = 100 bytes stored
on a disk with block size B = 1024 bytes. Suppose each index entry in index file
takes 15 bytes (9 bytes for index value, 5 bytes for pointer). What is the number of
accessing blocks for clustering index? [WBUT 2015]
Answer: .
Block Factor bfr = (B/R) =(1024/100)...

  Q11: 7. Write short notes on the following: |
a) B-tree !
p) File indexing [WBUT 2013, 2019]
c) B+ tree [WBUT 2016]
OR, [WBUT 2016]
B+ tree file organization
d) Ordered Index [WBUT 2018]
e) Primary Index and Secondary Index : IWVISH 20373
, [WBUT 2018]
Answer:
a) B-tree: .
. et andl fhase Revs pant i TREN non- eaf npde is one less than the number
| of i...

  Q12: 7. What do you mean by integrity constraint? [WBUT 2013, 2019]
Answer: ' i A . )
An integrity constraint defines a business ryle for a table column. When enabled. the rule
will be enforced by oracle ( and so will always be trye. ) To create an integrity constraint
all existing table data must satisfy the constraint -
Default valuc‘s are also subjec...

  Q13: 1. Explain the importance of view in providing security to the database. What are
the importance of GRANT and REVOKE commands? [MODEL QUESTION]
Answer: , ‘
1* Part: .
: Views can serve as security mechanisms by restricting the data available to users. Some
data can be accessible to users for query and modification, while the rest of the table or
da...

  Q14: 7. Define Data Warehouse and briefly describe its characteristics.
[MODEL QUESTION]
Answer; y f
A data warehouse consists of a computer database responsible for the collection and
storage of information for a specific organization. This collection of information is then {
Used to manage information efficiently and analyze the collected data. Althou...

  Q15: 6. What is Weak entity set? Explain with suitable example. ot 5}55’\\ 353
e ’ on o, . N NN
Ses Topiés ENTFTY-RELATIONSHIP MODEL, Short Ans#er TyRE SECc R
DBMSCS-149 X2
) See Topic: TRANSAC PROCESSING, Short Answer Type Question No. 2. PIIII
a) File indexing "figt?’i}:l?ﬁ
¢) Advantages of DBMS 209834
d) Database models A\};A 22
e) Inner join and Out...

  Q16: 3. Consider the following database with primary keys underlined 3{:%\;}5
Project (P — No, P — Name, P — incharge) 23 WD
Employee (E — no, E — Name) )\: e
Assigned-To (E — no, P.— no) {
Wirite relational algebra expression for the following: , , QA
(a) List detail of employee working on all projects. N
(b) List E — no, E — name of employee who do no...


======================================================================
  UNIT-7: Query Optimization & Advanced
======================================================================

  Q1: 1. Describe the three-schema i
archltectu(r)elgz [WBUT 2006]
Expiain in brief 3-schema architecture of DBMS. | [WBUT 2013]
a o)
Describe three layer architecture of DBMsR' . |
_ Oli [WBUT 2013]
Describe Three-Schem ; :
. a architectu
4
DBMSCS-2
DATABASE MANAGEMENT SYSTEMS
Answer:
Three Schema Architecture of DBMS
! Mapping supplied by.
CONCEPTUAL L...

  Q2: 2. What are the main functions of a database manager? List five major functions of
Data Base Administrator. [WBUT 2006]
OR,
Explain the roles of a database administrator (DBA). [WBUT 20089]
OR,
Discuss the role of DBA. | [WBUT 2017]
OR,
Explain the role of database administrator? [WBUT 2018]
Answer: . .
The functions of the DBA include the followin...

  Q3: 8. Write short note on Data Dictionary. [WBUT 2013]
Answer: ;
* Refer to Question No. 4(b) of Short Answer Type Questions. .!
]
:
_ DBMSCS-24
r’
l
F DATABASE MANAGEMENT SYSTEMS
; e —————————————————————————
E Multiple Choice Type Questions
\
| 1. Relational algebra is a [WBUT 2007, 2019]
'; a) procedural language b) non-procedural language
i c) que...

  Q4: 9. Define the following: [MODEL QUESTION]
i) Derived attribute [
ii) Domain 4
iii) 1 to Many relationship ‘ :
iv) Projection |
v) Union compatibility E
Answer: :
i) Derived Attribute: a
The attribute values which are not a part of the entity but can be computed in association |
with some other stored attributes. It is not stored but can be computed...

  Q5: 1. What is two phase locking protocol? [WBUT 2008, 2012, 20
i i ili ’ ' 17]
How does it guarantee serializability?
| ) OR, [WBUT 2008, 2017)] }
griefly explain two phase locking protocol, ‘
| OR, [WBUT 2015]
pescribe different 2PL protocol in brief. [WBUT 2018]
Answer:
Two-phase locking
According 1o ‘h? two-phase lgcking protocol, a transaction han...

  Q6: 5. What are the roles of the Analysis, Redo and Undo phases in the recovery
algorithm ‘ARIES’? [WBUT 2010, 2011, 2013, 2014, 20
Answer: ;
The ARIES recovery procedure consists of three main steps:
* Analysis: It identifies the dirty (updated) pages in the buffer and the set of
transactions active at the time of crash. The appropriate point in the l...

  Q7: 1. Explain the importance of view in providing security to the database. What are
the importance of GRANT and REVOKE commands? [MODEL QUESTION]
Answer: , ‘
1* Part: .
: Views can serve as security mechanisms by restricting the data available to users. Some
data can be accessible to users for query and modification, while the rest of the table or
da...

  Q8: 7. Define Data Warehouse and briefly describe its characteristics.
[MODEL QUESTION]
Answer; y f
A data warehouse consists of a computer database responsible for the collection and
storage of information for a specific organization. This collection of information is then {
Used to manage information efficiently and analyze the collected data. Althou...

  Q9: 3. Consider the following database with primary keys underlined 3{:%\;}5
Project (P — No, P — Name, P — incharge) 23 WD
Employee (E — no, E — Name) )\: e
Assigned-To (E — no, P.— no) {
Wirite relational algebra expression for the following: , , QA
(a) List detail of employee working on all projects. N
(b) List E — no, E — name of employee who do no...


======================================================================
  EXTRACTED MCQs (sample from raw text)
======================================================================
  a)6 b) 7 c)8 d) 3
  a) what files are in the database
  b) what attributes are possessed by the data
  c) what these files contain
  d) all of these .
  a) integrity constraint b) referential constraint
  c) over-defined constraint d) feasible constraint
  a) Metadata b) Teradata
  a) network model b) relational model
  c) hierarchical model d) file based system
  b) Number of Relation of an entity ll'et. n and number of entity of an entity-
  c) A ratio between number of relatio
  d) The numbsr of entities to which another entity can be associated via a
  a) ER diagram b) Records c) Relations d) Hierarchy
  a) meta data b) tera data c) hyper data d) none of these

======================================================================
  HIGH-FREQUENCY TOPICS (appearing across multiple years)
======================================================================
  index: 182 occurrences
  transaction: 169 occurrences
  log: 97 occurrences
  SELECT: 65 occurrences
  BCNF: 64 occurrences
  3NF: 62 occurrences
  view: 61 occurrences
  candidate key: 57 occurrences
  schema: 55 occurrences
  primary key: 49 occurrences
  keys: 45 occurrences
  SQL: 43 occurrences
  JOIN: 41 occurrences
  locking: 38 occurrences
  deadlock: 32 occurrences
  foreign key: 27 occurrences
  entity set: 23 occurrences
  2NF: 22 occurrences
  normal form: 22 occurrences
  recovery: 21 occurrences