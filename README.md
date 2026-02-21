Análisis del Código Intermedio (IR)

Introducción:
En los compiladores modernos, el código fuente no se traduce directamente a código máquina.  
Antes de llegar al hardware específico, el compilador genera una **representación intermedia (IR)** que facilita el análisis, la optimización y la portabilidad del programa.

En este repositorio se muestra un ejemplo sencillo en Java que ilustra:
- La generación de código intermedio después del análisis semántico.
- El uso del IR para realizar optimizaciones.
- Beneficios como la eliminación de código muerto y la propagación de constantes.

Generación de Código Intermedio

Después del **análisis semántico**, el compilador ya verificó que:
- Las variables estén declaradas.
- Los tipos sean correctos.
- Las operaciones sean válidas.

Una vez validado esto, el código Java se traduce a una representación intermedia (IR), la cual es **independiente de la arquitectura del hardware**.

Código fuente original (Java)

```java
int a = 5;
int b = 10;
int c;
int d;

c = a + b;
d = 20; // código muerto
```

Representación Intermedia IR
El compilador descompone las instrucciones en operaciones simples usando variables temporales:
```
t1 = 5
a = t1

t2 = 10
b = t2

t3 = a + b
c = t3

t4 = 20
d = t4
```

Beneficios de la Optimización con Código Intermedio
El uso del código intermedio permite aplicar diversas optimizaciones que mejoran el rendimiento del programa.

Eliminación de Código Muerto
La variable d nunca se utiliza en el programa, por lo que el compilador detecta que las instrucciones asociadas no afectan el resultado final y las elimina.

Propagación de Constantes
Como los valores de a y b son constantes, el compilador puede calcular el resultado en tiempo de compilación.

Antes de la optimización:
```
a = 5
b = 10
c = a + b
```

Después de la optimización:
```
c = 15
```

Conclusión:
El compilador puede aplicar optimizaciones como la eliminación de código muerto y la propagación de constantes, lo que reduce operaciones innecesarias y hace que el programa sea más eficiente antes de convertirse en código máquina.
