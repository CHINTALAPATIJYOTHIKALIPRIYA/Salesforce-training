
1. Difference Between:

App: The complete workspace or folder that holds everything for a specific job (like a "College Management" app).
Object: A specific list or table where you store data (like a list of "Students").
Record: One single item on that list (like one student named "Jyothi").
Field: One piece of specific information about that person (like their "Phone Number").

 2. Standard vs Custom Objects

Standard Objects: Built-in tables that Salesforce gives everyone, like Accounts and Contacts.
Custom Objects: New tables that I created myself to fit this project, like Student and Faculty.

3. Your College Data Model

Objects: Student, Faculty, Course, and Department.
Relationships:
  Department to Faculty: One-to-Many (A department has many teachers).
  Department to Course: One-to-Many (A department offers many classes).
  Course to Student: Many-to-Many (Many students can take many different courses).



 4. Formula Fields

Full Name: Automatically joins First Name and Last Name into one box.
Explanation: It makes work faster and stops people from making typing mistakes.


Pass/Fail Status: Automatically shows "Pass" if a score is above 40%.
Explanation: The system does the math instantly so teachers don't have to.


Days Until Course Starts: A countdown showing the days left until the start date.
Explanation: It provides real-time information that updates every day.



5. Validation Rules

Email Must Have @: Stops someone from saving a record if the email is missing the "@" symbol.
Problem Prevented: Stops fake or broken contact info from being saved.


Age Cannot Be Negative: Ensures a student's age is a real number (above 0).
Problem Prevented: Prevents "impossible" data that would mess up school reports.


Phone Number Length: Makes sure a phone number has exactly 10 digits.
Problem Prevented: Ensures we always have the correct way to contact a student.



6. Reflection

Why structured enterprise data matter:
Structured data is the foundation of a professional business. By using a system like Salesforce instead of a basic spreadsheet, we make sure that data is connected and follows strict rules. This turns a messy pile of information into a clean, powerful tool that helps a company run without making expensive manual errors.



Reflective Questions 

1. Why can’t companies manage everything using Excel? Excel is just a list that is easy to break. Salesforce connects data together like a web so it stays organized.
2. Why are relationships important between objects? They act like bridges. They connect a student to their specific teacher or course so you can see how everything fits together.
3. What problems happen if data is inconsistent? You get the wrong answers. If one person types "IT" and another types "Information Tech," the computer won't know they are the same.
4. Why should repetitive calculations be automated? To stop human errors. A computer will never make a math mistake when calculating a grade or a date.
5. Why should invalid data be blocked early? It is much easier to stop a mistake the second it is typed than to try and find and fix it months later.
6. Why is Salesforce called a metadata-driven platform? Because you can build apps by clicking buttons and choosing settings instead of writing thousands of lines of computer code.
