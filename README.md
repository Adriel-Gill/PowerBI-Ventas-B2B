# Analisis de Ventas B2B - Business Intelligence Dashboard

## Descripcion del Proyecto
El presente proyecto consiste en el diseno y desarrollo de un tablero interactivo de Inteligencia de Negocios en Power BI, alimentado a traves de una conexion directa a una base de datos en Microsoft SQL Server. Su objetivo principal es auditar el rendimiento comercial de una fuerza de ventas B2B, permitiendo a los tomadores de decisiones analizar el volumen de Ingresos Obtenidos, cuantificar los Ingresos Perdidos y evaluar la eficiencia general mediante la Tasa de Cierre.

## Arquitectura y Stack Tecnologico
* Base de Datos y Origen: Microsoft SQL Server
* Herramienta de Visualizacion: Microsoft Power BI
* Lenguaje de Consultas y Medidas: DAX
* Modelado de Datos: Esquema de Estrella separando tablas de hechos y dimensiones para garantizar un rendimiento optimo del modelo.
* Diseno UX/UI: Interfaz corporativa minimalista disenada con una jerarquia visual clara y paleta de colores de alto contraste para facilitar la lectura de los KPIs, integrando ademas un sistema de navegacion por marcadores.

## Funcionalidades Clave y Casos de Uso
1. Panel de Filtrado Retractil: Sistema de navegacion implementado mediante marcadores que permite al usuario segmentar la informacion por gerente, region, producto y rango de fechas sin saturar el lienzo principal de analisis.
2. Obtencion de Detalles (Drill-through): Funcionalidad de auditoria granular. Permite al gerente de ventas seleccionar un agente comercial especifico y viajar a una vista aislada para analizar a nivel de detalle el origen de sus ingresos y las perdidas asociadas a sus clientes.
3. Desarrollo de KPIs Comerciales: Diseno de metricas a medida para evaluar la rentabilidad y el exito de los cierres comerciales de la compania.

## Muestra de Codigo (DAX)
Implementacion de buenas practicas en el calculo de metricas criticas utilizando la funcion DIVIDE para prevenir errores de ejecucion por division entre cero:

```dax
Tasa de Cierre = 
DIVIDE(
    [Ingresos Ganados]; 
    [Ingresos Ganados] + [Ingresos Perdidos]; 
    0
)
