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

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método de Simpson 1/3 ">   TDA de un árbol  </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>

Este método proporciona una mayor precisión que el Método del Trapecio para la misma cantidad de puntos de integración y es bastante eficaz para integrandos suaves. Sin embargo, para funciones con oscilaciones rápidas o discontinuidades, puede no ser tan eficaz. En esos casos, métodos más avanzados, como la regla de Simpson 3/8 o métodos adaptativos, pueden ser más apropiados.

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

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método de Simpson 3/8 "> Recorridos de los  árbol (PRE- IN-POST ORDEN)</a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>

 Los recorridos de árboles (preorden, inorden y postorden) son herramientas esenciales en la implementación y manipulación de estructuras de datos arbóreas, permitiendo recorrer, construir, analizar y aplicar estas estructuras en una amplia gama de problemas computacionales.
 
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

[Screenshot 2024-05-01 122725](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/88fc0e4d-4e71-4a33-a0ff-b4172ca14b23)

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método de la Cuadratura Gaussiana ">   Transformación de la expresión de infija a postfija </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>
  
La transformación de una expresión de infija a postfija en estructura de datos es esencial para simplificar la evaluación de expresiones aritméticas, mejorar la eficiencia en el procesamiento de datos y facilitar la implementación de algoritmos y sistemas que requieren manipulación de expresiones matemáticas de forma óptima.

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>

    import java.util.Scanner;
    import java.util.Stack;
    public class Infija_postfija2 {

    static boolean isOperator(char c) {    
        return c == '+' || c == '-' || c == '*' || c == '/';
    }
    
    // Método para obtener la precedencia de un operador
    static int getPrecedence(char op) {
        switch(op) {
            case '+':
            case '-':
                return 1;
            case '*':
            case '/':
                return 2;
        }
        return -1;
    }
    
    // Método para convertir la expresión infija a postfija
    static String infixToPostfix(String expression) {
        StringBuilder result = new StringBuilder();
        Stack<Character> stack = new Stack<>();
        
        for (int i = 0; i < expression.length(); i++) {
            char c = expression.charAt(i);
            
            // Si el carácter es un operando, lo agregamos al resultado
            if (Character.isLetterOrDigit(c)) {
                result.append(c);
            } else if (c == '(') { 
                stack.push(c);
            } else if (c == ')') { 
                while (!stack.isEmpty() && stack.peek() != '(') {
                    result.append(stack.pop());
                }
                stack.pop(); 
            } else { 
                while (!stack.isEmpty() && getPrecedence(c) <= getPrecedence(stack.peek())) {
                    result.append(stack.pop());
                }
                stack.push(c); 
            }
        }
        
        while (!stack.isEmpty()) {
            if (stack.peek() == '(' || stack.peek() == ')') {
                return "Expresión inválida";
            }
            result.append(stack.pop());
        }
        
        return result.toString();
    }
    
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Ingrese la expresión infija: ");
        String infixExpression = scanner.nextLine();
        
        System.out.println("Expresión infija: " + infixExpression);
        System.out.println("Expresión postfija: " + infixToPostfix(infixExpression));
        
        scanner.close();
      }
    }

<h4> <font font face = "arial"> Programa ejecutado </h4>
    
![WhatsApp Image 2024-04-30 at 23 58 00_09db4158](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/89f19b10-5ea5-4de8-b045-d6ad0effbf43)

