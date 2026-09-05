# MySQL Pro Client 2.5.0 — ER Diagram Experience

## Release focus

2.5.0 is a usability and visualization release centered on making ER diagrams faster to arrange, easier to read, and substantially more customizable while keeping all modeling metadata local to VS Code.

## Highlights

- Smooth table dragging with pointer capture, `requestAnimationFrame`, `translate3d`, cancellation cleanup and deferred persistence.
- Orthogonal relationship routing by default, plus Straight and Curved modes.
- Solid, Dashed and Dotted relationships with configurable thickness and color.
- Snap-to-grid and configurable grid size.
- Global table appearance controls and per-table color overrides.
- Visual ER Groups with editable name/color, table assignment, whole-group movement, hide/show, collapse/expand and group-only auto-arrange.
- Layout, groups and per-table style overrides persist per workspace/database.
- Global ER appearance preferences persist locally.
- Existing schema refresh now preserves layout positions.
- PNG, PDF and Advanced Export preserve the configured ER appearance and groups.
- Shared WebView Design System 2.5 improves Dark, Light and High Contrast consistency.
- Six new ER geometry regression tests, bringing the expected suite to 101 test definitions.

## Compatibility and safety

- No ER appearance or group operation writes to MySQL.
- Table Designer, Visual Foreign Key Designer, Advanced Export, Query Results, Action Output, Stored Routines, Backup/Restore and Schema Compare behavior remain intact.
- Existing SQL safety confirmations remain unchanged.

## RC validation

Run:

```bash
npm install
npm run verify
```

Expected release gate:

```text
check-types                 PASS
lint                        PASS
WebView security audit     PASS
package hygiene            PASS
release readiness 2.5.0    PASS
production build           PASS
integration tests          PASS
all discovered tests passing
Exit code 0
```

Then test the ER-specific checklist in `RC-TEST-CHECKLIST.md` before packaging.

## Packaging

RC artifact:

```bash
npm run package:rc
```

Expected artifact: `mysql-pro-client-2.5.0-rc.1.vsix`.

Release artifact:

```bash
npm run package:release
```

Expected artifact: `mysql-pro-client-2.5.0.vsix`.
