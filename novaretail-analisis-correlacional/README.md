# 🛍️ NovaRetail+: Factores asociados al ingreso anual del cliente

Análisis correlacional exploratorio sobre qué variables del comportamiento del cliente están más asociadas con el ingreso anual que genera para el negocio. Proyecto desarrollado durante el bootcamp de Data Analytics de TripleTen.

## 🎯 Objetivo

Para el equipo de Crecimiento y Retención de NovaRetail+ (e-commerce en Latinoamérica): identificar qué factores del comportamiento del cliente están más fuertemente asociados con el ingreso anual generado, sin asumir causalidad.

## 🗂️ Datos

`novaretail_comportamiento_clientes_2024.csv` — 15,000 clientes con edad, nivel de ingreso, visitas y compras mensuales, gasto en publicidad dirigida, satisfacción, membresía premium, abandono, tipo de dispositivo, región e ingreso anual generado.

## 🛠️ Herramientas

Python: pandas, NumPy, seaborn, matplotlib, SciPy (Pearson, Spearman, punto-biserial, chi-cuadrada / V de Cramér).

## 🔍 Metodología

1. **Carga y validación** de tipos de datos y valores faltantes.
2. **Preparación de datos** — corrección de tipos y documentación de supuestos.
3. **Visualización de relaciones** — mapa de calor de correlaciones y scatterplots de los pares más relevantes.
4. **Coeficientes de correlación** según el tipo de variable: Pearson y Spearman (numérica-numérica), punto-biserial (numérica-binaria) y V de Cramér (categórica-categórica).
5. **Interpretación para el negocio** de cada hallazgo, señalando explícitamente qué no se puede afirmar (correlación ≠ causalidad).

## 📊 Hallazgos clave

- **Compras mensuales e ingreso anual** están fuertemente correlacionadas (ρ = 0.9675, p < 0.05) — la relación más fuerte del análisis.
- **Visitas mensuales e ingreso anual** muestran una correlación positiva pero moderada-débil (r = 0.3371) — más tráfico no se traduce directamente en más ingreso.
- La **membresía premium** tiene una asociación muy débil con el ingreso anual (r = 0.0931) y con el abandono (r = -0.1205): no es, por sí sola, un buen predictor de ninguno de los dos.
- **Tipo de dispositivo y región** son prácticamente independientes entre sí (V de Cramér = 0.0124).

## 💡 Recomendación de negocio

Enfocar las estrategias de retención e ingresos en aumentar la frecuencia de compra (la variable más asociada al ingreso anual) en vez de solo el tráfico, y complementar estos hallazgos correlacionales con modelos predictivos o experimentos controlados antes de tomar decisiones que asuman causalidad.

## 📁 Contenido

- [`analisis_novaretail.ipynb`](./analisis_novaretail.ipynb) — notebook completo con la limpieza, las 4 pruebas de correlación y la interpretación de negocio de cada hallazgo.
