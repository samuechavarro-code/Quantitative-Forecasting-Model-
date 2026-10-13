# Quantitative-Forecasting-Model-
Un modelo de inteligencia artificial y gestión de riesgo cuantitativo diseñado para evaluar la vulnerabilidad y la probabilidad de un incremento en el **Downside Beta ($\beta^-$)** de acciones tecnológicas (`QQQ` vs. `SPY`) antes de eventos macroeconómicos de alto impacto en EE. UU. (CPI, FOMC, NFP etc).

El sistema integra datos del mercado en tiempo real, validación temporal sin filtración (*Purged Time-Series Split*), simulación multifactorial de **Monte Carlo** y dimensionamiento óptimo de cobertura basado en el **Criterio de Kelly**.

---

## 🚀 Características Principales

* **Ingesta de Datos en Tiempo Real:** Extracción automática vía `yfinance` de ETF objetivo (`QQQ`), benchmark (`SPY`), índice de volatilidad (`^VIX`), rendimiento de bonos a 10 años (`^TNX`) y 3 meses (`^IRX`).
* **Cálculo de Downside Beta ($\beta^-$):** Mide la sensibilidad de los activos tecnológicos únicamente en los días con rendimientos negativos en el mercado general.
* **Calendario Macroeconómico & Estandarización ($Z$-score):** Ajusta las estimaciones mediante las sorpresas observadas respecto al consenso de Wall Street (ej. CPI, NFP, FED).
* **Purged Time-Series Cross-Validation:** Previene la filtración de datos futuros (*data leakage*) al entrenar el clasificador de ensamble (`HistGradientBoostingClassifier`).
* **Simulación Adaptativa de Monte Carlo:** Genera 5,000 escenarios correlacionados utilizando la matriz de covarianza real del mercado.
* **Cobertura con Criterio de Kelly:** Calcula el porcentaje exacto del portafolio que debería asignarse a activos de protección (`Puts` / `SQQQ`).

---





