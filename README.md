<h1> <font color = "darkred" size="+5" font face = "cooper black"> <b> <i># Estructuras_No_Lineales</i> </b> </font> </h1>

<h4> <font color = "darkred" size="+5" font face = "cooper black"> <b> <i>Integrantes </i> </b> </font> </h4>

<li>Miguel Ángel Flores López</li>
<li>Diego Alonso Fernández Delgadillo</li>
<li>Xavier Valle Dorantes</li>
<li>José Antonio Guerrero Lazcano</li>

-----------------------------------------------------------------------------------------

<h3 align = "center"> <font color = "darkorange" size = "+6"  font face =  "cooper black">  Índice </font> </h3>

<header> <font color = "red" size="+1" font face = "aharoni">
    <nav class = "navegacion">
      <ul class = "Indice">
        <li> <a href = "#Descripción"> Descripción </a> <br> </li>
        <li> <a href = "#Temario"> Temario </a> <br> </li>
        <li> <a href = "#Métodos"> Métodos </a> <br> </li>
          <ul class = "subindice">
              <li> <a href="# Método del Trapecio "> Método del Trapecio </a> <br> </li>
              <li> <a href="# Método de Simpson 1/3 "> Método de Simpson 1/3 </a> <br> </li>
              <li> <a href="# Método de Simpson 3/8"> Método de Simpson 3/8 </a> <br> </li> 
              <li> <a href="# Método de la Cuadratura Gaussiana "> Método de la Cuadratura Gaussiana </a> <br> </li> 
          </ul>
      </ul>
    </nav>
</font> </header>

-----------------------------------------------------------------------------------------

<h3 align = "center"> <font  font face = "bauhaus 93">  <a name="Descripción"> Descripción</a> </font> </h3>

Una estructura de datos no lineal es una estructura en la que los elementos de datos no están organizados de manera secuencial. Cada elemento de datos potencialmente se conecta con varios otros elementos, formando una red compleja de conexiones.
Algunas de las estructuras de datos no lineales más comunes son:

<h4 align = "left">Árboles </h3>

Los árboles son una estructura jerárquica donde cada elemento (nodo) puede tener varios hijos, pero solo un padre (excepto la raíz). Ejemplos de árboles incluyen:
<li>Árboles binarios</li>
<li>Árboles de búsqueda binaria</li>
<li>Árboles de decisión</li>

<h4 align = "left">Grafos </h3>

Los grafos son una estructura que representa un conjunto de objetos (vértices) y las conexiones (aristas) entre ellos. Cada vértice puede estar conectado a múltiples otros vértices. Ejemplos de grafos incluyen:
<li>Redes sociales</li>
<li>Mapas y rutas</li>
<li>Redes de computadoras</li>

Dentro de este documento se encuentran algunos ejemplos en código sobre este tipo de estructuras de datos no lineales.
-----------------------------------------------------------------------------------------

<h3 align = "center"> <font  font face = "bauhaus 93">  <a name="Temario"> Temario</a> </font> </h3>

   1.- Implementación de un árbol      
   
   2.- TDA de un árbol 
   
   3.- Recorridos de los árbol (PRE- IN-POST ORDEN)
   
   4.- Transformación de la expresión de infija a postfija

   5.-Implementación de un grafo (dirigido Y No dirigido )   

   6.-TDA de un  Grafo 

   7.- Implementación mediante matrices de adyacencia ///
    Implementación mediante listas de adyacencias.   

   8.- Recorridos sobre grafos. (Recorrido primero en profundidad y Recorrido primero en amplitud).   

   9.-El algoritmo de Kruskal
   
   10.-Búsquedas de caminos.

   11.-Algoritmo de Dijkstra


-----------------------------------------------------------------------------------------

<h2 align = "center"> <font  font face = "bauhaus 93"> <a name="Métodos"> Arboles</a> </font> </h2>

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método del Trapecio "> Implementación de un árbol   </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>
  
La implementación de un árbol binario en estructura de datos es esencial para optimizar la manipulación, búsqueda y almacenamiento de datos en aplicaciones informáticas, lo que contribuye a mejorar la eficiencia y rendimiento de los algoritmos y sistemas desarrollados.

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>

    package Arbol;
    
    public class Nodo{
    int valor;
    Nodo izquierdo;
    Nodo derecho
    
    public Nodo(int valor){
        this.valor = valor;
        this.izquierdo = null;
        this.derecho = null;
      }
    }
    
    public class Arbol {
    Nodo raiz;

    public Arbol() {
        this.raiz = null;
    }

    public void insertar(int valor) {
        raiz = insertarRecursivo(raiz, valor);
    }

    private Nodo insertarRecursivo(Nodo raiz, int valor) {
        if (raiz == null) {
            raiz = new Nodo(valor);
            return raiz;
        }

        if (valor < raiz.valor) {
            raiz.izquierdo = insertarRecursivo(raiz.izquierdo, valor);
        } else if (valor > raiz.valor) {
            raiz.derecho = insertarRecursivo(raiz.derecho, valor);
        }

        return raiz;
    }

    public void recorrerPreOrden() {
        recorrerPreOrden(raiz);
    }

    private void recorrerPreOrden(Nodo nodo) {
        if (nodo != null) {
            System.out.print(nodo.valor + " ");
            recorrerPreOrden(nodo.izquierdo);
            recorrerPreOrden(nodo.derecho);
        }
    }

    public void recorrerInOrden() {
        recorrerInOrden(raiz);
    }

    private void recorrerInOrden(Nodo nodo) {
        if (nodo != null) {
            recorrerInOrden(nodo.izquierdo);
            System.out.print(nodo.valor + " ");
            recorrerInOrden(nodo.derecho);
        }
    }

    public void recorrerPostOrden() {
        recorrerPostOrden(raiz);
    }

    private void recorrerPostOrden(Nodo nodo) {
        if (nodo != null) {
            recorrerPostOrden(nodo.izquierdo);
            recorrerPostOrden(nodo.derecho);
            System.out.print(nodo.valor + " ");
        }
      }
    }
    public class App {
    public static void main(String[] args) {
        Arbol arbol = new Arbol();
        
        // Insertar nodos en el árbol
        arbol.insertar(50);
        arbol.insertar(30);
        arbol.insertar(70);
        arbol.insertar(20);
        arbol.insertar(40);

        // Recorrer el árbol en preorden, inorden y postorden e imprimir los valores
        System.out.println("Recorrido PreOrden del árbol:");
        arbol.recorrerPreOrden();
        System.out.println("\nRecorrido InOrden del árbol:");
        arbol.recorrerInOrden();
        System.out.println("\nRecorrido PostOrden del árbol:");
        arbol.recorrerPostOrden();
      }
    }


<h4> <font font face = "arial"> Programa ejecutado </h4>
    
![Screenshot 2024-05-01 122725](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/6238fa7a-8f66-45e2-8ced-6eac6ac14b70)

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método de Simpson 1/3 ">  Método de Simpson 1/3 </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>

Este método proporciona una mayor precisión que el Método del Trapecio para la misma cantidad de puntos de integración y es bastante eficaz para integrandos suaves. Sin embargo, para funciones con oscilaciones rápidas o discontinuidades, puede no ser tan eficaz. En esos casos, métodos más avanzados, como la regla de Simpson 3/8 o métodos adaptativos, pueden ser más apropiados.

<h4> <font font face = "arial">Pseudocódigo </h4>
  
1. Pseudocódigo para realizar la integración

        Función Simpson_Integración(f, a, b, n):
            h = (b - a) / n
            suma = f(a) + f(b)
            Para i desde 1 hasta n-1:
                xi = a + i * h
                Si i es impar:
                    suma = suma + 4 * f(xi)
                Sino:
                    suma = suma + 2 * f(xi)
            resultado = h * suma / 3
            Devolver resultado

2. Pseudocódigo para realizar la diferenciación
    
       Función Simpson_Diferenciación(f, a, b, n):
        h = (b - a) / n
        suma = f(a) + f(b)
        Para i desde 1 hasta n-1:
            xi = a + i * h
            Si i es impar:
                suma = suma + 4 * f(xi)
            Sino:
                suma = suma + 2 * f(xi)
        resultado = h * suma / 3
        resultado = resultado / h # Para la diferenciación
        Devolver resultado

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>

    package Método_Simpson1_3;
    
    import java.util.function.Function;
    /**
     *
     * @author Migue
     */
    public class Ejercicio1 {
        // Método para calcular la integral numérica utilizando el Método de Simpson 1/3
        public static double integrate(double a, double b, int n, Function<Double, Double> func) {
            double h = (b - a) / n;
            double sum = func.apply(a) + func.apply(b);
    
            for (int i = 1; i < n; i += 2) {
                double x = a + i * h;
                sum += 4 * func.apply(x);
            }
    
            for (int i = 2; i < n - 1; i += 2) {
                double x = a + i * h;
                sum += 2 * func.apply(x);
            }
    
            return (h / 3) * sum;
        }
        
        // Método para calcular la derivada numérica utilizando el Método de Simpson 1/3
        public static double differentiate(double x, double h, Function<Double, Double> func) {
            double result = (func.apply(x - 2 * h) - 8 * func.apply(x - h) + 8 * func.apply(x + h) - func.apply(x + 2 * h)) / (12 * h);
            return result;
        }
        
        public static void main(String[] args) {
            // Definir la función que se desea integrar y diferenciar
            Function<Double, Double> func = (x) -> Math.sin(x); // Ejemplo: función seno
            
            // Definir los límites de integración y el número de segmentos
            double a = 0; // Límite inferior
            double b = Math.PI / 2; // Límite superior
            int n = 4; // Número de segmentos (debe ser par para el Método de Simpson 1/3)
            
            // Calcular la integral numérica utilizando el Método de Simpson 1/3
            double integral = integrate(a, b, n, func);
            System.out.println("Resultado de la integración: " + integral);
            
            // Calcular la derivada numérica utilizando el Método de Simpson 1/3
            double x0 = Math.PI / 4; // Punto en el que se desea calcular la derivada
            double h = 0.1; // Tamaño del paso
            double derivative = differentiate(x0, h, func);
            System.out.println("Resultado de la diferenciación en x = " + x0 + ": " + derivative);
        }
    }

<h4> <font font face = "arial"> Programa ejecutado </h4>

![Captura de pantalla 2024-04-21 142010](https://github.com/MiguelAngelFlores3/M-TODOS_T4/assets/167603831/4790a5b1-9e8c-4d36-ac32-fc21be24a584)

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método de Simpson 3/8 ">  Método de Simpson 3/8 </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>

El Método de Simpson 3/8 es una técnica de integración numérica que extiende el Método de Simpson 1/3 para mejorar aún más la precisión de la aproximación. Al igual que el Método de Simpson 1/3, utiliza polinomios de segundo grado (parábolas) para aproximar la función entre los puntos de integración. Sin embargo, en lugar de usar parábolas en cada subintervalo, el Método de Simpson 3/8 utiliza polinomios de tercer grado (cúbicos) para ajustar la función.

<h4> <font font face = "arial">Pseudocódigo </h4>
  
1. Pseudocódigo para realizar la integración

        Función Simpson_3_8_Integración(f, a, b, n):
            h = (b - a) / n
            suma = f(a) + f(b)
            Para i desde 1 hasta n-1:
                xi = a + i * h
                Si i es divisible por 3:
                    suma = suma + 2 * f(xi)
                Sino Si i no es divisible por 3 pero es impar:
                    suma = suma + 3 * f(xi)
                Sino:
                    suma = suma + 3 * f(xi)
            resultado = 3 * h * suma / 8
            Devolver resultado

2. Pseudocódigo para realizar la diferenciación

       Función Simpson_3_8_Diferenciación(f, a, b, n):
        h = (b - a) / n
        suma = f(a) + f(b)
        Para i desde 1 hasta n-1:
            xi = a + i * h
            Si i es divisible por 3:
                suma = suma + 2 * f(xi)
            Sino Si i no es divisible por 3 pero es impar:
                suma = suma + 3 * f(xi)
            Sino:
                suma = suma + 3 * f(xi)
        resultado = 3 * h * suma / 8
        resultado = resultado / h # Para la diferenciación
        Devolver resultado

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>

    package Método_Simpson3_8;
    
    import java.util.function.Function;
    
    /**
     *
     * @author Migue
     */
    public class Ejercicio1 {
        // Método para calcular la integral numérica utilizando el Método de Simpson 3/8
    
        public static double integrate(double a, double b, int n, Function<Double, Double> func) {
            double h = (b - a) / n;
            double sum = func.apply(a) + func.apply(b);
    
            for (int i = 1; i < n; i++) {
                double x = a + i * h;
                sum += i % 3 == 0 ? 2 * func.apply(x) : 3 * func.apply(x);
            }
    
            return (3 * h / 8) * sum;
        }
    
        // Método para calcular la derivada numérica utilizando el Método de Simpson 3/8
        public static double differentiate(double x, double h, Function<Double, Double> func) {
            double result = (-func.apply(x + 2 * h) + 9 * func.apply(x + h) - 9 * func.apply(x - h) + func.apply(x - 2 * h)) / (24 * h);
            return result;
        }
    
        public static void main(String[] args) {
            Function<Double, Double> func = (x) -> Math.sin(x); // Función a integrar y diferenciar: sin(x)
            double a = 0; // Límite inferior
            double b = Math.PI / 2; // Límite superior
            int n = 3; // Número de segmentos (debe ser múltiplo de 3 para el Método de Simpson 3/8)
            double x0 = Math.PI / 4; // Punto en el que se desea calcular la derivada
            double h = 0.1; // Tamaño del paso
    
            // Calcular la integral numérica utilizando el Método de Simpson 3/8
            double integral = integrate(a, b, n, func);
            System.out.println("Resultado de la integración: " + integral);
    
            // Calcular la derivada numérica utilizando el Método de Simpson 3/8
            double derivative = differentiate(x0, h, func);
            System.out.println("Resultado de la diferenciación en x = " + x0 + ": " + derivative);
        }
    }

<h4> <font font face = "arial"> Programa ejecutado </h4>

![Captura de pantalla 2024-04-21 144711](https://github.com/MiguelAngelFlores3/M-TODOS_T4/assets/167603831/2f81f60f-9961-47cc-b7d6-9cc7e679a7eb)

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método de la Cuadratura Gaussiana ">  Método de la Cuadratura Gaussiana </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>
  
El Método de la Cuadratura Gaussiana es una técnica de integración numérica que utiliza una selección cuidadosa de puntos de evaluación y pesos para proporcionar una alta precisión en la aproximación de integrales definidas. A diferencia de los métodos de interpolación como el Método del Trapecio o el Método de Simpson, la Cuadratura Gaussiana no intenta ajustar polinomios a la función a integrar. En cambio, aprovecha las propiedades de ciertas funciones de peso para elegir de manera óptima los puntos de evaluación.

<h4> <font font face = "arial">Pseudocódigo </h4>
  
1. Pseudocódigo para realizar la integración

        Función Cuadratura_Gaussiana_Integración(f, a, b, n):
            coeficientes, nodos = obtener_coeficientes_y_nodos(n)
            suma = 0
            Para i desde 0 hasta n-1:
                xi = (b - a) / 2 * nodos[i] + (b + a) / 2
                suma = suma + coeficientes[i] * f(xi)
            resultado = (b - a) / 2 * suma
            Devolver resultado

2. Pseudocódigo para realizar la diferenciación

        Función Cuadratura_Gaussiana_Diferenciación(f, a, b, n):
            coeficientes, nodos = obtener_coeficientes_y_nodos(n)
            suma = 0
            Para i desde 0 hasta n-1:
                xi = (b - a) / 2 * nodos[i] + (b + a) / 2
                suma = suma + coeficientes[i] * f(xi)
            resultado = suma
            Devolver resultado

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>

    package Método_Cuadratura_Gaussiana;
    
    import java.util.function.Function;
    
    /**
     *
     * @author Migue
     */
    public class Ejercicio1 {
        // Coeficientes y nodos de Cuadratura Gaussiana para dos puntos
    
        private static final double[] nodes = {-0.5773502692, 0.5773502692};
        private static final double[] weights = {1.0, 1.0};
    
        // Método para calcular la integral numérica utilizando Cuadratura Gaussiana
        public static double integrate(double a, double b, Function<Double, Double> func) {
            double integral = 0.0;
            double transform = (b - a) / 2.0;
    
            for (int i = 0; i < nodes.length; i++) {
                double x = transform * nodes[i] + (a + b) / 2.0;
                integral += weights[i] * func.apply(x);
            }
    
            return transform * integral;
        }
    
        // Método para calcular la derivada numérica utilizando Cuadratura Gaussiana
        public static double differentiate(double x, double h, Function<Double, Double> func) {
            double derivative = 0.0;
    
            for (int i = 0; i < nodes.length; i++) {
                double xi = x + h * nodes[i];
                derivative += weights[i] * func.apply(xi);
            }
    
            return derivative / h;
        }
    
        public static void main(String[] args) {
            Function<Double, Double> func = (x) -> Math.sin(x); // Función a integrar y diferenciar: sin(x)
            double a = 0; // Límite inferior
            double b = Math.PI / 2; // Límite superior
            double x0 = Math.PI / 4; // Punto en el que se desea calcular la derivada
            double h = 0.1; // Tamaño del paso
    
            // Calcular la integral numérica utilizando Cuadratura Gaussiana
            double integral = integrate(a, b, func);
            System.out.println("Resultado de la integración: " + integral);
    
            // Calcular la derivada numérica utilizando Cuadratura Gaussiana
            double derivative = differentiate(x0, h, func);
            System.out.println("Resultado de la diferenciación en x = " + x0 + ": " + derivative);
        }
    }

<h4> <font font face = "arial"> Programa ejecutado </h4>

![Captura de pantalla 2024-04-21 145400](https://github.com/MiguelAngelFlores3/M-TODOS_T4/assets/167603831/33d51347-cb05-4cdf-9611-78a99cd6448d)
