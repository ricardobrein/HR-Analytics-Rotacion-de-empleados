## Human Resources-Analytics / Rotacion de empleados
![Caso de estudio](media/img1.png)

La alta rotación de empleados supone **grandes perdidas para las empresas**, no se trata solo del dinero, sino de la incapacidad de retener el talento y tener que dedicar esfuerzos constantes a integrar nuevas personas en el equipo, además que reemplazar empleados de alto nivel suele ser una tarea ardua y costosa.
![Principales problemas de la rotacion](media/img2.png)

Los costos también incluyen:

- Costo de baja
- Costo de contratación (publicidad, entrevistas, contratación)
- Coste de incorporación de una nueva persona (formación, tiempo de gestión)
- Pérdida de productividad (una persona nueva puede tardar entre 1 y 2 años en alcanzar la productividad de una persona existente)

En este análisis vamos a hechar un vistazo al dataset de **IBM HR Analytics Employee Attrition & Performance**, que consta de 1470 registros de empleados de una compañia y recoge 35 caracteristicas para cada uno, 237 de los registros son de Ex-empleados, y nuestro objetivo es **averiguar cuales son los puntos débiles de nuestro sistema de RRHH** y por qué estos empleados se han ido. Queremos detectar esas necesidades y puntos en los cuales el trabajador no se siente contento.

## Objetivos especificos
- Comprender qué factores contribuyen más a la rotación de empleados.
- Agruparlos y clasificarlos para encontrar patrones significativos en las características de los empleados.
- Crear un modelo que prediga si un determinado empleado abandonará la empresa o no.
- Crear y mejorar las estrategias de retención de talento.
- Que la gerencia y el Departamento de RRHH tenga informacion solida para mejorar la toma de decisiones.

## Planteamiento del caso.

En este [notebook](https://github.com/ricardobrein/HR-Analytics-Rotacion-de-empleados/blob/main/Notebook-employee-retention-and-prediction.ipynb) está todo el código paso a paso y el modelo mental que se aplica a la hora de abordar el problema.
 
1. El EDA revisando los datos a ver que conseguimos y además gráficamente, vamos a buscar algunos patrones o generalidades en ambos grupos.
2. Continuaremos con la prueba de los tres modelos de clasificación para este tipo de situaciones donde lo que queremos conseguir es ls generalización de una probabilidad u otra los modelos son: Random Forest, Regresion Logística, Xgboost, por otra parte tambien crearemos una red neuronal con Tensorflow Para clasificación y evaluaremos el rendimiento con una **matriz de confusión**, para ver cuales modelos nos dan los mejores resultados en cusnto a F1, precision, sensibilidad, etc.
3. Sabiendo que los datos están desbalanceados se crea uns tendencia lógica a predecir mejor la clase mayoritária, entonces, vamos a aplicar oversampling con SMOTE, para igualar ambas clases y entrenaré los modelos nuevamente.
4. Evaluación de rendimiento con las pricnipales medidas utilizadas en problemas de clasificación.

Ya montados en el carro, como hw mencionado antes, creé una **red neuronal sencilla con la API sequential de Tensorflow.** sera una red por capas, que tendra algunas capas densas y funciones de activación ReLU y sigmoid. en el notebook encontrarás todo.

Como última parte, se me ocurre **eliminar más caracteristicas de los datos** ya que después de la limpieza básica me habian quedado 26, utilice el modulo de sklearn Recursive Feature Elimination, y seleccione las 15 carácteristicas principales, lo cual, aparte de reducir la complejidad del modelo, nos daría una visión más amplia de cuales podrían ser las preocupaciones principales de los empleados quen han abandona o que estan por hacerlo.

[JupyterNotebook completo](https://github.com/ricardobrein/HR-Analytics-Rotacion-de-empleados/blob/main/Notebook-employee-retention-and-prediction.ipynb)

 Gracias por leer, hasta la proxima. 🙋‍♂️

 ### Referencias y agradecimientos:
- **Dataset:** https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset
- **Lecturas** https://www.academia.edu/download/63206732/00-Guide-intellisys-employee20200505-127995-13vhqr8.pdf
- **Matriz de confusion** https://empresas.blogthinkbig.com/como-interpretar-la-matriz-de-confusion-ejemplo-practico/
