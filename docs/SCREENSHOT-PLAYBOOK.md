# Screenshot & Marketplace Playbook

Esta guía define exactamente qué capturas tomar para que el README y Marketplace parezcan una página de producto profesional.

## Objetivo

Las imágenes deben demostrar funciones reales, no mockups. Usa VS Code con tema oscuro, ventana limpia y una database demo sin datos sensibles.

## Capturas recomendadas

Guarda los archivos en `images/screenshots/` con estos nombres:

| Archivo | Qué debe mostrar |
|---|---|
| `hero.png` | Explorer + editor SQL + Query Results en una composición limpia |
| `connections.png` | varias conexiones y árbol de databases |
| `query-results.png` | SELECT real + tabla de resultados |
| `er-diagram.png` | ER Diagram con 5–10 tablas y varias FK |
| `live-er-preview.png` | SQL a la izquierda y Live ER Preview al lado |
| `visual-explain.png` | grafo EXPLAIN con diagnósticos visibles |
| `data-editor.png` | filas editables y cambios pendientes |
| `table-designer.png` | columnas/index/FK y SQL Preview |
| `schema-compare.png` | ADD / CHANGE / REMOVE y badge destructivo |
| `stored-procedure-form.png` | formulario Execute Procedure con parámetros |
| `stored-procedure-result.png` | output parameters + result set |
| `import-data.png` | mapping y preview CSV/JSON |
| `backup-restore.png` | preview de backup/restore |
| `history-favorites.png` | Query History y Saved Queries |

## Resolución

Recomendación práctica:

- ancho 1600–2000 px;
- relación 16:9 o 16:10;
- zoom de VS Code 100–110 %;
- sin notificaciones de error visibles;
- sin nombres de usuarios, hosts públicos, passwords ni información sensible.

## GIFs

Crea demostraciones de 5–12 segundos:

```text
docs/assets/demos/
├── execute-query.gif
├── er-diagram.gif
├── live-er-preview.gif
├── table-designer.gif
├── stored-procedure.gif
└── schema-compare.gif
```

Cada GIF debe enseñar **una sola acción**. Evita tutoriales de un minuto dentro del README.

## Orden visual recomendado para Marketplace

1. Hero.
2. Query Editor + Results.
3. ER Diagram.
4. Stored Procedure.
5. Schema Compare.
6. Visual EXPLAIN.
7. Table Designer.
8. Backup / Restore.

## Importante: repository en package.json

`vsce` necesita conocer la URL del repositorio para reescribir enlaces relativos del README al empaquetar.

Cuando tengas la URL GitHub definitiva, agrega algo como:

```json
"repository": {
  "type": "git",
  "url": "https://github.com/ORGANIZACION/REPOSITORIO.git"
}
```

Sustituye `ORGANIZACION/REPOSITORIO` por la URL real. No uses este ejemplo literalmente.

Después podrás insertar en `README.md` imágenes como:

```markdown
![ER Diagram](images/screenshots/er-diagram.png)
```

Y enlaces como:

```markdown
[Stored Routines Guide](docs/STORED-ROUTINES.md)
```

## Capturas ya disponibles

Este paquete incluye dos capturas reales obtenidas durante las pruebas de 2.1.0:

- `stored-procedure-form.png`
- `stored-procedure-result.png`

Completa las demás con la misma apariencia antes de hacer la próxima actualización de Marketplace.
