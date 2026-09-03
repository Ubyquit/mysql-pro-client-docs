# Stored Procedures & Functions

Disponible desde MySQL Pro Client 2.1.0.

## Execute Procedure

Haz clic derecho sobre un procedure y selecciona **Execute Procedure**.

La extensión consulta `information_schema.PARAMETERS` y detecta:

- `IN`;
- `OUT`;
- `INOUT`;
- tipo de dato;
- posición.

## Tipos de controles

Según el tipo MySQL se muestran controles apropiados para números, texto, fecha/hora, boolean-like `TINYINT(1)`, JSON, ENUM y NULL.

## Ejemplo

```sql
DELIMITER //

CREATE PROCEDURE calcular_total(
    IN p_subtotal DECIMAL(10,2),
    IN p_iva DECIMAL(6,4),
    OUT p_total DECIMAL(10,2)
)
BEGIN
    SET p_total = p_subtotal + (p_subtotal * p_iva);
END //

DELIMITER ;
```

La ejecución utiliza placeholders para inputs. Los valores no se concatenan directamente dentro del `CALL`.

## OUT / INOUT

Los parámetros de salida utilizan variables de sesión internas únicas y después se recuperan mediante `SELECT`.

## Result sets

Un procedure puede devolver uno o varios result sets. El panel muestra cada conjunto por separado junto con los parámetros de salida y el tiempo de ejecución.

## Functions

Las functions utilizan un flujo visual equivalente y muestran su valor retornado.

Conceptualmente:

```sql
SELECT `database`.`mi_funcion`(?, ?) AS `result`;
```

## DELIMITER

`DELIMITER` se procesa en el cliente. Nunca se envía al servidor MySQL como una consulta.
