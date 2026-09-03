# Data Editor

Data Editor permite editar filas existentes de forma visual conservando reglas de seguridad.

## Requisito de identidad

Para editar o eliminar una fila existente, la tabla debe disponer de una Primary Key.

Soporta:

- PK simple;
- PK compuesta.

Sin PK, las filas existentes permanecen en modo read-only.

## Operaciones

- Insert;
- Update;
- Delete;
- Save;
- Discard.

Los cambios pendientes se aplican como un lote dentro de una transacción.

## Valores y tipos

Los controles realizan validación consciente del tipo de dato. Los server defaults se preservan cuando corresponde.

## Delete

Eliminar una fila requiere confirmación. La identificación de la fila se realiza usando su PK en lugar de construir condiciones ambiguas sobre todas las columnas.
