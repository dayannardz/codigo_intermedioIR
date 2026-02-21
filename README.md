Después del análisis semántico, el compilador ya verificó que las variables estén declaradas y que las operaciones sean válidas. En esta etapa, el código Java se traduce a una representación intermedia (IR), la cual es independiente del hardware.
int a = 5;
int b = 10;
int c;
int d;

c = a + b;
d = 20; // código muerto

Representación intermedia.
t1 = 5
a = t1

t2 = 10
b = t2

t3 = a + b
c = t3

t4 = 20
d = t4

El código intermedio permite realizar optimizaciones antes de generar código máquina específico del hardware, mejorando el rendimiento del programa.
Eliminación de Código Muerto: como la variable d no se utiliza, el compilador elimina las instrucciones asociadas.
Antes de la optimización:
a = 5
b = 10
c = a + b
Después de la optimización:
c = 15

Estas optimizaciones reducen operaciones innecesarias y hacen el código más eficiente.
