# Análisis de Eficacia de Operadores de Telecomunicaciones (BI)

## Contexto del Proyecto

Una empresa de telecomunicaciones necesita identificar a los operadores de su call center que son "ineficaces" para implementar un plan de acción y coaching. Este proyecto no solo identifica a estos operadores, sino que también desarrolla y valida estadísticamente una metodología para hacerlo de forma proactiva.

El análisis utiliza un enfoque de Business Intelligence, desde la limpieza de datos en Python hasta la visualización en un dashboard de Tableau, para proporcionar a la gerencia de supervisión una herramienta de monitoreo accionable.

## Objetivos del Análisis

1.  **Definir la Ineficacia:** Establecer KPIs claros para medir el bajo rendimiento, como el **Tiempo de Espera Promedio** (`avg_waiting_time`) y la **Tasa de Llamadas Perdidas** (`tasa_perdidas_in`).
2.  **Establecer un Umbral:** Utilizar el **Percentil 95 (P95)** como un umbral estadístico robusto para identificar al 5% de operadores con peor rendimiento.
3.  **Validar la Metodología:** Usar una **Prueba t de Student** para confirmar que la diferencia de rendimiento entre el grupo "eficaz" y el "ineficaz" es estadísticamente significativa ($p < 0.05$).
4.  **Generar Recomendaciones:** Proporcionar un plan de acción segmentado para la gerencia.
5.  **Crear un Dashboard:** Entregar un dashboard en Tableau para el monitoreo proactivo y semanal.

## Herramientas Utilizadas

* **Python:** Lenguaje principal para el análisis.
* **Pandas:** Para la limpieza, transformación, agrupación y agregación de datos.
* **Matplotlib / Seaborn:** Para la visualización de distribuciones y la identificación de umbrales P95.
* **SciPy (stats.ttest_ind):** Para la ejecución de la **Prueba t de Student** y la validación estadística de hipótesis.
* **Tableau Public:** Para la creación del dashboard interactivo final.

## 🚀 Dashboard Interactivo (Tableau Public)

El resultado final del análisis es un dashboard interactivo diseñado para los supervisores, permitiendo el monitoreo semanal de los KPIs clave y la detección temprana de ineficacia.

**[Enlace a tu Dashboard de Tableau Public aquí]**

## Hallazgos Clave y Verificación de Hipótesis

* **Validación Estadística ($p < 0.05$):** Se **RECHAZÓ la Hipótesis Nula** ($H_0$). La diferencia de rendimiento (especialmente en el Tiempo de Espera Promedio) entre el grupo identificado como ineficaz y el eficaz es **estadísticamente significativa**. La metodología P95 es válida.

* **Identificación Sólida:** El análisis detectó a **109 operadores** que superan el umbral P95 en al menos una de las métricas críticas:
    1.  **Ineficiencia en Gestión:** Tiempo de Espera Promedio > 1127 segundos.
    2.  **Baja Disponibilidad:** Tasa de Llamadas Perdidas > 4.5%.

* **Segmento de "Doble Riesgo":** Se identificó un subgrupo de **33 operadores** ineficaces que, además, tienen un número de llamadas salientes casi nulo (< 50), sugiriendo un problema de rol o de proactividad.

## Recomendaciones Estratégicas

Se propone un plan de acción inmediato enfocado en los 109 operadores identificados:

1.  **Enfoque en Eficiencia (Tiempo de Espera):** Implementar **coaching intensivo y segmentado** para el grupo con `avg_waiting_time` alto, enfocado en el uso de herramientas (CRM) y procedimientos.
2.  **Revisión Operacional (Tasa de Pérdida):** El supervisor debe **investigar la causa raíz** de la alta Tasa de Llamadas Perdidas (problemas técnicos, sobrecarga de trabajo, o abandono de puesto).
3.  **Definición de Roles (Doble Riesgo):** Revisar el rol de los **33 operadores** de "doble riesgo". Si su función es proactiva, se debe establecer un KPI mínimo obligatorio de llamadas salientes.
4.  **Monitoreo Proactivo (Dashboard):** Poner en funcionamiento el **Dashboard de Tableau** para los supervisores, con los umbrales P95 como "línea roja" de alerta para la detección temprana.
