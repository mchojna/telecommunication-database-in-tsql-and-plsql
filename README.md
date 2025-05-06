# Telecommunication Database in T-SQL and PL/SQL

This repository contains SQL scripts for creating, managing, and interacting with a telecommunication database. The database is implemented in both T-SQL (Microsoft SQL Server) and PL/SQL (Oracle Database) to demonstrate compatibility and functionality across different database systems.

## Table of Contents

- [Overview](#overview)
- [Database Structure](#database-structure)
- [Features](#features)
- [Setup Instructions](#setup-instructions)
- [Files in the Repository](#files-in-the-repository)
- [Usage](#usage)

---

## Overview

The telecommunication database is designed to manage data related to customers, employees, contracts, marketing consents, and telecommunication services. It includes procedures, triggers, and scripts for data insertion, validation, and reporting.

---

## Database Structure

The database consists of the following tables:

1. **Adres**: Stores address details.
2. **Osoba**: Stores personal information of individuals.
3. **Klient**: Represents customers.
4. **Pracownik**: Represents employees.
5. **Forma_kontatku**: Stores types of communication methods.
6. **Kontakt**: Logs interactions between customers and employees.
7. **Numer_telefonu**: Stores phone numbers associated with customers.
8. **Oferta**: Represents offers made to customers.
9. **Pakiet**: Represents telecommunication service packages.
10. **Umowa**: Represents contracts between customers and the company.
11. **Zgoda_marketingowa**: Stores marketing consent types.
12. **Zgoda_klient**: Tracks customer marketing consents.

---

## Features

### T-SQL Features

- **Procedures**:
  - `RAPORT_SPRZEDAZY`: Generates a sales report for a specific date.
  - `RAPORT_UMOW_DO_ODNOWIENIA`: Lists contracts expiring within a specified number of months.
  - `USUN_STARE_ZGODY`: Deletes expired marketing consents.
- **Triggers**:
  - Automatically assigns marketing consents to new customers.
  - Validates phone number length during insertion.
  - Handles manager reassignment when a manager is deleted.

### PL/SQL Features

- **Procedures**:
  - `RAPORT_ZGOD_MARKETINGOWYCH`: Generates a report of active and inactive marketing consents.
  - `LICZBA_AKTYWNYCH_UMOW`: Counts active contracts for each customer.
  - `AKTUALIZUJ_NR_DOWODU_KLIENTA`: Updates a customer's ID document number.
- **Triggers**:
  - Prevents insertion of packages with prices exceeding a limit.
  - Prevents deletion of customers with active contracts.
  - Automatically sets the hire date for new employees if not provided.

---

## Setup Instructions

### Prerequisites

- A database server supporting T-SQL (e.g., Microsoft SQL Server) or PL/SQL (e.g., Oracle Database).
- A SQL client tool (e.g., SQL Server Management Studio, Oracle SQL Developer).

### Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/telecommunication-database-in-tsql-and-plsql.git
   ```

2. Navigate to the repository directory:

   ```bash
   cd telecommunication-database-in-tsql-and-plsql
   ```

3. Execute the scripts in the following order:

- For T-SQL:

  - BD_TSQL_projekt_create_delete.sql
  - SBD_TSQL_projekt_insert.sql
  - SBD_TSQL_projekt_procedure_trigger.sql

- For PL/SQL:

  - SBD_PLSQL_projekt_create_delete.sql
  - SBD_PLSQL_projekt_insert.sql
  - SBD_PLSQL_projekt_procedure_trigger.sql

## Files in the Repository

- SBD_TSQL_projekt_create_delete.sql: Contains T-SQL scripts for creating and deleting tables and constraints.
- SBD_TSQL_projekt_insert.sql: Contains T-SQL scripts for inserting sample data into the database.
- SBD_TSQL_projekt_procedure_trigger.sql: Contains T-SQL procedures and triggers.
- SBD_PLSQL_projekt_create_delete.sql: Contains PL/SQL scripts for creating and deleting tables and constraints.
- SBD_PLSQL_projekt_insert.sql: Contains PL/SQL scripts for inserting sample data into the database.
- SBD_PLSQL_projekt_procedure_trigger.sql: Contains PL/SQL procedures and triggers.

## Usage

1. Generate Reports:
    - Use the provided procedures to generate sales or marketing consent reports.

2. Data Validation:
    - Triggers ensure data integrity, such as validating phone numbers or preventing deletion of customers with active contracts.

3. Custom Modifications:
    - Modify the scripts to suit your specific telecommunication database needs.
