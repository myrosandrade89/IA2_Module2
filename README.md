# **Implementación de un modelo de Deep Learning**

_Autor: Myroslava Sánchez Andrade A01730712_

_Fecha de creación: 04/11/2022_

_Última modificación: 05/11/2022_

---

## **Extracción de datos**

Se decidió trabajar con un conjunto de imágenes para este proyecto. Las imágenes fueron descargadas del repositorio de GitHub **[Kuzushiji-MNIST](https://github.com/rois-codh/kmnist)**. Este conjunto contiene 270912 imágenes de 28x28 (escala de grises), el conjunto está desbalanceado pues contiene un total de 49 clases, 48 caracteres Hiragana y 1 marca de iteración Hiragana. Se proporcionan 4 archivos: 2 para el train (labels y target) y 2 para el test (labels y target).
<br>![image](https://user-images.githubusercontent.com/67491368/200153080-cb76f32e-3475-4781-ad81-750c0aace250.png)

Se optó por utilizar redes neuronales convolutivas ya que estás son apropiadas para la el procesamiento de imágenes, pues las capas convolutivas reducen la dimensión de las imágenes sin perder información. Las capas subdividen las imágenes y las analizan una por una.

---

## **Entrenamiento y testeo de los datos**

El primer modelo tiene las siguientes características:
- Capa convolutiva con 28 neuronas, kernel de 3x3 y activación relu
- Capa MaxPooling con tamaño de 2x2
- Capa convolutiva con 56 neuronas, kernel de 3x3 y activación relu
- Capa MaxPooling con tamaño de 2x2
- Capa convolutiva con 56 neuronas, kernel de 3x3 y activación relu
- Capa Flatten
- Capa densa con 64 neuronas y activación relu
- Capa densa con 49 (número de clases)

Después del entrenamiento se obtuvo una precisión del 89.49% en el test.

Intentando mejorar el modelo se optó por aumentar el número de neuronas para las capas convolutivas y se agregaron capas Dropout con 30%, estas capas eliminan el 30% del conjunto de imágenes de entrenamiento para evitar overfitting.
<br>Este cambio funcionó y la precisión aumentó hasta el 91.61% de precisión en el test.

---

## **Resultados**
Se obtuvó un total de precisión del 91.61% con el último modelo. En el último gráfico se pueden observar el resultado de las predicciones y el resultado original del test (en color rojo se muestran las predicciones fallidas y en azul las predicciones correctas).
<br>![image](https://user-images.githubusercontent.com/67491368/200155854-6789addf-d558-4f79-a2ba-09424944151a.png)
