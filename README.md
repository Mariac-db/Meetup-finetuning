## Fine-tuning de modelo de lenguaje para reconocimiento de entidades

## Introducción

El reconocimiento de entidades (NER, Named Entity Recognition) es una tarea fundamental en el procesamiento de lenguaje natural (NLP, Natural Language Processing). Consiste en identificar y clasificar entidades nombradas en un texto, como nombres de personas, organizaciones, lugares, fechas, entre otros.

NER es de gran importancia en el campo del NLP, ya que permite identificar y extraer información relevante de textos en diferentes dominios. El NER es utilizado en diversas aplicaciones, como la extracción de información en la industria de la salud, la identificación de entidades y relaciones en el análisis de sentimientos, la identificación de nombres de empresas en el análisis financiero, entre otros. En general, el NER es fundamental para el desarrollo de aplicaciones que involucren el procesamiento de grandes cantidades de datos en diferentes dominios, y su uso puede llevar a una mayor eficiencia y precisión en la toma de decisiones. En este caso se hace uso del dataset *eHealth-KD 2020* el cual es un conjunto de datos de anotación semántica para la extracción de información médica. Este conjunto de datos se enfoca en la identificación de entidades en el texto que se relacionan con la salud y la medicina. El conjunto de datos contiene 1099 oraciones en español, que están anotadas con cuatro tipos de entidades: *acción, referencia, predicado y concepto*. La entidad de acción describe una *acción* tomada por un sujeto, la entidad de *referencia* se refiere a una entidad previamente mencionada en el texto, la entidad de *predicado* describe una condición o estado, y la entidad de concepto se refiere a un objeto o idea específica relacionada con la salud y la medicina. Este conjunto de datos es útil para la creación y evaluación de modelos de extracción de información médica que pueden ser utilizados en aplicaciones como la detección temprana de enfermedades o la ayuda en la toma de decisiones clínicas.

En este repositorio se presenta un ejemplo de cómo se puede finetunear un modelo de lenguaje pre-entrenado para reconocimiento de entidades  utilizando la librería Hugging Face Transformers usando el modelo *PlanTL-GOB-ES/bsc-bio-ehr-es-pharmaconer*, el cual es una versión afinada del modelo base de RoBERTa y ha sido preentrenada utilizando el corpus biomédico español más grande conocido hasta la fecha, compuesto por documentos biomédicos, casos clínicos y documentos HCE para un total de Se procesaron 1.100 millones de tokens. Para mayor información: (https://huggingface.co/PlanTL-GOB-ES/bsc-bio-ehr-es-pharmaconer)

![bert-for-ner](https://github.com/Mariac-db/Meetup-finetuning/assets/70480328/54eb42eb-b1f2-4e77-aadd-b48d38a184db)

## Transformers

## Finetuning


## Modelo a usar


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

