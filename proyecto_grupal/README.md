# Proyecto grupal · Análisis de un dataset de UCI

Este es el proyecto integrador del curso. Lo hacen en equipos de 3 personas. La idea es simple: agarrar un dataset real, ensuciarse las manos con él, y contar lo que encontraron.

Es un ejercicio de **análisis exploratorio**: cargar datos reales, limpiarlos, explorarlos, y sacar conclusiones que se puedan defender con evidencia. Todo lo que necesitan ya lo vimos en clase.

## Qué tienen que entregar

Dos archivos:

1. **Un notebook** (`.ipynb`) con todo el código, corriendo de arriba a abajo sin errores.
2. **Una presentación en PDF** (5-8 slides está bien) explicando el proyecto: qué dataset eligieron, qué hicieron, qué encontraron y por qué les importa.

**Fecha de entrega:** _[completar]_
**Cómo entregar:** _[completar]_

## El dataset

Elijan **uno** de estos tres datasets del repositorio de UCI. Los tres están pensados para poder cargarse igual de fácil (revisen el notebook `ejemplo_carga_uci.ipynb` en esta misma carpeta, ahí está el código listo para copiar):

| Dataset | ID en UCI | Filas | De qué se trata |
|---|---|---|---|
| **Wine Quality** | 186 | ~4,900 | Propiedades físico-químicas de vinos (acidez, azúcar, alcohol, etc.) y una nota de calidad de 0 a 10. |
| **Student Performance** | 320 | ~650 | Datos de estudiantes (familia, hábitos de estudio, asistencia) y sus notas finales. Mezcla columnas numéricas y categóricas. |
| **Auto MPG** | 9 | ~400 | Caracterí|sticas de autos (cilindros, peso, potencia, año) y su consumo en millas por galón. Tiene valores faltantes de verdad. |

No hay un dataset "correcto". Wine Quality es el más numérico y limpio. Student Performance tiene más variedad de tipos de datos, útil si quieren trabajar agrupaciones y categorías. Auto MPG los obliga a lidiar con datos faltantes desde el inicio. Elijan según lo que les parezca más interesante analizar.

## Qué tiene que incluir el notebook

No es una lista de casillas para llenar por llenar — cada punto está ahí porque conecta con algo que vimos en el curso. La idea es que el notebook cuente una historia, con estas piezas dentro:

**1. Carga e inspección**
Cargar el dataset, revisar su forma (`shape`, `info()`, `describe()`), y detectar valores nulos o inconsistencias. Esto es la Clase 6/7.

**2. Limpieza**
Documentar qué decisiones tomaron con los datos faltantes o raros (¿los eliminaron? ¿los imputaron? ¿por qué?). No hay una respuesta única, pero la decisión tiene que estar justificada, no solo `dropna()` porque sí.

**3. Al menos un cálculo hecho "a mano"**
Este es el punto que más nos importa a nivel de fundamentos: pandas y numpy tienen métodos que hacen todo por ustedes (`value_counts()`, `groupby()`, operaciones vectorizadas), y está bien usarlos. Pero en **al menos un punto del análisis**, tienen que resolver algo reconstruyendo la lógica con las herramientas de las primeras clases, para demostrar que entienden qué hay detrás del método de pandas. Concretamente, el notebook debe usar, en algún momento con un propósito real:

- Una **comprensión de lista** — por ejemplo, para clasificar valores en categorías o armar una lista filtrada.
- Un **diccionario construido a mano** — por ejemplo, contar frecuencias con un `for` y `dict.get()`, y después comparar el resultado contra lo que da `value_counts()` (¿coincide?).
- Un **bucle `while`** — por ejemplo, una búsqueda iterativa o un cálculo acumulativo (cuántos registros hacen falta para llegar al 50% de algo, cuántas iteraciones toma converger a un valor, etc.).
- Un **bucle `for`** recorriendo datos "a mano" en al menos un caso donde normalmente usarían una operación vectorizada — y si quieren, comparen qué tan más lento es contra la versión de pandas/numpy. Es un buen argumento para su presentación.

No hace falta inventar un ejercicio artificial para esto: seguramente aparece solo si, por ejemplo, arman un diccionario de mapeo para categorizar una columna, o si quieren replicar a mano una agregación antes de confiar en `groupby`.

**4. Análisis con NumPy**
Al menos una parte del análisis usando arrays y operaciones vectorizadas de NumPy (estadísticas, indexado booleano, alguna operación entre columnas). No tiene que ser todo el análisis — pandas ya usa NumPy por debajo — pero muestren que saben trabajar directamente con arrays.

**5. Análisis con Pandas**
El grueso del análisis: filtrado, `groupby`, ordenamientos, alguna tabla pivote si aplica. Formulen 2-3 preguntas de negocio o de investigación sobre el dataset (ej. "¿qué variable se relaciona más con la calidad del vino?", "¿el nivel educativo de los padres influye en la nota final?") y respóndanlas con código.

**6. Al menos 2 visualizaciones**
Gráficos que ayuden a sostener sus conclusiones (no gráficos por decoración). Un histograma, un boxplot, un scatter, lo que tenga sentido para lo que están mostrando.

**7. Conclusiones**
Un cierre en markdown con lo que encontraron, en lenguaje claro. Si algo no dio lo que esperaban, también cuenten eso.

## Qué tiene que incluir el PPT

Es el resumen de lo que hicieron en el notebook, pensado para presentarse en 5-10 minutos:

- Qué dataset eligieron y por qué.
- Qué preguntas se hicieron.
- Los hallazgos principales, apoyados en los gráficos del notebook (no texto suelto — muestren evidencia).
- Una slide contando qué decisión de limpieza tomaron y por qué (esto suele ser lo más revelador de si entendieron los datos).
- Conclusión: si tuvieran que resumir el dataset en una frase para alguien que nunca lo vio, ¿cuál sería?

No hace falta que sea bonito ni con animaciones. Que sea claro.


## Por dónde empezar

Abran `ejemplo_carga_uci.ipynb` en esta misma carpeta. Tiene el código para cargar los tres datasets en Google Colab y una inspección rápida de ejemplo, para que no pierdan tiempo peleándose con la carga de datos y puedan ir directo al análisis.
