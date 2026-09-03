# Schema Compare

Schema Compare compara una database **Reference** contra una database **Target**.

## Dirección

```text
Reference (desired state)
          │
          ▼
        Target
```

## Objetos comparados

- tables;
- table options;
- columns;
- indexes;
- foreign keys;
- views;
- triggers.

## Estados

- `ADD TO TARGET`;
- `CHANGE TARGET`;
- `REMOVE FROM TARGET`.

Las diferencias destructivas reciben señalización adicional.

## Bases con nombres distintos

Las referencias internas a la propia database se normalizan durante la comparación para evitar falsos positivos entre, por ejemplo, `app_dev` y `app_prod`.

## Migration SQL

Puedes generar Migration SQL en un nuevo editor. **No se ejecuta automáticamente.**

## Lo que no hace

- no compara datos;
- no compara users/grants;
- no compara configuración del servidor;
- no intenta adivinar renombres.
