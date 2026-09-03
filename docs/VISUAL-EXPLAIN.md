# Visual EXPLAIN

Visual EXPLAIN ayuda a leer planes de ejecución sin depender exclusivamente de una tabla de `EXPLAIN`.

## Consultas compatibles

Principalmente `SELECT` y `WITH ... SELECT`.

## Ejecución

La extensión intenta:

```sql
EXPLAIN FORMAT=JSON ...
```

y utiliza fallback tabular cuando es necesario.

## Información visualizada

- access type;
- possible keys;
- chosen key;
- estimated rows;
- cost;
- conditions;
- full table scan;
- index scan;
- filesort;
- temporary table.

## Navegación

- zoom;
- pan;
- búsqueda;
- refresh;
- exportación PNG/PDF.

## Decisión de seguridad

MySQL Pro Client **no ejecuta `EXPLAIN ANALYZE`** automáticamente. Esa variante ejecuta realmente la consulta y puede ser una decisión relevante en entornos de producción.
