# Predictive-collection-Act-4

					
 


ACTIVIDAD 4

Actividad 4



Materia:	Gestión de proyectos de inteligencia artificial
Actividad:	Actividad 4
Alumno(a):	María Fernanda Olvera Pegueros
Matrícula:	AL07154082
Docente:	Luis Ariel Vázquez Piña
Fecha de entrega:	14 / 06 /2026

 
 
Declaración de Uso de Inteligencia Artificial

El alumno debe indicar de manera honesta si utilizó herramientas de Inteligencia Artificial (IA) para el desarrollo de esta actividad. Completa la siguiente tabla:
Herramienta de IA utilizada	¿La usaste?	Propósito / Descripción de uso / Prompt utilizado
ChatGPT / OpenAI	☐ Sí    ☐ No	“Mi Colaboratory no está leyendo este archivo”

“¿Cómo sé que negative, neutral y positive están en el orden correcto en la matriz de confusión?

“Qué agregarías a mi notebook comparado con  este notebook de GitHub: https://github.com/MelihGulum/Comprehensive-Data-Science-AI-Project-Portfolio/blob/main/Machine%20Learning%20Projects/01.%20Diabetes%20Classification/diabetes-eda-feature-engineering-86.ipynb ?”

“Genera una imagen de encabezado para mi notebook”

"¿Las matrices de confusión son coherentes con la elección de los modelos?"
Claude (Anthropic)	☐ Sí    ☐ No	 
Gemini (Google)	☐ Sí    ☐ No	 
Copilot (Microsoft)	☐ Sí    ☐ No	“¿Debo descargar algo de Hugging Face o registrarme?”

“¿Cómo se usa GitHub?”

“Arma un dataset simulado de 100 filas con variedad de correos, intenciones, sentimientos, riesgos y acciones.”

“¿Qué debe contener un archivo README?”

“¿Cómo le doy guardar en GitHub en el archivo README?”

“¿Cómo interpretar los resultados en esta matriz de confusión?”
Otra (especifica):	☐ Sí    ☐ No	 




Desarrollo de Contenido

1.	Introducción
A continuación, se ponen en práctica modelos preentrenados para la rama de Inteligencia Artificial de Procesamiento de Lenguaje Natural (PLN). Se pretende comprobar su efectividad en la solución de la problemática del caso de uso Predictive Collection, en el cual los clientes envían correos electrónicos informando su situación respecto a pagos pendientes y la inteligencia artificial debe deducir si se trata de un correo positivo, neutral o negativo, así como determinar qué acción se debe ejecutar.
Los modelos seleccionados de la plataforma Hugging Face fueron:
1.	distilbert/distilbert-base-uncased-finetuned-sst-2-english: modelo basado en DistilBERT, ajustado para análisis de sentimiento binario (positivo o negativo). 
2.	cardiffnlp/twitter-roberta-base-sentiment: modelo RoBERTa entrenado con aproximadamente 58 millones de tweets y ajustado para clasificación de sentimientos positivos, negativos y neutrales. 
3.	ProsusAI/finbert: modelo especializado en el análisis de sentimientos dentro de textos financieros. 
Los modelos fueron seleccionados debido a que fueron entrenados en idioma inglés y se pretende su aplicación sobre correos recibidos de clientes de Estados Unidos y Canadá, los cuales normalmente se comunican en este idioma.
A lo largo de esta actividad se presentan métricas de evaluación, resultados obtenidos, análisis comparativos y la justificación del modelo recomendado para el caso de uso.

2. Desarrollo
Instrucciones: Selecciona una rama de la inteligencia artificial, por ejemplo, procesamiento de lenguaje natural, visión por computadora, audio o aplicaciones multimodales, como contexto del caso de uso.
Rama seleccionada: Procesamiento de lenguaje natural.

1.Cuaderno Colab funcional.
o	Implementa al menos tres modelos con el siguiente contenido:
	Configuración de GPU.
	Instalación de dependencias.
	Autenticación en Hugging Face Hub.
	Carga de modelos y datasets.
	Pipeline de inferencia.
	Cálculo de métricas (accuracy, precision, recall, F1-score).
	Medición de latencia.
	Tablas o resúmenes.
	Conclusiones parciales.
Twitter-RoBERTa obtuvo los mejores resultados en las métricas de evaluación, seguido por FinBERT y posteriormente DistilBERT. Esto puede explicarse porque Twitter-RoBERTa trabaja con tres categorías de sentimiento: positivo, neutral y negativo, mientras que DistilBERT solamente clasifica entre positivo y negativo. Por su parte, FinBERT fue diseñado específicamente para textos financieros.
En cuanto a latencia, el modelo con mayor tiempo de respuesta fue Twitter-RoBERTa, seguido por FinBERT. DistilBERT presentó la menor latencia, convirtiéndose en la alternativa más rápida.
Al comparar métricas y latencia, puede observarse que existe un balance entre precisión y eficiencia. Twitter-RoBERTa ofrece mejores métricas, mientras que DistilBERT ofrece mayor velocidad.
Respecto a la matriz de confusión de Twitter-RoBERTa, se observa que el modelo distingue adecuadamente entre las categorías negativa y neutral, aunque presenta algunas confusiones entre las categorías neutral y positiva.
 

2.Documento de análisis comparativo de modelos.
o	Elabora un reporte técnico comparativo con el siguiente contenido:
	Descripción del caso de uso.
A continuación, se ponen en práctica modelos preentrenados para la rama de Inteligencia Artificial de Procesamiento de Lenguaje Natural (PLN). Se pretende comprobar su efectividad en la solución del caso de uso Predictive Collection, en el cual los clientes envían correos electrónicos informando su situación respecto a pagos pendientes.
El objetivo es que la inteligencia artificial pueda identificar el sentimiento del mensaje (positivo, neutral o negativo) y, con base en dicha clasificación, sugerir una acción de cobranza adecuada. Esto permitiría automatizar parte del proceso de seguimiento a clientes y apoyar la toma de decisiones dentro del área de Order to Cash.
	Criterios de selección.
Se seleccionó este caso de uso debido a que el área de Order to Cash (Collections) es un área financiera que requiere automatización para gestionar de manera más eficiente los correos recibidos por los clientes. Actualmente gran parte del análisis de estos mensajes se realiza de forma manual, por lo que una clasificación automática puede ayudar a identificar la situación del cliente y sugerir una acción que posteriormente la plataforma pueda ejecutar.
Asimismo, se seleccionaron modelos de análisis de sentimiento debido a que el objetivo principal es interpretar la respuesta del cliente respecto al pago pendiente y determinar si la comunicación refleja una disposición positiva, negativa o neutral. Esto permite apoyar la toma de decisiones dentro del proceso de cobranza.
Los modelos fueron seleccionados debido a que fueron preentrenados en idioma inglés, ya que se pretende su aplicación sobre correos recibidos de clientes de Estados Unidos y Canadá, los cuales normalmente se comunican en este idioma.

	Tabla comparativa de al menos tres modelos (tarea, tamaño, licencia, precisión, latencia y costo o recursos).
Modelo	Tarea principal	Tamaño aproximado	Licencia	Precisión observada	Latencia	Recursos requeridos
DistilBERT	Análisis de sentimiento binario	Reducido	Apache 2.0	Menor respecto a los demás modelos	Baja	Bajo consumo
Twitter-RoBERTa	Análisis de sentimiento multiclase	Medio	MIT	Mayor precisión general	Mayor	Consumo medio
FinBERT	Sentimiento financiero	Medio	Apache 2.0	Intermedia	Intermedia	Consumo medio

	Análisis de trade-offs (eficiencia frente a precisión).
Los resultados muestran diferencias importantes entre los modelos.
Twitter-RoBERTa obtuvo las mejores métricas generales de accuracy, precision, recall y F1-score. Esto se debe principalmente a que fue entrenado para clasificar sentimientos en tres categorías: positivo, neutral y negativo.
Por otro lado, DistilBERT obtuvo métricas inferiores, pero presentó resultados cualitativamente más alineados con la lógica de cobranza. Debido a que solamente clasifica entre positivo y negativo, obliga al modelo a tomar una decisión más directa sobre la intención de pago del cliente.
Por ejemplo, para el correo: "Hello, I will review with AP team to send payment this week, thank you."
Twitter-RoBERTa clasificó el mensaje como positivo con una confianza cercana al 53%, mientras que FinBERT lo clasificó como neutral. Esto demuestra que algunos modelos no encuentran evidencia suficiente para determinar claramente si existe un compromiso de pago.
Desde una perspectiva operativa de cobranza, la pregunta principal suele ser:
¿El cliente va a pagar o no va a pagar?
Por esta razón, aunque DistilBERT obtuvo métricas inferiores, sus respuestas pueden resultar más útiles para la toma de decisiones del negocio.

	Decisiones de ajuste mínimo.
Se identifican algunas mejoras que podrían incrementar el desempeño del sistema:
•	Incrementar el tamaño del dataset con ejemplos reales de clientes. 
•	Incluir más casos ambiguos o neutros para mejorar la diferenciación entre categorías. 
•	Ajustar las reglas de asignación de riesgo y acción recomendada. 
•	Incorporar ejemplos de distintos niveles de urgencia y compromiso de pago. 
•	Evaluar correos de mayor longitud y cadenas completas de conversaciones. 
Estas mejoras permitirían obtener clasificaciones más robustas y cercanas a escenarios reales.
 
	Justificación del modelo recomendado.
El modelo recomendado es DistilBERT.
Aunque Twitter-RoBERTa obtuvo mejores métricas de evaluación, DistilBERT generó resultados más consistentes con las necesidades operativas del área de cobranza.
La razón principal es que sus predicciones obligan a identificar una postura clara del cliente, evitando una clasificación neutral que en muchos casos no aporta información accionable para el proceso de seguimiento.
Además, el modelo presentó niveles de confianza altos en los ejemplos evaluados y una menor latencia de procesamiento, lo que favorece su utilización en ambientes productivos.
Por estas razones, se considera que DistilBERT ofrece el mejor equilibrio entre velocidad, simplicidad y utilidad para el caso de uso planteado.
Un ejemplo de ello es el siguiente correo:
"Hello, good day. I have been experiencing some issues regarding the invoice. I am currently reviewing the matter with the internal team, and they have informed me that Accounts Payable is processing it and that it is currently pending approval from Laura."
En este caso, DistilBERT logró identificar correctamente que todavía no existe una fecha definida de pago. Desde una perspectiva de cobranza, esta información es relevante debido a que el cliente aún no está confirmando cuándo se realizará el pago, por lo que sigue existiendo incertidumbre respecto a la recuperación de la cuenta.
 
	Umbrales y riesgos.
Para la utilización del modelo DistilBERT se recomienda establecer umbrales de confianza que permitan identificar predicciones con un nivel adecuado de certeza.
Las clasificaciones con alta confianza pueden utilizarse para automatizar acciones de cobranza, mientras que aquellas con niveles de confianza bajos o intermedios deberían ser revisadas por un analista antes de ejecutar una acción.
Entre los principales riesgos identificados se encuentran:
•	Clasificaciones incorrectas (falsos positivos y falsos negativos): una interpretación errónea de la intención del cliente podría provocar acciones inadecuadas. 
•	Dependencia excesiva del modelo: el resultado debe utilizarse como apoyo y no como sustituto del criterio humano. 
•	Variabilidad en el lenguaje de los clientes: expresiones ambiguas, errores ortográficos o mensajes poco claros pueden afectar la precisión. 
•	Model drift: los patrones de comunicación pueden cambiar con el tiempo, reduciendo el desempeño del modelo. 
•	Sesgos en los datos de entrenamiento: si el dataset no representa todos los escenarios posibles, las predicciones pueden verse afectadas. 
•	Idioma de entrenamiento: dado que los modelos fueron entrenados principalmente en inglés, su desempeño podría disminuir al utilizar mensajes en otros idiomas.
Otro riesgo identificado es la posible generación de falsos negativos o clasificaciones que, aunque técnicamente correctas desde el punto de vista del sentimiento, no reflejen adecuadamente el riesgo de cobranza.
Por ejemplo, ante el correo:
"Hello, I will review with my AP team, thank you."
DistilBERT arroja una clasificación positiva. Sin embargo, si se analiza desde una perspectiva de cobranza, esta respuesta también podría interpretarse como evasiva, ya que no proporciona una fecha de pago ni un compromiso concreto.
Como posible solución, se propone entrenar el modelo con un dataset que contemple este tipo de respuestas y las clasifique de acuerdo con el nivel de exigencia que se quiera tener en el proceso de cobranza. De esta forma, el modelo podría priorizar también aquellos casos donde el cliente evita proporcionar información concreta sobre el pago.
 

3.Dataset y scripts de soporte.
o	Debes incluir:
	Descripción del origen del dataset.
El dataset utilizado fue construido a partir de 100 correos electrónicos en idioma inglés generados mediante inteligencia artificial generativa. Los ejemplos fueron creados con base en situaciones reales observadas dentro de procesos de cobranza y seguimiento de facturas pendientes.
Los correos incluyen distintos escenarios como promesas de pago, solicitudes de aclaración, disputas de facturas, problemas internos de aprobación, solicitudes de crédito, respuestas evasivas y confirmaciones de pago.
El objetivo de utilizar datos sintéticos fue contar con un conjunto de ejemplos controlado que permitiera evaluar y comparar el desempeño de los modelos preentrenados sin utilizar información confidencial de clientes reales.

	Estructura (descripción de cada campo).
Campo	Descripción
id	Identificador único del correo electrónico.
email	Contiene el texto completo del correo electrónico enviado por el cliente.
intent	Describe la intención identificada en el mensaje. Las categorías utilizadas fueron: concerned, collaborative, evasiva y neutral.
sentiment	Clasificación del sentimiento del correo: positive, neutral o negative.
risk	Nivel de riesgo asignado al caso: low, medium o high.
action	Acción recomendada para el seguimiento: reminder, call o statement.

	Scripts reproducibles (procedimiento mediante el cual se generó o fuente de obtención).
Para la generación del dataset se utilizaron herramientas de inteligencia artificial generativa con el fin de crear ejemplos sintéticos de correos electrónicos relacionados con cobranza.
Se definieron previamente distintos escenarios de negocio y posteriormente se generaron ejemplos representativos de cada uno de ellos. Una vez obtenidos los correos, se realizó la clasificación manual de las variables sentiment, risk y action para construir el dataset final.
El archivo fue almacenado en formato CSV para facilitar su lectura mediante Python y su utilización dentro de Google Colab.
Los scripts desarrollados permiten:
•	Cargar el dataset. 
•	Ejecutar inferencias utilizando DistilBERT, Twitter-RoBERTa y FinBERT. 
•	Calcular accuracy, precision, recall y F1-score. 
•	Medir latencia. 
•	Generar tablas comparativas. 
•	Crear matrices de confusión. 
•	Clasificar nuevos correos ingresados por el usuario. 
Debido a que todos los modelos fueron evaluados utilizando el mismo conjunto de datos, los resultados obtenidos pueden reproducirse siguiendo el procedimiento descrito en el cuaderno de Google Colab.

4.Repositorio en GitHub.
o	Crea un repositorio público o privado que contenga:
	README.md con la descripción del proyecto.
	Entorno de ejecución.
	Pasos de ejecución.
	Conclusiones.
	Archivos de soporte (requirements.txt, data, notebooks, results y src).
Ejemplo de inferencia
Para validar el comportamiento de los modelos se realizó una prueba utilizando el siguiente correo:
"Hello, I have been requesting a credit as there is a discrepancy in price, thank you."
Los resultados obtenidos fueron los siguientes:
 
 
Se observa que DistilBERT clasificó el mensaje como negativo, mientras que Twitter-RoBERTa y FinBERT lo clasificaron como neutral. La decisión final del pipeline fue neutral, asignando un riesgo medio y recomendando la generación de un estado de cuenta como acción sugerida.

3. Conclusiones
Aunque Twitter-RoBERTa obtuvo las mejores métricas de evaluación y FinBERT presentó resultados competitivos dentro del contexto financiero, DistilBERT fue el modelo que generó las predicciones más alineadas con las necesidades reales del área de cobranza.
Si bien sus métricas fueron inferiores, la naturaleza binaria de sus clasificaciones permite obtener una conclusión más directa respecto a la disposición de pago del cliente. En muchas situaciones de cobranza la pregunta principal es si el cliente va a pagar o no, por lo que una clasificación neutral puede no aportar suficiente valor para la toma de decisiones.
Los modelos preentrenados demostraron ser capaces de generar resultados coherentes utilizando un dataset relativamente pequeño y tiempos reducidos de implementación. Sin embargo, para una implementación productiva se recomienda ampliar el conjunto de entrenamiento utilizando correos reales anonimizados y establecer procesos de monitoreo para detectar posibles sesgos o degradación del desempeño.
También se recomienda realizar pruebas con correos de mayor longitud y cadenas completas de conversaciones, ya que en escenarios reales la información relevante suele encontrarse distribuida en varios mensajes.
Finalmente, se concluye que la utilización de modelos preentrenados representa una alternativa viable para automatizar parcialmente procesos de cobranza, siempre que exista supervisión humana y una estrategia continua de mejora del modelo.






Referencias Bibliográficas

Hugging Face. (s. f.). distilbert-base-uncased-finetuned-sst-2-english. Hugging Face. Recuperado el 14 de junio de 2026, de https://huggingface.co/distilbert/distilbert-base-uncased-finetuned-sst-2-english

Cardiff NLP. (s. f.). twitter-roberta-base-sentiment. Hugging Face. Recuperado el 14 de junio de 2026, de https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment

ProsusAI. (s. f.). FinBERT. Hugging Face. Recuperado el 14 de junio de 2026, de https://huggingface.co/ProsusAI/finbert

