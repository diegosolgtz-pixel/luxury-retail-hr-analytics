# luxury-retail-hr-analytics
# Diagnóstico Ejecutivo de Fuga de Talento | Retail de Lujo

## Descripción del proyecto

Este proyecto analiza los patrones de rotación laboral voluntaria y riesgo de renuncia en las tiendas *Flagship* de un Atelier de lujo. A través de un análisis exploratorio de datos (EDA) en Python y un dashboard de diagnóstico en Power BI, se evaluaron variables de satisfacción, estancamiento profesional y compensación salarial con el fin de desmitificar supuestos demográficos, identificar los focos rojos en puestos operativos clave y proponer una estrategia de retención basada en el impacto financiero de la nómina expuesta.

---

## Objetivos principales

1. **Cuantificación del impacto económico del riesgo:** Identificar y auditar a los colaboradores en nivel de "Riesgo Alto" para calcular la masa salarial mensual expuesta a fuga inminente y sus costos asociados de reemplazo.
2. **Identificación del "Efecto Estancamiento":** Analizar la ventana de tolerancia (años sin promoción vs. permanencia en el puesto) en roles críticos de boutique para detectar catalizadores directos de renuncia.
3. **Desmitificación de supuestos y fricción operativa:** Evaluar la neutralidad de variables demográficas (género, estado civil) mediante pruebas estadísticas y medir la fricción causada por horas extras (`OverTime`) e inequidades salariales.

---

## Estructura del repositorio

* `Luxury Retail Talent Retention & Risk Diagnostic.pbix` : Dashboard interactivo en Power BI diseñado bajo arquitectura ejecutiva (páginas *Overview*, *Detail* e *Insights* ).
* `eda_hr_analytics.ipynb` : Notebook de Python con el análisis exploratorio (EDA), pruebas de hipótesis de neutralidad demográfica y lógica de segmentación de riesgo.
* `HR_Analytics_Luxury_Full.xlsx` : Dataset procesado y modelado para su consumo en el reporte.
* `WA_Fn-UseC_-HR-Employee-Attrition.csv` : Dataset base/original de rotación de personal (IBM HR Analytics Data).

---

## Tecnologías utilizadas

* **Python & SQL:** Análisis exploratorio de datos (EDA), consultas en `pandasql` para agregaciones complejas y pruebas de hipótesis estadísticas (evaluación de valores p y distribuciones).
* **Pandas & NumPy:** Limpieza, ingeniería de atributos (creación del índice de riesgo), manipulación de datos y preparación de variables de compensación.
* **Matplotlib & Seaborn:** Visualización de distribuciones salariales, matrices de correlación y mapas de calor de fricción operativa.
* **Power BI & DAX:** Modelado dimensional de datos, diseño UI/UX en *Dark Mode*, creación de métricas dinámicas (`SUM`, `COUNTROWS`, agregaciones de no-resumen) y paneles condicionales de filtrado.

---

## Visualizaciones clave y hallazgos

### Principales Hallazgos

* **Masa Salarial Expuesta en Riesgo Alto:** Se identificó a un grupo auditable de **100 empleados en Riesgo Alto**, lo que representa un impacto financiero directo de **$1.13M en masa salarial mensual** expuesta a pérdida por rotación inminente.
* **Concentración Crítica por Rol:** Los puestos de *Assistant Boutique Manager* y *Junior Designer* lideran la lista de fugas activas y concentran la mayor densidad de perfiles en riesgo (24 y 18 empleados respectivamente).
* **El "Efecto Estancamiento" (Tolerancia Cero):** En perfiles como *Assistant Manager*, la media de tiempo en el puesto es prácticamente idéntica al tiempo sin recibir un ascenso (~7.25 años), demostrando que la falta de progresión laboral es el catalizador principal de salida.
* **Neutralidad Demográfica vs. Fricción Operativa:** Se probó estadísticamente que el género es neutro ($p = 0.29$) respecto a la rotación, mientras que la combinación de sobretiempo (`OverTime = Yes`) y bajas calificaciones de balance vida-trabajo triplica el índice de insatisfacción.

### Recomendaciones / Lecciones

* **Ajuste de Pisos Salariales Operativos:** Reorganizar la banda salarial en roles clave donde la brecha entre el sueldo mínimo ($4.0k) y el promedio ($6.9k) genera descontento inmediato.
* **Plan de Movilidad Interna a 2 Años:** Implementar programas de promoción o rotación horizontal antes de cumplir el umbral crítico de 3 años de estancamiento en roles boutique.
* **Auditoría de Sobrecarga de Trabajo:** Revisar las políticas de horas extras en el personal soltero y operativo, redistribuyendo turnos para evitar la acumulación de factores de riesgo alto.
