<div align="center">

<img src="https://raw.githubusercontent.com/Ubyquit/mysql-pro-client-docs/main/images/icon.png" width="128" alt="MySQL Pro Client logo" />

# MySQL Pro Client

### The all-in-one MySQL client for Visual Studio Code

![Version](https://img.shields.io/badge/version-2.5.1-0ea5e9?style=for-the-badge)
![Tests](https://img.shields.io/badge/tests-101%20expected-22c55e?style=for-the-badge)
![Price](https://img.shields.io/badge/price-free-8b5cf6?style=for-the-badge)

**Built by OpSET México**

</div>

---

![MySQL Pro Client hero](https://raw.githubusercontent.com/Ubyquit/mysql-pro-client-docs/main/images/screenshots/hero.png)

## One workspace. Your complete MySQL workflow.

| Query | Model | Optimize | Manage |
|---|---|---|---|
| Smart SQL Editor | ER Diagrams | Visual EXPLAIN | Data Editor |
| Query Results | SQL → ER | Schema Compare | Table Designer |
| History & Favorites | Live ER Preview | Safety Controls | Backup / Restore |
| Stored Routines | ER Groups & Styling | Migration SQL | CSV / JSON Import |


## 🎨 ER Diagram Experience 2.5

MySQL Pro Client 2.5.1 turns the ER Diagram into a much more capable local modeling workspace:

- Smooth pointer-captured table dragging with `requestAnimationFrame`, snap-to-grid, and stuck-drag protection.
- Relationship routing modes: **Orthogonal**, **Straight**, and **Curved**.
- Relationship styles: **Solid**, **Dashed**, and **Dotted**, with configurable thickness and color.
- Custom table header/background/border/text colors, rounded or square corners, and per-table color overrides.
- Visual **ER Groups** with names and colors; assign tables, move a whole group, hide/show, collapse/expand, and auto-arrange only that group.
- Global Auto Layout remains available, while saved positions/groups are preserved locally per workspace and database.
- PNG, PDF, and Advanced Export preserve the configured ER appearance and visible groups.
- Shared WebView styling was refined for VS Code Dark, Light, and High Contrast themes.

All group and appearance metadata is local to MySQL Pro Client. It never changes the MySQL schema.

## ⚡ Smart Batch Execution & Action Output

Run complete SQL scripts without flooding your VS Code workspace with one tab per DDL/DML statement.

- Multi-statement `CREATE`, `ALTER`, `DROP`, `INSERT`, `UPDATE`, `DELETE`, `USE` and other non-row commands are consolidated into a single **Action Output** panel.
- Row-producing statements still open dedicated **Query Results** tabs.
- Action Output tracks statement number, status, command, rows affected/returned, execution time and the exact failing statement.
- Batch execution stops on SQL errors or cancelled mutation-safety prompts while preserving the completed execution log.
- Copy the SQL for any logged statement directly from Action Output.

## ⚡ Query without leaving VS Code

![Query Editor and Results](https://raw.githubusercontent.com/Ubyquit/mysql-pro-client-docs/main/images/screenshots/query-results.png)

Run the current statement, a selection, or the complete SQL document. Use contextual IntelliSense, CodeLens, multiple result sets, Smart Filters and CSV/JSON export.

## 🧬 Turn schemas into diagrams

![ER Diagram](https://raw.githubusercontent.com/Ubyquit/mysql-pro-client-docs/main/images/screenshots/er-diagram.png)

Generate ER diagrams from a live MySQL database, parse DDL without executing it, or open a Live SQL → ER Preview while typing.

## ▶️ Execute Stored Procedures visually

![Execute Procedure](https://raw.githubusercontent.com/Ubyquit/mysql-pro-client-docs/main/images/screenshots/stored-procedure-form.png)

MySQL Pro Client detects `IN`, `OUT` and `INOUT` parameters automatically from MySQL metadata.

![Stored Procedure Results](https://raw.githubusercontent.com/Ubyquit/mysql-pro-client-docs/main/images/screenshots/stored-procedure-result.png)

Multiple result sets and output parameters are displayed together with execution time.

## 🔄 Compare environments

![Schema Compare](https://raw.githubusercontent.com/Ubyquit/mysql-pro-client-docs/main/images/screenshots/schema-compare.png)

Compare Reference → Target, identify additive, changed and destructive differences, then open Migration SQL for review. Migrations are never auto-applied.

## 🔍 Understand query plans

![Visual EXPLAIN](https://raw.githubusercontent.com/Ubyquit/mysql-pro-client-docs/main/images/screenshots/visual-explain.png)

Explore access types, indexes, estimated rows, costs, conditions and diagnostic warnings visually.

## 🛠️ Design tables visually

![Table Designer](https://raw.githubusercontent.com/Ubyquit/mysql-pro-client-docs/main/images/screenshots/table-designer.png)

Edit columns, indexes, foreign keys, engine, charset and collation. Review generated SQL before applying changes.

## 💾 Backup / Restore

![Backup and Restore](https://raw.githubusercontent.com/Ubyquit/mysql-pro-client-docs/main/images/screenshots/backup-restore.png)

Use MySQL's official CLI tools with preview, tool discovery and reinforced confirmation for destructive operations.

## 🛡️ Safety by Design

- SecretStorage for saved passwords.
- Strong warning for `UPDATE` / `DELETE` without top-level `WHERE`.
- Typed confirmation for `DROP TABLE`.
- Conservative reconnect behavior.
- Query row limits with explicit unlimited mode.
- SQL Preview before Table Designer changes.
- Migration SQL review before Schema Compare changes.
- CSP + cryptographic nonce in WebViews.

## 🚀 Quick Start

1. Install **MySQL Pro Client** from Visual Studio Code Marketplace.
2. Add a connection.
3. Connect to MySQL.
4. Open a `.sql` file.
5. Use `Ctrl/Cmd + Enter`.

## 📚 Guides

- [Getting Started](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/GETTING-STARTED.md)
- [Database Explorer](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/DATABASE-EXPLORER.md)
- [Query Editor](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/QUERY-EDITOR.md)
- [Query Results](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/QUERY-RESULTS.md)
- [ER Diagrams](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/ER-DIAGRAMS.md)
- [Visual EXPLAIN](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/VISUAL-EXPLAIN.md)
- [Data Editor](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/DATA-EDITOR.md)
- [Table Designer](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/TABLE-DESIGNER.md)
- [Stored Procedures & Functions](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/STORED-ROUTINES.md)
- [Schema Compare](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/SCHEMA-COMPARE.md)
- [Import / Export](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/IMPORT-EXPORT.md)
- [Backup / Restore](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/BACKUP-RESTORE.md)
- [Security Model](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/SECURITY.md)
- [Troubleshooting](https://github.com/Ubyquit/mysql-pro-client-docs/blob/main/docs/TROUBLESHOOTING.md)

<div align="center">

### OpSET México

**Built for developers. Designed for productivity.**

</div>


## Advanced Table Design & Reporting

MySQL Pro Client 2.5.1 keeps the 2.4 **Visual Foreign Key Designer** and adds the new **ER Diagram Experience**: smoother drag interaction, orthogonal/straight/curved routing, customizable relationship styles, configurable table colors, visual groups, group movement/collapse/visibility, snap-to-grid, and persisted layouts. Advanced Export, composite keys, Table Designer safety, and the existing PNG/PDF flows remain available.

