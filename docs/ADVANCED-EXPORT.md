# Advanced Export

MySQL Pro Client 2.3.0 keeps the existing ER Diagram **PNG** and **PDF** buttons and adds a separate **Advanced Export** workflow.

## Report sections

You can build one PDF from any combination of:

- syntax-highlighted SQL code;
- the current ER Diagram;
- the latest Query Results already produced by MySQL Pro Client.

The export never re-executes SQL just to build a report.

## SQL source

Choose the current SQL file, the current selection, the current statement, or no SQL. MySQL Pro Client remembers the last SQL editor even after focus moves to the ER Diagram WebView.

## Appearance

- **Light / Print** — optimized for reports and printing.
- **Dark** — presentation-style output.

SQL is written to the PDF as vector text with MySQL-oriented syntax highlighting rather than captured as an editor screenshot. The ER Diagram uses the existing high-resolution export renderer.
