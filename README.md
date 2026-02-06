# 🛒 Análisis de Comportamiento y Test A/A/B - App Alimentaria

### 📊 Descripción del Proyecto
Este proyecto analiza el comportamiento de los usuarios en una aplicación de venta de productos alimenticios. El objetivo principal es evaluar si un cambio en la tipografía de la interfaz impacta en la tasa de conversión, utilizando un enfoque basado en datos para validar decisiones de diseño.

### 🎯 Objetivos
* Estudiar el **embudo de ventas (funnel)** para identificar las etapas con mayor pérdida de usuarios.
* Realizar un **Test A/A/B** comparando dos grupos de control frente a un grupo de prueba con el nuevo diseño.
* Validar estadísticamente si existen diferencias significativas en la conversión entre los grupos.

### 🛠️ Tech Stack
* **Python:** Pandas para manipulación de registros.
* **Visualización:** Matplotlib y Seaborn para gráficos de embudo y distribución temporal.
* **Estadística:** `statsmodels.stats.proportion` para pruebas de Z-test.

### 🔬 Análisis Estadístico y Rigor Científico
Para garantizar la validez de los resultados y evitar el error tipo I (falsos positivos) debido a las comparaciones múltiples, se implementó:

1. **Test A/A:** Validación de la homogeneidad de los grupos de control para asegurar que el sistema de división de usuarios fuera correcto.
2. **Corrección de Bonferroni:** Ajuste del nivel de significancia ($\alpha$). Con 16 pruebas de hipótesis realizadas simultáneamente, el $\alpha$ se ajustó para mantener un nivel de confianza del **99.68%**.
3. **Z-Test de Proporciones:** Comparación de cada evento del embudo entre los grupos de control y el grupo experimental.

### 📈 Conclusiones Clave
* **Análisis de Funnel:** Se detectó que la mayor pérdida de usuarios ocurre en el paso de la Pantalla Principal (MainScreenAppear) y a la Pantalla de Ofertas (OffersScreenAppear), donde solo el 61% de los usuarios avanza.
* **Resultado del Experimento:** Tras aplicar la Corrección de Bonferroni, se concluyó que **no hay diferencias estadísticamente significativas** entre las fuentes antiguas y las nuevas. 
* **Recomendación:** El cambio de diseño es seguro de implementar desde una perspectiva de usabilidad, ya que no intimida ni aleja a los usuarios actuales.

---
## 📂 Estructura del Repositorio
* [`notebook.ipynb`](notebook.ipynb): Jupyter Notebook con el preprocesamiento, análisis de embudo y pruebas estadísticas.
* [`datasets`](datasets): Dataset con los eventos y acciones de los usuarios (logs_exp_us.csv).
