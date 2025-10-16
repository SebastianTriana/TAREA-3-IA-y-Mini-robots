# TAREA 3 — IA y Mini-robots

Este repositorio contiene la solución de la **Guía #3** del curso de Inteligencia Artificial, centrada en la aplicación de algoritmos para problemas relacionados con mini-robots y toma de decisiones.

**Autores**:  
- Juan Diego Camacho  
- Sebastián Triana

---

## 📌 Punto 1: Maximización con Algoritmos Genéticos

Se implementa un **algoritmo genético (AG)** para encontrar el valor de \( x \in [0, 1] \) que maximiza la siguiente función:

f(x) = 10 * (x * sin(10πx) + 1)

markdown
Copiar código

### ⚙️ ¿Cómo funciona?

1. **Codificación binaria**:  
   Cada cromosoma es una cadena de 0s y 1s que representa un número real entre 0 y 1.

2. **Evaluación (fitness)**:  
   Se evalúa cada cromosoma usando la función objetivo como función de aptitud.

3. **Selección tipo ruleta**:  
   Los individuos con mejor aptitud tienen mayor probabilidad de reproducirse.

4. **Cruzamiento (crossover)**:  
   Se mezclan genes de pares de cromosomas para crear nueva descendencia.

5. **Mutación aleatoria**:  
   Cada bit tiene una baja probabilidad de mutar, para mantener diversidad genética.

6. **Mejor cromosoma**:  
   Se guarda y muestra el mejor cromosoma encontrado en todas las generaciones.

### 🧪 Parámetros utilizados

- `L = 10` → Longitud del cromosoma (número de bits)
- `N = 100` → Tamaño de la población
- `Gen = 1000` → Número de generaciones

### 📈 Ejemplo de resultado (salida de consola)

```text
Generacion actual: 1000
=== Mejor cromosoma total: de la generacion 947 ===
Cromosoma: [1, 0, 0, 1, 1, 0, 1, 0, 1, 1]
x* = 0.698
f(x*) = 9.85
```

---

## 📌 Punto 2: Democracia Verdadera con Asignación de Poder

Este ejercicio simula un sistema de gobierno con representación parlamentaria, donde se deben distribuir entidades del Estado entre partidos políticos, **respetando su proporción de curules**. El objetivo es lograr una asignación justa del poder, utilizando un algoritmo genético.

### 🏛️ Contexto

- Hay **5 partidos políticos** y **50 curules** en el congreso.
- Hay **50 entidades** (ministerios, agencias, etc.) que se deben repartir.
- Cada entidad tiene un **peso político** aleatorio entre 1 y 100.
- Se busca que el **poder político asignado a cada partido** refleje la **proporción real de curules** que tiene en el congreso.

### ⚙️ ¿Cómo funciona?

1. **Generación inicial**
   - Se asignan aleatoriamente los curules a partidos (no uniformemente).
   - Se generan entidades con pesos políticos aleatorios.

2. **Codificación**
   - Cada cromosoma representa una asignación de entidades a partidos (números del 1 al 5).

3. **Función de aptitud**
   - Calcula la diferencia entre el **poder esperado** (por curules) y el **poder asignado** (por entidades) para cada partido.
   - Busca minimizar esa diferencia usando esta fórmula:
     ```
     Aptitud = 100 * (1 - error relativo promedio)
     ```

4. **Selección, cruzamiento y mutación**
   - Se usa selección por ruleta, cruce por punto aleatorio y mutación aleatoria por gen.

5. **Resultado final**
   - Se muestra la asignación más justa lograda:
     - Qué partido controla qué entidad.
     - Cuánto poder recibió cada uno comparado con sus curules.
     - Precisión total de la asignación.

### 🧪 Parámetros utilizados

- `Num_curules = 50`  
- `Num_partidos = 5`  
- `Num_entidades = 50`  
- `N = 100` → Tamaño de la población  
- `Gen = 1000` → Número de generaciones

### 📊 Ejemplo de salida
```text
Generacion actual: 1000
=== Mejor cromosoma total: de la generacion 947 ===
Poder esperado = [0.28, 0.16, 0.22, 0.18, 0.16]
Poder asignado = [0.27, 0.15, 0.23, 0.17, 0.18]
Precision = 97.2%

