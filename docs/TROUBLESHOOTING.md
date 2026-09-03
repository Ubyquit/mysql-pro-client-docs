# Troubleshooting

## No puedo conectar

Comprueba:

- host;
- puerto;
- usuario;
- contraseña;
- permisos del usuario;
- que el servidor acepte conexiones desde tu equipo.

Usa **MySQL: Show Logs** para revisar detalles técnicos sin depender únicamente de una notificación.

## Backup / Restore no encuentra MySQL

Configura manualmente:

- `mysqlProClient.tools.mysqldumpPath`
- `mysqlProClient.tools.mysqlPath`

En macOS con MAMP puede ser necesario indicar la carpeta o ejecutable de la versión de MySQL instalada por MAMP.

## No puedo editar filas

Data Editor necesita una Primary Key para identificar inequívocamente filas existentes.

## Un UPDATE / DELETE muestra advertencia

La extensión no detectó un `WHERE` principal que proteja la mutación. Revisa el SQL antes de continuar.

## DELIMITER marca error

A partir de 2.1.0, scripts con `DELIMITER` son interpretados por MySQL Pro Client. Asegúrate de usar una versión 2.1.0 o superior.

## Smart Filter no encuentra filas fuera de la página

El filtro trabaja sobre **todas las filas cargadas**, no vuelve a consultar al servidor. Si el resultado fue limitado, carga más filas primero.

## Después de una reconexión perdí estado de sesión

Es esperado. Una reconexión crea una nueva sesión MySQL. Transacciones, temp tables, locks y variables de sesión de la conexión anterior no pueden reconstruirse de forma fiable.
