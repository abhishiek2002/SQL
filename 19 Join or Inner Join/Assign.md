Hey there!

# Watch the following video

Video Link:

[Joins](https://www.loom.com/share/2b5185aabe714cbbbf7729c753dbe313?sid=3a03c0ea-c17f-40b5-a0d8-782c06e977e3)

[Different Types of Joins](https://www.loom.com/share/440045ccd0a142a18e8a25a9e2869875?sid=622a5ca5-c335-4eb3-9dd8-35b93f0ec24f)

to understand how SQL JOINs work and how they help you combine data from multiple tables.

This clause is essential for retrieving related data from two or more tables, allowing you to combine records based on common columns.

Pay close attention to how different types of joins—**INNER JOIN, LEFT JOIN, RIGHT JOIN, FULL JOIN, and SELF JOIN**—are used in various scenarios to link data and retrieve meaningful results.

Once you've finished watching, complete the questions below to test your understanding of the different types of joins in SQL.

## Deliverables:

### Hotel Reservation System

You are managing the database for a hotel reservation system. The system tracks hotel guests, room bookings, and hotel staff.

The database consists of the following tables:

    Guests Table: Stores guest details, including guest ID, name, and contact information.
    Rooms Table: Stores room details, including room ID, type of room, and price.
    Reservations Table: Stores details about room bookings, including reservation ID, guest ID, room ID, and reservation date.
    Staff Table: Stores details of the hotel staff, including staff ID, name, and position.

### INNER JOIN

    You are tasked with retrieving the names of guests and the room type they have reserved, but only for guests who have actually made a reservation.

### Write an SQL query to retrieve the names of guests and the room ID they have reserved.

#### Sample Input

Guests Table:

guest_id | name | contact_info

    1 | John Doe | john.doe@gmail.com

    2 | Mary Jane | mary.jane@yahoo.com

    3 | James Smith | james.smith@outlook.com

Reservations Table:

reservation_id | guest_id | room_id | reservation_date

    1 | 1 | 2 | 2024-10-05

    2 | 2 | 3 | 2024-10-06

#### Sample Output

guest_name | reserved_room_id

    John Doe | 2

    Mary Jane | 3

# Query Code

```sql
-- CREATE TABLE Guests (
--     GuestID INT PRIMARY KEY,
--     Name VARCHAR(50),
--     Contact VARCHAR(50)
-- );

-- CREATE TABLE Reservations (
--     ReservationID INT PRIMARY KEY,
--     GuestID INT,
--     RoomID INT,
--     ReservationDate DATE
-- );

--Write your code here

select Guests.Name, Reservations.RoomID from Guests join Reservations on Guests.GuestID = Reservations.GuestID;
```
