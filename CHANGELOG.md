# Changelog

## [2.5.1] - 2026-09-05

### Added

- Clear state-aware eye icons for group visibility.
- Split-button group layout control that visually binds Arrange with its Automatic/Horizontal/Vertical/Grid mode selector.
- Dynamic layout icon and label reflecting the currently selected group layout mode.
- New inward-arrow Fit Group to Contents icon for clearer intent.

### Changed

- Group action iconography now uses compact SVG controls that inherit VS Code theme colors.
- Collapse/expand controls now use explicit panel-state icons while preserving the existing behavior and tooltips.
- Group controls include improved ARIA labels and hover feedback for better discoverability and accessibility.

### Fixed

- Preserves the 2.5 group containment, elastic group sizing, layout modes, self-reference routing, group dragging and Auto Layout behavior while improving only the group-control UX.

## [2.5.0] - 2026-09-05

### Added

- ER Diagram Experience customization panel with Appearance and Groups tabs.
- Orthogonal, straight and curved relationship routing.
- Solid, dashed and dotted relationship styles with configurable thickness and color.
- Snap-to-grid with selectable 8/16/24/32 px grid sizes.
- Global table appearance controls plus per-table color overrides.
- Visual ER Groups with editable names/colors, table assignment, hide/show, collapse/expand, group dragging and group-only auto arrange.
- Persistent ER positions, groups and table overrides per VS Code workspace/database.
- Persistent global ER appearance preferences.
- Six ER geometry regression tests (101 test definitions total).

### Changed

- ER Diagram Experience now scrolls internally while keeping its header and tabs fixed.
- Mouse-wheel scrolling inside Customize no longer zooms the diagram underneath it.
- Initial/Auto Layout now reserves a wider relationship channel and staggers hierarchy levels so foreign-key lines are visible immediately without manually moving tables.
- Orthogonal routing now uses thickness-aware lead segments and obstacle clearance around table cards.
- Table dragging now uses pointer capture, `requestAnimationFrame`, `translate3d`, pointer-cancel/lost-capture cleanup and deferred state persistence for smoother interaction.
- ER refresh preserves the existing visual layout instead of discarding table positions.
- PNG, PDF and Advanced Export now preserve relationship routing/style, table colors and ER Groups.
- Shared WebView Design System updated to 2.5 with improved controls, scrollbars, focus, Dark/Light and High Contrast behavior.
- Orthogonal routing is now the default ER relationship style.

### Safety

- ER groups and appearance metadata are local-only and never modify MySQL schema metadata.
- Existing SQL Preview, mutation safety, connection safety and schema-change confirmations remain unchanged.

## [2.4.0] - 2026-09-05

### Added

- Visual Foreign Key Designer inside Table Designer.
- Live referenced schema/table/column metadata selectors.
- Simple and composite foreign-key mappings with ordered local → referenced column pairs.
- Visual ON DELETE / ON UPDATE controls for RESTRICT, CASCADE, SET NULL and NO ACTION.
- Reference metadata badges/warnings and index-prefix validation before SQL is applied.
- Self-referencing foreign keys use the current in-memory table design.
- Four new Table Designer regression tests (94 tests total).

### Safety

- SET NULL is rejected when any mapped local column is NOT NULL.
- Referenced columns are validated against available metadata and indexed left-most prefixes.
- Existing SQL Preview and confirmation flow remain mandatory before schema changes are applied.

## [2.3.0] - 2026-09-04

### Added
- Advanced Table Designer column controls: PK, BINARY, ZEROFILL, and VIRTUAL/STORED generated columns.
- Composite primary keys directly from multiple PK checkboxes in the Columns grid.
- Advanced Export from ER Diagram: one PDF can include syntax-highlighted SQL, the current ER Diagram, and optional latest Query Results.
- Advanced report SQL source choices: current file, current selection, current statement, or no SQL.
- Light/Print and Dark report themes.

### Changed
- PRIMARY KEY editing is synchronized between Columns and Indexes.
- ZEROFILL automatically implies UNSIGNED and is identified as a legacy MySQL feature.
- Generated-column validation now rejects incompatible DEFAULT and AUTO_INCREMENT combinations.
- Automated Table Designer regression coverage expanded (90 tests total).

## [2.2.0] - 2026-09-03

### Added

- **Smart Batch Execution** for Run All and multi-statement selections.
- New consolidated **Action Output** WebView for DDL, DML, session and other non-row statements.
- Batch summary with executed/total statements, successes, errors, cancellations and cumulative SQL execution time.
- Per-statement status, command, output, timing and Copy SQL action.
- Dedicated Query Results are preserved for statements that return rows.
- Batch execution records the failing or cancelled statement and stops safely while keeping previous successful output visible.
- Five automated regression tests for batch statement classification and output entries (85 tests total).

### Changed

- Multi-statement scripts no longer create one Query Results tab for every `CREATE`, `INSERT`, `UPDATE`, `DELETE`, `DROP`, `USE`, or similar statement.
- `Run All` now behaves like a professional script runner: operational output is consolidated while actual row sets remain individually inspectable.
- WebView security/design audit now covers 13 panels, including Action Output.



## 2.1.1 — Connection Form Hotfix

- Fixed Connection Form buttons being blocked by the WebView Content Security Policy in the packaged Marketplace extension.
- Replaced inline HTML event handlers with nonce-authorized JavaScript event listeners.
- Added a WebView verification rule that fails the build if inline event-handler attributes are introduced again.

## [2.1.0] - 2026-09-03

- Editor SQL ahora interpreta `DELIMITER` como directiva de cliente para crear procedures/functions/triggers/events sin enviarla al servidor.
- CodeLens comparte el mismo parser delimiter-aware que la ejecución del editor.
- Se agregan 4 regresiones automáticas para scripts con delimitadores personalizados (80 pruebas totales).

### Added

- **Execute Procedure** desde el Explorer para stored procedures.
- **Execute Function** desde el Explorer para stored functions.
- Panel visual de ejecución con parámetros `IN`, `OUT` e `INOUT`.
- Lectura automática de firmas desde `information_schema.PARAMETERS`.
- Inputs adaptados a tipos numéricos, fecha, fecha/hora, hora, JSON y texto.
- Soporte para `NULL`, JSON validado y `TINYINT(1)` boolean-like.
- Recuperación de parámetros `OUT`/`INOUT` mediante variables de sesión únicas por ejecución.
- Visualización de múltiples result sets devueltos por `CALL`.
- Visualización del valor escalar devuelto por stored functions.
- SQL preview y logging de ejecución de routines.
- 6 pruebas automatizadas nuevas para metadata, functions, procedures, OUT/INOUT, JSON y booleanos.

Todos los cambios importantes de **MySQL Pro Client** se documentan aquí. El proyecto usa versionado semántico para releases estables.

## [2.0.0] - 2026-09-02

### Release Candidate / Hardening

La versión 2.0 consolida el conjunto funcional de 1.9.0. El objetivo principal es estabilidad, seguridad, regresión automática, consistencia visual, rendimiento y preparación de distribución.

### Added

- Design System compartido para los 11 WebViews.
- Helpers compartidos de seguridad y UI para nonce, CSP, HTML escaping y JSON embebido seguro.
- Allow-list de mensajes WebView en paneles críticos.
- Auditoría estática de CSP, nonce y adopción del Design System.
- Suite automática ampliada a 70 pruebas.
- Pruebas de `SqlStatementService`.
- Pruebas de `MutationSafetyService`.
- Pruebas de `SqlDdlSchemaParser`.
- Pruebas de `DataImportParser` y `DataImportService`.
- Pruebas de `TableDesignerSqlService`.
- Pruebas de `SchemaCompareService` y `SchemaMigrationService`.
- Pruebas de `RestorePreviewService`.
- Pruebas de `MetadataCacheService`.
- Smoke test de Extension Host y validación de todos los comandos contribuidos por `package.json`.
- Auditoría de higiene de empaquetado.
- Auditoría de release readiness.
- Scripts `package:rc` y `package:release`.
- `.gitignore` y `.vscodeignore` endurecidos para artefactos, tests y metadata del sistema operativo.
- Checklist de pruebas reales del Release Candidate.

### Changed

- Metadata cache ahora coalesce solicitudes concurrentes equivalentes para evitar lecturas repetidas al servidor.
- Los errores de carga de metadata no quedan cacheados como rechazo permanente.
- Nonces de WebView centralizados en un generador criptográfico compartido.
- Escapado HTML TypeScript centralizado donde era seguro hacerlo.
- Query Results usa serialización JSON compartida para datos embebidos.
- Pipeline `npm run verify` evita type-check/lint redundantes antes del build de producción.
- README reescrito para reflejar el producto actual y no la antigua beta 0.9.
- Metadata de Marketplace ampliada con descripción, keywords y pricing.
- `package.json` y `package-lock.json` sincronizados en `2.0.0`.

### Security

- CSP con nonce en todos los WebViews auditados.
- `script-src` no depende de `unsafe-inline`.
- Validación de tipos de mensajes entrantes en paneles críticos.
- Los controles de mutaciones inseguras, SecretStorage, redacción de logs y credenciales temporales de CLI se mantienen protegidos por regresión automatizada o auditorías.

### Validation

Quality gate validado durante la preparación de 2.0:

- TypeScript: PASS.
- ESLint: PASS.
- WebView security/design audit: 11/11 PASS.
- Package hygiene: PASS.
- Production build: PASS.
- VS Code Extension Test Host: PASS.
- Automated tests: 70 passing.

### Known limitations

- La etiqueta `rc.1` se usa en el nombre del artefacto interno. VS Code Marketplace no acepta `2.0.0-rc.1` como valor de `version`; el manifiesto usa `2.0.0`.
- Query Results sigue siendo un panel grande y complejo; en 2.0 se priorizó refactor conservador para evitar regresiones funcionales.
- La suite automática no reemplaza pruebas reales contra diferentes versiones/instalaciones de MySQL y sistemas operativos.

## [1.9.0] - 2026-09

### Added

- Schema Compare Reference → Target.
- Comparación de tables, columns, indexes, foreign keys, views y triggers.
- Detección de cambios destructivos.
- Normalización de referencias internas entre databases con nombres diferentes.
- Generación de Migration SQL sin auto-ejecución.
- Swap, refresh, filtros y detalle Reference/Target.

## [1.8.1] - 2026-09

### Changed

- Auto-detección mejorada de `mysql` y `mysqldump` en PATH e instalaciones comunes de macOS, Windows y Linux, incluyendo MAMP, XAMPP, WampServer, Laragon y Homebrew.

## [1.8.0] - 2026-09

### Added

- Backup mediante `mysqldump`.
- Restore mediante cliente `mysql`.
- Archivo temporal de credenciales con permisos restringidos.
- Preview de restore y confirmaciones destructivas.

## [1.7.0] - 2026-09

### Added

- Importación CSV / JSON.
- Parser CSV quote-aware con autodetección de delimitador, quoted newlines y BOM.
- Preview, mapping, validación y batch transaction.

## [1.6.1] - 2026-09

### Changed

- Selectores de charset y collation cargados desde el servidor en Table Designer.

## [1.6.0] - 2026-09

### Added

- Table Designer para creación y modificación visual de tablas.
- SQL Preview, Open SQL y Apply Changes con confirmación.
- Columns, indexes, foreign keys y opciones generales.

## [1.5.0] - 2026-09

### Added

- Visual EXPLAIN para SELECT / WITH SELECT.
- `EXPLAIN FORMAT=JSON` con fallback tabular.
- Grafo, diagnósticos, zoom/pan/search y exportación PNG/PDF.

## [1.4.0] - 2026-09

### Added

- Data Editor con PK simple/compuesta.
- Save/Discard, INSERT/UPDATE/DELETE transaccional y validación por tipo.
- Modo de solo lectura para edición de filas existentes sin PK.

## [1.3.0] - 2026-09

### Added

- Live SQL → ER Preview.
- Actualización automática con debounce sin guardar, ejecutar ni requerir conexión.

## [1.2.0] - 2026-09

### Added

- SQL → ER Diagram offline a partir de DDL.
- Parser para CREATE TABLE, ALTER, indexes y foreign keys.

## [1.1.1] - 2026-09

### Changed

- Mejoras visuales y de exportación para ER Diagram.
- Relaciones FK más claras, etiquetas, selección, badges y exportación limpia PNG/PDF.

## [1.1.0] - 2026-09

### Added

- ER Diagram desde metadata de una base MySQL conectada.

## [1.0.0] - 2026-09

### Added

- Núcleo estable de conexiones y Explorer.
- Ejecución SQL por selección, sentencia actual y documento completo.
- CodeLens, IntelliSense, snippets y contexto por editor.
- Query Results con paginación, filtros, exportación y protección de resultados grandes.
- Query History y Favorites.
- Seguridad para UPDATE/DELETE sin WHERE.
- Quick Actions, SHOW CREATE y operaciones destructivas confirmadas.
- Logging centralizado y reconexión conservadora.
- Multi-connection UX.

## [0.9.0] - 2026-09

### Added

- Beta de estabilización previa al núcleo 1.0.
- Base funcional de conexiones, Explorer, editor SQL, resultados, IntelliSense, historial, seguridad y logs.

## [0.0.1] - 2026

### Added

- Estructura inicial de MySQL Pro Client.
- Activity Bar, Explorer, conexión MySQL y primeras consultas.
