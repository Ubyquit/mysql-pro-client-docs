# MySQL Pro Client 2.3.0 — Advanced Design & Reporting

## Highlights

### Advanced Table Designer

- Primary-key checkbox directly in the Columns grid.
- Multiple checked PK columns become one valid composite `PRIMARY KEY (...)` constraint.
- PRIMARY remains synchronized with the Indexes tab.
- Added `BINARY` and `ZEROFILL` column modifiers.
- `ZEROFILL` is marked as a legacy MySQL feature; enabling it also enables `UNSIGNED`.
- Generated columns now support `VIRTUAL` and `STORED` modes with an expression editor.
- Existing generated columns are loaded from `information_schema` with their storage mode.
- Existing `ZEROFILL` metadata is preserved.
- SQL Preview remains the source of truth before Apply Changes.

### Advanced Export

The ER Diagram keeps its existing `PNG` and `PDF` buttons and adds a separate **Advanced Export** action.

Advanced Export can create one PDF containing any combination of:

- syntax-highlighted SQL code;
- the current high-resolution ER Diagram;
- the latest Query Results already produced by MySQL Pro Client.

SQL source can be:

- current SQL file;
- current selection;
- current statement;
- none.

The report supports **Light / Print** and **Dark** themes. SQL is rendered as vector PDF text rather than as an editor screenshot. Query Results are reused from the latest result snapshot and are never re-executed just for the report.

## Compatibility and safety

- Existing ER Diagram PNG export is unchanged.
- Existing ER Diagram PDF export is unchanged.
- Advanced Export is additive.
- Structural changes are still previewed before Table Designer executes DDL.
- Generated columns cannot use AUTO_INCREMENT or DEFAULT.
- AUTO_INCREMENT columns must be indexed.
- Only one PRIMARY constraint exists; composite primary keys are represented as multiple columns inside it.

## Release artifact

`mysql-pro-client-2.3.0.vsix`
