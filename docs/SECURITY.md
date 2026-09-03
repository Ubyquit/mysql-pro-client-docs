# Security Model

MySQL Pro Client está diseñado para reducir accidentes comunes sin intentar reemplazar la política de seguridad del servidor MySQL.

## Credenciales

Las contraseñas guardadas utilizan VS Code `SecretStorage`.

## WebViews

Las WebViews del proyecto utilizan una base compartida con:

- Content Security Policy;
- nonce criptográfico;
- HTML escaping;
- serialización segura de JSON embebido;
- allow-list de mensajes en paneles críticos;
- Design System basado en variables de VS Code.

## SQL peligroso

### UPDATE / DELETE

La extensión detecta mutaciones sin `WHERE` de nivel superior. El parser intenta ignorar `WHERE` que aparezca únicamente dentro de strings, comentarios, CTEs o subconsultas.

### DROP TABLE

Requiere confirmación y escritura exacta del nombre de la tabla.

### TRUNCATE

Requiere confirmación explícita.

## Reconexión

Las lecturas seguras pueden reintentarse bajo determinadas condiciones. Mutaciones, DDL, transacciones y comandos de sesión no se reintentan automáticamente cuando el resultado podría ser ambiguo.

Una nueva sesión no puede restaurar automáticamente:

- transacciones abiertas;
- temporary tables;
- locks;
- prepared statements;
- variables arbitrarias de sesión.

## Resultados grandes

La extensión aplica límites iniciales y solicita una decisión explícita antes de ejecutar sin límite cuando la configuración de advertencia está habilitada.

## Logs

Los logs centrales intentan redactar passwords, tokens y secrets y limitan SQL potencialmente sensible.
