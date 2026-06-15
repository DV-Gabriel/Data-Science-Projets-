# Proyecto de Business Intelligence - La Favorita (Kaggle)

## Descripción General

Este proyecto consiste en la construcción de una solución de Business Intelligence utilizando datos provenientes de la competencia **Corporación Favorita Grocery Sales Forecasting** de Kaggle.

El objetivo principal fue diseñar e implementar un proceso ETL para integrar grandes volúmenes de datos en un Data Warehouse, permitiendo posteriormente el análisis multidimensional y la visualización de información mediante dashboards interactivos en Power BI.

## Fuente de Datos

Los datos utilizados provienen de la competencia de Kaggle **Corporación Favorita Grocery Sales Forecasting**, que contiene información histórica de ventas de productos en diferentes tiendas y fechas.

Características del conjunto de datos:

- Más de 3 millones de registros procesados.
- Información de ventas por producto y tienda.
- Datos temporales para análisis histórico.
- Información relacionada con días festivos.

## Arquitectura de la Solución

La solución fue desarrollada siguiendo una arquitectura clásica de Business Intelligence:

1. Extracción de datos desde los archivos fuente.
2. Transformación y limpieza de datos mediante Pentaho Data Integration (PDI).
3. Carga de información en PostgreSQL.
4. Construcción de un Data Warehouse utilizando un modelo constelación.
5. Creación de dashboards analíticos en Power BI para consultas OLAP.

## Modelo de Datos

Se implementó un **Data Warehouse basado en un modelo constelación**, compuesto por múltiples tablas de hechos y dimensiones compartidas.

### Dimensiones

- Dimensión Tiempo
- Dimensión Producto
- Dimensión Tienda
- Dimensión Feriado

### Tablas de Hechos

- Hecho Ventas
- Hecho Transacciones

Este modelo permite realizar análisis multidimensionales sobre las ventas y el comportamiento de las transacciones a través del tiempo.

## Proceso ETL

El proceso ETL fue desarrollado utilizando Pentaho Data Integration (Kettle).

### Transformaciones

- `trf_dim_tiempo.ktr`
- `trf_dim_producto.ktr`
- `trf_dim_tienda.ktr`
- `trf_dim_feriado.ktr`
- `trf_fact_ventas.ktr`
- `trf_fact_transacciones.ktr`

### Job Principal

- `job_favorita_constellation.kjb`

El job principal orquesta la ejecución de todas las transformaciones necesarias para poblar el Data Warehouse de forma secuencial.

## Tecnologías Utilizadas

- PostgreSQL
- Pentaho Data Integration 
- Power BI
- SQL
- Modelo Dimensional (Constelación)

## Dashboard

Una vez cargada la información en el Data Warehouse, se desarrolló un dashboard en Power BI con el propósito de responder preguntas de análisis OLAP, permitiendo:

- Análisis de ventas por período.
- Comparación entre tiendas.
- Análisis por productos.
- Evaluación de tendencias temporales.
- Análisis de ventas durante feriados.
- Exploración multidimensional de la información.

## Resultados

La implementación permitió transformar millones de registros transaccionales en información organizada para la toma de decisiones, facilitando consultas analíticas de manera eficiente mediante un modelo dimensional y visualizaciones interactivas.
