# Clasificación de variedades de frijol con Machine Learning

Proyecto del diplomado de Analítica de Datos e Inteligencia Artificial. Clasifica 7 variedades de frijol seco a partir de 16 características morfológicas (área, perímetro, longitud de ejes, solidez, etc.) usando un árbol de decisión.

## Datos
- Archivo: `Dry_Bean_Dataset.xlsx` con 13.611 registros, 16 variables predictoras y la variable objetivo `Class`.
- Variedades: SEKER, BARBUNYA, BOMBAY, CALI, HOROZ, SIRA y DERMASON.
- Fuente: Dry Bean Dataset, UCI Machine Learning Repository.

## Metodología
1. Carga y exploración de los datos con pandas.
2. Balanceo de clases con SMOTE (imbalanced-learn): cada variedad pasa a 3.546 registros.
3. Codificación numérica de la variable objetivo (0 a 6).
4. Árbol de decisión con scikit-learn (criterio entropía, profundidad máxima 7, mínimo 2 muestras por hoja).
5. Evaluación con validación cruzada de 10 pliegues.
6. Visualización del árbol con Matplotlib (`plot_tree`).

## Resultados
Promedio de la validación cruzada de 10 pliegues:

| Métrica | Valor |
|---|---|
| Exactitud | 90,2 % |
| F1 ponderado | 0,89 |
| Precisión ponderada | 0,89 |
| Recall ponderado | 0,90 |

## Árbol de decisión
<img width="2044" height="944" alt="arbol_decision_frijol" src="https://github.com/user-attachments/assets/1159a6fe-ea7d-4bab-8f28-854e3c47c6f6" />

## Cómo ejecutarlo en Google Colab
Dentro del entorno de colab, en la sección de Archivos, adjunta los datos de los frijoles (Dry_Bean_Dataset.xlsx) en la carpeta sample_data (en la dirección /content/sample_data/Dry_Bean_Dataset.xlsx). En caso de que se adjunte el archivo en otra ubicación, se debe hacer lo siguiente:
- Poner el cursor en el archivo y dar click en los tres puntos en la parte derecha.
- Seleccionar "Copiar la ruta de acceso"
- Pegar la ruta dentro de las comillas (ubicado en el segundo bloque de código con la variable "datos"), reemplazando la ubicación del archivo (/content/sample_data/Dry_Bean_Dataset.xlsx).
