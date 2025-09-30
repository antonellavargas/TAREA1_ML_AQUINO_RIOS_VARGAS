# TAREA1_ML_AQUINO_RIOS_VARGAS
TAREA 1 - MACHINE LEARNING

# Linear Models, Regularization, and Model Selection — Deliverables

# Grupo
- AQUINO MEDINA, CRISTIAN GUSTAVO
- RIOS MEZA, JENNIFER SASKIA
- VARGAS FLORES, JOHANNA ANTONELLA

# Differences Observed between OLS, Ridge, and Lasso

## Ordinary Least Squares (OLS):
El modelo de mínimos cuadrados ordinarios entrega una solución exacta al problema de regresión lineal. En este caso, comprobamos que la implementación cerrada coincide con la de scikit-learn, lo cual valida nuestra implementación. Sin embargo, OLS es sensible a la multicolinealidad y puede generar coeficientes inestables si existen variables altamente correlacionadas.

## Ridge Regression (Regularización L2):
Ridge introduce un término de penalización proporcional a la suma de los cuadrados de los coeficientes. Esto hace que los coeficientes se reduzcan, aunque nunca se vuelvan exactamente cero. Su principal ventaja es controlar la varianza del modelo y mejorar la generalización en presencia de multicolinealidad. En nuestros experimentos, Ridge produjo un ajuste más estable que OLS en validación cruzada.

## Lasso Regression (Regularización L1):
Lasso no solo reduce la magnitud de los coeficientes, sino que también puede llevar algunos a cero. Esto equivale a realizar una selección automática de variables, simplificando el modelo y mejorando la interpretabilidad. En nuestros resultados, Lasso descartó predictores menos relevantes, demostrando ser útil cuando se busca un modelo más parsimonioso.
________________________________________
# Effect of Learning Rate on Gradient Descent
La tasa de aprendizaje (lr) es un hiperparámetro crítico en el descenso por gradiente:
•	Con lr = 0.001, observamos una convergencia muy lenta. El error descendía progresivamente, pero se necesitaban muchas más iteraciones para acercarse a la solución de OLS.
•	Con lr = 0.01, el entrenamiento fue más eficiente y alcanzó una buena aproximación al resultado de referencia.
•	Con lr = 0.1, la convergencia fue rápida y precisa, logrando reproducir la solución de OLS en pocas iteraciones.
Esto nos permitió comprobar cómo un lr demasiado bajo implica un gasto computacional innecesario, mientras que uno demasiado alto puede volver inestable el proceso. En este caso, el valor 0.1 fue el óptimo, logrando equilibrio entre rapidez y estabilidad.
________________________________________
# Influence of k-Fold Cross-Validation on Regularization Strength
Para determinar la fuerza de regularización (α o λ), aplicamos validación cruzada k-fold. Este procedimiento divide el conjunto de entrenamiento en varios pliegues, entrenando el modelo en k-1 subconjuntos y validando en el restante.
•	Con este enfoque se pudo evaluar cómo distintos valores de λ afectan el error promedio en validación.
•	Una regularización muy fuerte (λ alto) generó underfitting, con pérdida de capacidad predictiva.
•	Una regularización muy débil (λ cercano a cero) produjo overfitting, con un desempeño alto en entrenamiento pero pobre en validación.
•	El valor óptimo se seleccionó como aquel que minimizó el error promedio en los pliegues, logrando un buen balance entre sesgo y varianza.
Esto garantizó un modelo más robusto y generalizable a datos no vistos.
________________________________________
# Conclusions
1.	Consistencia de Implementación: OLS en forma cerrada y scikit-learn entregaron resultados prácticamente idénticos, confirmando la validez de nuestra solución.
2.	Descenso por Gradiente: Aunque es más costoso iterativamente, demostró ser eficiente con una tasa de aprendizaje adecuada y escalable para datasets grandes, donde la forma cerrada sería impráctica.
3.	Regularización: Tanto Ridge como Lasso mejoraron la estabilidad y generalización frente a OLS. Ridge fue más efectivo reduciendo la varianza, mientras que Lasso añadió valor en selección de variables.
4.	Validación Cruzada: Fue clave en la elección de hiperparámetros de regularización, permitiendo evitar tanto el underfitting como el overfitting y mejorando la confianza en el modelo final.

