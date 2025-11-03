# Proyecto-Data
Ciencia de Datos

---
## Presentación del Proyecto

---
### CASO:  Análisis Predictivo y Modelamiento Avanzado con IA para predecir la MORA de INCABANK
---

![Lámina 1](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/01.%20Descripcion%20Empresa.png) 

### Incabank es un banco con más de 30 años en Perú, cuyo enfoque principal es la Banca Minorista (60%), en el cual actualmente, experimenta un notable crecimiento en la demanda de tarjetas de crédito
---

![Lámina 2](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/02.%20Descripcion%20Empresa%20(mision%2C%20viison%2C%20objetivo).png)

### El objetivo central del proyecto es identificar a los clientes con mayor probabilidad de mora (impago). Esto se hace utilizando datos históricos y modelos predictivos para ayudar al área de créditos a reducir la morosidad , optimizar la asignación de líneas de crédito y fortalecer la rentabilidad del banco
---

![Lámina 3](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/03.%20Problem%C3%A1tica.png)

### El problema es que el aumento en la demanda de tarjetas de crédito incrementa el riesgo de impago. Se busca resolver esto prediciendo la probabilidad de que un cliente caiga en mora (definida como un retraso de más de 60 días).
---

![Lámina 4](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/04.%20Propuesta%20Mejora.png)

### El diagrama muestra el flujo de la solución. Los datos históricos y de clientes son procesados por un "Data Scientist" para crear una solución (el modelo) que será utilizada por el "Área de Crédito" en su interacción con el "Cliente".
---

![Lámina 5](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/05.%20Origen%20Datos.png)

### Los datos utilizados provienen de dos fuentes: internas (datos del cliente, historial crediticio) y externas (principalmente la clasificación de riesgo de la SBS, que es la variable VAR13).
---

![Lámina 6](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/06.%20Variables.png)

### Se define el diccionario de datos. La variable más importante es el Target (objetivo): MORA60. Esta variable es binaria: '1' si el cliente tuvo una mora mayor a 60 días, y '0' si no la tuvo.
---

![Lámina 7](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/07.%20Limpieza%20y%20Transformacion%20de%20Datos.png)

### Insight (Valores Nulos): La tabla de valores nulos muestra "0.0" para todas las variables , lo que indica que el conjunto de datos estaba completo y no requirió imputación (relleno) de datos faltantes.
### La gran mayoría de los clientes tiene vivienda "FAMILIAR" (69.45%) o "PROPIA" (28.55%).
### Una alta proporción de clientes tiene productos de ahorro por 12 meses (78.56%) y ha recibido 12 depósitos de sueldo (51.77%), sugiriendo estabilida.
---

![Lámina 8](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/08.%20Limpieza%20y%20Transformacion%20de%20Datos.png)

### Riesgo SBS (VAR13): La mayoría (62.86%) está en la categoría "Normal" (0), pero un 37% ya presenta algún nivel de riesgo (categorías 1 a 4).
### Educación (VAR14): La cartera de clientes tiene un alto nivel educativo; el 92.4% son "PROFESIONAL" (53.15%) o "TECNICO" (39.25%).
---

![Lámina 9](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/09.%20An%C3%A1lisis%20Exploratorio%20de%20Datos%20(EDA).png)

### El dato más crítico es la media de MORA60, que es 0.70. Esto significa que el 70% de los clientes en esta muestra histórica cayó en mora de más de 60 días. La edad promedio es de 36 años y el ingreso promedio es S/ 4,344.
---

![Lámina 10](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/10.%20EDA-Analisis%20Univariante.png)

### La distribución de ingresos está fuertemente sesgada a la derecha, ya que la gran mayoría de clientes se concentra en los rangos de ingresos más bajos (cerca de 0-5000) , y muy pocos clientes tienen ingresos altos.
---

![Lámina 11](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/11.%20EDA-An%C3%A1lisis%20Bivariante.png)

### Analiza el Ingreso Mensual (VAR07) contra la Mora. Confirma que los clientes que caen en mora (MORA60=1) tienen un ingreso mensual promedio más bajo (S/ 3,745) que aquellos que no caen en mora (S/ 5,745).
---

![Lámina 12](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/12.%20EDA-Analisis%20Univariante-Bivariante.png)

### Analiza la Línea de Crédito (VAR08) contra la Mora. La conclusión es directa: "Clientes con MENOR Monto LÍNEA DE CRÉDITO --> han incurrido en MORA>60DÍAS".
---

![Lámina 13](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/13.%20EDA-Analisis%20Univariante-Bivariante.png)

### Analiza el Saldo Deudor (VAR09) contra la Mora. La conclusión es directa: "Clientes con MAYOR Monto SALDO DEUDOR --> han incurrido en MORA<60DÍAS".
---

![Lámina 14](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/14-%20EDA-An%C3%A1lisis%20Bivariante.png)

### Analiza la Antiguedad de la Tarjeta de Crédito (VAR05) contra la Mora. Confirma que los clientes que caen en mora (MORA60=1) tienen una tarjeta de credito mas nuevo, lo que significa que representan clientes recientemente nuevos.
---

![Lámina 15](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/15.%20EDA-An%C3%A1lisis%20Multivariante.png)

### Vemos que la mediana es mayor en los clientes que caen en mora en el tipo de vivienda(Alquilada) respecto al saldo deudor, en cambio respecto a la linea de credito y el ingreso mensual siempre la mediana es mayor en los clientes que no caen en mora.
---

![Lámina 16](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/16.%20EDA-An%C3%A1lisis%20Multivariante.png)

### Vemos que siempre la mediana es mayor en los clientes que no caen en mora respecto al Riesgo SBS Alquilada, y esta respecto a la linea de credito y el ingreso mensual.
---

![Lámina 17](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/17.%20EDA-An%C3%A1lisis%20Multivariante.png)

### Vemos que la mediana es mayor en los clientes que caen en mora en el nivel de Educacion(Sin Educacion) respecto a la linea de credito y el ingreso mensual.
---

![Lámina 18](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/18.%20EDA-Diagrama%20de%20barras%20apiladas.png)

### Más del 64% de los clientes, independientemente del Tipo de Vivienda, presenta MORA >60 DÍAS.
### El 84% de clientes en tipo de Vivienda OTRAS han presentado MORA60 vs el 64% de clientes con vivienda PROPIA.
---

![Lámina 19](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/19.%20EDA-Diagrama%20de%20barras%20apiladas.png)

### Más del 63% de los clientes, independientemente del nivel educativo, presenta MORA >60 DÍAS.
### El 84% de clientes en nivel de educacion Basica han presentado MORA60 vs el 63% de clientes con nivel de educacion Profesional y Superior.
---

![Lámina 20](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/20.%20EDA-Grafico%20de%20densidad.png)

### Vemos que la mayor concetracion de esta al lado izquierdo , lo que significa que hay mayor cantidad de clientes nuevos, porque tienen menos meses.
### Vemos que la mayor concetracion de esta al lado derecho , lo que significa que hay mayor cantidad de clientes que abonaron su sueldo en los 12 meses.
---

![Lámina 21](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/21.%20Gr%C3%A1fico%20de%20Correlaci%C3%B3n.png)

### El mapa de calor muestra que casi todas las variables predictoras tienen colores pálidos o muy oscuros, indicando baja correlación (cercana a 0) entre ellas. Esto es excelente para el modelamiento, ya que significa que las variables no son redundantes (no hay multicolinealidad).
---

![Lámina 22](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/22.%20Random%20Forest.png)

### Este modelo funciona creando una gran cantidad de "árboles de decisión" (como diagramas de flujo) y luego hace que voten entre todos para obtener el resultado más preciso. Su ventaja es que es muy robusto y evita el "sobreajuste" (memorizar los datos en lugar de aprender).
---

![Lámina 23](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/23.%20Regresi%C3%B3n%20Log%C3%ADstica.png)

### Es un modelo estadístico clásico usado para clasificación binaria (Sí/No). No te dice simplemente "Mora" o "No Mora", sino que calcula la probabilidad (ej. "este cliente tiene un 70% de probabilidad de mora"). Es rápido y fácil de interpretar.
---

![Lámina 24](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/24.%20XGBOOST.png)

### Es un modelo avanzado y muy potente (basado en "Gradient Boosting"). Es conocido en la industria por su alto rendimiento y velocidad. Es uno de los modelos más usados en competencias de ciencia de datos por su gran precisión.
---

![Lámina 25](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/25.%20LightGBM.png)

### Este es el competidor directo de XGBoost. También es un modelo "Gradient Boosting", pero su principal ventaja es que es extremadamente rápido y consume menos memoria. Es ideal para manejar grandes volúmenes de datos, como los de un banco.
---

![Lámina 26](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/26.%20Decision%20Tree%20Classifier.png)

### Este es el modelo más simple, la base del "Random Forest". Crea un único árbol de reglas "si... entonces..." (ej. SI el ingreso es < 2000 Y los días de atraso > 10 ENTONCES hay alta probabilidad de mora). Es fácil de entender, pero menos preciso que los otros.
---

![Lámina 27](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/27.%20Comparaci%C3%B3n%20de%20Modelos.png)

### La tabla compara las métricas (ROC_AUC, F1, Accuracy) de los 5 modelos. La conclusión es clara: "CONSIDERANDO LOS PRINCIPALES INDICADORES SE DECIDE UTILIZAR EL MODELO LightGBM".
---

![Lámina 28](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/28.%20Predicci%C3%B3n%20nueva%20data%20set.png)

---

![Lámina 29](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/29.%20Resultados.png)

---

![Lámina 30](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/30.%20Perfiles.png)

---

![Lámina 31](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/31.%20Estrategias%20Mejora.png)

---

![Lámina 32](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/32.%20Clientes%20Bajamente%20probable.png)

### El diagrama muestra que el bajo riesgo (37% de mora real) no es solo para "vigilar", sino una oportunidad de negocio. La acción recomendada es Cross-Selling o aumentar la línea de crédito, transformando a este cliente en una fuente de ingresos.
---

![Lámina 33](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/33.%20Clientes%20Medianamente%20probable.png)

### Para el riesgo medio (76% mora real), el diagrama muestra un flujo de prevención. La acción es el seguimiento preventivo y una evaluación de solvencia para evitar pérdidas estimadas en S/500 por cliente.
---

![Lámina 34](https://github.com/Nelson0301/Proyecto-Data/blob/main/imagenes/34.%20Clientes%20Altamente%20probable..png)

### Para el riesgo alto (94% mora real), el flujo es de contención y recuperación. El cliente pasa directo al área de Cobranza, se le aplican restricciones de crédito y alertas tempranas (SMS/Email) para reducir la pérdida.
---

### CONCLUSIÓN: El uso del modelo LightGBM permite a INCABANK tomar decisiones más rápidas y precisas. El banco ahora puede "anticipar el comportamiento de los clientes", optimizar la gestión del riesgo y diseñar acciones preventivas, mejorando la eficiencia y competitividad.
