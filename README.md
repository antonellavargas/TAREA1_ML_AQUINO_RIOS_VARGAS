# TAREA1_ML_AQUINO_RIOS_VARGAS
TAREA 1 - MACHINE LEARNING

# Linear Models, Regularization, and Model Selection — Deliverables

# Grupo
- AQUINO MEDINA, CRISTIAN GUSTAVO
- RIOS MEZA, JENNIFER SASKIA
- VARGAS FLORES, JOHANNA ANTONELLA

Differences Observed between OLS, Ridge, and Lasso
OLS (Ordinary Least Squares):
Produce coeficientes exactos usando la solución cerrada. Funciona bien, pero es sensible a multicolinealidad y puede generar varianzas altas en los coeficientes cuando las variables están correlacionadas.

Ridge Regression:
Aplica penalización L2. Reduce la magnitud de los coeficientes pero no los lleva exactamente a cero. Fue útil para estabilizar los resultados y controlar la varianza, mejorando la generalización.

Lasso Regression:
Aplica penalización L1. Además de reducir la magnitud, puede hacer que algunos coeficientes se vuelvan exactamente cero, actuando como selección de variables. En los experimentos, Lasso simplificó el modelo eliminando predictores menos relevantes.

Effect of Learning Rate on Gradient Descent
Con lr = 0.001, la convergencia fue muy lenta: el error disminuyó pero requería muchas iteraciones.

Con lr = 0.01, el aprendizaje fue más estable, con un balance entre velocidad y precisión.

Con lr = 0.1, se alcanzó rápidamente un valor cercano al óptimo, convergiendo al mismo resultado que OLS de forma más eficiente.

Aprendimos que una tasa de aprendizaje demasiado baja desperdicia cómputo, mientras que una muy alta podría causar inestabilidad. En este caso, 0.1 resultó ser la más efectiva.

Influence of k-Fold Cross-Validation on Regularization Strength
Usamos validación cruzada para comparar valores de α (λ) en Ridge y Lasso.

El k-fold permitió observar cómo la regularización afectaba al error promedio en diferentes subconjuntos de datos.

La elección final de regularización se basó en minimizar el error promedio de validación, evitando tanto el underfitting (regularización demasiado fuerte) como el overfitting (regularización muy débil).

Esto permitió encontrar un equilibrio entre sesgo y varianza, garantizando un modelo más robusto en datos no vistos.




