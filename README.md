# Project Overview

This project focuses on creating a PostgreSQL database named **universe** and designing its structure to accommodate various celestial entities such as galaxies, stars, planets, and moons. Follow the instructions below to set up the database and ensure all tests pass to successfully complete the project.

## Database Setup Instructions

1. **Log in to PostgreSQL:**
   - Open your terminal.
   - Enter the following command:
     ```bash
     psql --username=freecodecamp --dbname=postgres
     ```

2. **Create Database:**
   - After logging in, create a database named **universe**.

3. **Connect to Database:**
   - Use `\c universe` to connect to the created database.

4. **Run Tests:**
   - Make sure to complete all tasks and pass the provided tests.

5. **Save Progress (Optional):**
   - If you're saving your progress on freeCodeCamp.org, follow the instructions to save a dump of your database.

## Additional Notes

- **Backup Database:**
  - Use `pg_dump` command to create a backup of your database.

- **Repository Submission:**
  - Save the `universe.sql` file in a public repository and submit the URL to it on freeCodeCamp.org.

## Task List

Complete the following tasks to fulfill the project requirements:

1. Create a database named **universe**.
2. Add tables named **galaxy**, **star**, **planet**, and **moon**.
3. Ensure each table has a primary key with automatic incrementation.
4. Include necessary columns with appropriate data types.
5. Use BOOLEAN data type for specific columns.
6. Establish foreign key relationships between tables.
7. Ensure a minimum number of rows and columns for each table.
8. Apply constraints such as NOT NULL and UNIQUE where necessary.
9. Follow naming conventions for primary and foreign key columns.

## Ideas for Column and Table Names

Feel free to use the following suggestions for column and table names:

- description
- has_life
- is_spherical
- age_in_millions_of_years
- planet_types
- galaxy_types
- distance_from_earth

## Instructions for Tests

Ensure the following conditions are met to successfully complete the project:

- Each table should have at least three rows.
- The **galaxy** and **star** tables should have at least six rows each.
- The **planet** table should have at least 12 rows.
- The **moon** table should have at least 20 rows.
- Each table should have at least three columns.
- The **galaxy**, **star**, **planet**, and **moon** tables should each have at least five columns.
- At least two columns per table should not accept NULL values.
- At least one column from each table should be required to be UNIQUE.
- All columns named **name** should be of type VARCHAR.
- Each primary key column should follow the naming convention **table_name_id**. For example, the **moon** table should have a primary key column named **moon_id**.
- Each foreign key column should have the same name as the column it is referencing.





# Project Overview

This project aims to create a PostgreSQL database named **universe** and define its structure to manage celestial entities like galaxies, stars, planets, moons, and additional information. Below is the SQL script representing the database schema and sample data insertion.

## Database Schema

### Table: galaxy
| Column Name | Data Type | Constraints |
|-------------|-----------|-------------|
| galaxy_id   | SERIAL    | PRIMARY KEY |
| star_id     | INTEGER   | NOT NULL    |
| name        | VARCHAR(20) | UNIQUE, NOT NULL |
| area        | INTEGER   |             |
| volume      | INTEGER   |             |
| age         | NUMERIC   |             |
| material    | TEXT      |             |
| has_life    | BOOLEAN   |             |
| has_water   | BOOLEAN   |             |

### Table: star
| Column Name | Data Type | Constraints |
|-------------|-----------|-------------|
| star_id     | SERIAL    | PRIMARY KEY |
| galaxy_id   | INTEGER   | NOT NULL    |
| planet_id   | INTEGER   | NOT NULL    |
| name        | VARCHAR(20) | UNIQUE, NOT NULL |
| area        | INTEGER   |             |
| volume      | INTEGER   |             |
| age         | NUMERIC   |             |
| material    | TEXT      |             |
| has_life    | BOOLEAN   |             |
| has_water   | BOOLEAN   |             |

### Table: planet
| Column Name | Data Type | Constraints |
|-------------|-----------|-------------|
| planet_id   | SERIAL    | PRIMARY KEY |
| star_id     | INTEGER   | NOT NULL    |
| moon_id     | INTEGER   | NOT NULL    |
| name        | VARCHAR(20) | UNIQUE, NOT NULL |
| area        | INTEGER   |             |
| volume      | INTEGER   |             |
| age         | NUMERIC   |             |
| material    | TEXT      |             |
| has_life    | BOOLEAN   |             |
| has_water   | BOOLEAN   |             |

### Table: moon
| Column Name | Data Type | Constraints |
|-------------|-----------|-------------|
| moon_id     | SERIAL    | PRIMARY KEY |
| planet_id   | INTEGER   | NOT NULL    |
| name        | VARCHAR(20) | UNIQUE, NOT NULL |
| area        | INTEGER   |             |
| volume      | INTEGER   |             |
| age         | NUMERIC   |             |
| material    | TEXT      |             |
| has_life    | BOOLEAN   |             |
| has_water   | BOOLEAN   |             |

### Table: more_info
| Column Name | Data Type | Constraints |
|-------------|-----------|-------------|
| more_info_id| SERIAL    | PRIMARY KEY |
| object_id   | INTEGER   |             |
| name        | VARCHAR(20) | UNIQUE, NOT NULL |
| description | TEXT      |             |

## Sample Data Insertion

```sql
-- Galaxy
INSERT INTO galaxy VALUES 
(1, 1, 'galaxy1', 500, 750, 1500.75, 'solid', true, true),
(2, 2, 'galaxy2', 500, 750, 1500.75, 'solid', true, true),
(3, 3, 'galaxy3', 500, 750, 1500.75, 'solid', true, true),
(4, 4, 'galaxy4', 500, 750, 1500.75, 'solid', true, true),
(5, 5, 'galaxy5', 500, 750, 1500.75, 'solid', true, true),
(6, 6, 'galaxy6', 500, 750, 1500.75, 'solid', true, true);

-- Star
INSERT INTO star VALUES
(1, 1, 1, 'star1', 500, 750, 1500.75, 'solid', true, true),
(2, 2, 2, 'star2', 500, 750, 1500.75, 'solid', true, true),
(3, 3, 3, 'star3', 500, 750, 1500.75, 'solid', true, true),
(4, 4, 4, 'star4', 500, 750, 1500.75, 'solid', true, true),
(5, 5, 5, 'star5', 500, 750, 1500.75, 'solid', true, true),
(6, 6, 6, 'star6', 500, 750, 1500.75, 'solid', true, true);

-- Planet
INSERT INTO planet VALUES
(1,  1,  1, 'planet1', 500, 750, 1500.75, 'solid', true, true),
(2,  2,  2, 'planet2', 500, 750, 1500.75, 'solid', true, true),
(3,  3,  3, 'planet3', 500, 750, 1500.75, 'solid', true, true),
(4,  4,  4, 'planet4', 500, 750, 1500.75, 'solid', true, true),
(5,  5,  5, 'planet5', 500, 750, 1500.75, 'solid', true, true),
(6,  6,  6, 'planet6', 500, 750, 1500.75, 'solid', true, true),
(7,  6,  7, 'planet7', 500, 750, 1500.75, 'solid', true, true),
(8,  6,  8, 'planet8', 500, 750, 1500.75, 'solid', true, true),
(9,  6,  9, 'planet9', 500, 750, 1500.75, 'solid', true, true),
(10, 6, 10, 'planet10', 500, 750, 1500.75, 'solid', true, true),
(11, 6, 11, 'planet11', 500, 750, 1500.75, 'solid', true, true),
(12, 6, 12, 'planet12', 500, 750, 1500.75, 'solid', true, true);

-- Moon
INSERT INTO moon VALUES 
(1,   1, 'moon1', 500, 750, 1500.75, 'solid', true, true),
(2,   2, 'moon2', 500, 750, 1500.75, 'solid', true, true),
(3,   3, 'moon3', 500, 750, 1500.75, 'solid', true, true),
(4,   4, 'moon4', 500, 750, 1500.75, 'solid', true, true),
(5,   5, 'moon5', 500, 750, 1500.75, 'solid', true, true),
(6,   6, 'moon6', 500, 750, 1500.75, 'solid', true, true),
(7,   7, 'moon7', 500, 750, 1500.75, 'solid', true, true),
(8,   8, 'moon8', 500, 750, 1500.75, 'solid', true, true),
(9,   9, 'moon9', 500, 750, 1500.75, 'solid', true, true),
(10, 10, 'moon10', 500, 750, 1500.75, 'solid', true, true),
(11, 11, 'moon11', 500, 750, 1500.75, 'solid', true, true),
(12, 11, 'moon12', 500, 750, 1500.75, 'solid', true, true),
(13, 11, 'moon13', 500, 750, 1500.75, 'solid', true, true),
(14, 11, 'moon14', 500, 750, 1500.75, 'solid', true, true),
(15, 11, 'moon15', 500, 750, 1500.75, 'solid', true, true),
(16, 11, 'moon16', 500, 750, 1500.75, 'solid', true, true),
(17, 11, 'moon17', 500, 750, 1500.75, 'solid', true, true),
(18, 11, 'moon18', 500, 750, 1500.75, 'solid', true, true),
(19, 11, 'moon19', 500, 750, 1500.75, 'solid', true, true),
(20, 11, 'moon20', 500, 750, 1500.75, 'solid', true, true);

-- Additional Information
INSERT INTO more_info VALUES
(1, 1, 'info1', 'lorem impsum'),
(2, 2, 'info2', 'lorem impsum'),
(3, 3, 'info3', 'lorem impsum'),
(4, 4, 'info4', 'lorem impsum'),
(5, 5, 'info5', 'lorem impsum');
