# sprint7-final-project

Análisis ConnectaTel

1. **Objetivo del proyecto**

Como analista de datos, el objetivo de este proyecto es evaluar el comportamiento de los clientes de ConnectaTel, una empresa de telecomunicaciones en Latinoamérica. Se busca identificar patrones de uso, segmentar a los clientes según su edad y nivel de consumo, y traducir esos hallazgos en recomendaciones accionables para el negocio.

El análisis se basa en información registrada hasta el año 2024.

2. **Datasets utilizados**

plans.csv:	Información de los planes actuales de ConnectaTel (precio, minutos incluidos, GB incluidos, costo por extra)
users_latam.csv:	Información de los clientes (edad, ciudad, fecha de registro, plan contratado, churn)
usage.csv:	Detalle de uso por cliente (llamadas, mensajes, fecha, duración)

3. **Etapas del análisis**

- *Carga y exploración inicial*

Revisión de estructura, columnas y tipos de datos de los tres datasets.

- *Revisión y estandarización de fechas*

Conversión de reg_date y date a formato datetime, identificación de años inconsistentes (ej. registros con año 2026) y fechas inválidas.

- *Corrección de valores centinela y nulos*

Limpieza de valores placeholder (-999 en age, ? en city), y evaluación de nulos en duration/length según su relación con el tipo de registro (llamada vs. mensaje).

- *Agregación de uso por usuario*

Construcción de una tabla resumen (user_profile) con el total de mensajes, llamadas y minutos por cliente, combinada con la información demográfica.

- *Estadística descriptiva* 

Resumen numérico de variables clave y distribución porcentual del tipo de plan contratado.

- *Visualización de distribuciones y outliers* 

Histogramas con KDE y boxplots para age, cant_mensajes, cant_llamadas y cant_minutos_llamada; cálculo de límites con el método IQR.

- *Segmentación de clientes*

Clasificación de usuarios en grupos de uso (Bajo uso, Uso medio, Alto uso) y grupos de edad (Joven, Adulto, Adulto Mayor).

- *Insight ejecutivo* 

Síntesis de hallazgos y recomendaciones orientadas a negocio para stakeholders.

4. **Cómo ejecutar el notebook**

Opción recomendada: Google Colab
Abre Google Colab.
Selecciona Archivo → Subir notebook y carga el archivo S7_Version-Estudiante-Project-ConnectaTel.ipynb desde tu computador, o GitHub y pega la URL de este repositorio.
Sube los tres archivos CSV (plans.csv, users_latam.csv, usage.csv) a la carpeta /datasets/ dentro del entorno de Colab.
Ejecuta las celdas en orden desde el principio.

5. **Guía de reproducción rápida**
Requisitos: pandas, numpy, seaborn, matplotlib.

Orden de ejecución: el notebook está diseñado para correrse de arriba hacia abajo sin saltar celdas, ya que cada paso depende de transformaciones aplicadas en pasos anteriores (por ejemplo, la limpieza de fechas y sentinels deben ejecutarse antes de la agregación y segmentación).

Salida esperada: al final de la ejecución, el notebook genera un DataFrame user_profile con las columnas demográficas originales más las métricas de uso agregadas (cant_mensajes, cant_llamadas, cant_minutos_llamada) y las segmentaciones (grupo_uso, grupo_edad), junto con visualizaciones de distribución y outliers.


**Autor**

Julián Santiago Hernández Pecha

