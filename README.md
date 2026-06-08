# Segmentación de Perfiles de Consumidores de Drogas — Clustering

## Descripción
Proyecto final del curso **Modelado Predictivo, Automatización y Proyectos Inteligentes**.

La base de datos contiene registros de 1885 encuestados. Para cada encuestado se conocen 12 atributos: mediciones de personalidad que incluyen NEO-FFI-R (neuroticismo, extraversión, apertura a la experiencia, amabilidad y responsabilidad), BIS-11 (impulsividad) e ImpSS (búsqueda de sensaciones), nivel de educación, edad, género, país de residencia y etnicidad. Todos los atributos de entrada son originalmente categóricos y están cuantificados. Después de la cuantificación, los valores de todas las características de entrada pueden considerarse como valores reales. Además, se cuestionó a los participantes sobre su uso de 18 drogas legales e ilegales (alcohol, anfetaminas, nitrito de amilo, benzodiazepinas, cannabis, chocolate, cocaína, cafeína, crack, éxtasis, heroína, ketamina, sustancias psicoactivas legales [legal highs], LSD, metadona, hongos, nicotina y abuso de sustancias volátiles), y una droga ficticia (Semeron) que se introdujo para identificar a quienes exageran o falsean respuestas. Para cada droga, debían seleccionar una de las respuestas: nunca usó la droga, la usó hace más de una década, o en la última década, año, mes, semana o día. La base de datos contiene 18 problemas de clasificación. Cada una de las variables de etiqueta independientes contiene siete clases: "Nunca usado", "Usado hace más de una década", "Usado en la última década", "Usado en el último año", "Usado en el último mes", "Usado en la última semana" y "Usado en el último día".

Se preguntó a los participantes sobre sustancias que fueron clasificadas como depresores del sistema nervioso central, estimulantes o alucinógenos. Las drogas depresoras incluyeron alcohol, nitrito de amilo, benzodiazepinas, tranquilizantes, disolventes e inhalantes de gamma-hidroxibutirato y opiáceos como la heroína y la metadona/opiáceos recetados. Los estimulantes consistieron en anfetaminas, nicotina, cocaína en polvo, crack, cafeína y chocolate. Aunque el chocolate contiene cafeína, los datos del chocolate se midieron por separado, dado que puede inducir efectos psicofarmacológicos y conductuales paralelos en individuos de manera congruente con otras sustancias adictivas [31]. Los alucinógenos incluyeron cannabis, éxtasis, ketamina, LSD y hongos mágicos.
También se midieron las sustancias psicoactivas legales (legal highs) como la mefedrona, la salvia y varias mezclas legales para fumar.

Aplica técnicas de Machine Learning No Supervisado (K-Means y Clustering Jerárquico) para identificar perfiles diferenciados de consumidores de drogas a partir de características demográficas, de personalidad y patrones de consumo.

**Dataset:** Drug Consumption Dataset
**Pregunta:** ¿Existen perfiles diferenciados de consumidores según sus rasgos de personalidad y sus patrones de consumo de sustancias?

## Estructura del proyecto
```
proyecto_clustering/
│
├── data/
│   └── drug_consumption.xlsx
│
├── Proyecto_III_Unal_BDTP.ipynb
├── requirements.txt
└── README.md
```

## Estructura del notebook
Sección 1 — Problema y datos
Sección 2 — Modelado: K-Means vs. Clustering Jerárquico
Sección 3 — Interpretación y visualizaciones
Sección 4 — Conclusiones
Sección 5 — Uso de IA

## Cómo correr el proyecto

1. Clonar o descargar el repositorio.
2. Instalar las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Asegurarse de que el archivo `drug_consumption.xlsx` esté en su lugar.
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
