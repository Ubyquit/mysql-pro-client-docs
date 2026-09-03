# ER Diagrams

MySQL Pro Client ofrece tres flujos distintos de diagramación.

## 1. Database → ER Diagram

Lee metadata real de una database conectada y genera un modelo visual con tablas, claves y relaciones.

## 2. SQL → ER Diagram

Analiza DDL sin conectarse ni ejecutar SQL.

```sql
CREATE TABLE cliente (
    id INT PRIMARY KEY,
    nombre VARCHAR(120) NOT NULL
);

CREATE TABLE pedido (
    id INT PRIMARY KEY,
    cliente_id INT NOT NULL,
    FOREIGN KEY (cliente_id) REFERENCES cliente(id)
);
```

## 3. Live SQL → ER Preview

Abre un panel Beside y actualiza el diagrama después de un pequeño debounce mientras escribes SQL.

## Interacción

- posicionamiento de tablas;
- selección visual;
- relaciones FK;
- claves primarias y únicas;
- exportación PNG;
- exportación PDF.

## Buen uso en clase

Live ER Preview es especialmente útil para enseñar cómo una definición SQL se traduce en estructura relacional antes de crear físicamente las tablas.
