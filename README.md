# Campus Course & Records Manager (CCRM)

A console-based **Java SE project** for managing students, courses, enrollments, grades, transcripts, and file utilities.  
This project demonstrates **OOP principles, Java Streams, NIO.2, Date/Time API, exception handling, design patterns (Singleton, Builder), enums, and recursion**.

---

## 🚀 Features

### 1. Student Management
- Add, list, update, deactivate students
- Print student profile & transcript

### 2. Course Management
- Add, list, update, deactivate courses
- Search & filter (by instructor, department, semester) using **Streams API**

### 3. Enrollment & Grading
- Enroll/Unenroll students into courses
- Business rules: max credits per semester
- Record marks & compute GPA
- Enum `Grade` & `Semester`
- Transcript generation (using `toString()` + polymorphism)

### 4. File Operations (NIO.2)
- Import/Export CSV files
- Export students, courses, enrollments
- Backup exported files into **timestamped folders**
- Recursive utility → compute backup folder size

### 5. CLI Workflow
- Menu-driven interface with loops, switch, break/continue
- Options: Students, Courses, Enrollments, Grades, Import/Export, Backup, Reports, Exit

---

## 🛠️ Tech Stack

- **Java SE 24**
- **Maven 3.9+**
- Uses: Java Streams, NIO.2, Date/Time API, OOP principles, Design Patterns

---

## 📂 Project Structure

edu.ccrm
├─ cli/ # CLI menu & input handling
├─ config/ # AppConfig (Singleton)
├─ domain/ # Person, Student, Instructor, Course, Enrollment, Enums
├─ service/ # StudentService, CourseService, EnrollmentService, DataStore
├─ io/ # Import/Export CSV, Backup utilities
├─ util/ # ConsoleUtils, IdGenerator
└─ exceptions/ # Custom exceptions

yaml
Copy code

---

## ▶️ How to Run

### Prerequisites
- Java 24+
- Apache Maven 3.9+

### Steps
```bash
# Clone repository
git clone https://github.com/<your-username>/ccrm.git
cd ccrm

# Compile
mvn clean compile

# Run
mvn exec:java -Dexec.mainClass="edu.ccrm.cli.Main"
📊 Sample Workflow
Add a student

Add a course

Enroll student into course

Record marks

Print transcript & GPA

Export data to CSV

Backup CSV files into timestamped folder

Reports → Top students by GPA

📂 Test Data
Inside test-data/ folder:

students.csv

csv
Copy code
id,regNo,fullName,email
s1,REG001,Ravi Pal,ravi@example.com
s2,REG002,Anita Sharma,anita@example.com
courses.csv

csv
Copy code
code,title,credits,instructor,semester,department
CS101,Intro to CS,4,Dr. A,SPRING,CSE
MA101,Calculus,3,Dr. B,FALL,Math
📷 Screenshots (to add)
Java version check

Eclipse/IntelliJ setup

CLI menu output

Exported CSV files

Backup folder with timestamp

📖 Academic Notes
Evolution of Java
1995 – Java 1.0 released by Sun Microsystems

2004 – Java 5.0 (Generics, Enums)

2011 – Java 7 (NIO.2 API)

2014 – Java 8 (Streams, Lambdas)

2017 – Java 9 (Modules)

2021 – Java 17 LTS

2025 – Java 24 (latest in use)

Java ME vs SE vs EE
Edition	Use Case	Example
Java ME	Embedded & Mobile devices	Smartcards, IoT
Java SE	Core desktop applications	CCRM project
Java EE	Enterprise/web apps	Banking, E-commerce

JDK, JRE, JVM
JDK – Development kit (compiler + tools + JRE)

JRE – Runtime environment (JVM + libraries)

JVM – Virtual Machine executing bytecode

🧪 Mapping Syllabus → Code
Requirement	Location
Encapsulation	Student.java (private fields + getters/setters)
Inheritance	Person.java → Student, Instructor
Abstraction	Person.profile()
Polymorphism	Person p = new Student(...)
Enums	Grade.java, Semester.java
Streams API	reportsFlow() in Main.java
Recursion	BackupService.computeSizeRecursively()
Builder Pattern	Course.Builder
Singleton Pattern	AppConfig, DataStore
Custom Exceptions	DuplicateEnrollmentException, MaxCreditLimitExceededException
NIO.2	ImportExportService, BackupService
