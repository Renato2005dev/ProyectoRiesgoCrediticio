Data Pipeline & Machine Learning: Módulo de Análisis de Riesgo Crediticio y Sensibilidad
Este proyecto es la implementación de una solución analítica integral que fusiona modelos predictivos (Machine Learning), procesos ETL y Business Intelligence. Su objetivo es evaluar la probabilidad de impago (default), identificar los verdaderos motores del riesgo y simular el impacto en el capital bancario bajo diferentes escenarios de estrés.

El Reto de Negocio
Tradicionalmente, la evaluación de crédito se basa en reglas estáticas o "cajas negras" algorítmicas que la gerencia no puede interpretar. Este proyecto resuelve ese problema mediante Explainable AI (IA Explicable) y pruebas de estrés.

El modelo entrenado descubrió que, contraintuitivamente, factores como "tener casa propia" apenas influyen en la morosidad. Más del 75% del riesgo está dictado por solo dos variables: El Monto del Crédito y la Duración del pago. Implementado en el entorno de visualización, el modelo demostró un 96% de Accuracy y un 75% de Recall en la detección de morosos, blindando la cartera al permitir aislar a los clientes en riesgo frente a los buenos pagadores, y posibilitando la simulación dinámica de la exposición del capital.

Estructura del Proyecto
A continuación, se presenta la estructura del repositorio, separada por las capas del pipeline de datos y modelado:

Plaintext
PROYECTOCREDITICIO/
├── 📁 bi/
│   └── 📄 Proyecto_Crediticio.pbix
├── 📁 data/
│   └── 📄 german_credit_data.csv
├── 📄 01_data_riesgo.ipynb
├── 📄 README.md
└── 📄 SQLQuery1.sql
Descripción Técnica por Capas
1. Extracción, Análisis y Machine Learning (Python)
Ubicado en la raíz del repositorio.

data/german_credit_data.csv: Dataset histórico con la información financiera, demográfica y el estado de riesgo de los clientes del banco.

01_data_riesgo.ipynb: Notebook de Jupyter que contiene el Análisis Exploratorio de Datos (EDA) y el entrenamiento del modelo de clasificación algorítmica (Random Forest). Incluye la extracción de la importancia de las características (Feature Importance) para determinar el peso matemático de cada variable en la decisión de otorgamiento de crédito.

2. Almacenamiento y Consulta (SQL)
Ubicado en la raíz del repositorio.

SQLQuery1.sql: Script DDL/DML utilizado para la exploración relacional, estructuración y validación de los datos históricos crediticios.

3. Visualización y Business Intelligence (Power BI)
Ubicado en la carpeta bi/.

Proyecto_Crediticio.pbix: Dashboard forense interactivo con diseño Dark Mode corporativo.

ETL & DAX: Utiliza Power Query para la limpieza y funciones DAX para traducir las predicciones del modelo en métricas legibles para el negocio.

Simulador de Sensibilidad: Implementación de un parámetro interactivo (What-If) que funciona como un simulador de deuda, recalculando en tiempo real el KPI de "Exposición Total Simulada" sobre el capital del banco según distintos perfiles laborales (incluyendo alta dirección).

Autor
Este proyecto ha sido desarrollado por Renato Alonso Uipan Mantari.