# Ejerecicios Semana 7

## Autor

Jesus Alejandro Hernandez Mendez y Luis Holgado Arranz

## Respuestas:

### 61. Explique la diferencia entre tipo abstracto de datos (TAD) y estructura de datos.

Un TAD es una descripción teórica de un conjunto de datos y las operaciones que se pueden realizar sobre ellos, sin especificar cómo están implementados. Se centra en qué hace el tipo de datos, no en cómo lo hace. En comparacion con las Estructura de datos las cuales son la implementacion concreta de un TAD. Definiendo como se organizan y almacenan los datos en memoria para cumplir con las operaciones del TAD de manera eficiente.

### 62.Explique qué es una lista y cuáles son sus operaciones típicas.

Una lista es una estructura de datos lineal que almacena una secuencia ordenada de elementos, en la que se pueden realizar operaciones como inserción, eliminación y acceso. Las listas pueden ser estáticas (tamaño fijo) o dinámicas (pueden crecer y reducirse en tiempo de ejecución).

Operaciones de las listas:
- Inserción (insert, add)

Agregar un elemento al inicio, al final o en una posición específica.
EJ: lista.add(5);  // Agrega 5 al final
lista.add(0, 10);  // Agrega 10 en la posición 0

- Eliminación (remove)

Se puede eliminar un elemento por valor o por índice.
EJ: lista.remove(Integer.valueOf(5)); // Elimina el número 5
lista.remove(0); // Elimina el primer elemento

- Búsqueda (search, contains)

Verifica si un elemento existe en la lista y en qué posición.
EJ: boolean existe = lista.contains(10);  // ¿La lista tiene un 10?
int indice = lista.indexOf(10);  // Obtiene la posición de 10

- Acceso (get)

Permite obtener un elemento en una posición específica.
EJ: int valor = lista.get(0);  // Obtiene el primer elemento

- Modificación (set)

Permite reemplazar el valor de un elemento en una posición dada.
EJ: lista.set(0, 20); // Cambia el primer elemento a 20

- Longitud (size)

Devuelve el número de elementos en la lista.
EJ: int tamaño = lista.size();  // Número de elementos


### 63. Explique las diferentes formas de implementar una lista:

1. Lista utilizando Arreglos (Array): Usa un array estático como base. tienen un tamaño fijo, determinado en el momento de la creación. Permite el acceso rápido a los elementos (O(1)). Aunque la inserción y eliminación de elementos son costosas (O(n)) porque requieren desplazar elementos.

2. Lista Enlazada: Implementada con nodos, donde cada nodo apunta al siguiente. Puede ser simplemente enlazada, doblemente enlazada o circular. No necesita tamaño fijo, crece dinámicamente. Las inserciones y eliminaciones rápidas (O(1)) en los extremos. Aunque el acceso a un elemento en el medio es lento (O(n)).

3. Lista Doblemente Enlazada: Cada nodo apunta tanto al siguiente como al anterior nodo. Permite recorrer la lista en ambas direcciones. Pero con la desventaja de un mayor consumo de memoria que una lista simplemente enlazada.

4. Lista Basada en ArrayList: Su implementación es basada en arrays dinámicos. Permite acceso rápido a los elementos (O(1)).La inserción y eliminación son más costosas (O(n)) si no se hacen al final. Pero en su contraparte, maneja automáticamente el crecimiento del array.

5. Lista Basada en LinkedList: Implementación basada en una lista doblemente enlazada. Es más eficiente que un ArrayList para inserciones y eliminaciones (O(1)) en cualquier posición. Pero el acceso a elementos en medio de la lista es más lento (O(n)).

### 65. Examine los siguientes códigos fuente e identifique la relación entre ellos:
1. Collection.java:

Es la interfaz base de todas las colecciones en Java.

Define métodos generales como add(), remove(), size(), iterator(), etc.

Otras interfaces más específicas, como List, Set y Queue, heredan de Collection.

2. List.java.

Extiende Collection, por lo que hereda todos sus métodos.

Define operaciones específicas de una lista ordenada, como:

get(int index): Acceso a elementos por índice.

add(int index, E element): Inserción en una posición específica.

remove(int index): Eliminación de elementos por índice.

Implementada por ArrayList y LinkedList.

3. ArrayList.java.

Implementa List usando un array dinámico.

Ofrece acceso rápido a los elementos (O(1)), pero las inserciones y eliminaciones en el medio son costosas (O(n)).

Es la implementación más utilizada para listas en Java.


4. LinkedList.java.

Implementa List usando una lista doblemente enlazada.

Facilita inserciones y eliminaciones en cualquier posición (O(1) si se tiene la referencia), pero el acceso por índice es lento (O(n)).

También implementa Deque, permitiendo operar como una cola doble.

### 66. Explique qué es una pila y cuáles son sus operaciones típicas.

Una pila (stack) es una estructura de datos LIFO (Last In, First Out), lo que significa que el último elemento en entrar es el primero en salir.

Las operaciones principales de una pila son:

- push(elemento) → Inserta un elemento en la cima de la pila.

- pop() → Elimina y devuelve el elemento en la cima de la pila.

- peek() o top() → Devuelve el elemento en la cima sin eliminarlo.

- isEmpty() → Verifica si la pila está vacía.

- size() → Devuelve el número de elementos en la pila.

### 67. Indique dos aplicaciones en que se utilzan pilas.

1. Deshacer/Rehacer en editores de texto

Cuando escribes en un editor de texto (como Word o Google Docs), cada cambio se almacena en una pila.

Ejemplo: Si escribes "Hola" y luego borras la "a", puedes presionar Ctrl + Z para deshacer la acción porque el último cambio ("borrar la 'a'") estaba en la cima de la pila.

2.  Navegación en navegadores web

Los navegadores usan pilas para almacenar el historial de páginas visitadas.

Ejemplo: Si visitas A → B → C y presionas el botón "Atrás", la página C se elimina de la pila y vuelves a B.

### 68. Explique la relación existente entre el TAD lista y el TAD pila.

El Tipo Abstracto de Datos (TAD) Pila es un caso particular del TAD Lista, ya que una pila sigue una política de acceso LIFO (Last In, First Out), lo que significa que solo permite insertar y eliminar elementos por un único extremo llamado tope. 

El TAD Lista es más general, ya que permite insertar, eliminar y acceder a elementos en cualquier posición.

### 69. Examine el código fuente de las clases Stack.java y Vector.java. Identifique la relación entre ellos y con ArrayList.java

La clase Stack<E> hereda de Vector<E>, lo que significa que Stack es una especialización de Vector con un comportamiento LIFO.

Vector<E> es una implementación sincronizada de una lista basada en arrays dinámicos, lo que lo hace similar a ArrayList<E>, pero con métodos sincronizados para garantizar seguridad en entornos concurrentes.

Ambos implementan la interfaz List<E>, lo que los convierte en estructuras de datos basadas en listas, aunque Stack restringe sus operaciones para cumplir con la política LIFO.

### 71. Explique qué es una cola y cuáles son sus operaciones típicas.

Una cola es una estructura de datos que sigue una política de acceso FIFO (First In, First Out), donde los elementos se insertan por un extremo llamado final (o trasero) y se eliminan por el otro extremo llamado frente. Sus operaciones típicas son:

- enqueue(elemento): Inserta un elemento al final de la cola.

- dequeue(): Elimina y devuelve el elemento en el frente de la cola.

- peek(): Retorna el elemento en el frente sin eliminarlo.

- isEmpty(): Verifica si la cola está vacía.

- size(): Retorna la cantidad de elementos en la cola.

### 72. Indique tipos de aplicaciones en que se utilicen colas.

1. Gestión de tareas en impresoras

Los documentos se imprimen en el orden en que fueron enviados.

2. Sistemas de atención al cliente

En bancos o centros de llamadas, los clientes se atienden en el orden en que llegan.

### 73. Examine el código de la clase ArrayDequeue.java y explique cómo aplica la aritmética modular.

La clase ArrayDeque<E> utiliza un array circular para gestionar eficientemente las inserciones y eliminaciones en ambos extremos. 
Emplea aritmética modular para calcular las posiciones dentro del array subyacente.

Al insertar un elemento al frente o al final, ArrayDeque usa operaciones con el operador módulo (%) para mantener los índices dentro del rango del array. Por ejemplo:

- elementoFinal = (elementoFinal + 1) % array.length; 
- elementoInicio = (elementoInicio - 1 + array.length) % array.length;
