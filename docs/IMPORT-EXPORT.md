# Import / Export

## CSV / JSON Import

Desde el contexto de una tabla usa **Import CSV / JSON**.

### CSV

Soporta:

- header;
- delimiter auto-detect;
- quoted values;
- quoted commas;
- quoted newlines;
- UTF-8 BOM;
- archivos sin header.

### JSON

Soporta:

- array de objetos;
- objeto único.

## Mapping

La extensión realiza auto-mapping case-insensitive y permite revisar el mapping antes de insertar.

## Validación

- columnas requeridas;
- nullable;
- unsigned;
- ENUM;
- JSON;
- generated columns.

Puede configurarse para omitir filas inválidas.

## Escritura

La importación se realiza en transacción y lotes para evitar una inserción monolítica.

## Export desde Query Results

Los resultados cargados pueden exportarse a CSV o JSON.
