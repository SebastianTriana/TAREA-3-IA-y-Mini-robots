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
