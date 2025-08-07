<img width="844" height="957" alt="image" src="https://github.com/user-attachments/assets/d0de5ca0-df9f-48fc-be20-46a58a8d3e37" /># Oracle-SQL

[Agenda]
1. Introduction
2. Creation of Tables
3. Oracle setup and installation
4. Relational Model
5. Miscellaneous Topics
6. Operators as keywords
7. Functions
8. Clauses
9. Nested Query
10. SQL Commands
11. Database Objects and SP



**1. Introduction**

Database = Group of Information
>In 1960s, High level programming language developers suggested to make a use of programming languages to manage(store and retrive)the Facts and Figure.
>In programming language there is a concept called datatypes,variables and arrays. One can make a use of it and can store facts and figures.
>People were very happy because computers do not hava a disadvantage like LEDGERS, and now they have a why to store facts and figure in the computers and they did that using the programming language.
>But as the size of facts and the figure increased, programming languages failed to manage it.
>Programming language are successful only to manageing (Storeing and retriving) data (small volumns of facts and figures) but not database(Large volumn of facts and figure).


**DBMS(DATABASE MANAGEMENT SYSTEM)**
It is a software which is used to (manage)store data permanently and retrive the large amount of data efficiently.
for eg: Oracle, MySQL, DB2, Informix etc...

**2. Creation of Tables**
    1. Creation of Table:

      CREATE TABLE Student
      (
      ID number(10),
      Name varchar2(30),
      Age number,
      Gender varchar2(6),
      Marks number,
      SEM number
      );

    2. Now, Let's see how to insert the data into the table:

      INSERT INTO Student VALUES(52, 'AMAN', 26, 'MALE', 98, 8);
      INSERT INTO Student VALUES(52, 'MOHAN', 27, 'MALE', 94, 8);


**3. Oracle setup and installation**
git clone  https://github.com/oracle/docker-image

./buildContainerImage.sh -v 19.3. 0 -e

docker run -d --name oracle19 -e ORACLE_PWD=mypassword1 -p 1521:1521 oracle/database:19.3.0-ee 


rm -rf ~/Library/Application\ Support/Code
rm -rf ~/.vscode

https://code.visualstudio.com/


git config --global user.name "Anee"
git config --global user.email "thapaanita1111@gmail.com"


docker exec -it <container_name> bash
lsnrctl status




**4. Relational Model**

<img width="914" height="955" alt="image" src="https://github.com/user-attachments/assets/87e97e82-ea41-4a90-8edd-7a5d8316960d" />

    1. Relation = Table
    2. Tuple = A Row or a record in a relation
    3. Attribute = A feild or a column in a relation
    4. Cardinality of a relatuin = The number of tuple in a relation
    5. Degree of a relation = The number of attribute in a relaion
    6. Primary Key of a relation = An Attribute or a combination of atteributes that uniquely defines each tuple in a relation
    7. Foreign key = An Attribute or a combination of attributes in one relation R1 that indicates the relationship of R1 with another relation R2. The foreign kry attributes inR1 must contain values maching with those of the valuesin R2
     
**5. Miscellaneous Topics:**
  > Projection:
     Projection means choosing which columns (or expressions) the query shall return. Projection is the process of displaying the result using project queries. Project queries are all those queries which is used to display(project) particular columns  to the user based on the requirement from user. 
  >  Selection:
     Selection means which rows are to be returned. Selection is the process of displaying the result using select queries. Select queries are those queries which display particular rows to the users base on specific conditions.
  > Case Sensitivity in SQL:  
    The SQL keywords are case-insensitive (SELECT, FROM, WHERE, AS, ORDER BY, HAVING, GROUP BY, etc), but are usually written in all capitals.
            1. KEYWORDS IN SQL IS NOT CASE SENSITIVE.
            2. TABLE NAME IN SQL ARE NOT CASE SENSITIVE.
            3. COLUMN NAME IN SQL ARE NOT CASE SENSITIVE.
            4. DATA IN SQL IS CASE SENSITIVE.
<img width="1522" height="1005" alt="image" src="https://github.com/user-attachments/assets/c6779c2d-364a-49f2-bdd3-d2cdf02e9560" />
    > DataTypes:
        A data type specifies a particular types of data, such as integer, floating-point, Boolean etc.




















































