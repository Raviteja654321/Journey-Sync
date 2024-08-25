# Journey-Sync

A command-line interface (CLI) for managing and querying information related to a bus travel agency. The system interacts with a MySQL database to retrieve and manipulate data related to passengers, buses, drivers, and ticket prices.

## Features

- **Search by Passenger ID:** Retrieve passengers whose Passenger ID contains a specific subpart.
- **Search Buses by State:** Retrieve all buses operating in a specific state.
- **Search Drivers by ID:** Retrieve driver names whose ID ends in a specific digit.
- **Max Journeys:** Retrieve the passenger with the maximum number of journeys.
- **Journey Analysis:** Retrieve the sum, count, and average of journeys done by passengers in a specific age range.
- **Passengers with Min Journeys:** Retrieve passengers who have taken more than a certain number of journeys.
- **Add New Bus:** Add details of a new bus to the system.
- **Add Passenger Details:** Add new passenger details to the database.
- **Remove Driver:** Remove a driver from the database.
- **Update Ticket Prices:** Update ticket prices for sleeper and seater seats based on the category of the day.

## Prerequisites

To run this project, you will need to have the following installed:

- Python 3.x
- MySQL Server
- `pymysql` library (install using `pip install pymysql`)
- `prettytable` library (install using `pip install prettytable`)

## Database Setup

1. Set up a MySQL database named `Project`.
2. Create the necessary tables for `PASSENGERS`, `BUSES`, `DRIVERS`, and `TICKET_PRICES`.
3. Populate the tables with the required data.

Example SQL schema:

```sql
CREATE TABLE PASSENGERS (
    Pr_ID INT PRIMARY KEY,
    Pr_Name VARCHAR(100),
    Age INT,
    Gender VARCHAR(10),
    Journeys INT
);

CREATE TABLE BUSES (
    Bus_ID INT PRIMARY KEY,
    State VARCHAR(50),
    Number_assigned INT,
    AC VARCHAR(10),
    nSeater_seats INT,
    nSleeper_seats INT,
    Total INT
);

CREATE TABLE DRIVERS (
    Driver_ID INT PRIMARY KEY,
    Dr_Name VARCHAR(100)
);

CREATE TABLE TICKET_PRICES (
    Category_of_day VARCHAR(50) PRIMARY KEY,
    Sleeper_price INT,
    Seater_price INT
);
```

## How to Run

1. Clone the repository.
2. Ensure the MySQL database is set up and running.
3. Update the database connection details in the script if needed (`host`, `port`, `user`, `password`, `db`).
4. Run the script:

```bash
python3 main.py
```

5. Use the CLI menu to interact with the system.

## Usage

Once the script is running, you can perform various operations such as retrieving passenger and bus details, updating ticket prices, or adding new records to the database. The menu-driven interface allows you to select operations easily.

## Error Handling

The system includes basic error handling to rollback transactions and notify the user in case of any issues during database operations.
