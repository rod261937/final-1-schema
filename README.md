# Fisheries Star Schema — Lab 1

This project implements the classroom task using PostgreSQL 16+.

## Files
- `fisheries_star_schema.sql` — complete SQL setup, sample data, required queries, and SCD Type 2 demonstration.
- `.gitignore` — excludes local editor and environment files.

## Requirements
- PostgreSQL 16+
- VS Code
- SQLTools extension and SQLTools PostgreSQL/CockroachDB driver, or pgAdmin 4 / DBeaver.

## Run in VS Code
1. Install PostgreSQL 16+ and make sure its server is running.
2. Open this folder in VS Code.
3. Install the VS Code extensions **SQLTools** and **SQLTools PostgreSQL/CockroachDB Driver**.
4. Open SQLTools and create a PostgreSQL connection:
   - Host: `localhost`
   - Port: `5432` (unless your PostgreSQL installation uses another port)
   - Database: `postgres` (or another database you own)
   - Username/password: your PostgreSQL login details
5. Connect, open `fisheries_star_schema.sql`, and execute the whole file.
6. Refresh the database explorer. The `fisheries_dw` schema should contain the five tables.

You can alternatively open the SQL file in pgAdmin Query Tool or DBeaver and execute the whole script.

## Important
The script starts with `DROP SCHEMA IF EXISTS fisheries_dw CASCADE;`. This deletes and recreates only the `fisheries_dw` schema in the connected database. Back up any important objects in that schema before running.

## Expected results
- Date dimension covers 2020-01-01 to 2030-12-31.
- 5 ports, 8 species, and sample vessels.
- 240 initial fact rows; 241 after the SCD Type 2 example inserts one new fact row.
- Three reports: kg per month, top species per port, and value per cooperative.
- SCD Type 2 comparison should show `historical_report_unchanged = TRUE`.

All records are generated sample data for practice, not official fisheries statistics.

## Upload to GitHub
Create an empty GitHub repository, for example `fisheries-star-schema`. In the VS Code terminal, run these commands and replace the URL with your own repository URL:

```bash
git init
git add .
git commit -m "Add Fisheries Star Schema lab project"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/fisheries-star-schema.git
git push -u origin main
```

If Git is not installed, install Git for Windows first. Sign in to GitHub when prompted.
