# Understanding RIGHT JOINs through Hotel Reservation System

You are managing the database for a hotel reservation system. The system tracks hotel guests, room bookings, and reservations. The database consists of the following tables:

    Rooms Table: Stores room details, including room ID, type of room, and price.
    Reservations Table: Stores details about room bookings, including reservation ID, guest ID, room ID, and reservation date.

## Deliverables:

### Question:

Write a query to display all reservations and their corresponding room details.

If a reservation references a room that does not exist in the Rooms table, the reservation should still be included in the output, with NULL for room details.

### Sample Input:

#### Rooms Table
RoomID|RoomType|Price

    1|Single|100

    2|Double|150

    3|Suite|300

#### Reservations Table
ReservationID|GuestID|RoomID|ReservationDate

    1|101|2|2024-10-05

    2|102|4|2024-10-07

### Expected Output
ReservationID|RoomType|ReservationDate

    1|Double|2024-10-05

    2|NULL|2024-10-07


# Query Code

```sql
select ReservationID, RoomType, ReservationDate from Rooms Right Join Reservations on Rooms.RoomID = Reservations.RoomID;
```