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

![Screenshot 2024-05-01 122725](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/6238fa7a-8f66-45e2-8ced-6eac6ac14b70)

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

-----------------------------------------------------------------------------------------

<h2 align = "center"> <font  font face = "bauhaus 93"> <a name="Métodos"> Grafos </a> </font> </h2>

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método del Trapecio ">  Implementación de un Grafo (dirigido Y no dirigido ) </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>
  
La implementación de grafos, tanto dirigidos como no dirigidos, en estructura de datos es esencial para modelar y analizar relaciones complejas, optimizar operaciones, estudiar la conectividad y aplicar algoritmos avanzados en una amplia gama de problemas computacionales.

<h4> <font font face = "arial"> <b> <i> Ejemplo en código de grafo dirigido </i> </b> </h4>

    import java.util.ArrayList;
    import java.util.HashMap;
    import java.util.List;
    import java.util.Map;
    import java.util.Scanner;

    class GrafoDirigido {
       private Map<Integer, List<Integer>> grafo;

    public GrafoDirigido() {
        this.grafo = new HashMap<>();
    }

    public void agregarVertice(int vertice) {
        grafo.put(vertice, new ArrayList<>());
    }

    public void agregarArista(int origen, int destino) {
        if (!grafo.containsKey(origen) || !grafo.containsKey(destino)) {
            System.out.println("Vertice no encontrado");
            return;
        }
        grafo.get(origen).add(destino);
    }

    public List<Integer> obtenerAdyacentes(int vertice) {
        return grafo.get(vertice);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        GrafoDirigido grafo = new GrafoDirigido();

        System.out.print("Ingrese el número de vértices: ");
        int numVertices = scanner.nextInt();

        for (int i = 1; i <= numVertices; i++) {
            grafo.agregarVertice(i);
        }

        System.out.print("Ingrese el número de aristas: ");
        int numAristas = scanner.nextInt();

        for (int i = 0; i < numAristas; i++) {
            System.out.print("Ingrese el origen de la arista: ");
            int origen = scanner.nextInt();
            System.out.print("Ingrese el destino de la arista: ");
            int destino = scanner.nextInt();
            grafo.agregarArista(origen, destino);
        }

        System.out.println("Grafo dirigido creado:");
        for (int vertice : grafo.grafo.keySet()) {
            System.out.println("Adyacentes de " + vertice + ": " + grafo.obtenerAdyacentes(vertice));
        }
      }
    }


<h4> <font font face = "arial"> Programa ejecutado </h4>
    
![WhatsApp Image 2024-05-01 at 00 15 23_235be8d5](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/c8873586-dba3-4b6b-8b26-3f8c3f5d7568)

<h4> <font font face = "arial"> <b> <i> Ejemplo en código de grafo no dirigido </i> </b> </h4>

    import java.util.ArrayList;
    import java.util.HashMap;
    import java.util.List;
    import java.util.Map;
    import java.util.Scanner;

    public class GrafoNoDirigido {

    private Map<Integer, List<Integer>> grafo;

    public GrafoNoDirigido() {
        this.grafo = new HashMap<>();
    }

    public void agregarVertice(int vertice) {
        grafo.put(vertice, new ArrayList<>());
    }

    public void agregarArista(int vertice1, int vertice2) {
        if (!grafo.containsKey(vertice1) || !grafo.containsKey(vertice2)) {
            System.out.println("Vertice no encontrado");
            return;
        }
        grafo.get(vertice1).add(vertice2);
        grafo.get(vertice2).add(vertice1);
    }

    public List<Integer> obtenerAdyacentes(int vertice) {
        return grafo.get(vertice);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        GrafoNoDirigido grafo = new GrafoNoDirigido();

        System.out.print("Ingrese el número de vértices: ");
        int numVertices = scanner.nextInt();

        for (int i = 1; i <= numVertices; i++) {
            grafo.agregarVertice(i);
        }

        System.out.print("Ingrese el número de aristas: ");
        int numAristas = scanner.nextInt();

        for (int i = 0; i < numAristas; i++) {
            System.out.print("Ingrese el primer vértice de la arista: ");
            int vertice1 = scanner.nextInt();
            System.out.print("Ingrese el segundo vértice de la arista: ");
            int vertice2 = scanner.nextInt();
            grafo.agregarArista(vertice1, vertice2);
        }

        System.out.println("Grafo no dirigido creado:");
        for (int vertice : grafo.grafo.keySet()) {
            System.out.println("Adyacentes de " + vertice + ": " + grafo.obtenerAdyacentes(vertice));
        }
      }
    }

<h4> <font font face = "arial"> Programa ejecutado </h4>
    
![WhatsApp Image 2024-05-01 at 00 24 28_e3b56784](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/164a0e06-ff8d-42f9-9a51-8d1815765f29)

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método del Trapecio ">  TDA de un  Grafo  </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>
  
El TDA de un Grafo en estructura de datos es esencial para modelar y analizar relaciones complejas, optimizar operaciones, estudiar la conectividad y aplicar algoritmos avanzados en una amplia gama de problemas computacionales.

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>

    import java.util.ArrayList;
    import java.util.HashMap;
    import java.util.List;
    import java.util.Map;
    import java.util.Scanner;

    class GrafoDirigido {
       private Map<Integer, List<Integer>> grafo;

    public GrafoDirigido() {
        this.grafo = new HashMap<>();
    }

    public void agregarVertice(int vertice) {
        grafo.put(vertice, new ArrayList<>());
    }

    public void agregarArista(int origen, int destino) {
        if (!grafo.containsKey(origen) || !grafo.containsKey(destino)) {
            System.out.println("Vertice no encontrado");
            return;
        }
        grafo.get(origen).add(destino);
    }

    public List<Integer> obtenerAdyacentes(int vertice) {
        return grafo.get(vertice);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        GrafoDirigido grafo = new GrafoDirigido();

        System.out.print("Ingrese el número de vértices: ");
        int numVertices = scanner.nextInt();

        for (int i = 1; i <= numVertices; i++) {
            grafo.agregarVertice(i);
        }

        System.out.print("Ingrese el número de aristas: ");
        int numAristas = scanner.nextInt();

        for (int i = 0; i < numAristas; i++) {
            System.out.print("Ingrese el origen de la arista: ");
            int origen = scanner.nextInt();
            System.out.print("Ingrese el destino de la arista: ");
            int destino = scanner.nextInt();
            grafo.agregarArista(origen, destino);
        }

        System.out.println("Grafo dirigido creado:");
        for (int vertice : grafo.grafo.keySet()) {
            System.out.println("Adyacentes de " + vertice + ": " + grafo.obtenerAdyacentes(vertice));
        }
      }
    }


<h4> <font font face = "arial"> Programa ejecutado </h4>
    
![WhatsApp Image 2024-05-01 at 00 15 23_235be8d5](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/c8873586-dba3-4b6b-8b26-3f8c3f5d7568)

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método del Trapecio ">  Implementación mediante matrices de adyacencia /// Implementación mediante listas de adyacencias </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>
  
La elección entre matrices de adyacencia y listas de adyacencias depende del tipo de grafo, el tamaño del grafo y las operaciones que se necesitan realizar sobre el grafo. Ambas implementaciones tienen sus ventajas y desventajas, y la decisión final dependerá de los requisitos específicos de la aplicación.

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>

    public class Grafo {
    private int V; // Número de vértices
    private LinkedList<Integer> adj[]; // Lista de adyacencia

    public Grafo(int v) {
        V = v;
        adj = new LinkedList[v];
        for (int i = 0; i < v; ++i)
            adj[i] = new LinkedList<>();
    }

    // Método para agregar una arista al grafo
    public void agregarArista(int v, int w) {
        adj[v].add(w);
        adj[w].add(v); // Para un grafo no dirigido
    }

    // Método para imprimir el grafo
    public void imprimirGrafo() {
        for (int i = 0; i < V; ++i) {
            System.out.print("Vértice " + i + " está conectado a: ");
            for (Integer n : adj[i]) {
                System.out.print(n + " ");
            }
            System.out.println();
        }
    }

    public static void main(String args[]) {
        Grafo g = new Grafo(5);
        g.agregarArista(0, 1);
        g.agregarArista(0, 4);
        g.agregarArista(1, 2);
        g.agregarArista(1, 3);
        g.agregarArista(1, 4);
        g.agregarArista(2, 3);
        g.agregarArista(3, 4);

        g.imprimirGrafo();
     }
    }


<h4> <font font face = "arial"> Programa ejecutado </h4>
    
![Screenshot 2024-05-01 125649](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/59e4754c-6ed0-48ee-a11a-b3b9ceac2d34)

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método del Trapecio ">  Recorridos sobre grafos. (Recorrido primero en profundidad y recorrido primero en amplitud) </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>
  
Tanto el recorrido primero en profundidad (DFS) como el recorrido primero en amplitud (BFS) son estrategias fundamentales en la implementación y manipulación de grafos en estructura de datos, cada una con sus propias características y aplicaciones.

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>

    public class Grafo {
    private int V; // Número de vértices
    private LinkedList<Integer> adj[]; // Lista de adyacencia

    public Grafo(int v) {
        V = v;
        adj = new LinkedList[v];
        for (int i = 0; i < v; ++i)
            adj[i] = new LinkedList<>();
    }

    // Método para agregar una arista al grafo
    public void agregarArista(int v, int w) {
        adj[v].add(w);
        adj[w].add(v); // Para un grafo no dirigido
    }

    // Método para imprimir el grafo
    public void imprimirGrafo() {
        for (int i = 0; i < V; ++i) {
            System.out.print("Vértice " + i + " está conectado a: ");
            for (Integer n : adj[i]) {
                System.out.print(n + " ");
            }
            System.out.println();
        }
    }

    public static void main(String args[]) {
        Grafo g = new Grafo(5);
        g.agregarArista(0, 1);
        g.agregarArista(0, 4);
        g.agregarArista(1, 2);
        g.agregarArista(1, 3);
        g.agregarArista(1, 4);
        g.agregarArista(2, 3);
        g.agregarArista(3, 4);

        g.imprimirGrafo();
     }
    }


<h4> <font font face = "arial"> Programa ejecutado </h4>
    
![Screenshot 2024-05-01 125649](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/59e4754c-6ed0-48ee-a11a-b3b9ceac2d34)

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método del Trapecio "> El algoritmo de Kruskal </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>
  
El algoritmo de Kruskal es un método efectivo para encontrar el árbol recubridor mínimo en grafos conexos y ponderados. Utiliza estructuras de datos como cola de prioridades y union-find para lograr su objetivo.

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>
    
    class Edge implements Comparable<Edge> {
    int source, destination, weight;

    public Edge(int source, int destination, int weight) {
        this.source = source;
        this.destination = destination;
        this.weight = weight;
    }

    @Override
    public int compareTo(Edge otherEdge) {
        return this.weight - otherEdge.weight;
      }
    }

    class Graph {
    int vertices;
    ArrayList<Edge> edges;

    public Graph(int vertices) {
        this.vertices = vertices;
        edges = new ArrayList<>();
    }

    public void addEdge(int source, int destination, int weight) {
        edges.add(new Edge(source, destination, weight));
     }
    }

    public class Main {
    public static void main(String[] args) {
        int vertices = 4;
        Graph graph = new Graph(vertices);
        graph.addEdge(0, 1, 10);
        graph.addEdge(0, 2, 6);
        graph.addEdge(0, 3, 5);
        graph.addEdge(1, 3, 15);
        graph.addEdge(2, 3, 4);

        kruskalMST(graph);
    }

    public static void kruskalMST(Graph graph) {
        PriorityQueue<Edge> pq = new PriorityQueue<>(graph.edges);
        ArrayList<Edge> result = new ArrayList<>();
        int[] parent = new int[graph.vertices];
        for (int i = 0; i < graph.vertices; i++)
            parent[i] = i;

        while (!pq.isEmpty()) {
            Edge edge = pq.poll();
            int u = find(parent, edge.source);
            int v = find(parent, edge.destination);
            if (u != v) {
                result.add(edge);
                parent[u] = v;
            }
        }

        System.out.println("HOLA");
        for (Edge edge : result) {
            System.out.println(edge.source + " - " + edge.destination + ": " + edge.weight);
        }
    }

    public static int find(int[] parent, int vertex) {
        if (parent[vertex] != vertex)
            parent[vertex] = find(parent, parent[vertex]);
        return parent[vertex];
      }
    }

<h4> <font font face = "arial"> Programa ejecutado </h4>
    
![Screenshot 2024-05-01 125![WhatsApp Image 2024-04-30 at 23 37 58_fc1eed03](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/1a12e4d6-4a5c-49ae-a686-6c3fa6834cd2)

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método del Trapecio "> Búsquedas de caminos </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>
  
Las búsquedas de caminos en estructura de datos son fundamentales para resolver problemas de optimización, planificación y análisis de conectividad, utilizando algoritmos especializados que permiten encontrar rutas eficientes y soluciones óptimas en diversos escenarios.

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>

    class Grafo {
     private int V; // Número de vértices
     private LinkedList<Integer> adj[]; // Lista de adyacencia

    Grafo(int v) {
        V = v;
        adj = new LinkedList[v];
        for (int i = 0; i < v; ++i)
            adj[i] = new LinkedList();
    }

    void agregarArista(int v, int w) {
        adj[v].add(w);
    }

    void DFSUtil(int v, boolean visitado[]) {
        visitado[v] = true;
        System.out.print(v + " ");

        Iterator<Integer> i = adj[v].listIterator();
        while (i.hasNext()) {
            int n = i.next();
            if (!visitado[n])
                DFSUtil(n, visitado);
        }
    }

    void DFS(int v) {
        boolean visitado[] = new boolean[V];
        DFSUtil(v, visitado);
     }
    }

    public class Main {
    public static void main(String args[]) {
        Grafo g = new Grafo(4);

        g.agregarArista(0, 1);
        g.agregarArista(0, 2);
        g.agregarArista(1, 2);
        g.agregarArista(2, 0);
        g.agregarArista(2, 3);
        g.agregarArista(3, 3);

        System.out.println("Recorrido en Profundidad empezando desde el vértice 2:");
        g.DFS(2);
     }
    }
<h4> <font font face = "arial"> Programa ejecutado </h4>
  
![WhatsApp Image 2024-04-30 at 23 41 02_42dcf095](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/041c49f9-a48e-48ab-99f8-eb67ca1382ae)

<h3 align = "center"> <font  font face = "bauhaus 93"> <a name=" Método del Trapecio "> Algoritmo de Dijkstra </a> </font> </h3>

<h4> <font font face = "arial"> Descripción </h4>
  
El algoritmo de Dijkstra es una herramienta fundamental en estructura de datos para encontrar la ruta más corta en grafos ponderados y conexos, con aplicaciones en una amplia variedad de problemas de optimización y planificación.

<h4> <font font face = "arial"> <b> <i> Ejemplo en código </i> </b> </h4>

    class Grafo {
    private int V; // Número de vértices
    private List<List<Nodo>> adj; // Lista de adyacencia

    Grafo(int v) {
        V = v;
        adj = new ArrayList<>(V);
        for (int i = 0; i < V; ++i)
            adj.add(new ArrayList<>());
    }

    void agregarArista(int origen, int destino, int peso) {
        Nodo nodo = new Nodo(destino, peso);
        adj.get(origen).add(nodo);
    }

    void dijkstra(int origen) {
        PriorityQueue<Nodo> pq = new PriorityQueue<>(V, Comparator.comparingInt(a -> a.peso));

        int[] distancia = new int[V];
        Arrays.fill(distancia, Integer.MAX_VALUE);
        pq.add(new Nodo(origen, 0));
        distancia[origen] = 0;

        while (!pq.isEmpty()) {
            int u = pq.poll().vertice;

            for (Nodo nodo : adj.get(u)) {
                int v = nodo.vertice;
                int peso = nodo.peso;

                if (distancia[u] != Integer.MAX_VALUE && distancia[u] + peso < distancia[v]) {
                    distancia[v] = distancia[u] + peso;
                    pq.add(new Nodo(v, distancia[v]));
                }
            }
        }

        System.out.println("Distancias mínimas desde el vértice " + origen + ":");
        for (int i = 0; i < V; ++i)
            System.out.println("Vértice " + i + ": " + distancia[i]);
    }

    static class Nodo {
        int vertice;
        int peso;

        Nodo(int vertice, int peso) {
            this.vertice = vertice;
            this.peso = peso;
        }
      }
    }

    public class Main {
    public static void main(String[] args) {
        Grafo g = new Grafo(5);
        g.agregarArista(0, 1, 2);
        g.agregarArista(0, 2, 4);
        g.agregarArista(1, 2, 1);
        g.agregarArista(1, 3, 7);
        g.agregarArista(2, 4, 3);
        g.agregarArista(3, 4, 1);

        g.dijkstra(0);
      }
    }
<h4> <font font face = "arial"> Programa ejecutado </h4>
    
  ![WhatsApp Image 2024-04-30 at 23 42 52_3683ab1e](https://github.com/Hante990/Estructuras_No_Lineales/assets/107586879/316f0eaf-1f40-4f3e-a6af-1a8c44341824)

