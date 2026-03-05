# Medical Appointment No-Show Prediction — XGBoost

> Clasificación binaria para predecir inasistencias a consultas médicas usando datos del sistema de salud de Vitória, Brasil. ROC-AUC: 0.7516.

**Autor:** Hugo Martínez Tornaria
**Curso:** Automatización y Machine Learning — UTEC / ECDIA
**Rama:** `/no-show-prediction`

---

## Descripción del problema

Predecir si un paciente **faltará a su consulta médica programada**, utilizando únicamente información disponible al momento de hacer la reserva del turno.

Se trata de un problema de **clasificación binaria** con variable objetivo `Falta a consulta` (Yes = faltó / No = asistió).

> Desde la perspectiva clínica, este modelo tiene aplicación directa en la gestión de turnos: permite anticipar inasistencias, optimizar la agenda médica y reducir el desperdicio de tiempo clínico — un problema real y cotidiano en cualquier sistema de salud.

---

## Dataset

| Característica | Valor |
|----------------|-------|
| Fuente | Sistema de salud de Vitória, Brasil (UTEC) |
| Filas (turnos) | 110.527 |
| Variables | 14 |
| Período | Abril — Junio 2016 |
| Clase mayoritaria | Asiste (≈ 80%) |
| Clase minoritaria | Falta (≈ 20%) |

### Variables originales

| Variable | Tipo | Descripción |
|----------|------|-------------|
| `PatientId` | Numérico | ID del paciente (no predictivo) |
| `AppointmentID` | Numérico | ID del turno (no predictivo) |
| `Gender` | Categórico | Género (M / F) |
| `FechaReserva` | Fecha | Fecha en que se agendó el turno |
| `FechaConsulta` | Fecha | Fecha de la consulta programada |
| `Edad` | Numérico | Edad del paciente |
| `Barrio` | Categórico | Barrio de residencia (81 categorías) |
| `Becado` | Binario | Recibe subsidio social (0/1) |
| `Hipertension` | Binario | Tiene hipertensión (0/1) |
| `Diabetes` | Binario | Tiene diabetes (0/1) |
| `Alcoholismo` | Binario | Tiene alcoholismo registrado (0/1) |
| `Discapacidad` | Binario | Tiene alguna discapacidad (0/1) |
| `Recibió SMS` | Binario | Recibió recordatorio por SMS (0/1) |
| `Falta a consulta` | Categórico | **Variable objetivo** |

---

## Feature Engineering

Variables creadas durante el análisis con alto poder predictivo:

| Variable nueva | Descripción |
|----------------|-------------|
| `dias_espera` | Días entre la fecha de reserva y la fecha de consulta |
| `faltas_previas` | Tasa histórica de inasistencias del paciente |
| `turnos_previos` | Cantidad de turnos anteriores registrados del paciente |

> **Manejo de data leakage:** Se aplicó un tratamiento riguroso para garantizar que ninguna variable construida con información "futura" contamine el entrenamiento del modelo. Este fue uno de los puntos centrales de la defensa ante el tribunal.

---

## Modelo y resultados

| Parámetro | Detalle |
|-----------|---------|
| Algoritmo | XGBoost (optimizado con GridSearchCV) |
| Métrica principal | ROC-AUC |
| **ROC-AUC obtenido** | **0.7516** |
| Justificación de métrica | Dataset desbalanceado (80/20) → ROC-AUC es más informativo que accuracy |

### Métricas evaluadas
- ROC-AUC (principal)
- Precision / Recall
- F1-Score
- Matriz de confusión

---

## Estructura del notebook

1. **Resumen y descripción del dataset**
2. **Análisis exploratorio (EDA)** — distribuciones, correlaciones, desbalance de clases
3. **Preprocesamiento** — encoding, escalado, manejo de fechas
4. **Feature engineering** — creación de `dias_espera`, `faltas_previas`, `turnos_previos`
5. **Modelado** — baseline, XGBoost, optimización de hiperparámetros
6. **Evaluación** — métricas, curva ROC, análisis de errores
7. **Conclusiones** — interpretación clínica y técnica de los resultados

---

## Stack tecnológico

`pandas` · `numpy` · `matplotlib` · `seaborn` · `scikit-learn` · `xgboost`

---

## Archivo

| Archivo | Descripción |
|---------|-------------|
| `Hugo_Martinez_Tornaria_Notebook_Examen_Automatizacion__1_.ipynb` | Notebook completo del examen |

---

## Cómo ejecutar

El notebook fue desarrollado en **Google Colab / Jupyter**.

1. Asegurate de tener el dataset de turnos médicos disponible
2. Instalar dependencias: `pip install xgboost scikit-learn pandas matplotlib seaborn`
3. Ejecutar las celdas en orden desde el inicio

---

## Contexto clínico

Como médico con 30 años de experiencia en nutrición clínica y telemedicina, este problema refleja un desafío real del día a día: las inasistencias generan tiempos muertos, retrasos en la atención y pérdida de recursos. Un modelo predictivo de este tipo permitiría implementar recordatorios proactivos, llamadas de confirmación selectivas o gestión dinámica de la agenda, priorizando los turnos con mayor riesgo de inasistencia.
