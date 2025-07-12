# Exploring Database Constraints!

Hello, everyone! 🌟

Today, we’re diving into database constraints—the essential rules that help keep your data organized and reliable.

These constraints ensure that your database functions smoothly, preventing errors and maintaining data integrity.

To get started, check out this quick video that breaks it all down:

Video link: [Understanding Database Constraints](https://www.loom.com/share/adbca710fb6f45859218ee7a184cc708?sid=86efa6bf-ae21-457a-9cb9-52aac4b1bc5b)

# Deliverable:

After watching, complete the following questions.

    1 What is the purpose of the NOT NULL constraint in the Students table?

    2 Why was the PRIMARY KEY constraint implemented in the StudentID column?

    3 What problem does the FOREIGN KEY constraint solve in the Students table?

    4 In the context of the given scenarios, what issue arises from not using the NOT NULL constraint?

    5 How does the PRIMARY KEY constraint impact data integrity in the Students table?

    6 What does a FOREIGN KEY constraint do in the context of the Students table?

    7 What happens if a student is assigned to a ClassID that doesn’t exist in the Classes table?

    8 Why is it important to maintain valid relationships using FOREIGN KEY constraints?

    9 Which SQL statement correctly creates the Classes table with a primary key?

    10 Which of the following statements correctly implements a NOT NULL constraint on the FirstName column?

    11 We have two tables: Students and Classes like shown in the video.

    The Students table should include the following columns:

    StudentID: An integer that is the primary key.
    FirstName: A string (VARCHAR) that cannot be NULL.
    LastName: A string (VARCHAR) that cannot be NULL.
    ClassID: An integer that acts as a foreign key referencing the ClassID in the Classes table.
    The Classes table should include:

    ClassID: An integer that is the primary key.
    ClassName: A string (VARCHAR) representing the name of the class.

    What is the correct way to define a foreign key in the Students table that references the ClassID in the Classes table?
