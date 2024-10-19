# Registration System

This project implements a simple registration system using Oracle SQL. It includes a SQL table for storing registration information and PL/SQL procedures for performing CRUD (Create, Read, Update, Delete) operations.

## Table of Contents

- [Features](#features)
- [Technologies Used](#technologies-used)
- [Database Setup](#database-setup)
- [CRUD Operations](#crud-operations)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Features

- Create a new registration entry.
- Read registration details by ID.
- Update existing registration information.
- Delete a registration entry.
- Input validation and error handling.

## Technologies Used

- Oracle SQL
- PL/SQL

## Database Setup

1. **Install Oracle Database**: Ensure you have Oracle Database installed on your machine. You can download it from the [Oracle website](https://www.oracle.com/database/technologies/).

2. **Create a User**: Create a user in your Oracle Database to run the scripts.

3. **Run the SQL Scripts**: Execute the following SQL scripts in your Oracle SQL environment:

   - Create the `Registration` table and sequence:
     ```sql
     CREATE TABLE Registration (
       ID NUMBER PRIMARY KEY,
       Name VARCHAR2(100) NOT NULL,
       Email VARCHAR2(100) UNIQUE NOT NULL,
       Date_of_Birth DATE NOT NULL,
       Phone_Number VARCHAR2(20),
       Address VARCHAR2(200),
       Created_At TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
       Updated_At TIMESTAMP DEFAULT CURRENT_TIMESTAMP
     );

     CREATE SEQUENCE Registration_ID_SEQ START WITH 1 INCREMENT BY 1;
     ```

   - Create the PL/SQL procedures for CRUD operations:
     ```sql
     -- Include the Create, Read, Update, and Delete procedures here
     ```

## CRUD Operations

### Create Operation

To create a new registration, call the `Create_Registration` procedure with the required parameters.

### Read Operation

To read registration details, call the `Read_Registration` procedure with the registration ID.

### Update Operation

To update an existing registration, call the `Update_Registration` procedure with the registration ID and new values.

### Delete Operation

To delete a registration, call the `Delete_Registration` procedure with the registration ID.

## Usage

1. **Connect to Oracle Database**: Use your preferred SQL client (e.g., SQL Developer) to connect to your Oracle Database.

2. **Execute Procedures**: You can execute the procedures in an anonymous PL/SQL block or through your application code.

   Example of creating a registration:
   ```sql
   DECLARE
     v_ID Registration.ID%TYPE;
   BEGIN
     Create_Registration('John Doe', 'john.doe@example.com', '1990-01-01', '123-456-7890', '123 Main St', v_ID);
     DBMS_OUTPUT.PUT_LINE('Registration created with ID: ' || v_ID);
   END;



   
### Notes:
- Make sure to replace the placeholder text with actual content where necessary.
- If you have a license file, include it in the repository and link it in the README.
- You can add more sections or details based on your project requirements.
