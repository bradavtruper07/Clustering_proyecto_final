# Segmentación de Perfiles de Consumidores de Drogas — Clustering

## Descripción
Proyecto final del curso **Modelado Predictivo, Automatización y Proyectos Inteligentes (Nivel Intermedio)**.

Aplica técnicas de Machine Learning No Supervisado (K-Means y Clustering Jerárquico) para identificar perfiles diferenciados de consumidores de drogas a partir de características demográficas, de personalidad y patrones de consumo.

**Dataset:** Drug Consumption Dataset — Fehrman et al. (2017)  
**Pregunta:** ¿Existen perfiles diferenciados de consumidores según sus rasgos de personalidad y patrones de consumo?

## Estructura del proyecto
```
proyecto_clustering/
│
├── data/
│   └── drug_consumption.xlsx      # Dataset original
│
├── clustering_consumo_drogas.ipynb  # Notebook principal (fuente)
├── requirements.txt
└── README.md
```

## Cómo correr el proyecto

1. Clonar o descargar el repositorio.
2. Instalar las dependencias:
   ```bash
   pip install -r requirements.txt
   ```
3. Asegurarse de que el archivo `data/drug_consumption.xlsx` esté en su lugar.
4. Abrir el notebook:
   ```bash
   jupyter notebook clustering_consumo_drogas.ipynb
   ```
5. Ejecutar todas las celdas en orden con **Kernel → Restart & Run All**.

## Resultados principales
- Se identificaron **3 perfiles de consumidores** con características distintas.
- Los grupos difieren principalmente en **impulsividad, búsqueda de sensaciones y patrones de consumo**.
- Se validaron los resultados comparando K-Means vs. Clustering Jerárquico.
