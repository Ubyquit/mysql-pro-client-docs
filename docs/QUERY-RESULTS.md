# Query Results

Query Results está diseñado para inspección rápida sin convertir el editor en una hoja de cálculo gigantesca.

## Capacidades

- múltiples result sets;
- paginación visual 50 / 100 / 250 / 500;
- búsqueda;
- Smart Result Filter;
- Copy Cell;
- Copy Row;
- Copy Row as JSON;
- exportación CSV;
- exportación JSON;
- metadata de columnas;
- tiempo de ejecución;
- filas afectadas;
- modo limitado para resultados grandes.

## Smart Result Filter

Operadores:

```text
=  !=  >  >=  <  <=  ~  !~
```

Ejemplos:

```text
precio >= 100
nombre ~ garden
estado != NULL
precio >= 100, stock > 0
```

La coma representa AND. Los nombres de columnas no distinguen mayúsculas/minúsculas y pueden escribirse con backticks.

## Resultados grandes

La extensión utiliza `SQL_SELECT_LIMIT` dentro de un ámbito seguro de conexión. El SQL del usuario no se reescribe ingenuamente agregando `LIMIT` al final.

Cuando se alcanza el límite, puedes elegir **Load More** o ejecutar explícitamente sin límite si realmente lo necesitas.


## Query Results vs Action Output

For multi-statement execution, row-producing SQL uses Query Results while operational DDL/DML feedback is consolidated in the Action Output panel. Single-statement execution keeps the traditional Query Results behavior.
