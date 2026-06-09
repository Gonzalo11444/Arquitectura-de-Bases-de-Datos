# Distributed Database Architecture & Performance Tuning 🗄️⚡

Implementación, monitorización y optimización de un entorno de bases de datos distribuidas utilizando PostgreSQL. Este proyecto documenta la configuración de clústeres, estrategias de replicación, planes de recuperación ante desastres (Disaster Recovery) y el *tuning* de consultas para entornos con cargas masivas de datos.

## Arquitectura y Optimizaciones Clave

El proyecto aborda la administración avanzada de sistemas de bases de datos a nivel corporativo, centrándose en la alta disponibilidad y el rendimiento:

*   **Replicación y Alta Disponibilidad:** Despliegue de arquitecturas *Master-Slave*. Configuración de replicación física (Streaming Replication con Hot Standby) y replicación lógica (Publish/Subscribe) distribuyendo la carga de lectura y escritura entre nodos.
*   **Performance Tuning y Carga Masiva:** Optimización de tiempos de ingesta para conjuntos de datos masivos (más de 25 millones de registros) mediante la desactivación temporal de integridad referencial. Análisis y mejora de cuellos de botella utilizando `EXPLAIN ANALYZE`.
*   **Estrategias de Indexación y Particionamiento:** Creación de índices B-Tree y Hash para reducir drásticamente los bloques leídos en disco. Implementación de particionamiento de tablas (Table Partitioning) para segmentar datos históricos y acelerar las consultas secuenciales.
*   **Gestión de Transacciones y Tolerancia a Fallos:** Control de concurrencia multiversión (MVCC), análisis de interbloqueos (Deadlocks) y configuración del diario del sistema (Write-Ahead Logging / WAL) para auditoría mediante `pg_waldump`. Implementación de backups completos (Basebackups) y *Point-in-Time Recovery* (PITR).

## Stack Tecnológico
*   **Motor de Base de Datos:** PostgreSQL 16/17
*   **Herramientas de Monitorización:** pg_stat_activity, pg_waldump, vistas estadísticas del sistema.
*   **Conceptos Aplicados:** DDL/DML, MVCC, MLOps Data Plumbing, DB Clustering.

## Estructura del Repositorio
Este repositorio contiene la documentación técnica, los esquemas de replicación y los scripts SQL utilizados para las pruebas de estrés, balanceo y recuperación del sistema frente a caídas de nodos críticos.
