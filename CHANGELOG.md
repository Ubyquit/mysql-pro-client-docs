# Changelog

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
