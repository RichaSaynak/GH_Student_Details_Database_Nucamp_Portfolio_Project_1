# GH_Student_Details_Database_Nucamp_Portfolio_Project_1


For my Portfolio Project, I am working on creating a database storing students online course details.

Currently , I have created 6 tables in the database.

1. Student_Account - Storing student's username and password
2. Student - Storing name, address , email, foreign key referring to user_id of Student_Account Table
3. Course - Storing course name
4. Instructor - Storing instructor name and foreign key referring to course_id of Course Table
5. Grade - For storing grades of the students for the course. It is an Intermediate table for the Many to Many relationship between STudent and Course. Grades is an extra column( field ) in the Many Many Relationship Table.
6. Attendance - For storing Date and whether the student attended the course on that date. It is another Intermediate table for the same Many to Many relationship between Student and Course. I made second Intermediate table because I was not able to store grades, date and attendance confirmation in the same table as date is a column where the date will change everyday whereas Grade is something that will be written just once.


Right now , I have just added these few tables, but will expand this project further later.


I have done Unit testing for all the urls and Integration  testing for all the tables created.
In integration testing, I have done testing for inserting records into the tables, checking if the records exists after insertion, whether we can update the records and comparing whether 2 records inserted have different primary keys.

To check the tests , please run pytest -v in the /app folder


# students_database_django_workflow


1. https://github.com/RichaSaynak/students_database_django_workflow . This is the workflow that I have created for building and testing my student database  project.
2. I have created this workflow in the app folder as I was having some issues when I created in this main folder ( 1 folder up the App folder ).
3. So, I have created  another repository for the workflow where I created the workflow in my app folder . This is the repository - https://github.com/RichaSaynak/students_database_django_workflow . Here the workflow runs successfully.
4. I tried running the workflow from this repository by writing cd app but it was giving me different types of errors. So created a new repository for the app folder.
5. As I was short of time couldn't investigate further.






vvvvvvvvvvvvvvvvv
