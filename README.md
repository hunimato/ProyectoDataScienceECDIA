# CO₂ Emissions Prediction — Agro-food Sector (BID Countries)

> Análisis histórico y modelado predictivo de emisiones de CO₂ del sector agro-alimentario en países miembros del BID, con proyecciones hacia 2030.

**Equipo:** Hugo Martínez · Andrea Aranda · Yuri Biardo
**Programa:** MISTI GTL AI Uruguay 2026
**Rama:** `feature/co2-emissions`

---

## Descripción del proyecto

Este proyecto analiza las emisiones de CO₂ asociadas al sistema agro-industrial y agro-alimentario en los países miembros del **Banco Interamericano de Desarrollo (BID)**. El dataset proviene de Kaggle y contiene información anual por país con desglose sectorial dentro de la cadena de valor agro-alimentaria.

El horizonte de proyección elegido es **2030**, por su relevancia en los compromisos internacionales de sostenibilidad climática adoptados por los países de la región.

---

## Objetivos

- Explorar patrones históricos de emisiones de CO₂ agro-industrial por país y subsector
- Identificar las variables más relevantes para predecir la trayectoria de emisiones
- Evaluar la viabilidad de modelos predictivos con proyecciones a 2030
- Proveer un marco analítico reproducible para monitoreo de sostenibilidad en países BID

> Este trabajo es **exploratorio y predictivo**. No asume relaciones causales ni prescribe políticas públicas.

---

## Alcance del análisis

| Parámetro | Detalle |
|-----------|---------|
| Países incluidos | Miembros del BID |
| Período analizado | Últimos 10 años disponibles en el dataset |
| Subsectores | Procesamiento de alimentos, manufactura de insumos, transporte agro |
| Horizonte de proyección | 2030 |
| Fuente del dataset | Kaggle (datos públicos FAO/FAOSTAT) |

---

## Estructura del análisis

### Exploración y preprocesamiento
- Filtrado por países BID y últimos 10 años
- Limpieza y estandarización de variables
- Análisis de valores faltantes y consistencia temporal

### Análisis exploratorio
- Patrones históricos de emisiones por país y subsector
- Comparativas regionales entre países BID
- Identificación de tendencias y outliers

### Feature engineering
- Selección y construcción de variables predictoras relevantes
- Evaluación de la importancia de cada variable sobre las emisiones

### Modelado predictivo
- Evaluación de modelos para proyección de emisiones
- Proyecciones hacia el año 2030
- Análisis de incertidumbre en las predicciones

---

## Contexto y relevancia

Este trabajo se enmarca en la agenda climática internacional. El sector agro-alimentario es uno de los principales emisores de gases de efecto invernadero a nivel global, y los países de América Latina y el Caribe —mayoría miembros del BID— enfrentan el desafío de conciliar el desarrollo agropecuario con los compromisos de reducción de emisiones asumidos en acuerdos como el Acuerdo de París.

Contar con modelos predictivos robustos y reproducibles es un insumo clave para organismos multilaterales, ministerios de agricultura y agencias de medio ambiente de la región.

---

## Stack tecnológico

`pandas` · `numpy` · `matplotlib` · `seaborn` · `scikit-learn` · `plotly`

---

## Archivo

| Archivo | Descripción |
|---------|-------------|
| `MI_CO2__4_.ipynb` | Notebook principal con el análisis completo |

---

## Cómo ejecutar

El notebook fue desarrollado en **Google Colab**.

1. Descargar el dataset desde [Kaggle](https://www.kaggle.com/) (CO2 emissions agro-food)
2. Subir el archivo a Google Drive
3. Abrir `MI_CO2__4_.ipynb` en Colab y ajustar la ruta del dataset
4. Ejecutar las celdas en orden

## Resultados principales

| Métrica | Valor |
|---------|-------|
| Modelo seleccionado | ElasticNet (alpha=0.01, l1_ratio=0.8) |
| R² en test | Mayor al de Random Forest y Gradient Boosting |
| Período de entrenamiento | Hasta 2015 |
| Período de evaluación | 2016–2020 |
| Horizonte de proyección | 2030 |

Hallazgos clave:

Las emisiones agroindustriales en los países BID siguen patrones relativamente estables y estructurados una vez considerados los quiebres estructurales históricos.
Un modelo lineal regularizado (ElasticNet) superó a los modelos de árbol (Random Forest, Gradient Boosting) en estabilidad temporal, con mayor R² y menor RMSE, siendo más adecuado para proyecciones de largo plazo.
Las emisiones están altamente concentradas geográficamente: un grupo reducido de países explica la mayor parte del total regional, con Brasil como principal contribuyente proyectado a 2030.
Las fuentes de emisión con mayor co-movimiento son: procesamiento de alimentos, transporte, consumo doméstico, retail y uso de energía en campo — lo que sugiere que responden a un driver económico común.
Bajo un escenario de mayor integración comercial MERCOSUR-UE, se proyecta un aumento de emisiones concentrado en los países de mayor escala productiva, con impacto relativo mayor en países pequeños pero con menor peso regional absoluto.
