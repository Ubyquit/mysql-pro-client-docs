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


## Advanced column controls — 2.3.0

The Columns grid now includes **PK**, **NN**, **UN**, **BIN**, **ZF**, **AI** and **Generated** controls. Checking PK on multiple columns creates one composite `PRIMARY KEY` in the same order. The Indexes tab remains synchronized with the PK checkboxes.

Generated columns support `VIRTUAL` and `STORED` expressions. `ZEROFILL` is supported for compatibility but is identified as a legacy MySQL feature; enabling it also implies `UNSIGNED`.


## Visual Foreign Key Designer — 2.4.0

The **Foreign Keys** tab now provides a fully visual relationship editor. Click **+ Add Foreign Key**, choose the referenced database and table from live MySQL metadata, and map one or more local columns to referenced columns. Multiple ordered mappings generate a composite foreign key.

Each relationship supports `RESTRICT`, `CASCADE`, `SET NULL` and `NO ACTION` for both `ON DELETE` and `ON UPDATE`. The designer warns when referenced columns do not match the left-most columns of an available index and rejects `SET NULL` when local columns are `NOT NULL`. Self-referencing relationships are supported using the current in-memory table design.

Example generated SQL:

```sql
CONSTRAINT `fk_order_item_order`
  FOREIGN KEY (`order_id`, `tenant_id`)
  REFERENCES `app`.`orders` (`order_id`, `tenant_id`)
  ON DELETE CASCADE
  ON UPDATE CASCADE
```

The designer never applies a foreign key while you are editing. Review **SQL Preview** first, then use **Apply Changes** and confirm the generated DDL.
