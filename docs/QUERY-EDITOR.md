# Query Editor

## Ejecución

MySQL Pro Client permite ejecutar:

- selección actual;
- sentencia actual bajo el cursor;
- documento completo.

```sql
SELECT * FROM clientes;
SELECT * FROM pedidos;
```

Las sentencias se procesan secuencialmente y los resultados se muestran por separado.

## Parser de sentencias

La separación de SQL respeta:

- strings con comillas simples;
- strings con comillas dobles;
- identificadores entre backticks;
- comentarios;
- `DELIMITER` personalizado.

Esto evita dividir por error un procedimiento que contiene `;` dentro de `BEGIN ... END`.

## DELIMITER

```sql
DELIMITER //
CREATE PROCEDURE demo()
BEGIN
    SELECT 'hola; mundo';
END //
DELIMITER ;
```

`DELIMITER` es una directiva del cliente, no una sentencia del servidor. MySQL Pro Client la interpreta localmente y envía al servidor únicamente el SQL ejecutable.

## CodeLens

El editor puede mostrar acciones `Run` y `Explain` sobre bloques SQL compatibles.

## IntelliSense

Ofrece sugerencias contextuales para:

- databases;
- tables;
- views;
- columns;
- aliases;
- keywords;
- funciones;
- snippets.

Snippets incluidos: `SEL`, `SELW`, `SELJ`, `UPD`, `UPDJ`, `INS`, `DEL`, `GRO`, `ORD`, `CAS`.

## Mutaciones

`UPDATE` y `DELETE` sin un `WHERE` de nivel superior activan una advertencia especial cuando la protección está habilitada.


## Smart Batch Execution

When a selection or **Run All** contains multiple statements, MySQL Pro Client consolidates DDL/DML/session feedback into **Action Output**. Statements returning rows still open dedicated Query Results panels. This prevents large setup and migration scripts from creating dozens of result tabs.
