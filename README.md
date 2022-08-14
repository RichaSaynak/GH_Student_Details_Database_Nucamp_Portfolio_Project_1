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