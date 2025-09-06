# Preparación del entorno

Para trabajar con SQL se necesita instalar un Sistema Gestor de Bases de Datos (SGBD) como PostgreSQL o MySQL. Estos sistemas implementan el motor que almacena los datos y responde a las consultas. También es necesario un cliente, ya sea gráfico o de línea de comandos, que permita enviar sentencias al servidor.

## Ejemplo
```bash
# Conexión a una base de datos PostgreSQL
psql -U usuario -d ejemplo
```

## Diagrama
```mermaid
graph LR;
  U[Usuario] --> C[Cliente SQL];
  C --> S[Servidor de base de datos];
```
