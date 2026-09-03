# Backup & Restore

MySQL Pro Client utiliza las herramientas CLI oficiales en lugar de reimplementar el formato de dump.

## Backup

Utiliza `mysqldump`.

Opciones disponibles dependen del flujo seleccionado e incluyen estructura/datos y objetos auxiliares como routines, triggers y events.

## Restore

Utiliza el cliente `mysql`.

Antes de restaurar se genera un preview que identifica elementos relevantes del script y operaciones destructivas.

## Herramientas

La extensión intenta localizar ejecutables en:

- PATH;
- Homebrew;
- MAMP;
- XAMPP;
- WampServer;
- Laragon;
- instalaciones comunes de MySQL.

También puede configurarse una ruta manual mediante Settings.

## Credenciales

Las credenciales de CLI se proporcionan mediante un archivo temporal con permisos restrictivos en lugar de colocar la contraseña en argumentos del proceso.

## Confirmaciones

Operaciones como `DROP DATABASE` o cambios de database potencialmente peligrosos requieren confirmación reforzada.

## Cancelación

Cancelar un proceso CLI puede detener el proceso, pero no puede garantizar revertir operaciones que el servidor ya haya aplicado.
