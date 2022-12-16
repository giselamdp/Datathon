![HenryLogo](https://d31uz8lwfmyn8g.cloudfront.net/Assets/logo-henry-white-lg.png)


# <h1 align="center">**`Proyecto Individual 2`**

<p align="center">
<img src="https://www.ibm.com/blogs/client-voices/wp-content/uploads/2019/09/Glinnt.jpg"   
>
</p>

## **Agenda**

+ 1.-Antecedentes.
+ 2.-Objetivo del proyecto.
+ 3.-Esquema preliminar del trabajo a realizar.
+ 4.-Desarrollo.
+ 5.-Conclusiones y resultados.


## **Antecedentes**

Un importante Centro de Salud necesita poder predecir si un paciente tendrá una estancia hospitalaria prolongada o no, para lo cual se define 'prolongada' si ha estado hospitalizado más de 8 días.
A la fecha cuenta con un registro historico de información que es entregado para el analisis. 
​
​
## **Objetivo del Proyecto**
​
Administrar de manera adecuada la demanda de camas, para lo cual se requiere elaborar una predicción optima de estancia hospitalaria, información que es de gran importancia para medir la capacidad de atencion que tiene el Hospital.

Para evaluar el error del modelo elegido se prioriza la sensibilidad o Recall, formula que calcula el numero de predicciones positivas correctas/numero total de positivos.
Sin embargo para tener una mejor evaluacion se realizaran adcionalmente los calculos de Acuracy y Presicion:

+ 1.-Sensibilidad o Recall
+ 1.-Acuracy
+ 1.-Precision



## 🏥 **Esquema Preliminar** 🏥

Nuestra tarea se basa en extraer la data entregada, preparla y seleccionar que tipo de modelo es el mas adecuado, entrenar el modelo e ir ajustando las variables revisando la acertidad del mismo. una vez concluido se realiza la prediccion que debe ser entregada como una sola columna en formato CSV.

<p align="center">
<img src="./imagenplan.jpg"   


​


## 🏥 **Desarrollo** 🏥

Se bosqueja los pasos a seguir para lograr el objetivo:

+ 1.-Recolectar Data. Utilizando la herramienta de Visual Studio Code se extrae la información usando Jpynb.
+ 2.-Preparar Data. 
Para seleccionar que datos seran usados en el modelo se revisa la data, el ipo de variable, la cantidad de nulos, informacion repetida y se saca un cuadro de correlacion. 
Como los modelos solo trabajan con datos numericos es necesario convertir los datos categoricos importantes en columnas numericas para que sean incluidas, en donde se debe analizar la forma de conversion label encoder o dummies, principalmente para evaluar si los datos se convierten en una sola columna o se crea una columna por cada clasificacion categorica. que no existe una variable con correlación predominante por lo que se procede a utilizar todas las variables.
Sobre las variables categoricas fueron convertidas a numericas. las que corresponden a rangos se decidió utilizar label encoder 
    - Age Rango
    - health_conditions
    - Ward_Facility_Code
Para las demas variables categoricas se utiliza dummies.
Creacion de Variables
   - Variable Prep- se crea la variable Prep con la logica objetivo para que sea definida como la variable Y en el modelo.
Eliminacion de Variables
   - Patient Id
   -'Stay (in days)'

+ 3.-Seleccionar Algoritmo. Para seleccionar el modelo se usa un Pipeline que evalua entre regresion lineal y arbol de decision y da como resultado apostar por el arbol de decisión.
+ 4.-Entrenar Modelo. Para entrenar el modelo de arbol de decision se tomaron decidió dividir la data para manejar una base de train y una base de Test.
        test_size=0.3,
        random_state=30, considero el random importante y significativo, al no tener una variable predominante y tener muchas variables para el modelo.
+ 6.-Evaluar Modelo. Para evaluar el modelo de acuerdo a las premisas se decidio priorizar el recall, generando las siguientes metricas.
        + 1.-Sensibilidad o Recall
        + 2.-Acuracy
        + 3.-Precision
    Los resultados nos indican que la metrica obtenida de 0.81 es optima.
+ 7.-Realizar Prediccion. se realiza de acuerdo a las premisas y se entrega


## 🏥 **Desarrollo** 🏥
Se realizó la entrega y nos dió como resultado
    Recall   0.814684381836615
    Acuracy  0.7690555555555556

    En el test nos dió
    Recall   0.8225530971720623
    Acuracy  0.7757235772357723

    Lo cual concluye que esta dentro de los rangos y no esta con overfiting, ya que responde bien a otros set de datos