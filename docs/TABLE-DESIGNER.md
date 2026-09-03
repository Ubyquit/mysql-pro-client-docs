# Table Designer

Table Designer permite crear o modificar estructuras MySQL visualmente.

## Secciones

- General;
- Columns;
- Indexes;
- Foreign Keys;
- engine;
- charset;
- collation.

## SQL Preview

El diseñador no modifica la database mientras editas controles. Primero genera SQL.

```text
Visual changes
     │
     ▼
 SQL Preview
     │
     ├── Open SQL
     └── Apply Changes
```

Para alteraciones existentes se intenta agrupar las cláusulas relevantes en `ALTER TABLE`.

## Tipos

Soporta, entre otros, tipos normales, `ENUM` y generated columns. Algunas representaciones son normalizadas por MySQL; por ejemplo `BOOLEAN` puede aparecer como `tinyint(1)`.
