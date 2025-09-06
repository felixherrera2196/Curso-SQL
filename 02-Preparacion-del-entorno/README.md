# Preparación del entorno

Antes de trabajar con SQL se debe instalar un gestor como PostgreSQL o MySQL y configurar un cliente para conectarse.

## Ejemplo
```bash
psql -U usuario -d ejemplo
```

## Diagrama
```mermaid
graph LR;
  U[Usuario] --> C[Cliente SQL];
  C --> S[Servidor de base de datos];
```
