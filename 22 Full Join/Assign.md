# Deliverables:
## Question:

Write an SQL query to display all guests and all rooms, including guests without a reservation and rooms without any bookings.

### Guests Table:

GuestID|Name|Contact

    1|John Doe|john.doe@gmail.com

    2|Mary Jane|mary.jane@yahoo.com

    3|James Smith|james.smith@outlook.com

### Rooms Table:

RoomID|RoomType|Price

    1|Single|100

    2|Double|150

    3|Suite|300

### Reservations Table:

ReservationID|GuestID|RoomID|ReservationDate

    1|1|2|2024-10-05

## Expected Output:

GuestName|RoomType|ReservationDate

    John Doe|Double|2024-10-05

    Mary Jane|NULL|NULL

    James Smith|NULL|NULL

    NULL|Single|NULL

    NULL|Suite|NULL


# Query Code

```sql
select Guests.Name as Name, RoomType, ReservationDate from Guests Full Join Reservations on Guests.GuestID = Reservations.GuestID full join Rooms on Reservations.RoomID = Rooms.RoomID;
```