## Fine-tuning de modelo de lenguaje para reconocimiento de entidades

## Introducción

El reconocimiento de entidades (NER, Named Entity Recognition) es una tarea fundamental en el procesamiento de lenguaje natural (NLP, Natural Language Processing). Consiste en identificar y clasificar entidades nombradas en un texto, como nombres de personas, organizaciones, lugares, fechas, entre otros.

NER es de gran importancia en el campo del NLP, ya que permite identificar y extraer información relevante de textos en diferentes dominios. El NER es utilizado en diversas aplicaciones, como la extracción de información en la industria de la salud, la identificación de entidades y relaciones en el análisis de sentimientos, la identificación de nombres de empresas en el análisis financiero, entre otros. En general, el NER es fundamental para el desarrollo de aplicaciones que involucren el procesamiento de grandes cantidades de datos en diferentes dominios, y su uso puede llevar a una mayor eficiencia y precisión en la toma de decisiones. En este caso se hace uso del dataset *eHealth-KD 2020* el cual es un conjunto de datos de anotación semántica para la extracción de información médica. Este conjunto de datos se enfoca en la identificación de entidades en el texto que se relacionan con la salud y la medicina. El conjunto de datos contiene 1099 oraciones en español, que están anotadas con cuatro tipos de entidades: *acción, referencia, predicado y concepto*. La entidad de acción describe una *acción* tomada por un sujeto, la entidad de *referencia* se refiere a una entidad previamente mencionada en el texto, la entidad de *predicado* describe una condición o estado, y la entidad de concepto se refiere a un objeto o idea específica relacionada con la salud y la medicina. Este conjunto de datos es útil para la creación y evaluación de modelos de extracción de información médica que pueden ser utilizados en aplicaciones como la detección temprana de enfermedades o la ayuda en la toma de decisiones clínicas.

En este repositorio se presenta un ejemplo de cómo se puede finetunear un modelo de lenguaje pre-entrenado para reconocimiento de entidades  utilizando la librería Hugging Face Transformers usando el modelo *PlanTL-GOB-ES/bsc-bio-ehr-es-pharmaconer*, el cual es una versión afinada del modelo base de RoBERTa y ha sido preentrenada utilizando el corpus biomédico español más grande conocido hasta la fecha, compuesto por documentos biomédicos, casos clínicos y documentos HCE para un total de Se procesaron 1.100 millones de tokens. Para mayor información: (https://huggingface.co/PlanTL-GOB-ES/bsc-bio-ehr-es-pharmaconer)

## Transformers

Los Transformers son modelos de lenguaje basados en atención que han revolucionado el campo del procesamiento del lenguaje natural (NLP). A diferencia de los modelos de lenguaje tradicionales, que utilizan RNN y LSTM, los Transformers no requieren una estructura secuencial y pueden procesar de manera eficiente secuencias de texto más largas. Utilizan una técnica llamada atención para enfocarse en partes relevantes del texto de entrada durante la codificación y decodificación, y han sido entrenados en enormes cantidades de datos para aprender patrones lingüísticos complejos. Los Transformers se han utilizado en una amplia variedad de tareas de NLP, como la traducción automática, la generación de texto y la identificación de entidades con nombre (NER), y han demostrado un rendimiento sobresaliente en comparación con los modelos anteriores.

![Bloque de un transformer](https://www.codificandobits.com/img/posts/2020-06-30/red-transformer-diagrama-bloques-general.jpg)


## Finetuning

Fine-tuning es un enfoque común para ajustar los modelos de lenguaje pre-entrenados para una tarea específica de NER. En este enfoque, los pesos del modelo pre-entrenado se utilizan como punto de partida y se ajustan en una tarea específica de NER.

En la práctica, cuando se realiza el fine-tuning, los pesos del modelo pre-entrenado se ajustan durante el entrenamiento de la tarea de NER para que se ajusten mejor a los datos de entrenamiento específicos de NER. Durante el proceso de fine-tuning, los pesos del modelo pre-entrenado no se dejan estáticos, sino que se ajustan continuamente para minimizar la función de pérdida de la tarea de NER.

El fine-tuning de un modelo pre-entrenado para una tarea de NER específica implica la adición de una capa de salida que se entrena específicamente para la tarea de NER. Esta capa de salida está conectada a la última capa oculta del modelo pre-entrenado y se entrena para predecir las etiquetas de entidad en la tarea de NER.

En resumen, durante el fine-tuning, el modelo pre-entrenado se entrena nuevamente con los datos específicos de la tarea de NER, ajustando continuamente los pesos del modelo para minimizar la función de pérdida de la tarea de NER.

## Modelo a usar

Una versión afinada del modelo bsc-bio-ehr-es , un modelo base de RoBERTa y ha sido preentrenada utilizando el corpus biomédico español más grande conocido hasta la fecha, compuesto por documentos biomédicos, casos clínicos y documentos HCE para un total de Se procesaron 1.100 millones de tokens de texto limpio y desduplicado.

Para más detalles sobre los corpus y la formación, consulta el modelo de ficha bsc-bio-ehr-es o desde el siguiente link: (https://huggingface.co/PlanTL-GOB-ES/bsc-bio-ehr-es-cantemist)

## Prerequisitos

```bash
pip install transformers
pip install torch==1.8.1
pip install datasets
pip install nervaluate
pip install evaluate
pip install sklearn-crfsuite
pip install pynvml

```

