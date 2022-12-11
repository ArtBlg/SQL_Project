# SQL_Project

This database is a system for managing flight information at an airport. It has several tables:

1. The "terminals" table stores information about the different terminals at the airport. It has an auto-incrementing primary key "id" and a "name" for each terminal.

2. The "gates" table stores information about the gates at the airport. It has an auto-incrementing primary key "id", a "name" for each gate, and a "terminal_id" foreign key that references the "id" of the terminal that the gate belongs to.

3. The "destinations" table stores information about the different destinations that the airport's flights go to. It has an auto-incrementing primary key "id", an "iata_code" for each destination, a "name", and a "country".

4. The "airlines" table stores information about the different airlines that operate flights at the airport. It has an auto-incrementing primary key "id", an "icao_code" for each airline, a "name", and a "country".

5. The "planes" table stores information about the planes that the airlines use for their flights. It has an auto-incrementing primary key "id", a "registration" for each plane, a "plane_type", and an "airline_id" foreign key that references the "id" of the airline that the plane belongs to.

6. The "flights" table stores information about the flights that operate at the airport. It has an auto-incrementing primary key "id", an "airline_id" foreign key that references the "id" of the airline that operates the flight, a "flight_number", a "destination_id" foreign key that references the "id" of the destination that the flight goes to, "departure_time" and "arrival_time" timestamps, a "plane_id" foreign key that references the "id" of the plane that the flight uses, and a "gate_id" foreign key that references the "id" of the gate that the flight departs from.

7. The "passengers" table stores information about the passengers who are booked on flights. It has an auto-incrementing primary key "id", "first_name" and "last_name" for each passenger, an "email" and a "phone" number, a "passport_num" for passengers who are travelling internationally, and a "flight_id" foreign key that references the "id" of the flight that the passenger is booked on.

8. The "employees" table stores information about the employees who work at the airport. It has an auto-incrementing primary key "id", "first_name" and "last_name" for each employee, an "email" and a "phone" number, a "position" that describes the employee's job, and a "terminal_id" foreign key that references the "id" of the terminal that the employee works at.

## Airport departures table 
This query is selecting flight information from the "flights" table and joining it with information from the "airlines", "destinations", and "gates" tables. It is using table aliases to make the query more concise and easier to read.

The query is selecting the "flight_number" from the "flights" table, the "name" of the airline from the "airlines" table, the "name" of the destination from the "destinations" table, the "departure_time" from the "flights" table, and the "name" of the gate from the "gates" table. These columns are aliased as "flight_number", "airline", "destination", "departure_time", and "gate" respectively.

The query is using INNER JOINs to combine the data from the different tables. It is joining the "flights" table with the "airlines" table on the "airline_id" column, the "flights" table with the "destinations" table on the "destination_id" column, and the "flights" table with the "gates" table on the "gate_id" column.

The query is also using a WHERE clause to only include flights with a "departure_time" that is greater than the current time. This means that only future flights will be included in the result set.

Finally, the query is using an ORDER BY clause to sort the result set by the "departure_time" in ascending order. This means that the flights will be listed in order of their departure time, starting with the earliest flights.
