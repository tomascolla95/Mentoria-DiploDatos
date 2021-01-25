# Mentoria-DiploDatos

Este es el repositorio donde se subirán las notebooks de cada una de las entregas de la Mentoría de la Diplomatura en Aprendizaje Automático y Ciencia de Datos 2020 del FaMAF. El proyecto de la mentoría consiste en la predicción univariada y miltivariada de índices financieros. En cada entrega se le agrega al análisis un nivel mayor de complejidad en la predicción. 

En la primera entrega se hace un trabajo de análisis y visualización de datos que comienza con el cargado del dataset y la obtención del tipo de datos con los que se cuenta para trabajar. El notebook luego hace un análisis descriptivo: período analizado, cantidad de valores faltantes, distribución de los datos, tratamiento de outliers y análisis de estacionalidad, estacionariedad y tendencia. 

En la segunda entrega se comienza con el procesado de datos. Primero se expresan todos los índices en una moneda común (dólar estadounidense) para poder hacer comparaciones directas que tengan sentido. Luego se toma logaritmo de las series porque dicha transformación facilita tanto el análisis como la obtención de los rendimientos que se analizan posteriormente. El análisis del rendimiento diario, mensual, anual y acumulado de cada uno de los índices arroja como resultado que el Merval fue uno de los mercados más volátiles y decepcionantes de todo el mundo. 

En la tercera entrega comienza el trabajo de predicción con algoritmos más complejos. En primer lugar se separan los datos de entrenamiento de los de test utilizando un método de división conocido como Walk Forward Validation. Luego se construyen dos modelos baseline de predicción que son muy simples y por ende serán el objetivo a vencer luego con los modelos más avanzados. Los modelos base a vencer son un Average Forcast (que intenta predecir el rendimiento diario de los índices) y un Naive Forecast (que intenta predecir el valor futuro de los índices). La métrica con la que se juzga la performance de los modelos es el Error Cuadrático Medio, y una vez obtenido ese valor para cada uno de los modelos base se la intenta superar con dos modelos algo más avanzados: un modelo ARMA sobre los rendimientos diarios y un modelo ARIMA sobre el logaritmo de los índices. Los resultados fueron decepcionantes pero no sorpresivos: ninguno de los modelos más avanzado logró vencer a los modelos base, a juzgar por su error cuadrático medio. 

En la cuarta entrega se desarrolla un modelo VAR en niveles para la predicción. La ventaja de utilizar un modelo VAR por encima de un ARMA es que éste último no tiene en cuenta las relaciones entre las variables al momento de predecir porque utiliza únicamente los valores anteriores de la propia variable en cuestión, en cambio el modelo VAR nos permite considerar todos los índices en simultáneo y la influencia que puedan ejercerse entre sí. Usar las relaciones entre las variables genera mejores predicciones porque incorpora el comportamiento dinámico de los datos. Nuevamente, el modelo VAR resultó no ser lo suficientemente bueno como para vencer a un “modelo” incluso tan simple como decir que el rendimiento de un índice en un día cualquiera será igual a cero.  Posteriormente se procede a intentar predecir los índices con un modelo VECM (similar al VAR pero para series no estacionarias), obteniendo resultados igual de desalentadores.

En la quinta y última entregan se aplican algunos algoritmos de aprendizaje no supervisado: K-means clustering, Mean Shifts y Clustering Jerárquico. Los tres modelos llevan a la conclusión de que cuando intentamos agrupar los índices financieros de todos estos países en clusters, el único que nunca consigue “compañero de grupo” es el Merval, principalmente debido a su inédita e incomparable volatilidad y pobre desempeño. 
