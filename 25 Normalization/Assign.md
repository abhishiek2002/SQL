# SELF JOIN

Watch this video to understand how the SELF JOIN works in SQL.

Video Link: [Self Joins](https://www.loom.com/share/4c390624a6c54de6a1cb17081c33d7a0?sid=5354a4dc-165e-4c83-a4a2-9ab93e873356)

A SELF JOIN is a join where a table is joined with itself. This is useful for comparing rows within the same table, such as finding pairs of employees in the same department or customers with the same contact information.

## Understanding FULL JOINs through Hotel Reservation System

You are managing the database for a hotel reservation system. The system tracks hotel guests, room bookings, and hotel staff. The database consists of the following tables:

    Guests Table: Stores guest details, including guest ID, name, and contact information.
    Rooms Table: Stores room details, including room ID, type of room, and price.
    Reservations Table: Stores details about room bookings, including reservation ID, guest ID, room ID, and reservation date.
    Staff Table: Stores details of the hotel staff, including staff ID, name, and position.

## Deliverables:

You are working with a database of guests at a hotel. Sometimes, there are duplicate entries or family members who share the same contact information.

**Write an SQL query to retrieve pairs of guests who have the same contact information**

    Note: To avoid duplicate pairs, use aliases for the table (e.g., g1 and g2). Join the table with itself on a condition that ensures you're comparing different rows, such as g1.GuestID != g2.GuestID. You can also use g1.GuestID < g2.GuestID to ensure each pair appears only once.

### Guests Table:

GuestID|Name |Contact

    1 |John Doe |john.doe@gmail.com

    2 |Mary Jane |mary.jane@yahoo.com

    3 |James Smith |james.smith@outlook.com

    4 |John Doe |john.doe@gmail.com

    5 |Anna Johnson |anna.johnson@gmail.com

    6 |James Smith |james.smith@outlook.com

### Expected Output:

Guest1Name|Guest2Name |Contact

    John Doe |John Doe |john.doe@gmail.com

    James Smith|James Smith|james.smith@outlook.com

# Query Code:

```sql
-- -- Create Guests Table
-- CREATE TABLE Guests (
--     GuestID INT PRIMARY KEY,
--     Name VARCHAR(50),
--     Contact VARCHAR(50)
-- );

-- Write your code here

select g1.Name as Guest1Name, g2.Name as Guest2Name, g1.Contact from Guests g1 join Guests g2 on g1.Contact = g2.Contact and not g1.GuestID = g2.GuestID and g1.GuestID < g2.GuestID;
```
