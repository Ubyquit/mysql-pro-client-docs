# MySQL Pro Client 2.2.0 — Release Notes

## Smart Batch Execution & Action Output

MySQL Pro Client 2.2.0 improves large-script execution by replacing tab-per-statement output with a consolidated Action Output experience.

### Highlights

- Run All and multi-statement selections use one Action Output panel for DDL/DML/session statements.
- Statements returning rows continue to open dedicated Query Results panels.
- Batch summary shows executed/total, successes, errors, cancellations and cumulative SQL execution time.
- Each Action Output row shows statement number, status, command, rows affected/returned and timing.
- Copy SQL is available for every logged statement.
- SQL errors and mutation-safety cancellations stop the remaining batch but preserve completed output.
- WebView CSP/design audit covers 13 panels.
- Automated regression suite increases from 80 to 85 tests.

## Marketplace artifact

Expected release package:

`mysql-pro-client-2.2.0.vsix`

Before publishing, run:

```bash
npm install
npm run verify
npm run package:release
```

Then test the generated VSIX locally before uploading it as an update to `opset-mexico.mysql-pro-client`.
