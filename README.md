# Student Management System

A MongoDB-based system to manage student records, courses, and enrollments. This project allows administrators and instructors to efficiently handle student information, course details, grades, and enrollments.

## Overview

The **Student Management System** is a backend application built using **MongoDB** as the database. It is designed to store and manage the following data:
- **Student Information**: Names, emails, and other personal details.
- **Courses**: Course names, IDs, durations, and descriptions.
- **Enrollments**: Student enrollment in various courses, along with grades.

This project helps demonstrate basic MongoDB CRUD operations (Create, Read, Update, Delete) and provides a simple interface to interact with the data.

## Features

- Add, update, and delete student records.
- Add and manage courses.
- Track student enrollment in courses.
- Update and manage grades for enrolled students.
- Query student and course data using MongoDB’s aggregation and lookup features.

## Technologies Used

- **MongoDB**: NoSQL database for storing student and course data.
- **JavaScript**: Programming language for both backend or frontend.


### Prerequisites

1. **Install MongoDB**: You need to have MongoDB installed compass and use MongoDB Shell.
   - For local installation, follow the official guide: [Install MongoDB](https://docs.mongodb.com/manual/installation/).
   - Alternatively, set up a free MongoDB cluster on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/StudentManagementSystem.git
cd StudentManagementSystem
```
# MongoDB Queries for Student Management System

Here are the common queries used in the Student Management System to manage student records, courses, and enrollments.

| **Operation**             | **Query**                                                                                                                                                      | **Description**                                                                            |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
| **Find All Students**      | ```javascript\n db.students.find() \n```                                                                                                                           | Retrieves all student records from the `students` collection.                             |
| **Find Specific Student**  | ```javascript\n db.students.find({studentId: 1}) \n```                                                                                                           | Retrieves a student with a specific `studentId` (e.g., `1`).                              |
| **Add a New Student**      | ```javascript\n db.students.insertOne({ fname: "John", lname: "Doe", email: "john.doe@example.com" }) \n```                                                      | Adds a new student record to the `students` collection.                                   |
| **Update Student Details** | ```javascript\n db.students.updateOne({ studentId: 1 }, { $set: { email: "new.email@example.com" } }) \n```                                                      | Updates the email of a student with `studentId: 1`.                                        |
| **Delete a Student**       | ```javascript\n db.students.deleteOne({ studentId: 1 }) \n```                                                                                                 | Deletes the student record with `studentId: 1`.                                            |
| **Find All Courses**       | ```javascript\n db.courses.find() \n```                                                                                                                           | Retrieves all courses from the `courses` collection.                                       |
| **Add a New Course**       | ```javascript\n db.courses.insertOne({ courseId: "C101", courseName: "Machine Learning", description: "Learn ML" }) \n```                                         | Adds a new course to the `courses` collection.                                            |
| **Update a Course**        | ```javascript\n db.courses.updateOne({ courseId: "C101" }, { $set: { description: "Advanced Machine Learning" } }) \n```                                          | Updates the course description for the course with `courseId: "C101"`.                   |
| **Delete a Course**        | ```javascript\n db.courses.deleteOne({ courseId: "C103" }) \n```                                                                                              | Deletes a course with `courseId: "C103"`.                                                 |
| **Enroll a Student**       | ```javascript\n db.enrollments.insertOne({ studentId: 1, courseId: "C101", grade: "B" }) \n```                                                                 | Adds an enrollment record for student `1` in course `C101` with a grade of `"B"`.          |
| **Update Student's Grade** | ```javascript\n db.enrollments.updateOne({ studentId: 1, courseId: "C101" }, { $set: { grade: "A+" } }) \n```                                                    | Updates the grade for a student in a particular course.                                   |
| **Delete Enrollment**      | ```javascript\n db.enrollments.deleteOne({ studentId: 1, courseId: "C101" }) \n```                                                                            | Removes an enrollment record for a student in a specific course.                         |
| **Count Enrolled Students**| ```javascript\n db.enrollments.countDocuments({ courseId: "C101" }) \n```                                                                                      | Returns the number of students enrolled in the course `C101`.                             |
| **Find Students in Course**| ```javascript\n db.enrollments.find({ courseId: "C101" }).forEach(e => printjson(e)) \n```                                                                     | Finds and prints all students enrolled in the course `C101`.                              |
| **Find All Enrollments**   | ```javascript\n db.enrollments.find() \n```                                                                                                                      | Retrieves all enrollment records from the `enrollments` collection.                       |
| **Aggregate Students by Grade**| ```javascript\n db.enrollments.aggregate([ { $group: { _id: "$grade", totalStudents: { $sum: 1 } } } ]) \n```                                                   | Aggregates students based on their grade and counts how many students have each grade.    |

---

## Usage Examples:

### Find All Students
This query retrieves all student records from the `students` collection:

```javascript
db.students.find()
```



This format helps present your queries clearly and gives others an easy-to-follow reference for understanding the operations used in your project.

Let me know if you need any additional modifications or explanations! 😊




