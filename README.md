# Market Basket Analysis — UK Retail (2010–2011)

> Análisis exploratorio y de comportamiento de compra sobre 522.000 transacciones de un minorista del Reino Unido.

**Equipo:** Hugo Martínez · Jeasmine Nahui · Leticia Colombo · Valentina Ghan
**Institución:** UTEC / ECDIA — Fundamentos de Programación para Ciencia de Datos e IA
**Rama:** `/market-basket`

---

## Descripción del proyecto

Este proyecto analiza el comportamiento de compra de clientes de un comercio minorista del Reino Unido durante el período diciembre 2010 – diciembre 2011. El dataset contiene **522.065 transacciones** con 7 variables (número de factura, nombre del ítem, cantidad, fecha, precio, ID de cliente y país).

El foco está en identificar patrones de venta, tendencias temporales, y relaciones entre categorías de productos que permitan generar recomendaciones comerciales accionables.

---

## Preguntas clave respondidas

- ¿Cuáles son los productos y categorías más vendidos?
- ¿Qué explica el aumento del 60% en ventas en el último trimestre?
- ¿Los clientes compran más o son más los que compran?
- ¿Existen categorías de productos con comportamiento de compra similar?
- ¿Hay patrones temporales (día, hora, mes) en las transacciones?

---

## Estructura del análisis

### Etapa I — Problemática y dataset
- Descripción del dataset (7 variables, 522.065 filas)
- Definición de 8 preguntas clave sobre comportamiento de compra

### Etapa II — Limpieza y preprocesamiento
- Conversión de tipos y estandarización de formatos
- Imputación de nulos en `CustomerID` (26%) con ID genérico 99999
- Eliminación de devoluciones y transacciones no válidas
- Categorización manual de productos en **25+ categorías** (reduciendo "Otros" a < 5%)
- Creación de variables temporales: momento del día, momento del mes, trimestre

### Etapa III — Visualización y análisis
- Evolución mensual y semanal de ventas, transacciones y clientes
- Análisis de ticket promedio y diversidad de ítems por compra
- Mapas de calor por día/hora y día/mes
- Series de tiempo: descomposición, tests ADF/KPSS, ACF/PACF
- Análisis de correspondencia múltiple (MCA) entre variables categóricas
- Medidas de similitud entre categorías: Manhattan, Euclidiana, **Jaccard**
- Dashboard interactivo con Dash + ngrok

### Etapa IV — Resultados y recomendaciones
- El crecimiento en Q4 se explica por **captación de nuevos clientes**, no por mayor gasto individual
- La categoría **Papelería y Regalos** lidera el impacto en ingresos totales
- Clientes "heavy users" identificados (IDs 12748 y 17841) con potencial mayorista
- Similitudes fuertes detectadas: Papelería↔Bolsas (0.65), Ornamentos↔Decoración (0.72)

---

## Resultados destacados

| Métrica | Valor |
|---------|-------|
| Filas post-limpieza | 475.171 (UK) |
| Categorías creadas | 25+ |
| Categoría "Otros" final | < 5% |
| Período analizado | Dic 2010 – Nov 2011 |
| País de foco | Reino Unido (93% del dataset) |

---

## 🛠️ Stack tecnológico

`pandas` · `numpy` · `matplotlib` · `seaborn` · `plotly` · `statsmodels` · `scipy` · `sklearn` · `prince` · `dash` · `networkx` · `swifter`

---

## Archivo

| Archivo | Descripción |
|---------|-------------|
| `grupo_3.ipynb` | Script principal con todas las etapas del análisis |

---

## Cómo ejecutar

El script fue desarrollado en **Google Colab**. Para ejecutarlo:

1. Subir el dataset `AssignmentData.csv` a Google Drive en `/My Drive/Notebooks/`
2. Abrir el archivo en Colab
3. Ejecutar primero el bloque de **Funciones e Imports**
4. Continuar con las etapas en orden

> El dashboard interactivo (Dash + ngrok) requiere un authtoken de ngrok válido.
