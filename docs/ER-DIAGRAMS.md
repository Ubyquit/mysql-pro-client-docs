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

## ER Diagram Experience 2.5

### Movimiento y layout

- Drag suave basado en Pointer Events + pointer capture.
- Actualización visual sincronizada con `requestAnimationFrame`.
- Protección ante `pointercancel` y pérdida de captura para evitar tablas pegadas al puntero.
- Snap to Grid opcional.
- Cuadrícula configurable: 8, 16, 24 o 32 px.
- Auto Layout global.
- Refresh de metadata conservando las posiciones existentes.

### Relaciones

Routing disponible:

- **Orthogonal** — predeterminado.
- **Straight**.
- **Curved**.

Estilo de línea:

- **Solid**.
- **Dashed**.
- **Dotted**.

También se puede configurar grosor y color, o regresar al color del tema de VS Code.

### Apariencia de tablas

El panel **Customize → Appearance** permite modificar:

- color del header;
- color de fondo;
- color del borde;
- color del texto;
- grosor del borde;
- esquinas redondeadas o cuadradas.

Una tabla seleccionada puede tener un override de color sin modificar el resto del diagrama.

## ER Groups

Los grupos son metadata visual local de MySQL Pro Client. **No crean schemas, tablas ni objetos adicionales en MySQL.**

Cada grupo permite:

- nombre y color editables;
- asignar o retirar tablas;
- mover todas sus tablas juntas;
- ocultar/mostrar;
- colapsar/expandir;
- Auto Arrange solo para ese grupo.

Al colapsar un grupo, sus relaciones internas dejan de mostrarse y las relaciones externas se conectan con la tarjeta del grupo.

Las posiciones, grupos y overrides de tabla se guardan por workspace/database. La apariencia global del ER se conserva como preferencia local de VS Code.

## Exportación

Se mantienen los tres flujos existentes:

- PNG;
- PDF;
- Advanced Export.

A partir de 2.5.0, la exportación conserva el routing, estilo/grosor/color de relaciones, apariencia de tablas y grupos visibles del diagrama.

## Uso práctico

Los grupos sirven para separar dominios funcionales como Ventas, Inventario, Seguridad o Facturación. En bases grandes, ocultar o colapsar módulos reduce ruido visual sin alterar el modelo físico.

Live ER Preview sigue siendo útil para enseñar cómo una definición SQL se traduce en estructura relacional antes de crear físicamente las tablas.

## Layout modes and group controls — 2.5.1

The ER workspace supports layout at two levels.

### Global Auto Layout

Top-level items can be arranged using:

- **Automatic** — lets MySQL Pro Client choose a relationship-aware arrangement.
- **Horizontal** — aligns top-level groups/tables horizontally.
- **Vertical** — aligns top-level groups/tables vertically.
- **Grid** — distributes top-level groups/tables in a grid.

When groups exist, they are treated as top-level layout blocks. Ungrouped tables remain top-level items as well.

### Arrange a group

Each group has its own layout selector with the same modes:

- Automatic;
- Horizontal;
- Vertical;
- Grid.

The Arrange control is a split control: its main action runs the selected mode and the attached dropdown changes that mode.

### Fit Group to Contents

**Fit Group to Contents** keeps the current manual table positions and resizes only the visual group frame around those tables, preserving the header and internal margins.

Groups are elastic while manually arranging tables: they can expand to keep moved tables contained. Fit Group to Contents can then compact unused space around the current arrangement.

### Interaction model

- Drag the **canvas background** to pan the diagram.
- Drag a **table** to reposition that table.
- Drag a **group header** to move the complete group and its tables without changing their internal arrangement.
- Tables remain contained by their group and cannot occupy the reserved group-header area.
- **Fit** adjusts the viewport/zoom; it does not reorganize the diagram.
- **Auto Layout** reorganizes top-level items.

### Group toolbar

2.5.1 improves the group toolbar for discoverability:

- state-aware open/closed eye icon for visibility;
- clear collapse/expand state;
- integrated Arrange split button and layout dropdown;
- layout-aware Arrange icon/label;
- inward-arrow icon for Fit Group to Contents;
- improved tooltips, hover states and ARIA labels.

### Self-referencing relationships

Self-referencing foreign keys are routed explicitly in **Curved**, **Orthogonal** and **Straight** modes so the parent/child cardinalities remain readable without drawing the relationship through the table card.
