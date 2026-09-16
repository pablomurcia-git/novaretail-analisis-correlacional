# 🛍️ NovaRetail+: Factores asociados al ingreso anual del cliente

Análisis correlacional exploratorio sobre qué variables del comportamiento del cliente están más asociadas con el ingreso anual que genera para el negocio. Proyecto desarrollado durante el bootcamp de Data Analytics de TripleTen.

## 📌 Sobre el proyecto

NovaRetail+ es una plataforma de e-commerce en Latinoamérica con millones de usuarios. Hacia el cierre de 2024, su equipo de Crecimiento y Retención tenía una pregunta abierta y sin responder: de todo lo que se sabe del comportamiento de un cliente (cuánto visita, cuánto compra, si tiene membresía premium, cuánto se invierte en publicidad dirigida a él), ¿qué es lo que realmente se mueve junto con su ingreso anual? La respuesta debía servir para enfocar esfuerzos de retención, pero sin caer en el error de confundir correlación con causalidad.

## 🎯 Objetivo inicial

Para el equipo de Crecimiento y Retención de NovaRetail+: identificar qué factores del comportamiento del cliente están más fuertemente asociados con el ingreso anual generado, dejando explícito en cada hallazgo qué se puede y qué no se puede afirmar a partir de una correlación.

## 🗂️ Datos

`novaretail_comportamiento_clientes_2024.csv` — 15,000 clientes con edad, nivel de ingreso, visitas y compras mensuales, gasto en publicidad dirigida, satisfacción, membresía premium, abandono, tipo de dispositivo, región e ingreso anual generado.

## 🛠️ Herramientas

Python: pandas, NumPy, seaborn, matplotlib, SciPy (Pearson, Spearman, punto-biserial, chi-cuadrada / V de Cramér).

## 🚀 Cómo lo desarrollé

Abordé el análisis como una exploración progresiva, dejando que el tipo de cada variable determinara qué prueba estadística usar en lugar de aplicar una sola fórmula a todo:

1. **Cargué y validé el dataset** revisando tipos de datos y valores faltantes o fuera de rango, para entender el "terreno" antes de correlacionar nada.
2. **Preparé los datos** corrigiendo tipos y documentando los supuestos que iba tomando en el camino, de forma que cualquier persona pudiera auditar el análisis después.
3. **Visualicé las relaciones primero**, con un mapa de calor de correlaciones y scatterplots de los pares de variables más relevantes, para tener una intuición visual antes de calcular ningún coeficiente.
4. **Elegí el coeficiente correcto según el tipo de variable**: Pearson y Spearman para pares numéricos, punto-biserial para relaciones numérica-binaria, y V de Cramér para relaciones entre categóricas — en vez de forzar una sola métrica sobre datos que no la soportaban.
5. **Interpreté cada hallazgo para negocio**, señalando explícitamente los límites de un análisis correlacional (correlación ≠ causalidad) para que el equipo no tomara decisiones más allá de lo que los datos realmente permitían afirmar.

## ✅ Qué logré

- Identifiqué la relación más fuerte de todo el análisis: **compras mensuales e ingreso anual** están fuertemente correlacionadas (ρ = 0.9675, p < 0.05), señalando la frecuencia de compra como la palanca más clara sobre el ingreso.
- Descubrí que **más tráfico no es lo mismo que más ingreso**: las visitas mensuales solo muestran una correlación positiva moderada-débil con el ingreso anual (r = 0.3371).
- Puse a prueba una suposición común del negocio y la refuté con datos: la **membresía premium** tiene una asociación muy débil tanto con el ingreso anual (r = 0.0931) como con el abandono (r = -0.1205), por lo que no es, por sí sola, un buen predictor de ninguno de los dos.
- Verifiqué que **tipo de dispositivo y región** son prácticamente independientes entre sí (V de Cramér = 0.0124), descartando una hipótesis de segmentación que no tenía sustento.
- Entregué cada hallazgo con su propia advertencia de interpretación, dejando claro qué se puede accionar directamente y qué requeriría un experimento controlado adicional.

## 💡 Recomendación de negocio

Enfocar las estrategias de retención e ingresos en aumentar la frecuencia de compra (la variable más asociada al ingreso anual) en vez de solo el tráfico, y complementar estos hallazgos correlacionales con modelos predictivos o experimentos controlados antes de tomar decisiones que asuman causalidad.

## 📁 Contenido

- [`analisis_novaretail.ipynb`](./analisis_novaretail.ipynb) — notebook completo con la limpieza, las 4 pruebas de correlación y la interpretación de negocio de cada hallazgo.
