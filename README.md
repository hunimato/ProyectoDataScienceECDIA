# Proyectos de Data Science & Machine Learning

**Hugo Martínez Tornaria**
Nutricionista clínico · Especialista en Telemedicina · Docente universitario
Especialización en Ciencia de Datos e IA — UTEC / ECDIA

---

## Estructura del repositorio

Este repositorio contiene **3 proyectos independientes**, cada uno en su propia rama:

| Rama | Proyecto | Archivo |
|------|----------|---------|
| [`feature/market-basket`](#-rama-featuremarket-basket) | Market Basket Analysis — UK Retail | `grupo_3.py` |
| [`feature/co2-emissions`](#-rama-featureco2-emissions) | Predicción CO₂ Agro-alimentario (BID) | `MI_CO2__4_.ipynb` |
| [`feature/no-show-prediction`](#-rama-featureno-show-prediction) | Predicción de Inasistencias Médicas | `Hugo_Martinez_...ipynb` |

---

##  Rama: `feature/market-basket`
### Market Basket Analysis — UK Retail (2010–2011)

**Equipo:** Hugo Martínez · Jeasmine Nahui · Leticia Colombo · Valentina Ghan
**Contexto:** Fundamentos de Programación para Ciencia de Datos e IA — UTEC/ECDIA

Análisis exploratorio completo sobre **522.065 transacciones** de un minorista del Reino Unido (dic 2010 – dic 2011). El objetivo fue identificar patrones de venta, tendencias temporales y relaciones entre categorías de productos para generar recomendaciones comerciales accionables.

**Lo más destacado:**
-  Limpieza de datos con imputación del 26% de nulos en `CustomerID`
-  Categorización manual de productos en **25+ categorías** (reduciendo "Otros" a < 5%)
-  El crecimiento del 60% en Q4 se explica por **captación de nuevos clientes**, no por mayor ticket promedio
-  Similitudes fuertes entre categorías detectadas con índice Jaccard: Papelería↔Bolsas (0.65), Ornamentos↔Decoración (0.72)
-  Dashboard interactivo con Dash + ngrok

**Stack:** `pandas` · `numpy` · `matplotlib` · `seaborn` · `plotly` · `statsmodels` · `prince` · `dash` · `networkx`

---

## 🌱 Rama: `feature/co2-emissions`
### CO₂ Emissions Prediction — Agro-food Sector (BID Countries)

**Equipo:** Hugo Martínez · Andrea Aranda · Yuri Biardo
**Contexto:** MISTI GTL AI Uruguay 2026

Análisis y predicción de emisiones de CO₂ del sector agro-alimentario en países miembros del **Banco Interamericano de Desarrollo (BID)**, con proyecciones hacia **2030** alineadas a compromisos climáticos internacionales.

**Lo más destacado:**
- Datos filtrados a los últimos 10 años disponibles, solo países BID
- Subsectores analizados: procesamiento de alimentos, manufactura de insumos, transporte agro
- Identificación de tendencias históricas y variables predictoras de emisiones
- Proyecciones a 2030 como insumo para organismos multilaterales y ministerios de la región
- Enfoque exploratorio y predictivo — sin prescripción de políticas

**Stack:** `pandas` · `numpy` · `matplotlib` · `seaborn` · `scikit-learn` · `plotly`

---

## 🏥 Rama: `feature/no-show-prediction`
### Medical Appointment No-Show Prediction — XGBoost

**Autor:** Hugo Martínez Tornaria
**Contexto:** Examen — Automatización y Machine Learning, UTEC/ECDIA

Modelo de **clasificación binaria** para predecir si un paciente faltará a su consulta médica, usando datos del sistema de salud de Vitória, Brasil (110.527 turnos, abril–junio 2016). Desbalance de clases: 80% asiste / 20% falta.

**Lo más destacado:**
- Feature engineering: `dias_espera`, `faltas_previas`, `turnos_previos`
- Tratamiento riguroso de **data leakage** — punto central de la defensa ante tribunal
- Modelo final: **XGBoost** con optimización de hiperparámetros
- **ROC-AUC: 0.7516** sobre el conjunto de prueba
- Aplicación clínica directa: gestión de agenda médica y reducción de tiempos muertos

**Stack:** `pandas` · `numpy` · `matplotlib` · `seaborn` · `scikit-learn` · `xgboost`

---

## Autor

**Hugo Martínez Tornaria**
- Especialización en Ciencia de Datos e IA — UTEC / ECDIA
