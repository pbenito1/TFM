Este repositorio contiene el código del trabajo fin de master titulado "Predicción de nombres de dominio potencialmente usados en ciberataques" de la titulación "Máster Universitario en Ciencia de Datos" de la Universitat Oberta de Catalunya.

# Resumen
El servicio de resolución de nombres de dominio (DNS) es una parte básica del funcionamiento de Internet. Gracias al mismo podemos acceder a los sitios web utilizando nombres fácilmente recordables en lugar de direcciones IP numéricas. Este servicio es tan popular que en la actualidad hay más de 16 millones de dominios registrados con el dominio raíz más habitual, el .com.
Desgraciadamente, este servicio también es empleado por ciberdelincuentes, bien para hacer más resilientes sus herramientas, o para suplantar dominios legítimos, tratando de engañar a sus víctimas por medio de phising.
El enfoque habitual en entornos corporativos trata de cortar las comunicaciones de malware contra su centro de mando y control (C2C) empleando elementos perimetrales de seguridad, como pueden ser los cortafuegos y los sistemas de detección de intrusos (IDS). Estos elementos se basan generalmente en listas negras, recopiladas y publicadas por organismos o empresas de seguridad, con lo que únicamente pueden detener amenazas conocidas.
El siguiente trabajo de fin de máster tiene por objetivo estudiar y elaborar diversos modelos de aprendizaje automático y redes neuronales profundas que permitan determinar si un dominio es potencialmente malicioso, a partir exclusivamente de su nombre. Para ello, se partirá de la lista de los dominios más populares en Internet, y de diversas listas de dominios empleados por distintos tipos de malware (phising, ransomware, APT,…).

# Código fuente

El código está implementado en los siguientes Jupyter Notebook: 

- [Preprocesado y extracción de características](Preprocesado_ExtraccionCaracteristicas_AnalisisExploratorio.ipynb). En este _notebook_ se descargan y procesan los conjuntos de datos, realizando el proceso de _feature engineering_. Asimismo, se hace un análisis exploratorio (EDA) del conjunto de datos.
- [Elaboración y comparación de modelos de _machine learning_ para las características léxicas](MachineLearning_FeaturesLexicas.ipynb). En este _notebook_ se elaborarán y compararán tres modelos de _machine learning_ utilizando como elementos para su entrenamiento las características léxicas obtenidas en el paso de "Preprocesado y extracción de características".
- [Elaboración y comparación de modelos de _machine learning_ para n-gramas](MachineLearning_Ngrams.ipynb). En este _notebook_ se elaborarán y compararán tres modelos de _machine learning_ utilizando como elementos para su entrenamiento las características tipo n-grama obtenidas en el paso de "Preprocesado y extracción de características".
- [Elaboración y comparación de modelos de _deep learning_](RedesNeuronales.ipynb). En este _notebook_ se elaborarán y compararán diversas arquitecturas de redes neuronales para su entrenamiento los propios nombres de dominio.
- [Predicción de bondad de dominios registrados `.com`](CZDS.ipynb). En este _notebook_ se evalúa el modelo de red neuronal tipo CNN (Conv1D) entrenado en el _notebook_ anterior contra dominios reales con TLD `.com` proporcionados por el servicio CZDS de la ICANN
