# Funciones avanzadas

Incluyen funciones de ventana que calculan valores sobre un conjunto de filas relacionadas.

## Ejemplo
```sql
SELECT nombre, ROW_NUMBER() OVER (ORDER BY id) FROM usuarios;
```

## Diagrama
```mermaid
graph TD;
  T[usuarios] --> W[Window];
  W --> R[Fila numerada];
```
