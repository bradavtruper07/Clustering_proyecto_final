# Segmentación de Perfiles de Consumidores de Drogas — Clustering

## Descripción
Proyecto final del curso **Modelado Predictivo, Automatización y Proyectos Inteligentes**.

Se preguntó a los participantes sobre sustancias que fueron clasificadas como depresores del sistema nervioso central, estimulantes o alucinógenos. Las drogas depresoras incluyeron alcohol, nitrito de amilo, benzodiazepinas, tranquilizantes, disolventes e inhalantes de gamma-hidroxibutirato y opiáceos como la heroína y la metadona/opiáceos recetados. Los estimulantes consistieron en anfetaminas, nicotina, cocaína en polvo, crack, cafeína y chocolate. Aunque el chocolate contiene cafeína, los datos del chocolate se midieron por separado, dado que puede inducir efectos psicofarmacológicos y conductuales paralelos en individuos de manera congruente con otras sustancias adictivas [31]. Los alucinógenos incluyeron cannabis, éxtasis, ketamina, LSD y hongos mágicos.
También se midieron las sustancias psicoactivas legales (legal highs) como la mefedrona, la salvia y varias mezclas legales para fumar.

Aplica técnicas de Machine Learning No Supervisado (K-Means y Clustering Jerárquico) para identificar perfiles diferenciados de consumidores de drogas a partir de características demográficas, de personalidad y patrones de consumo.

**Dataset:** Drug Consumption

**Pregunta:** ¿Existen perfiles diferenciados de consumidores según sus rasgos de personalidad y sus patrones de consumo de sustancias?

## Estructura del proyecto
```
proyecto_clustering/
│
├── data/
│   └── drug_consumption.xlsx
├── notebook/
│   └── Proyecto_III_Unal_BDTP.ipynb
├── requirements.txt
└── README.md
```

# Descripción de la Base de Datos

Este conjunto de datos contiene información sociodemográfica, rasgos de personalidad (basados en el modelo de los Cinco Grandes, impulsividad y búsqueda de sensaciones) y patrones de consumo de diversas sustancias (clasificadas en depresores, estimulantes y alucinógenos) para un total de 1,885 participantes.

Para cada encuestado se conocen 12 atributos: mediciones de personalidad que incluyen NEO-FFI-R (neuroticismo, extraversión, apertura a la experiencia, amabilidad y responsabilidad), BIS-11 (impulsividad) e ImpSS (búsqueda de sensaciones), nivel de educación, edad, género, país de residencia y etnicidad. Además, se cuestionó a los participantes sobre su uso de 18 drogas legales e ilegales (alcohol, anfetaminas, nitrito de amilo, benzodiazepinas, cannabis, chocolate, cocaína, cafeína, crack, éxtasis, heroína, ketamina, sustancias psicoactivas legales [legal highs], LSD, metadona, hongos, nicotina y abuso de sustancias volátiles), y una droga ficticia (Semeron) que se introdujo para identificar a quienes exageran o falsean respuestas. Para cada droga, debían seleccionar una de las respuestas: nunca usó la droga, la usó hace más de una década, o en la última década, año, mes, semana o día. La base de datos contiene 18 problemas de clasificación. Cada una de las variables de etiqueta independientes contiene siete clases: "Nunca usado", "Usado hace más de una década", "Usado en la última década", "Usado en el último año", "Usado en el último mes", "Usado en la última semana" y "Usado en el último día".

## Diccionario de Datos (Variables)

### Datos Sociodemográficos
| Nombre de la Variable | Descripción | Interpretación / Valores |
| :--- | :--- | :--- |
| ID | Participante | Código numérico (1 - 1885) |
| Edad | Edad del participante | Rangos de edad |
| Género | Género del participante | Femenino y masculino |
| Nivel de educación | Nivel de educación del participante | Desde 'Abandonó la escuela' hasta varios niveles de educación |
| País de residencia | País de residencia actual del participante | Nombre del país |
| Etnicidad | Etnicidad del participante | Etnicidad del participante |

### Rasgos de Personalidad y Conducta
| Variable | Nombre de la Variable | Descripción | Interpretación / Valores |
| :--- | :--- | :--- | :--- |
| `Nscore` | NEO-FFI-R Neuroticismo | El neuroticismo es uno de los rasgos de personalidad. | Puntuación del rasgo |
| `Escore` | NEO-FFI-R Extraversión | La extraversión es uno de los cinco rasgos de personalidad. | Indica qué tan extrovertida y social es una persona. |
| `Oscore` | NEO-FFI-R Apertura a la experiencia | La apertura es uno de los cinco rasgos de personalidad. | Indica qué tan abierta de mente es una persona. |
| `Ascore` | NEO-FFI-R Amabilidad | La amabilidad (o afabilidad) es uno de los cinco rasgos. | Una persona con un alto nivel de amabilidad... |
| `Cscore` | NEO-FFI-R Responsabilidad | La responsabilidad (o escrupulosidad) es uno de los rasgos. | Una persona que obtiene una puntuación alta... |
| `Impulsive` | Impulsividad medida por BIS-11 | Impulsividad medida por la escala BIS-11. | En psicología, la impulsividad es una tendencia... |
| `SS` | Búsqueda de sensaciones medida | Búsqueda de sensaciones medida por ImpSS. | La sensación es la información sobre el riesgo... |

### Variables de Consumo de Sustancias
> **Nota sobre la escala de consumo:** Para todas las variables de sustancias (excepto donde se indique lo contrario), la escala de medición de la descripción corresponde a:
> * **CL0:** Nunca usado
> * **CL1:** Usado hace más de una década
> * **CL2:** Usado en la última década
> * **CL3:** Usado en el último año
> * **CL4:** Usado en el último mes
> * **CL5:** Usado en la última semana
> * **CL6:** Usado en el último día

| Variable | Nombre de la Variable | Tipo de Sustancia / Interpretación |
| :--- | :--- | :--- |
| `Alcohol` | Uso de alcohol | Depresores |
| `Amphet` | Uso de anfetaminas | Estimulantes |
| `Amyl` | Uso de nitrito de amilo | Depresores |
| `Benzos` | Uso de benzodiazepinas | Depresores |
| `Caff` | Uso de cafeína | Estimulantes |
| `Cannabis` | Uso de cannabis | Alucinógenos |
| `Choc` | Uso de chocolate | Estimulantes |
| `Coke` | Uso de cocaína | Estimulantes |
| `Crack` | Uso de crack | Estimulantes |
| `Ecstasy` | Uso de éxtasis | Alucinógenos |
| `Heroin` | Uso de heroína | Depresores |
| `Ketamine` | Uso de ketamina | Alucinógenos |
| `Legalh` | Uso de sustancias psicoactivas legales | Todas. Nuevas sustancias psicoactivas que... |
| `LSD` | Uso de LSD | Alucinógenos |
| `Meth` | Uso de metadona | Depresores |
| `Mushrooms` | Uso de hongos (setas alucinógenas) | Alucinógenos |
| `Nicotine` | Uso de nicotina | Estimulantes |
| `Semer` | Uso de droga ficticia (Semeron) | Introducida para identificar a quienes exageran/mienten. |
| `VSA` | Uso/Abuso de sustancias volátiles | Depresores. Implica el uso de gases o vapores. |

## Estructura del notebook

Sección 1 — Problema y datos
Sección 2 — Modelado: K-Means vs. Clustering Jerárquico
Sección 3 — Interpretación y visualizaciones
Sección 4 — Conclusiones
Sección 5 — Uso de IA

## ¿Cómo correr el proyecto?

1. Clonar o descargar el repositorio.
2. Instalar las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Verificación de la base de datos `drug_consumption.xlsx`.
4. Abrir el notebook:
   ```bash
   jupyter notebook Proyecto_III_Unal_BDTP.ipynb
   ```
5. Ejecutar todas las celdas en orden con **Kernel → Restart & Run All**.

## Resultados principales
- Se identificaron **3 perfiles de consumidores** con características distintas.
- Los grupos difieren principalmente en **impulsividad, búsqueda de sensaciones y patrones de consumo**.
- Se validaron los resultados comparando K-Means vs. Clustering Jerárquico.

## Referencias

1. Drug, Wikipedia URL: https://en.wikipedia.org/wiki/Drug
2. The Five Factor Model of personality Model of Personality and Evaluation of Drug Consumption risk, E.Fehrman, A.K. Muhammad, E.M. Mirkes, V. Egan, A.N Gorban. URL: https://arxiv.org/abs/1506.06297
3. Detecting and Assessing Alcohol and Other Drug Use. URL: https://www.ncbi.nlm.nih.gov/books/NBK236259/
4. Ibid.
5. UCI-Machine Learning Repository URL: archive.ics.uci.edu/ml/datasets/Drug+consumption+%28quantified%29
6. Numpy Documentation
7. Matplotlib Documentation
8. Seaborn Documentation
9. Pandas Documentation.
