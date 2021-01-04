## DH - DESAFIO 4

Desde nuesto trabajo con modelos de clasificacion supervisados, analizados en la entrega [anterior](https://github.com/mauriciomem/DH_DS_desafio_3), extraemos el modelo con mejor performance para analizar:

 * Performance por cantidad de features utilizadas con PCA (explained variance).
 * Visualizacion de dimensionalidad reducida de dataset con tecnicas de Mainfold learning.
 * Feature seleccion con metodo K Best. 
 * LIME para comprension en la clasificacion de imagenes[1].
 * Construccion de aplicacion de carga de imagenes y aplicacion de LIME y PCA [Covid RX app](https://github.com/mauriciomem/flask_photo_pred "RX app")

### Alcance del trabajo

 * Trabajo de laboratorio, con fines de practica en la aplicacion de tecnicas de machine learning y programacion en python.
 * No se utilizaron modelos de redes neuronales para la clasificacion de imagenes.
 * Se utilizaron 607 imagenes para ser clasificadas con un modelo de Regresion Logistica, identificado como el modelo mejor performante (ver entrega anterior).
 * El modelo tiene poca capacidad de generalizacion (alto overfitting). Decae la performance al incorporar nuevas imagenes
 
### Datasets

 Fuente de repositorio de imagenes:

* [Covid-19 Image Dataset](https://www.kaggle.com/pranavraikokte/covid19-image-dataset). Usability: 8.8
  * Dataset para deteccion de casos de Covid o Neumonia a traves de imagenes de radiografias de torax.
  * Las imagenes fueron liberadas por la Universidad de Montreal.


* [COVID19 High quality images](https://www.kaggle.com/theroyakash/covid19). Usability: 5.0
  * Dataset para deteccion de casos de Covid o Neumonia a traves de imagenes de radiografias de torax.
  * Fuente no oficial. Imagenes extraidas desde sitios publicos mediante Web Scrapping.

Ambos datasets se encuentran dispuestos en una estructura de directorios que comienza con la separacion de carpetas de training y testing. Luego a partir de estas carpetas se crean nuevas carpetas que identifican los casos de Covid, Neumonia y casos sin afecciones.

Para poder distribuir de forma uniforme el set de datos utilizados para testing y training, unificamos ambos repositorios en la siguiente estructura de directorios:

```
$ tree -d .

.
├── photos1
│   ├── Covid
│   ├── Normal
│   └── Viral Pneumonia
├── photos2
│   ├── Covid
│   ├── Normal
│   └── Viral Pneumonia
└── photos3
    ├── Covid
    ├── Normal
    └── Viral Pneumonia
```

Con el armado del dataset delegaremos luego en los metodos `train_test_split()` y `StratifiedKFold()` de la bilbioteca scikit-learn la distribucion del set de datos para training y testing.

### Referencias

 [1][Local Interpretable Model-agnostic Explanations para clasificacion de imagenes](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC7269964/), Cristian Arteaga, Oct 21, 2019
 

### Integrantes

 * [Natalia Soria](https://github.com/natsoria)
 * [Fernando Torres](https://github.com/fetorres0)
 * [Mauricio Mitolo](https://github.com/mauriciomem)
