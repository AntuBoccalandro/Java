# **Fundamentos de Java**

## **Funcionamiento de Java**

## **Estructura de un programa**

```java
public class NombreDeLaClase {
    // Variables de instancia o miembros de la clase
    // Constructor(es) de la clase

    // Métodos de la clase
    public static void main(String[] args) {
        // Código ejecutable del programa
    }
}
```

## **Comentarios**

**Comentarios de una sola línea:**
```java
// Comentario de una sola línea
```

**Comentarios de varias líneas:**
```java
/*
Comentario
De varias
Líneas
*/
```

**JavaDoc:**
```java
/**
 * JavaDoc comments look like this. Used to describe the Class or various
 * attributes of a Class.
 * Main attributes:
 *
 * @author         Name (and contact information such as email) of author(s).
 * @version     Current version of the program.
 * @since        When this part of the program was first added.
 * @param         For describing the different parameters for a method.
 * @return        For describing what the method returns.
 * @deprecated  For showing the code is outdated or shouldn't be used.
 * @see         Links to another part of documentation.
*/
```

## **Output**

```java
// Use System.out.println() to print lines.
System.out.println("Hello World!");
System.out.println(
	"Integer: " + 10 +
    " Double: " + 3.14 +
    " Boolean: " + true);

// To print without a newline, use System.out.print().
System.out.print("Hello ");
System.out.print("World");

// Use System.out.printf() for easy formatted printing.
System.out.printf("pi = %.5f", Math.PI); // => pi = 3.14159
```

## **Input**

```java
// use Scanner to read input
// must import java.util.Scanner;
Scanner scanner = new Scanner(System.in);

// read string input
String name = scanner.next();

// read byte input
byte numByte = scanner.nextByte();

// read int input
int numInt = scanner.nextInt();

// read long input
float numFloat = scanner.nextFloat();

// read double input
double numDouble = scanner.nextDouble();

// read boolean input
boolean bool = scanner.nextBoolean();
```

## **Variables**

**Declaración**:
```java
// Declare a variable using <type> <name>
int fooInt;

// Declare multiple variables of the same
// type <type> <name1>, <name2>, <name3>
int fooInt1, fooInt2, fooInt3;
```

**Inicialización**:
```java
// Initialize a variable using <type> <name> = <val>
int barInt = 1;
// Initialize multiple variables of same type with same
// value <type> <name1>, <name2>, <name3>
// <name1> = <name2> = <name3> = <val>
int barInt1, barInt2, barInt3;
barInt1 = barInt2 = barInt3 = 1;
```

## **Constantes**

```java
// final variables can't be reassigned
final double E = 2.71828;
```

## Scope de las variables y constantes

El scope de una variable es definido por el bloque de código en el que está contenida, ejemplos, métodos, condicionales o bucles. La variable se limitará al bloque de código en el que fue definida.
   
```java
public class Ejemplo {
    int variableDeInstancia = 100; // Variable de instancia

    public void metodo() {
        int variableLocal = 200; // Variable local al método
        System.out.println("El valor de variableDeInstancia es: " + variableDeInstancia);
        System.out.println("El valor de variableLocal es: " + variableLocal);
    }

    public static void main(String[] args) {
        Ejemplo e = new Ejemplo();
        e.metodo();
    }
}
```

**Tipos de memoria:**
Cuando se crea una variable local esta se almacena en la memoria STACK mientras que cuando creamos variables que hagan referencia a un objeto esta se almacenará en la memoria HEAP.

![](https://drive.google.com/file/d/1C3hEM9EWdIjxZ8DW9K-zRbbJ76vipC-6/view?usp=sharing)

La memoria STACK se almacenan las variables y se van eliminando de la memoria en la ejecución, en cambio las variables que se almacenan en la memoria HEAP permancerán en la memoria en toda la ejecución del programa.

La función `System.gc()` permite ejecutar el recolector de basura, aunque estas funciones no son de lo más recomendable para ejecutar en el programa. 


## **Tipos de datos**

```java
// var's type detect the datatype
var fooVar = "Hello World";


// Byte - 8-bit signed two's complement integer
// (-128 <= byte <= 127)
byte fooByte = 100;


// Short - 16-bit signed two's complement integer
// (-32,768 <= short <= 32,767)
short fooShort = 10000;


// Integer - 32-bit signed two's complement integer
// (-2,147,483,648 <= int <= 2,147,483,647)
int bazInt = 1;


// Long - 64-bit signed two's complement integer
// (-9,223,372,036,854,775,808 <= long <= 9,223,372,036,854,775,807)
long fooLong = 100000L;


// Float - Single-precision 32-bit IEEE 754 Floating Point
// 2^-149 <= float <= (2-2^-23) * 2^127
float fooFloat = 234.5F;


// Double - Double-precision 64-bit IEEE 754 Floating Point
// 2^-1074 <= x <= (2-2^-52) * 2^1023
double fooDouble = 123.4D;


// Boolean - true & false
boolean fooBoolean = true;


// Char - A single 16-bit Unicode character
char fooChar = 'A';


// BigInteger - Arbitrary Precision Immutable Integers BigInteger is a data type that allows programmers to manipulate integers larger than 64 bits. Integers are stored as an array of bytes and manipulated using BigInteger built-in functions BigInteger can be initialized using an array of bytes or a string.
BigInteger fooBigInteger = new BigInteger(fooByteArray);


// It is equal to BigInteger with one exception, it is for a number with Decimal sign.
BigDecimal fooBigDecimal = new BigDecimal(fooBigInteger, fooInt);
BigDecimal tenCents = new BigDecimal("0.1");

// Strings
String fooString = "My String Is Here!";

// Arrays
// The array size must be decided upon instantiation
// The following formats work for declaring an array
// Define Array
String names;
// Inicialize Array
String[] names = new String[10];
// Asigned Array
names[9] = "Java"

// <datatype>[] <var name> = new <datatype>[<array size>];
// <datatype> <var name>[] = new <datatype>[<array size>];
String[] stringArray = new String[10];
boolean boolArray[] = new boolean[10];

// Declare and initialize an array
int[] y = {9000, 1000, 1337};
String names[] = {"Bob", "John", "Fred", "Juan Pedro"};
boolean bools[] = {true, false, false};

// Work with arrays
String names[] = {"Bob", "John", "Fred", "Juan Pedro"};
System.out.println(names[0]); // Bob
names[0] = "Java";
System.out.println(names[0]); // Java

// Arrays Methods


// ArrayLists
// You need import ArrayList java.util.ArrayList;
ArrayList<String> miArrayList = new ArrayList<String>();
// Other form of define ArrayList with diamont reference
ArrayList<String> miArrayList = new ArrayList<>();
// Define and asigned value to ArrayListin one line
ArrayList<String> nombres = new ArrayList<>(List.of("Juan", "Pedro", "María"));

// Matrix
// Define a matrix with 3 rows and 4 columns
int[][] matrix = new int[3][4];
// Define and asigned value to Matrix one line
int[][] matrix = {{1, 2, 3, 4}, {5, 6, 7, 8}, {9, 10, 11, 12}};


// Null
// La palabra null en Java la utilizamos con el objetivo de indicar que aún no se le ha asignado ninguna referencia de ningún objeto a una variable de tipo Object.
// No es posible asignar el valor null a una variable de tipo primitivo
int number;
MyClass object;
System.out.println(number); // 0
System.out.println(object); // null
```

## **Default values**
A veces queremos crear variables pero no asignarles ningún valor.
* Las variables de tipos primitivos contienen un valor por defecto de 0 (para los numéricos) o algunas secuencias de caracteres para los tipos como Char. En el caso de los Strings se inicializan con un valor de null porque no pertenecen a los datos primitivos.
* Las variables que guardan referencias de objetos se inicializan con un valor null.

**NOTA ACLARATORIA:** el tipo de dato null no es posible asignarlo a una variable de tipo primitivo, solo a de tipo Object.

## **Formateo de strings**

```java
//Type 1
String nombre = "Juan";
int edad = 25;
String mensaje = "Hola, mi nombre es " + nombre + " y tengo " + edad + " años.";


//Type 2
String nombre = "Juan";
int edad = 25;
String mensaje = String.format("Hola, mi nombre es %s y tengo %d años.", nombre, edad);


//Type 3
String nombre = "Juan";
int edad = 25;
String mensaje = new Formatter().format("Hola, mi nombre es %s y tengo %d años.", nombre, edad).toString();


//Type 4
String nombre = "Juan";
int edad = 25;
StringBuilder sb = new StringBuilder();
sb.append("Hola, mi nombre es ").append(nombre).append(" y tengo ").append(edad).append(" años.");
String mensaje = sb.toString();
```

## **Operadores**
### **Artiméticos**

Para los ejemplos utilizaremos estas dos variables:
```java
int i1 = 1
int i2 = 2;
```

```java
// Arithmetic is straightforward
System.out.println("1+2 = " + (i1 + i2)); // => 3
System.out.println("2-1 = " + (i2 - i1)); // => 1
System.out.println("2*1 = " + (i2 * i1)); // => 2
System.out.println("1/2 = " + (i1 / i2)); // => 0 (int/int returns int)
System.out.println("1/2.0 = " + (i1 / (double)i2)); // => 0.5
System.out.println("11%3 = "+(11 % 3)); // => 2
```

### **Lógicos**

```java
// Comparison operators
System.out.println("3 == 2? " + (3 == 2)); // => false
System.out.println("3 != 2? " + (3 != 2)); // => true
System.out.println("3 > 2? " + (3 > 2)); // => true
System.out.println("3 < 2? " + (3 < 2)); // => false
System.out.println("2 <= 2? " + (2 <= 2)); // => true
System.out.println("2 >= 2? " + (2 >= 2)); // => true

// Boolean operators
System.out.println("3 > 2 && 2 > 3? " + ((3 > 2) && (2 > 3))); // => false
System.out.println("3 > 2 || 2 > 3? " + ((3 > 2) || (2 > 3))); // => true
System.out.println("!(3 == 2)? " + (!(3 == 2))); // => true
```

### **Incrementales/Decrementales**

```java
// Increment operators
int i = 0;
System.out.println("\n->Inc/Dec-rementation");
// The ++ and -- operators increment and decrement by 1 respectively.
// If they are placed before the variable, they increment then return;
// after the variable they return then increment.
System.out.println(i++); // i = 1, prints 0 (post-increment)
System.out.println(++i); // i = 2, prints 2 (pre-increment)
System.out.println(i--); // i = 1, prints 2 (post-decrement)
System.out.println(--i); // i = 0, prints 0 (pre-decrement)
```

### **Bitwise**

```java
// Bitwise operators!
/*
~      Unary bitwise complement
<<     Signed left shift
>>     Signed/Arithmetic right shift
>>>    Unsigned/Logical right shift
&      Bitwise AND
^      Bitwise exclusive OR
|      Bitwise inclusive OR
*/
```

## **Condicionales**


```java
// If-else-else if statements
int j = 10;
if (j == 10) {
       System.out.println("I get printed");
} else if (j > 10) {
       System.out.println("I don't");
} else {
       System.out.println("I also don't");
}


// Switch Case
int month = 3;
String monthString;
switch (month) {
   	case 1: monthString = "January";
    	break;
    case 2: monthString = "February";
    	break;
    case 3: monthString = "March";
    	break;
    default: monthString = "Some other month";
    	break;
}
System.out.println("Switch Case Result: " + monthString);


// Switch case abbreviated
int month = 3;
String monthString;
monthString = switch (month) {
       case 1 -> "January";
       case 2 -> "February";
       case 3 -> "March";
       default -> "Some other month";
};
System.out.println("Switch Case Result: " + monthString);


// Ternary operator
// (condition) ? (value if true) : (value if false)
int x = 10;
int y = 20;
String result = (x > y) ? "x is greater than y" : "y is greater than or equal to x";
System.out.println(result);
```

## **Ciclos**
```java
// While loop
int fooWhile = 0;
while(fooWhile < 100) {
	System.out.println(fooWhile);
	// Increment the counter
	// Iterated 100 times, fooWhile 0,1,2...99
	fooWhile++;
}
System.out.println("fooWhile Value: " + fooWhile);


// Do While Loop
int fooDoWhile = 0;
do {
	System.out.println(fooDoWhile);
	// Increment the counter
	// Iterated 100 times, fooDoWhile 0->99
	fooDoWhile++;
} while(fooDoWhile < 100);
System.out.println("fooDoWhile Value: " + fooDoWhile);


// For Loop
for (int fooFor = 0; fooFor < 10; fooFor++) {
	System.out.println(fooFor);
	// Iterated 10 times, fooFor 0->9
}
System.out.println("fooFor Value: " + fooFor);


// For Each Loop
int[] fooList = {1, 2, 3, 4, 5, 6, 7, 8, 9};
for (int bar : fooList) {
	System.out.println(bar);
	//Iterates 9 times and prints 1-9 on new lines
}
```

## **Funciones**

```java
// 
public class Example {
    public static void main(String[] args) {
        int a = 2, b = 3;
        // Call to own function
        int resultado = sumar(a, b);
        System.out.println("La suma de " + a + " y " + b + " es " + resultado);
    }

    // Own
    public static int sumar(int x, int y) {
        int suma = x + y;
        return suma;
    }
}
```

## **Manejo excepciones**

```java
/* 
Sintaxis:
try {
    // código que puede lanzar una excepción
} catch (TipoDeExcepción1 e1) {
    // código para manejar la excepción de TipoDeExcepción1
} catch (TipoDeExcepción2 e2) {
    // código para manejar la excepción de TipoDeExcepción2
} finally {
    // código que se ejecuta siempre, independientemente de si hay una excepción o no
}
*/

try {
    int[] arr = {1, 2, 3};
    System.out.println(arr[3]);
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("El índice está fuera de rango.");
} finally {
    System.out.println("Este mensaje siempre se imprimirá.");
}
```

## **Manejo de archivos con Java**
```java
import java.io.File;
import java.io.FileWriter;
import java.io.FileReader;
import java.io.IOException;


public class HolaMundo {
    public static void main(String args[]) throws IOException{
        System.out.println(ReadWrite("ruta/del/archivo.txt"));
        WriteFile("ruta/del/archivo.txt", "Esta es una línea de texto");
    }
    
    public static void WriteFile(String ruta, String texto) throws IOException {
        File file = new File(ruta);
        FileWriter writter = null;
        try {
            writter = new FileWriter(file);
            writter.write(texto);
        } finally {
            if (writter != null) {
                writter.close();
            }
        }
    }
    
    public static String ReadWrite(String ruta) throws IOException {
    FileReader lector = null;
    StringBuilder contenido = new StringBuilder();
    try {
        File archivo = new File(ruta);
        lector = new FileReader(archivo);
        int c = lector.read();
        while (c != -1) {
            contenido.append((char) c);
            c = lector.read();
        }
    } finally {
        if (lector != null) {
            lector.close();
        }
    }
    return contenido.toString();
}
}
```

## **Programación Orientada a Objetos**

### **Keywords importantes**
* **static:** La keyword static se utiliza para declarar miembros de una clase que pertenecen a la propia clase.
* **public:** La keyword public significa que el miembro es accesible desde cualquier otra clase o paquete.
* **private:** La keyword private significa que el miembro solo es accesible dentro de la misma clase.
* **protected:** La keyword protected significa que el miembro es accesible dentro de la misma clase y también por las subclases que se encuentren en el mismo paquete o en paquetes diferentes.

### **La keyword `this`**

* En Java, la keyword this se refiere a la instancia actual de la clase en la que se está utilizando. Se utiliza para hacer referencia a los miembros de la clase (variables y métodos) desde dentro de la propia clase, y para evitar ambigüedades entre los nombres de las variables locales y los miembros de la clase.
* Es una referencia implícita al objeto que se está ejecutando.
* Permite a un objeto enviarse él mismo como parámetro.

**Ejemplo de objeto enviándose a él mismo como argumento de un método:**
```java
public class Persona {
   private String nombre;

   // Constructor y otros métodos de la clase Persona

   public void imprimirNombre() {
      System.out.println("Nombre: " + this.nombre);
      imprimirPersona(this); // Se envía la instancia actual como argumento al método imprimirPersona
   }

   public void imprimirPersona(Persona p) {
      System.out.println("Nombre: " + p.nombre);
   }
}
```


### **Clases**
```java
// Class Declaration Syntax:
// <public/private/protected> class <class name> {
//    // data fields, constructors, functions all inside.
//    // functions are called as methods in Java.
// }

class Bicycle {
    // Attibutes, methods and constructors
} 
```

### **Atributos**
```java
// Bicycle's Fields/Variables
public int cadence; // Public: Can be accessed from anywhere
private int speed;  // Private: Only accessible from within the class
protected int gear; // Protected: Accessible from the class and subclasses
String name; // default: Only accessible from within this package
static String className; // Static class variable

// Static block
// Java has no implementation of static constructors, but
// has a static block that can be used to initialize class variables
// (static variables).
// This block will be called when the class is loaded.
static {
    className = "Bicycle";
}
```


### **Métodos**
```java
// Method Syntax:
// <public/private/protected> <return type> <function name>(<args>)

// Method declaration syntax:
// <access modifier> <return type> <method name>(<args>)
public int getCadence() {
    return cadence;
}

// void methods require no return statement
public void setCadence(int newValue) {
    cadence = newValue;
}
public void setGear(int newValue) {
    gear = newValue;
}
public void speedUp(int increment) {
    speed += increment;
}
public void slowDown(int decrement) {
    speed -= decrement;
}
public void setName(String newName) {
    name = newName;
}
public String getName() {
    return name;
}


// Sobreescritura de métodos heredados de otra clase.
@Override
public String toString() {
    return "gear: " + gear + " cadence: " + cadence + " speed: " + speed +
    " name: " + name;
}
```

### **Decorador Override**
En Java, la anotación`@Override` se utiliza para indicar que un método en una clase está sobrescribiendo un método de la clase padre

```java
// Java Example:
class Animal {
    void hacerSonido() {
        System.out.println("El animal hace un sonido");
    }
}

class Perro extends Animal {
    @Override
    void hacerSonido() {
        System.out.println("El perro ladra");
    }
}

class Gato extends Animal {
    @Override
    void hacerSonido() {
        System.out.println("El gato maulla");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal animal = new Animal();
        animal.hacerSonido(); // Output: "El animal hace un sonido"

        Perro perro = new Perro();
        perro.hacerSonido(); // Output: "El perro ladra"

        Gato gato = new Gato();
        gato.hacerSonido(); // Output: "El gato maulla"
    }
}
```

### **Sobrecarga de constructores**
```java
//Sobrecarga de métodos. Los tipos de datos o la cantidad de argumentos son los que definen el método que se llamará, a pesar de tener todos el mismo nombre.
public class Calculadora {

    // Método sumar para dos números enteros
    public int sumar(int a, int b) {
        return a + b;
    }
    
    // Método sumar para dos números decimales
    public double sumar(double a, double b) {
        return a + b;
    }
    
    // Método sumar para tres números enteros
    public int sumar(int a, int b, int c) {
        return a + b + c;
    }
    
    // Método sumar para dos Strings
    public String sumar(String a, String b) {
        return a + b;
    }
    
}
```

### **Constructores**
```java
// Constructors are a way of creating classes
// This is an empty constructor
public Bicycle() {
    // You can also call another constructor:
    // this(1, 50, 5, "Bontrager");
    gear = 1;
    cadence = 50;
    speed = 5;
    name = "Bontrager";
}
// This is a constructor that takes arguments
public Bicycle(int startCadence, int startSpeed, int startGear, String name) {
    this.gear = startGear;
    this.cadence = startCadence;
    this.speed = startSpeed;
    this.name = name;
}
```

#### **Sobrecarga de constructores**
```java
public class Persona{
    protected String nombre;
    protected char genero;
    protected int edad;
    protected String direccion;
    
    // Constructor vacío
    public Persona(){
        
    }
    
    // Constructor con un parámetro
    public Persona(String nombre){
        this.nombre = nombre;
    }

    // Constructor con varios parámetros
    public Persona(String nombre, char genero, int edad, String direccion) {
        this.nombre = nombre;
        this.genero = genero;
        this.edad = edad;
        this.direccion = direccion;
    }

    // Métodos getters y setters
    public String getDireccion() {
        return this.direccion;
    }

    public void setDireccion(String direccion) {
        this.direccion = direccion;
    }

    public String getNombre() {
        return this.nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public char getGenero() {
        return this.genero;
    }

    public void setGenero(char genero) {
        this.genero = genero;
    }

    public int getEdad() {
        return this.edad;
    }

    public void setEdad(int edad) {
        this.edad = edad;
    }

    // Método para mostrar los atributos de la clase.
    @Override
    public String toString() {
        StringBuilder sb = new StringBuilder();
        sb.append("Persona{nombre=").append(nombre);
        sb.append(", genero=").append(genero);
        sb.append(", edad=").append(edad);
        sb.append(", direccion=").append(direccion);
        sb.append(", ").append(super.toString());
        sb.append('}');
        return sb.toString();
    }


public class Empleado extends Persona {

    private int idEmpleado;
    private double sueldo;
    private static int contadorEmpleado;

    public Empleado() {
        //super();
        this.idEmpleado = ++Empleado.contadorEmpleado;
    }
    
    public Empleado(String nombre, double sueldo) {
        this(); // this() llama al constructor de la clase padre.
        this.nombre = nombre;
        this.sueldo = sueldo;
    }

    public int getIdEmpleado() {
        return this.idEmpleado;
    }

    public double getSueldo() {
        return sueldo;
    }

    public void setSueldo(double sueldo) {
        this.sueldo = sueldo;
    }

    @Override
    public String toString() {
        StringBuilder sb = new StringBuilder();
        sb.append("Empleado{idEmpleado=").append(this.idEmpleado);
        sb.append(", sueldo=").append(this.sueldo);
        sb.append(", ").append(super.toString());
        sb.append('}');
        return sb.toString();
    }

}
```

### **Objetos**
```java
// Create an object of a class
// Sintaxis:
// <className> <objectName> = new <constructorName>()
Bicycle object = new Bicycle()
```

### **Encapsulación**

#### **Métodos accesores:**
**Getters**
```java
public String getNombre(){
    return this.nombreDelCampo;
}
```

**Setters**
```java
public void clearNombreDelCampo(newValue) {
    this.nombreDelCampo = newValue;
}
```

**Deletters**
```java
public void clearNombreDelCampo() {
    this.nombreDelCampo = null;
}
```

**Ejemplo de encapsulación**
```java
public class Persona {
    // Variables privadas de clase.
    private String nombre;
    private double sueldo;
    private boolean eliminado;
    
    // Constructor
    public Persona(String nombre, double sueldo, boolean eliminado){
        this.nombre = nombre;
        this.sueldo = sueldo;
        this.eliminado = eliminado;
    }
    
    // Método getter
    public String getNombre(){
        return this.nombre;
    }
    
    // Método setter
    public void setNombre(String nombre){
        this.nombre = nombre;
    }
    
    // Método getter
    public double getSueldo(){
        return this.sueldo; 
    }
    
    // Método setter
    public void setSueldo(double sueldo){
        this.sueldo = sueldo;
    }
    
    // Método getter. En el caso de los métodos getter para los tipos booleanos, por convenición, se empieza el método get con la palabra "is". Esto es así porque es como si hicieramos una pregunta, es más entendible que colocar "get" al inicio del método get.
    public boolean isEliminado(){
        return this.eliminado;
    }
    
    // Método setter
    public void setEliminado(boolean eliminado){
        this.eliminado = eliminado;
    }
    
}
```

### **Herencia Simple**

```java
// Creamos la clase Padre
public class Calculadora {
    int a;
    int b;

    // Constructor
    public Calculadora(int a, int b){
        this.a = a;
        this.b = b;
    }

    // Métodos de la clase
    public int sumar() {
        return this.a + this.b;
    }

    public int restar() {
        return this.a - this.b;
    }

    public int multiplicar() {
        return this.a * this.b;
    }

    public int dividir() {
        return this.a / this.b;
    }
}

// Creamos la clase que herede o extienda de la clase Padre
public class CalculadoraAvanzada extends Calculadora {
    int c;

    // Constructor
    public CalculadoraAvanzada(int a, int b, int c){
        // Llamamos al constructor de la clase que heredamos
        super(a, b);
        this.c = c
    }

    public double elevar() {
        return Math.pow(this.a, this.b);
    }

    public int sumaTriple() {
        return this.a + this.b + this.c;
    }
}


public class Test{
    public static void main(String[] args){
        // Operaciones con la clase Padre
        Calculadora operacionBasica = new Calculadora(90, 100);
        System.out.println(operacionBasica.sumar()); // 110

        // Operaciones con la clase Hija
        CalculadoraAvanzada operacionAvanzada = new CalculadoraAvanzada(80, 90, 100);
        System.out.println(operacionAvanzada.sumaTriple()); // 270
    }
}
```

### **Herencia Múltiple**

```java

```

### **Polimorfismo**

```java

```

### **Abstracción**

### **Contexto Estático**

Podemos utilizar la palabra static para interactuar con el contexto estático. Por ejemplo, si definimos un atributo o un método como estático, lo que estamos indicamos es que el atributo o método pertenecen a la clase y no al objeto. Por lo tanto, los atributos o métodos marcados con la palabra static se les conoce como miembros de clase o métodos de clase, ya que pertenecen a la clase y no a los objetos que se crean de dicha clase.

**Ejemplo 1:**
```java
// Queremos un programa que cuente la cantidad de objetos creados de una clase. Para ello crearemos una variable estática de la clase. Crearemos un constructor en el que cada vez que se lo ejecute se incrementará en 1 el contador de personas. Para acceder al contador de personas definiremos un método getter. 
public class EjemploStatic {

    public static void main(String[] args){
        Persona p1 = new Persona("Juan");

    }
}

class Persona {

    private String nombre;
    private int idPersona;
    private static int contadorPersonas;

    public Persona(String nombre) {
        contadorPersonas++;
        idPersona = contadorPersonas;
        this.nombre = nombre
    }

    public static int getContadorPersonas() {
        return contadorPersonas;
    }
}
```

**Ejemplo 2:**
```java
// Este es un ejemplo de contexto estático en Java, donde una función estática se asocia con una clase y se puede llamar directamente en la clase sin necesidad de crear una instancia de la clase.
public class EjemploStatic {

    public static void main(String[] args){
        // No creamos una instancia de la clase, directamente llamamos al método estático de la clase.
        int resultado = MathHelper.suma(4, 5);
    }
}

public class MathHelper {
   public static int suma(int num1, int num2) {
      return num1 + num2;
   }
}
```

## **Diseño de clases**
El diseño de clases en Java es fundamental y permite la creación


#### **Keyword final**

Esta keyword realiza diferentes acciones para cada caso:
* **En variables:** evita  cambiar el valor que almacena la variable.
* **En métodos:** evita que se modifique la definición de un métoo desde una subclase.
* **En clases:** evita que se cree una subclase.

## **Paquetes**

Los paquetes son una forma de organizar la aplicación de Java.
```java
// Definir un paquete
package nombrePaquete
```

**Nombres de los paquetes:**
* Convención de nomenclatura en minúsculas: Los nombres de los paquetes en Java deben estar en minúsculas.
* Uso de nombres descriptivos: Los nombres de los paquetes deben ser descriptivos y representar claramente el contenido del paquete.
* Uso de nombres de dominio inverso: Es común utilizar nombres de dominio inverso como parte del nombre del paquete en Java.
* Evitar nombres demasiado largos: Aunque se debe usar un nombre descriptivo, también se debe evitar que los nombres de los paquetes sean demasiado largos. Los nombres de paquetes largos pueden volverse incómodos de escribir y leer en el código. Se recomienda mantener los nombres de los paquetes lo más cortos y significativos posible.
* Evitar caracteres especiales: Los nombres de paquetes en Java deben evitar el uso de caracteres especiales, espacios o caracteres no alfabéticos. Además, es importante evitar palabras clave de Java como nombres de paquetes.


### **Importación de paquetes**
Permite traerse clases y métodos de otro paquete.
```java
import com.paquete1.Utileria;   // Importa del paquete "com.paquete1" la clase "Utileria"

import com.paquete1.*;  // importa todo el contenido del paquete "com.paquete1"

import static com.paquete1.Utileria.Imprimir;   // Importamos el método estático del paquete. Esta práctica solo se hace para métodos estáticos
```

## **Argumentos Variables**

Los argumentos variables se guardan como un array.
```java
public class Ejemplo {
    public static void main(String[] args){
        imprimirNumeros(1, 2, 3, 4, 5, 6, 7, 8, 9, 10); // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    }

    // <datatype>...<name>
    public static void imprimirNumeros(int... numeros) {
        System.out.println(numeros);
    }
}
```

