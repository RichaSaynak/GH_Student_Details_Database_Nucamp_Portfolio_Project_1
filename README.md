# GH_Student_Details_Database_Nucamp_Portfolio_Project_1


For my Portfolio Project, I created a database storing students online course details. 

# Technologies used

Technologies used -
1. Django
2. Docker
3. Postgresql
4. Pgadmin
5. Insomnia
6. Git Workflow - for building and testing
7. Deployed to Google Cloud
8. Created unit and integration testing using pytests

I have not worked on the Front End part of the Project ( HTML, CSS , React, etc) as I am yet to learn that. So, I have used the basic Front End template as used in the workshops. I have used Insomnia to check the endpoints.

# Tables brief information
Currently , I have created 6 tables in the database.

1. Student_Account - Storing student's username and password
2. Student - Storing name, address , email, foreign key referring to user_id of Student_Account Table
3. Course - Storing course name
4. Instructor - Storing instructor name and foreign key referring to course_id of Course Table
5. Grade - For storing grades of the students for the course. It is an Intermediate table for the Many to Many relationship between STudent and Course. Grades is an extra column( field ) in the Many Many Relationship Table.
6. Attendance - For storing Date and whether the student attended the course on that date. It is another Intermediate table for the same Many to Many relationship between Student and Course. I made second Intermediate table because I was not able to store grades, date and attendance confirmation in the same table as date is a column where the date will change everyday whereas Grade is something that will be written just once.


Right now , I have just added these few  relationships and tables as I was short of time, but will expand this project further in future.


# Relationships between tables

The relationships between the tables are as follows-
1. Many to Many relationship - between Student and Course table. There are extra fields such as grades received and attendance record. I have created two different intermediate tables as mentioned above.
2. Many to One Relationship - between Course and Instructor tables. Here , we have considered that 1 course can be taught by many instructors but one instructor can teach only one course.
3. One to One Relationship - between Student and STudent Account


I have attached the ER diagram - student_database_ER_diagram.


# Information about the table columns -

1. Student_Account Table
Columns - ID, username(unique and not null), password(not null). 

2. Student Table
Columns - ID, student_name, student_address, student_email (unique), student_account_id(foreign key referring to Student_Account table).
All fields are not null

3. Course Table
Columns - ID, course_name(unique and not null)

4. Instructor Table
Columns - ID, instructor_name, instructor_short_id(unique and not null), course_id(foreign key referring to Course table)
All fields are not null

5. Grade Table - Intermediate Many-Many Relationsgip Table between Student and Course
Columns- student_id,  course_id, grade_received
All fields are not null. 


6. Attendance Table - Intermediate Many-Many Relationsgip Table between Student and Course
Columns- student_id,  course_id, date_of_attendance, attended_question
All fields are not null




# API Endpoints information- 

Below are the API Reference Table of endpoint paths, methods, parameters. I have also provided the Insomnia Request Collection Export .

API Endpoints information- 

For Student_Account table
Base_url = http://127.0.0.1:8000/student_accounts/

1. POST - http://127.0.0.1:8000/student_accounts/api/student_accounts/              - Adds student accounts
2. GET -  http://127.0.0.1:8000/student_accounts/api/student_accounts/              - Get all the accounts
3. DEL -  http://127.0.0.1:8000/student_accounts/api/student_accounts/              - Delete all the accounts
4. GET -  http://127.0.0.1:8000/student_accounts/api/student_accounts/<int:pk>/     - Get accounts by primary key id
5. PUT -  http://127.0.0.1:8000/student_accounts/api/student_accounts/<int:pk>/     - Update account by primary key id 
6. DEL -  http://127.0.0.1:8000/student_accounts/api/student_accounts/<int:pk>/     - Delete account by ID


For Student table
Base_url = http://127.0.0.1:8000/

1. POST - http://127.0.0.1:8000/api/students/   				                        - Add students
2. GET -  http://127.0.0.1:8000/api/students/   				                        - Get all the students
3. DEL -  http://127.0.0.1:8000/api/students/   				                        - Delete all the students
4. GET -  http://127.0.0.1:8000/api/students/<int:pk>/  			                    - Get students by primary key id
5. PUT -  http://127.0.0.1:8000/api/students/<int:pk>/   			                    - Update student by primary key id 
6. DEL -  http://127.0.0.1:8000/api/students/<int:pk>/   			                    - Delete student by primary key id 
7. GET -  http://127.0.0.1:8000/api/students/address/<str:address>/ 	                - Get the list of students with the same address

For Grade Table
Base_url = http://127.0.0.1:8000/

1. POST - http://127.0.0.1:8000/api/grades/ 					- Add grades
2. GET -  http://127.0.0.1:8000/api/grades/  					- Get all the grades
3. DEL -  http://127.0.0.1:8000/api/grades/ 					- Delete all the grades
4. GET -  http://127.0.0.1:8000/api/grades/<int:pk>/  			- Get grades by primary key id
5. PUT -  http://127.0.0.1:8000/api/grades/<int:pk>/   			- Update grade by primary key id 
6. DEL -  http://127.0.0.1:8000/api/grades/<int:pk>/   			- Delete grade by primary key id 


For Attendance Table
Base_url = http://127.0.0.1:8000/

1. POST - http://127.0.0.1:8000/api/attendances/ 					    - Add attendances
2. GET -  http://127.0.0.1:8000/api/attendances/  					    - Get all the attendances
3. DEL -  http://127.0.0.1:8000/api/attendances/ 					    - Delete all the attendances
4. GET -  http://127.0.0.1:8000/api/attendances/<int:pk>/  				- Get attendances by primary key id
5. PUT -  http://127.0.0.1:8000/api/attendances/<int:pk>/   			- Update attendance by primary key id 
6. DEL -  http://127.0.0.1:8000/api/attendances/<int:pk>/   			- Delete attendance by primary key id 



For Course Table
Base_url = http://127.0.0.1:8000/courses/

1. POST - http://127.0.0.1:8000/courses/api/courses/ 						- Add courses
2. GET -  http://127.0.0.1:8000/courses/api/courses/  					    - Get all the courses
3. DEL -  http://127.0.0.1:8000/courses/api/courses/ 						- Delete all the courses
4. GET -  http://127.0.0.1:8000/courses/api/courses/<int:pk>/  				- Get courses by primary key id
5. PUT -  http://127.0.0.1:8000/courses/api/courses/<int:pk>/   			- Update course by primary key id 
6. DEL -  http://127.0.0.1:8000/courses/api/courses/<int:pk>/   			- Delete course by primary key id 


For Instructor Table

Base_url = http://127.0.0.1:8000/instructors/

1. POST - http://127.0.0.1:8000/instructors/api/instructors/ 						    - Add instructors
2. GET -  http://127.0.0.1:8000/instructors/api/instructors/  						    - Get all the instructors
3. DEL -  http://127.0.0.1:8000/instructors/api/instructors/ 						    - Delete all the instructors
4. GET -  http://127.0.0.1:8000/instructors/api/instructors/<int:pk>/  					- Get instructors by primary key id
5. PUT -  http://127.0.0.1:8000/instructors/api/instructors/<int:pk>/   				- Update course by primary key id 
6. DEL -  http://127.0.0.1:8000/instructors/api/instructors/<int:pk>/   				- Delete course by primary key id 
7. GET -  http://127.0.0.1:8000/instructors/api/instructors/course/<int:course_id>/		- Gives the list of teachers teaching 1 course by using the course_id




# Unit Testing and Integration Testing
I have done Unit testing for all the urls and Integration  testing for all the tables created.Fpr Integration testing , I have done with and without fixtures.
In integration testing with fixtures, I have done testing for inserting records into the tables, checking if the records exists after insertion, whether we can update the records and comparing whether 2 records inserted have different primary keys.

To check the tests , please run pytest -v in the /app folder


# Git Workflow - for automating building and testing

I have created this students_database_django_workflow ( https://github.com/RichaSaynak/students_database_django_workflow ) to automate building and testing my student database app. You can find the main.yml file in the .github/workflows inside the app folder. It works.

1. I have created this workflow in the app folder as I was having some issues when I created in the main folder ( 1 folder up the App folder ).
2. So, I have created  this repository for the workflow where I created the workflow in my app folder . This is the repository - https://github.com/RichaSaynak/students_database_django_workflow . Here the workflow runs successfully after every push and pull.
3. I tried running the workflow from this cuurent main repository ( https://github.com/RichaSaynak/GH_Student_Details_Database_Nucamp_Portfolio_Project_1.git ) by writing cd app but it was giving me different types of errors. So created a new repository for the app folder.
4. As I was short of time couldn't investigate further.


# Deployed to Google Cloud

I have deployed my project to Google Cloud and it works .

Below are the links. As mentioned earlier , I have not worked on the Front End Part as I am yet to learn it , so used the Front End part from the Workshop's Tutorial  application.

https://portfolioprojectcloud-dmm3mqgx6q-uc.a.run.app                                              - Will display all the Students
https://portfolioprojectcloud-dmm3mqgx6q-uc.a.run.app/student_accounts/                            - Will display all the student accounts
https://portfolioprojectcloud-dmm3mqgx6q-uc.a.run.app/courses/                                     - Will display all courses
https://portfolioprojectcloud-dmm3mqgx6q-uc.a.run.app/instructors/                                 - Will display all instructors
https://portfolioprojectcloud-dmm3mqgx6q-uc.a.run.app/api/grades/                                  - Will display the grades received
https://portfolioprojectcloud-dmm3mqgx6q-uc.a.run.app/api/attendances/                             - Will display the attendance record


I will attach the Insomnia Request Collection for the POST methods. As, I have alreday shared many different methods and endpoints above, I won't be repeating again here.



# Challenges faced

I faced many difficulties while doing this project and so I am very happy to finally complete it. It was a great learning experience. Next in the future, will work on the Front End part.

1. I had to to brainstorm the diffrent tables that will be present in my student database and what will be the relationship between them ( Many-to-Mnay, etc.). It took time and research to finally narrow down on the present design.
2. I had created the flask project for the SQL course but I also wanted to do it with django, so again created the database with django.
3. Working with ORM was challenging as compared to Raw SQL. Had to google and research the syntax.
4. Django doesn't have validation for duplicates for the many to Many Intermediate Table with extra fields. So as I had to put the validation code myself in the views.py file.
5. I got multiple issues while testing the API endpoints. I ggogled the errors and solved them.
6. I had issues while creating integration tests for tables which had foreign keys. I googled and got the answers.
7. I had issues while creating the Git workflow. The migration run check was failing. Again googled, researched and got the answers.
8. I have created GIT workflow in the app folder as I was having some issues when I created in the main folder ( 1 folder up the App folder ,the one with docker-compose file ).So, I have created the repository for the workflow where I created the workflow in my app folder.





