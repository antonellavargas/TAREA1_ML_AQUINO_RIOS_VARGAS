# TAREA1_ML_AQUINO_RIOS_VARGAS
TAREA 1 - MACHINE LEARNING

# Linear Models, Regularization, and Model Selection — Deliverables

# Grupo
- AQUINO MEDINA, CRISTIAN GUSTAVO
- RIOS MEZA, JENNIFER SASKIA
- VARGAS FLORES, JOHANNA ANTONELLA

# Differences observed between OLS, Ridge, and Lasso
- **OLS**: sin regularización; varianza alta si hay multicolinealidad. Coeficientes no se encogen a 0.
- **Ridge (L2)**: encoge coeficientes; reduce varianza; **no** hace selección exacta (coeficientes rara vez son 0).
- **Lasso (L1)**: puede poner coeficientes **exactamente en 0** (selección de variables); útil con muchas features y colinealidad.
- Con **features polinomiales** (grado 2), el espacio crece y aparecen fuertes correlaciones → Ridge/Lasso evitan overfitting.

# Effect of learning rate on gradient descent
- **LR muy bajo**: convergencia lenta (muchas iteraciones para reducir el coste).
- **LR moderado**: converge de forma estable y rápida.
- **LR muy alto**: puede divergir u oscilar (coste no desciende de forma monótona).

# How k-fold cross-validation influenced the choice of regularization strength
- Con **KFold=5**, se evalúa el error medio en validación para cada α (λ).
- **α óptimo** equilibra sesgo-varianza; típicamente mejora el **MSE de test** respecto a OLS, sobre todo con multicolinealidad.
- En práctica, `RidgeCV` y `LassoCV` simplifican el proceso y evitan fugas de validación al hacer búsqueda y ajuste de forma integrada.




