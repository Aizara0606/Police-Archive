# Police Archive Management System

## Overview
This project is a **Police Archive Management System** that allows administrators to manage cases and regular users to search cases. The system supports user authentication, role-based access control, and PostgreSQL database integration.

## Features
- **User Authentication**: Users can log in or register as either a regular user or an admin.
- **Role-Based Access Control**:
   - Regular users can add, search, and view cases.
   - Admins can add, delete, and edit cases.
- **Database Integration**: Uses PostgreSQL to store users and cases.
- **Search Cases**: Both users and admins can search cases by name.
- **View All Cases**: Users and admins can view all cases in the database.
- **Edit Cases**: Admins can modify case details.

## Technologies Used
- **Java**: Core programming language
- **JDBC**: Database connectivity
- **PostgreSQL**: Database management system
- **Scanner**: User input handling
- **IntelliJ IDEA**: Recommended IDE for development

## Main Classes
### 1. `Main`
- Entry point of the application.
- Handles user input and navigation.

### 2. `UserManager`
- Handles user authentication and registration.

### 3. `User`
- Represents a general user.
- Stores user credentials and personal details.

### 4. `Admin`
- Extends `User`.
- Has additional privileges like deleting and editing cases.

### 5. `CaseManager`
- Handles adding, deleting, searching, and editing cases in the database.

### 6. `DatabaseHandler`
- Manages database connection and queries.

## Installation and Setup
### Prerequisites
- Java Development Kit (JDK) installed
- IntelliJ IDEA installed
- PostgreSQL installed and running

### Database Configuration
1. Create a PostgreSQL database named `police_archive`.
2. Create the required tables using the following SQL commands:

```sql
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    email VARCHAR(255) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    role VARCHAR(50) NOT NULL
);

CREATE TABLE cases (
    id SERIAL PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    year INT NOT NULL,
    category VARCHAR(255) NOT NULL,
    victim VARCHAR(255) NOT NULL,
    archived BOOLEAN NOT NULL DEFAULT FALSE
);
```

## How to Run the Application
1. Clone the repository or download the source code.
2. Open the project in IntelliJ IDEA.
3. Configure database connection in `DatabaseHandler.java`.
4. Compile and run `Main.java`.
5. Follow on-screen prompts to register or log in.

## Usage
### Admin Menu Options
1. Add a case
2. Delete a case
3. Search for a case by name
4. Edit a case
5. View all cases
6. Exit

### User Menu Options
1. Add a case
2. Search for a case by name
3. View all cases
4. Exit

## Example Input & Output
```bash
1. Log in
2. Register
Choose an option: 1
Enter email: john@example.com
Enter password: 1234
Welcome, John Winchester!
You are an admin.
1. Add a case
2. Delete a case
3. Search for a case by name
4. Edit a case
5. View all cases
6. Exit
Choose an option: 1
Enter case name: Shapeshifter
Enter year: 2007
Enter category: Robber
Enter victim name: Kelvin
Enter archived: true
Case added successfully!
```

## Troubleshooting
- If you get a database connection error, ensure PostgreSQL is running and credentials are correctly configured.
- If an error occurs when adding a case, verify that all fields are correctly entered.

## Future Improvements
- Implement a graphical user interface (GUI)
- Add more detailed case search and filtering
- Implement case status updates

## License
This project is released under the MIT License.
