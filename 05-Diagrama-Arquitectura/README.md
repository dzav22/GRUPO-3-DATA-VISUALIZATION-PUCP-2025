# Diagrama de Arquitectura
Diagrama final de la solución, mostrando la integración entre:
- Capa de datos
- Capa ETL
- Capa de almacenamiento
- Capa de presentación
![Diagrama de Arquitectura](Arquitectura_solución.png)

La arquitectura implementada sigue un flujo moderno y escalable que garantiza la calidad, trazabilidad y disponibilidad de los datos en cada etapa del proceso analítico.
El punto de partida es la información proveniente de la Superintendencia de Banca, Seguros y AFP (SBS), la cual es ingerida inicialmente en un entorno de Azure SQL (staging). En esta capa se almacena la data cruda con el objetivo de disponer de una fuente intermedia confiable antes de ejecutar cualquier transformación.

Posteriormente, el proceso ETL se orquesta mediante Fabric Data Factory, donde se aplican las reglas de limpieza, estandarización y consolidación necesarias para preparar los datos para su uso analítico. Una vez transformados, los datos son cargados en el Fabric Data Warehouse, que actúa como repositorio central optimizado para consultas analíticas y modelamiento semántico.

Desde esta capa de almacenamiento, la información fluye hacia las herramientas de consumo final.
Por un lado, Power BI utiliza el modelo para generar visualizaciones, tableros interactivos y análisis con capacidades de drill-through.
Por otro lado, Excel puede conectarse directamente al Data Warehouse para facilitar análisis adicionales o validaciones operativas por parte del usuario.

Finalmente, el usuario final consume tanto los dashboards como los reportes derivados, asegurando una experiencia integrada, consistente y alineada con los objetivos del negocio.
