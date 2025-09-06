# Fundamentos de SQL

SQL es un lenguaje declarativo diseñado para gestionar datos en sistemas relacionales. Se compone de sublenguajes como DDL para definir estructuras, DML para manipular datos y DQL para realizar consultas. La sintaxis se basa en sentencias que describen qué datos se desean y no cómo obtenerlos.

## Preparación
Para los ejemplos de este curso utilizaremos la base de datos `tienda` con la tabla `usuarios`.
Si aún no la tienes, créala y agrega algunos registros de prueba:

```sql
CREATE DATABASE tienda;
\c tienda
CREATE TABLE usuarios (
  id SERIAL PRIMARY KEY,
  nombre TEXT NOT NULL,
  correo TEXT,
  edad INT,
  activo BOOLEAN DEFAULT TRUE,
  ciudad TEXT
);

INSERT INTO usuarios (nombre, correo, edad, activo, ciudad) VALUES
('Ana', 'ana@example.com', 25, TRUE, 'Madrid'),
('Luis', 'luis@example.com', 32, TRUE, 'Bogotá'),
('Marta', 'marta@example.com', 40, FALSE, 'Buenos Aires');
```

## Ejemplo
```sql
-- Consulta y actualización de registros
SELECT nombre FROM usuarios WHERE id = 1;
UPDATE usuarios SET nombre = 'Juan' WHERE id = 1;
```

## Diagrama
```mermaid
graph TD;
  Q[Consulta] --> F[FROM];
  F --> W[WHERE];
```

## Tipos de comandos y consultas

### SELECT
Permite recuperar datos de una tabla de forma declarativa.

```sql
SELECT id, nombre
FROM usuarios;
```

**Ejercicio**

Obtener los correos electrónicos de los usuarios activos de la tabla `usuarios`.

**Solución paso a paso**

1. Identificar las columnas necesarias: `correo`.
2. Indicar la tabla de origen: `usuarios`.
3. Filtrar por la condición `activo = TRUE`.
4. Ejecutar la consulta: `SELECT correo FROM usuarios WHERE activo = TRUE;`.

### INSERT
Agrega nuevos registros a una tabla existente.

```sql
INSERT INTO usuarios (nombre, correo)
VALUES ('Lucía', 'lucia@example.com');
```

**Ejercicio**

Insertar un usuario llamado `Carlos` con correo `carlos@example.com` en la tabla `usuarios`.

**Solución paso a paso**

1. Determinar la tabla y las columnas a rellenar: `usuarios (nombre, correo)`.
2. Escribir la sentencia `INSERT INTO` con los valores correspondientes.
3. Ejecutar: `INSERT INTO usuarios (nombre, correo) VALUES ('Carlos', 'carlos@example.com');`.

### UPDATE
Modifica valores existentes en registros ya creados.

```sql
UPDATE usuarios
SET nombre = 'Juan Pérez'
WHERE id = 1;
```

**Ejercicio**

Cambiar el estado `activo` a `FALSE` para el usuario con `id = 5`.

**Solución paso a paso**

1. Seleccionar la tabla que contiene el dato: `usuarios`.
2. Definir la columna a modificar: `activo`.
3. Establecer la condición de selección: `id = 5`.
4. Ejecutar: `UPDATE usuarios SET activo = FALSE WHERE id = 5;`.

### DELETE
Elimina registros que cumplen una condición específica.

```sql
DELETE FROM usuarios
WHERE id = 10;
```

**Ejercicio**

Eliminar todos los usuarios cuyo campo `activo` sea `FALSE`.

**Solución paso a paso**

1. Indicar la tabla objetivo: `usuarios`.
2. Definir la condición de eliminación: `activo = FALSE`.
3. Ejecutar: `DELETE FROM usuarios WHERE activo = FALSE;`.
