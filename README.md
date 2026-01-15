# QuickHull-Interactive-Algorithm
# QuickHull: Cálculo y visualización del cierre convexo

Proyecto final de **Geometría Computacional**  
Grado en Ingeniería Matemática e Inteligencia Artificial (iMAT)  
Curso académico 2025–2026

---

## Resumen

Este repositorio presenta una implementación del algoritmo **QuickHull** para el cálculo del **cierre convexo** de una nube de puntos en el plano, junto con una herramienta de **visualización interactiva** desarrollada en **SageMath** e integrada en una página web.

El proyecto combina el desarrollo algorítmico con una interpretación geométrica visual, permitiendo analizar paso a paso el funcionamiento interno del algoritmo y su comportamiento en distintos conjuntos de puntos.

---

## Introducción

Dado un conjunto finito de puntos \( P \subset \mathbb{R}^2 \), el cierre convexo es el polígono convexo de menor área que contiene a todos los puntos de \( P \).

El algoritmo **QuickHull** aborda este problema mediante una estrategia de *divide y vencerás*. A partir de puntos extremos que pertenecen con certeza a la envolvente convexa, el algoritmo divide el conjunto en subconjuntos más pequeños, descartando de forma eficiente los puntos interiores mediante construcciones triangulares sucesivas. Este proceso recursivo finaliza cuando no quedan puntos candidatos fuera de los segmentos de la envolvente.

---

## Descripción del algoritmo

La implementación se estructura en dos niveles principales:

### Función principal `QuickHull(P)`
- Trata los casos triviales (menos de tres puntos).
- Determina los puntos extremos en el eje X.
- Divide el conjunto inicial en dos subconjuntos según su posición relativa a la recta definida por dichos extremos.
- Llama recursivamente a la función auxiliar para cada lado.
- Devuelve la envolvente convexa completa en orden antihorario, junto con un historial detallado de las iteraciones.

### Función auxiliar `Quickhull(a, b, S)`
- Selecciona el punto de \( S \) más alejado de la recta dirigida \( ab \).
- Forma el triángulo \( a\!-\!c\!-\!b \) y elimina los puntos que quedan en su interior o borde.
- Divide el conjunto restante en dos subconjuntos y aplica recursión sobre cada uno.
- Construye progresivamente la cadena de la envolvente entre los puntos \( a \) y \( b \).

Adicionalmente, se implementa una función de **clasificación de puntos**, que permite distinguir en cada iteración entre puntos ya descartados (interiores) y puntos que continúan siendo candidatos a formar parte de la envolvente.

---

## Visualización interactiva

El proyecto incluye una aplicación interactiva basada en SageMath que permite:

- Generar nubes de puntos de forma aleatoria (con control de semilla).
- Introducir manualmente conjuntos de puntos.
- Explorar el algoritmo iteración a iteración mediante un deslizador.
- Visualizar simultáneamente:
  - La envolvente convexa parcial y final.
  - Los puntos descartados y los puntos activos.
  - El triángulo y el segmento procesados en cada paso.

Esta visualización facilita una comprensión detallada del comportamiento geométrico del algoritmo y de su eficiencia práctica.

---

## Contenido del repositorio

- `QuickHull.html`  
  Página web que integra la applet interactiva de SageMath.

- `QuickHull.ipynb`  
  Notebook con la implementación del algoritmo y pruebas asociadas.

- `Proyecto Final 4.pdf`  
  Documento con el enunciado oficial del proyecto.

---

## Instrucciones de uso

### Ejecución mediante navegador
1. Abrir el archivo `QuickHull.html` en un navegador con acceso a internet.
2. Lanzar la applet interactiva.
3. Seleccionar el modo de generación de puntos.
4. Avanzar por las iteraciones del algoritmo utilizando el control deslizante.

### Ejecución en entorno SageMath
1. Abrir el archivo `QuickHull.ipynb` en un entorno compatible con SageMath.
2. Ejecutar las celdas del notebook.
3. Modificar o definir nuevos conjuntos de puntos si se desea.

---

## Discusión y aplicaciones

QuickHull es un algoritmo ampliamente utilizado para el cálculo del cierre convexo debido a su buen rendimiento promedio y a su clara interpretación geométrica. Aunque su complejidad en el peor caso es cuadrática, en la práctica resulta eficiente para distribuciones de puntos habituales.

El problema del cierre convexo tiene aplicaciones en múltiples ámbitos, entre ellos:
- Visión por computador y análisis de contornos.
- Robótica y planificación de trayectorias.
- Sistemas de información geográfica.
- Análisis de datos y detección de valores atípicos.
- Logística y delimitación de áreas de servicio.

---

## Autores

- Jaime Sainz  
- Rafael Onieva  
- Iñaki Juan-Aracil  

---

## Fecha de última actualización

29 de noviembre de 2025

---

## Nota

El diseño visual de la página HTML ha sido elaborado con apoyo de herramientas de inteligencia artificial.
