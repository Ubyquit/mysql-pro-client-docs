# Getting Started

## Objetivo

Esta guía lleva de una instalación limpia a la primera consulta ejecutada con MySQL Pro Client.

## 1. Instalar la extensión

Desde Visual Studio Code abre **Extensions** y busca `MySQL Pro Client`.

También puedes instalar un VSIX local desde **Extensions → … → Install from VSIX…**.

## 2. Abrir MySQL Pro Client

Busca el icono de MySQL Pro Client en la Activity Bar. La vista principal muestra las conexiones guardadas.

## 3. Crear una conexión

Selecciona **Add Connection** e introduce los datos del servidor:

- nombre de la conexión;
- host;
- puerto;
- usuario;
- contraseña;
- database opcional.

Las contraseñas persistentes se almacenan usando VS Code `SecretStorage`.

## 4. Conectar

Selecciona la conexión y usa **Connect**. El árbol cambiará al estado conectado y permitirá explorar databases.

## 5. Crear una consulta

Usa **MySQL: New SQL Query** o crea un archivo `.sql`.

```sql
SELECT VERSION();
```

Ejecuta con:

- Windows/Linux: `Ctrl + Enter`
- macOS: `Cmd + Enter`

Sin selección, la extensión ejecuta la sentencia donde está el cursor. Con selección, ejecuta únicamente el SQL seleccionado.

## 6. Seleccionar contexto

La barra de estado permite elegir la conexión y database activa del editor SQL. Cada editor puede mantener su propio contexto.

## 7. Próximos pasos

Prueba estos flujos:

1. **View / Edit Data** sobre una tabla.
2. **Generate ER Diagram** sobre una database.
3. **Visual EXPLAIN** sobre un `SELECT`.
4. **Design Table** sobre una tabla.
5. **Execute Procedure** sobre un stored procedure.
6. **Compare Schema…** entre dos databases conectadas.
