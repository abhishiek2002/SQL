# Understanding Joins through Hotel Reservation System

You are managing the database for a hotel reservation system. The system tracks hotel guests, room bookings, and hotel staff. The database consists of the following tables:

    Guests Table: Stores guest details, including guest ID, name, and contact information.
    Rooms Table: Stores room details, including room ID, type of room, and price.
    Reservations Table: Stores details about room bookings, including reservation ID, guest ID, room ID, and reservation date.
    Staff Table: Stores details of the hotel staff, including staff ID, name, and position.

## Deliverables:

Retrieve a list of all guests and the room type they reserved, even if a guest hasn’t made a reservation yet.

### Sample Input:

Guests Table:

GuestID|Name|Contact

    1|John Doe|john.doe@gmail.com

    2|Mary Jane|mary.jane@yahoo.com

    3|James Smith|james.smith@outlook.com

Rooms Table:

RoomID|RoomType|Price

    1|Single|100

    2|Double|150

    3|Suite|300

Reservations Table:

ReservationID|GuestID|RoomID|ReservationDate

    1|1|2|2024-10-05

    2|2|3|2024-10-06

### Expected Output:

GuestName|RoomType

    John Doe|Double

    Mary Jane|Suite

    James Smith|NULL

# Query Code

```sql
-- -- Create Guests Table
-- CREATE TABLE Guests (
--     GuestID INT PRIMARY KEY,
--     Name VARCHAR(50),
--     Contact VARCHAR(50)
-- );

-- -- Create Rooms Table
-- CREATE TABLE Rooms (
--     RoomID INT PRIMARY KEY,
--     RoomType VARCHAR(50),
--     Price INT
-- );

-- -- Create Reservations Table
-- CREATE TABLE Reservations (
--     ReservationID INT PRIMARY KEY,
--     GuestID INT,
--     RoomID INT,
--     ReservationDate DATE
-- );

-- Wrtie your code here

select Guests.Name, Rooms.RoomType from Guests left join Reservations on Reservations.GuestID = Guests.GuestID left join Rooms on Reservations.RoomID = Rooms.RoomID;
```
