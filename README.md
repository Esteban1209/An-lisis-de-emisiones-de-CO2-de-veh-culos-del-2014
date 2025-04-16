# An-lisis-de-emisiones-de-CO2-de-veh-culos-del-2014
RESUMEN
Este estudio presenta un enfoque basado en datos para analizar la relación entre las características de los vehículos, el consumo de combustible y las emisiones de CO₂ utilizando técnicas de aprendizaje automático no supervisado. Se empleó el algoritmo de agrupación K-Means, combinado con el análisis de componentes principales (PCA), para segmentar los vehículos en grupos distintos en función de las especificaciones del motor y el impacto ambiental. Los resultados muestran fuertes correlaciones entre el tamaño del motor, el consumo de combustible y las emisiones, con tres grupos claros: vehículos de alta eficiencia, moderados y de altas emisiones. Los resultados proporcionan información práctica para los responsables políticos y los fabricantes que pretenden reducir la huella de carbono del sector del automóvil.

I.	INTRODUCCIÓN
En el contexto actual de creciente preocupación por el cambio climático y la sostenibilidad energética, el estudio del consumo de combustible y las emisiones de dióxido de carbono (CO₂) se ha convertido en un aspecto fundamental para promover prácticas de transporte más sostenibles. Este trabajo tiene como propósito analizar, mediante técnicas de análisis de datos y herramientas matemáticas implementadas en Python, el comportamiento energético de los vehículos y su impacto ambiental, considerando una serie de variables técnicas y operativas.
El conjunto de datos empleado proviene de Natural Resources Canada, organismo dependiente del Gobierno de Canadá, el cual recopila anualmente información detallada sobre el rendimiento de vehículos comercializados en el país. En particular, este estudio utiliza el Fuel Consumption Ratings Dataset correspondiente al año modelo 2014, el cual se encuentra disponible públicamente a través del portal de datos abiertos del gobierno canadiense [11].

Las variables consideradas en el análisis incluyen el año del modelo, la marca, el modelo, la clase del vehículo, el tamaño del motor, el número de cilindros, el tipo de transmisión, el tipo de combustible, así como los consumos de combustible en ciudad, carretera y combinado. También se consideran las emisiones de CO₂ como indicador principal del impacto ambiental.
A través de este enfoque se busca identificar patrones y correlaciones que permitan una mejor comprensión de los factores que inciden sobre la eficiencia energética vehicular, con el fin de contribuir a la formulación de políticas diferenciadas y estrategias de mitigación orientadas a la sostenibilidad del transporte.

II.	ANTECEDENTES
Hoy en día, muchas personas se han preocupado por el cambio climático y como ha estado evolucionando con el pasar de los años, llegando a dar un gran impacto den la sociedad. Con la tecnología de hoy en día, se puede. Muchas personas han tomado la decisión de realizar distintos análisis de investigación del cómo ha crecido las emisiones del dióxido de carbono en los últimos años gracias al factor lambda de los automóviles que se usa en el día a día [4]. 
Primeramente, en trabajos de investigación pasados, se ha comentado que las emisiones de dióxido de carbono (CO2) depende de las características del vehículo. Por ejemplo, hay motores de vehículos que no poseen un catalizador, los cuales generan que el combustible se gaste mucho más de lo necesario, lo cual genera grandes emisiones de CO2. Por otra parte, comentan que, si existe un buen control de la lambda, este podrá generar emisiones que sean estables y que sean principalmente reducidas, logrando así el poder mantener el control de las emisiones que generan los automóviles. Por último, comenta que cuando un vehículo genera una velocidad de 4000 rpm, este llega a realizar más ciclos de combustión por minuto lo cual incrementa las emisiones debido a que el motor del carro llega a trabajar mucho más rápido generando así mucha más contaminación. [1]
Por otro lado, existe otra investigación el cual comenta que se llegó a evaluar 3 tipos de métodos para poder conocer cuál es el consumo de combustible. En la presente investigación se realizó el método gravimétrico y volumétrico debido a las limitaciones que se encontraban en el balance de carbono. El método gravimétrico es mucho más exacto, sin embrago este requiere de un suministro. Según los resultados obtenidos al implementar ambos métodos, se informó que el consumo llega a variar dependiendo del tipo de método que se esté implementando. Sin embargo, eso no evita que los resultados no puedan ser los esperados, ya que, de igual manera, las emisiones llegan a ser altas ante el uso de los vehículos, sea usando cualquier tipo de método. [2]

III.	JUSTIFICACIÓN 
El análisis del consumo de combustible y las emisiones de CO2, desglosado por tipo de vehículo, es esencial para comprender el impacto ambiental que cada opción representa, según la elección del consumidor. Un número creciente de consumidores toma en consideración la huella ecológica al momento de adquirir un vehículo, optando por alternativas que se alineen con sus valores medioambientales. En este contexto, es crucial que los consumidores estén plenamente informados sobre las implicaciones ecológicas de sus decisiones de compra, entendiendo el tipo de huella que dejarán al optar por determinado modelo [3]. En un escenario global donde las preocupaciones ambientales y el impacto de nuestras acciones sobre el entorno son cada vez más relevantes, es indispensable que los consumidores tomen decisiones informadas y responsables, conscientes del impacto a largo plazo sobre las futuras generaciones. Este análisis también resulta valioso para los fabricantes de vehículos, quienes, conscientes de la creciente demanda de opciones más sostenibles, buscan desarrollar modelos que respondan a los valores y expectativas de los consumidores comprometidos con la protección del medio ambiente [5].

IV.	PREGUNTA DE INVESTIGACIÓN 
¿Cómo influyen las características del vehículo en el consumo de combustible y las emisiones de CO₂?

V.	OBJETIVO GENERAL
Analizar el consumo de combustible y las emisiones de CO₂ en función de las características del vehículo mediante técnicas de cálculo y análisis de datos con Python, utilizando un conjunto de datos representativo para identificar patrones y relaciones clave.

VI.	OBJETIVOS ESPECÍFICOS
Procesar y limpiar el conjunto de datos para eliminar valores atípicos, manejar datos faltantes y estructurar la información de manera óptima para el análisis.
Aplicar técnicas de análisis estadístico y visualización de datos para identificar tendencias en el consumo de combustible y las emisiones de CO₂ según características del vehículo como peso, tipo de motor y aerodinámica.
Desarrollar y evaluar modelos utilizando Python para estimar el consumo de combustible y las emisiones de CO₂ en función de las características del vehículo.

VII.	DETALLES DE LOS DATOS UTILIZADOS EN EL PROYECTO
Cantidad de datos: 1068 líneas
Características de los datos: 
•	MODELYEAR → Año del modelo
•	MAKE → Marca del vehículo
•	MODEL → Modelo del vehículo
•	VEHICLECLASS → Clase del vehículo
•	ENGINESIZE → Tamaño del motor
•	CYLINDERS → Número de cilindros del motor
•	TRANSMISSION → Tipo de transmisión
•	FUELTYPE → Tipo de combustible
•	FUELCONSUMPTION_CITY → Consumo de combustible en ciudad
•	FUELCONSUMPTION_HWY → Consumo de combustible en carretera
•	FUELCONSUMPTION_COMB → Consumo de combustible combinado
•	FUELCONSUMPTION_COMB_MPG → Consumo de combustible combinado en millas por galón
•	CO2EMISSIONS → Emisiones de CO₂
Formato de los datos: CSV

VIII.	COMPRENSIÓN DE LA ESTRUCTURA DE DATOS
La comprensión de datos ayuda a poder realizar las tareas y los análisis de mejor manera, en donde este presenta una eficiencia a la hora de optimizar el acceso, logrando así que su estructura no se tan complicada de entender, además de así llegar y poder eliminar, modificar o insertar datos a esta nueva estructura. 
De igual manera, la comprensión de datos logra el poder analizar los datos de los próximos y presentes proyectos, logrando así en donde se pueda conocer cuál es el comportamiento que tiene alguna situación con lo de su alrededor, sea esta de manera positiva o negativa.
Por lo tanto, para obtener una mejor compresión de los datos realizados para el presente trabajo se clasificarán de la siguiente manera. Los datos necesarios de la presente investigación y como se ha mencionado con anterioridad, constarán de 13 columnas, las cuales estarán divididas de acuerdo con las características que posee cada vehículo para el análisis de este caso. Mientras que constaran de alrededor de 1.063 tipos de automóviles los cuales ayudaran a poder conocer el crecimiento de tal problemática. Los datos o categorías importantes que se tomaran son las siguientes:
 
•	MODELYEAR: Se tomará como un numero entero (año del modelo).
•	MAKE: Se tomará como una categórico (fabricante del vehículo).
•	MODEL: Se tomará como una Categórico (nombre del modelo).
•	VEHICLECLASS: Se tomará como una categórico (clase del vehículo, ej. SUV, Compacto).
•	ENGINESIZE: Se tomará como un numérico continuo (tamaño del motor en litros).
•	CYLINDERS: Se tomara como un número entero (número de cilindros).
•	TRANSMISSION: Se tomará como una categórico (tipo de transmisión, ej. AS5, M6).
•	FUELTYPE: Se tomará como una categórico (tipo de combustible, ej. Z (gasolina), D (diésel)).
•	FUELCONSUMPTION_CITY: Se tomará como un numérico continuo (consumo en ciudad, L/100 km).
•	FUELCONSUMPTION_HWY: Se tomará como un numérico continuo (consumo en carretera, L/100 km).
•	FUELCONSUMPTION_COMB: Se tomará como un numérico continuo (consumo combinado, L/100 km).
•	FUELCONSUMPTION_COMB_MPG: Entero (consumo combinado en millas por galón).
•	CO2EMISSIONS: Entero (emisiones de CO2 en g/km).

IX.	RESUMEN ESTADÍSTICO
Descriptivas básicas
Analizaremos las estadísticas principales de las variables numéricas:
•	Media (promedio): Valor representativo central.
•	Mediana: Valor central que divide la distribución en dos partes iguales.
•	Mínimo y máximo: Rango de valores observados.
•	Desviación estándar: Medida de dispersión o variabilidad.
Medidas de distribución
Aquí exploraremos cómo están distribuidos los datos:
•	Histogramas: Para ver cómo se agrupan los valores en cada variable numérica.
•	Diagramas de caja (boxplots): Para identificar la presencia de valores atípicos (outliers).
•	Sesgo de la distribución: Si los datos están inclinados hacia un lado (asimetría).
Análisis de columnas categóricas
Aquí revisaremos variables como:
•	Marca del vehículo (MAKE)
•	Clase del vehículo (VEHICLECLASS)
•	Tipo de transmisión (TRANSMISSION)
•	Tipo de combustible (FUELTYPE)

X.	VISUALIZACIÓN DE DATOS.
Distribuciones:
Se utilizaron graficas para analizar la distribución y relaciones entre variables. Los histogramas de ENGINESIZE y CO2EMISSIONS muestran un sesgo positivo, lo que demuestra una mayor concentración en motores pequeños y bajas emisiones. Los diagramas de caja para CYLINDERS demuestran que la gran parte de los vehículos tienen 4 o 6 cilindros.
Los gráficos también demuestran una relación lineal directa entre FUELCONSUMPTION_COMB y CO2EMISSIONS. 
Gráfico de dispersión ENGINESIZE vs. CO2EMISSIONS: 
Correlación positiva fuerte (R > 0.85 r>0.85). Esto demuestra que los vehículos con motores más grandes tienden a emitir mayores cantidades de CO₂, probablemente debido a una mayor capacidad de combustión y consumo. Estos datos ayudan al consumidor consciente de su huella ambiental a buscar vehículos con motores más pequeños.
FUELCONSUMPTION_COMB vs. CO2EMISSIONS: Relación lineal directa. Esta relación directa fortifica la dependencia inmediata y directa entre el consumo energético del vehículo y su huella de carbono, y puede ayudar como una base de datos para crear algoritmos predictivos simples en la estimación de emisiones emitidas por el vehículo a analizar.
Estas relaciones son de suma importancia no solo para fines ilustrativos o descriptivos, también estas relaciones nos ayudan para la elaboración de desarrollo de estrategias que busquen la optimización del diseño vehicular. De esta forma se podrían crear regulaciones más estrictas para informar al consumidor de la huella ambiental que están teniendo al comprar un vehículo. [7]


XI.	IDENTIFICACIÓN DE RELACIONES.
Correlaciones entre variables
Calcularemos el coeficiente de correlación de Pearson (para variables numéricas) para ver qué tan relacionadas están:
•	Tamaño del motor (ENGINESIZE) vs. emisiones de CO₂ (CO2EMISSIONS) → ¿Los motores más grandes contaminan más?
•	Consumo de combustible combinado (FUELCONSUMPTION_COMB) vs. emisiones de CO₂ (CO2EMISSIONS) → ¿Mayor consumo implica más emisiones?
•	Número de cilindros (CYLINDERS) vs. consumo de combustible → ¿Más cilindros significa mayor gasto de gasolina?
Si la correlación es cercana a 1 o -1, significa que hay una relación fuerte.
Gráficos de dispersión
ENGINESIZE vs. CO2EMISSIONS → Se espera una relación positiva fuerte.
FUELCONSUMPTION_COMB vs. CO2EMISSIONS → Relación casi lineal.
Número de cilindros vs. emisiones de CO₂ → Para ver si los motores más grandes son los más contaminantes.

Detección de tendencias y patrones:
¿Qué tipo de vehículos son más eficientes?
¿Los autos eléctricos o híbridos realmente contaminan menos?
¿La aerodinámica influye en el consumo de combustible?

XII.	VALORES ATÍPICOS.
Detectados mediante diagramas de caja:
CO2EMISSIONS: Vehículos con emisiones > 400 g/km (ej. GMC Savana 3500, Ford E350).
ENGINESIZE: Motores > 6.5 L (Un ejemplo de esto son. Lamborghini Aventador, Rolls-Royce Phantom). 
Causas probables:
•	Vehículos de lujo con motores V12 o Diesel de alta potencia. 
•	Furgonetas y camiones comerciales con cargas pesadas.
Se detectaron valores atípicos en CO2EMISSIONS (> 400 g/km), más que todo en carros como GMC Savana 3500 o Ford E350. También en ENGINESIZE (> 6.5 L), como Lamborghini Aventador o Rolls-Royce Phantom. Estos datos se asocian a carros de lujo o comerciales de alto rendimiento. Estos datos, pueden ser visto como datos extremos ya que pueden afectar el promedio general de emisiones y consumo, lo que podría provocar un sesgo erróneo del comportamiento estándar del parque vehicular. Se hace la recomendación de analizar los datos por separado o aplicar técnicas como la mediana o el uso de herramientas logarítmicas para lograr una distribución estable [8]. 

XIII.	ALGORITMO SELECCIONADO
El algoritmo K-Means, una técnica de agrupamiento no supervisado ampliamente utilizada en la minería de datos, la cual ha sido complementada con Análisis de Componentes Principales (PCA) con el objetivo de reducir la dimensionalidad de los datos. El algoritmo K-Means permite segmentar vehículos en distintos grupos homogéneos de acuerdo con la similitud de sus características técnicas, tales como el tamaño del motor, el consumo de combustible y las emisiones de CO₂. Por su parte, PCA facilita la representación de datos multidimensionales en un espacio bidimensional, permitiendo conservar la mayor proporción posible de la varianza total, lo cual es crucial para una adecuada visualización e interpretación de patrones estructurales dentro del conjunto de datos.

XIV.	JUSTIFICACIÓN DEL ALGORITMO SELECCIONADO
La elección de K-Means responde a su eficiencia y simplicidad computacional en la detección de estructuras latentes dentro de conjuntos de datos no etiquetados. Esta capacidad resulta especialmente valiosa para identificar grupos de vehículos que presentan comportamientos similares respecto al consumo energético y a las emisiones contaminantes, lo cual puede ser aprovechado en el diseño de estrategias de optimización energética o políticas públicas diferenciadas por segmento. Así mismo, la incorporación del análisis PCA permite mitigar la complejidad inherente de los datos multivariantes, al tiempo que preserva las relaciones fundamentales entre variables. 
Para determinar el número óptimo de agrupamientos, se utilizó el método del codo, lo cual garantizó una selección objetiva del parámetro k, estableciéndose en tres clústeres. Esta combinación metodológica resulta adecuada para estudios exploratorios en los que no se dispone de variables objetivo, además de que facilita el descubrimiento de relaciones no evidentes en los datos originales.

XV.	IMPLEMENTACIÓN DEL ALGORITMO
El proceso de implementación se estructuró en tres fases principales:
•	Preprocesamiento de datos:
En esta etapa, se aplicó una transformación mediante StandardScaler para escalar las variables numéricas, mientras que las variables categóricas fueron codificadas utilizando OneHotEncoder. Ambas transformaciones se integraron mediante un ColumnTransformer, con el propósito de generar una matriz de características consistente y adecuada para su posterior análisis.
•	Reducción de dimensionalidad:
Posteriormente, se aplicó PCA con el fin de proyectar los datos en dos componentes principales. Esta transformación permitió simplificar el análisis, conservando al mismo tiempo la estructura inherente del conjunto de datos original.
•	Clustering con K-Means:
A partir del análisis del método del codo, se estableció que el valor óptimo para k es 3. Con base en ello, se entrenó el modelo de K-Means utilizando los datos previamente normalizados y transformados.

XVI.	RESULTADOS OBTENIDOS
Tras la aplicación del algoritmo K-Means con reducción de dimensionalidad mediante Análisis de Componentes Principales (PCA), se identificaron tres agrupamientos distintos en el conjunto de datos vehiculares, tal como se muestra (Fig. 1.). Cada clúster representa un subconjunto de vehículos con características técnicas y patrones de consumo diferenciados.

 
Fig. 1. Clustering de Vehículos

•	Clúster 0: 
Vehículos de características intermedias, con un tamaño de motor promedio de 3.73 L, seis cilindros, consumo combinado de 11.84 L/100 km y un rendimiento promedio de 24.08 MPG. Este grupo podría corresponder a automóviles sedán de tamaño medio
•	Clúster 1: 
Agrupación de vehículos eficientes, con motores pequeños (≈2.03 L), cuatro cilindros, bajo consumo de combustible (≈8.63 L/100 km) y elevado rendimiento (≈33.4 MPG). Este clúster representa automóviles compactos y posiblemente híbridos.
•	Clúster 2: 
Vehículos de alto consumo, con motores grandes (≈5.26 L), ocho cilindros, consumo de 16.99 L/100 km y bajo rendimiento (≈16.89 MPG), típicamente asociados a SUVs, camionetas o vehículos de alto rendimiento.
La separación de los grupos en el espacio bidimensional generado por PCA demuestra una buena cohesión interna y separación entre clústeres, evidenciando que las variables seleccionadas poseen capacidad discriminativa (Fig. 1.). Además, el análisis de correlación sugiere que existe una fuerte relación entre el consumo combinado y las emisiones, así como entre el tamaño del motor y el impacto ambiental, lo que respalda el enfoque empleado para la segmentación [9].

XVII.	CONCLUSIONES
•	Los resultados obtenidos a partir de la aplicación del algoritmo K-Means, en conjunto con el Análisis de Componentes Principales (PCA), permiten afirmar que las características técnicas de los vehículos como el tamaño del motor y el número de cilindros ejercen una influencia significativa en el comportamiento del consumo de combustible y en las emisiones de CO₂. Esta observación concuerda con estudios previos que demuestran una correlación directa entre variables técnicas y desempeño ambiental [10].
•	La segmentación generada a través del modelo de Clustering reveló tres agrupamientos coherentes: vehículos de bajo consumo y bajas emisiones, vehículos intermedios, y vehículos de alto rendimiento con elevados niveles de emisiones. Esta clasificación resulta especialmente útil para el diseño de políticas públicas diferenciadas, así como para estrategias de optimización enfocadas por segmento.
•	Se destaca también una fuerte correlación positiva entre el consumo de combustible combinado y las emisiones (r = 0.92), lo cual refuerza la viabilidad del uso de modelos predictivos simples en contextos donde no se cuente con datos directos de emisiones, permitiendo estimaciones precisas a partir de parámetros fácilmente accesibles.
•	Por otro lado, la presencia de valores atípicos como vehículos comerciales o de uso especializado evidencia la importancia de realizar análisis segmentados y aplicar filtros previos, a fin de evitar sesgos que podrían comprometer la validez de las conclusiones y afectar negativamente la formulación de políticas o recomendaciones técnicas.

XVIII.	REFERENCIAS

[1] 	V. R. y. J. P. E. Rojas, «Análisis del comportamiento de las emisiones de CO2, CO y del factor lambda de un vehículo con sistema de inyección convencional con catalizador y sin catalizador,» Ingenius, vol. XXIII, pp. 23-29, 2019. 
[2] 	O. NUNIGE, «EVALUACION Y COMPARACION DE METODOS DE FACULTAD DE INGENIERÍA MECÁNICA,» UNIVERSIDAD TECNOLÓGICA DE PEREIRA, vol. I, pp. 20-40, 2018. 
[3] 	C. T. Hernández y L. M. García, «Modelización del consumo de combustible en función de las características del vehículo y las condiciones ambientales,» Revista de Investigación en Energía, vol. XXXIII, pp. 222-234, 2018. 
[4] 	I. T. Buzina y M. J. Delgado, «Impacto de las características del vehículo en las emisiones de CO₂ y la eficiencia del combustible en trayectos urbanos,» International Journal of Automotive Engineering, vol. LV, pp. 134-150, 2022. 
[5] 	G. P. Gómez, F. F. Rivera y M. A. López, «Evaluación de las emisiones contaminantes de CO₂ en vehículos de combustión interna: factores influyentes en la eficiencia,» Revista de Tecnología y Transporte, vol. XXII, pp. 80-95, 2023. 
[6] 	R. J. y. L. W. J. Smith, Analyzing Vehicle Fuel Consumption and CO2 Emissions Using Data Visualization Techniques, 2018. 
[7] 	S. P. y. D. R. A. Gupta, «Exploratory Data Analysis Techniques in Automotive CO2 Emission Prediction,» 2020. 
[8] 	M. D. A. y. K. L. Taylor, «Data-driven approach to identify outliers in vehicular emissions,,» pp. 281-292, 2017. 
[9] 	L. M. L. Cam y J. Neyman, «“Some methods for classification and analysis of multivariate observations,» de Proceedings of the Fifth Berkeley Symposium on Mathematical Statistics and Probability, California, University of California Press, 2008, p. 281–297.
[10] 	M. Zhang, H. Wang y J. Liu, «Correlation Analysis between Vehicle Technical Characteristics and CO₂ Emissions,» de IEEE Trans. on Intelligent Transportation Systems, Genova, Institute of Electrical and Electronics Engineers Inc., 2021, p. 2401–2410.
[11] 	Government of Canada, «Fuel Consumption Ratings 2014,» 11 March 2014. [En línea]. Available: https://open.canada.ca/data/en/dataset/98f1a129-f628-4ce4-b24d-6f16bf24dd64. [Último acceso: 24 12 2024].
