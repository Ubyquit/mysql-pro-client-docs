# Database Explorer

El Explorer es el mapa principal de objetos MySQL.

## Jerarquía

```text
Connection
└── Database
    ├── Tables
    │   └── Table
    │       ├── Columns
    │       ├── Indexes
    │       ├── Foreign Keys
    │       └── Triggers
    ├── Views
    ├── Procedures
    └── Functions
```

## Conexiones

Estados visuales soportados:

- connected;
- disconnected;
- connecting;
- reconnecting;
- error.

Acciones principales:

- Connect / Disconnect;
- Edit Connection;
- Delete Connection;
- Refresh.

## Database

Desde una database puedes:

- Generate ER Diagram;
- Create Table;
- Compare Schema…;
- Backup Database;
- Restore Database.

## Table

Acciones disponibles:

- View / Edit Data;
- Design Table;
- Generate SELECT;
- Select Top 100;
- Count Rows;
- Show CREATE;
- Import CSV / JSON;
- Copy Table Name;
- TRUNCATE;
- DROP TABLE.

Las acciones destructivas incorporan confirmaciones adicionales.

## Procedures y Functions

Desde 2.1.0:

- **Execute Procedure**;
- **Execute Function**;
- **Show CREATE**.
