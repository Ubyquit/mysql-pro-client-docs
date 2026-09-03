# Action Output

**Action Output** is the consolidated execution log introduced in MySQL Pro Client 2.2.0 for multi-statement SQL scripts.

## Why it exists

A large SQL file can contain dozens or hundreds of DDL/DML statements. Opening one editor tab for each successful `CREATE`, `INSERT`, `UPDATE`, `DROP`, or `USE` makes the workspace difficult to use. MySQL Pro Client now groups this operational feedback into one panel.

## Behavior

When more than one SQL statement is executed:

- statements returning rows open a dedicated **Query Results** panel;
- non-row statements are logged only in **Action Output**;
- errors are highlighted and stop the remaining batch;
- cancelled mutation-safety confirmations are recorded and stop the remaining batch;
- completed statements remain in the log;
- each log row shows statement number, status, SQL command, rows affected/returned and execution time;
- **Copy SQL** copies the exact statement for inspection or debugging.

Single-statement execution keeps the traditional Query Results behavior.

## Recommended use

Action Output is especially useful for schema creation scripts, migrations, seed scripts, classroom exercises and database setup files.
