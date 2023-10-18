# Unnamed Classes and Instance Main Methods (JEP 445)

**_This is a [preview language feature](https://openjdk.org/jeps/12)_, disabled by default**


### Objetivos

- Ofrecer una vía de acceso fluida a Java para que los educadores puedan introducir conceptos de programación de manera gradual.

- Ayudar a los estudiantes a escribir programas básicos de manera concisa. 

- Reducir la ceremonia de escribir programas simples como: scripts y utilidades de línea de comandos. 

- No introducir un dialecto diferente de Java para principiantes.

- No introducir un conjunto de herramientas separadas para principiantes, Los programas de los principiantes deben compilarse y ejectuarse con las mismas herramientas que cualquier otro programa escrito en Java. 

### En que consiste? 

Java pretende ser el primer lenguaje de programación de un desarrollador, cuando un desarrollador se inicia, no escribe programas grandes en equipo, sino que escriben programas pequeños solos. 

#### Main methods 

El usual ejemplo de **Hola, Mundo!**

```java 
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hola, Mundo!"); //Yes - "Hola, Mundo" in spanish. :)
    }
}
```
En el ejemplo anterior para la simplicidad del resultado hay demasiados conceptos envueltos, por ejemplo: 

1. Declaración de la clase y modificador de acceso público. 
2. El parámetro **String[]**, existe para interconectar el código con un componente externo, en este caso la consola del SO. 
3. El modificador **static**, es parte del modelo de clases y objetos de Java. No aporta nada en este contexto, más bien puede confundir al estudiante, principiante, etc.

La motivación de este JEP no es simplemente reducir lo verboso de Java, sino ayudar a los nuevos programadores a aprender Java de una manera que introduzca los conceptos en el orden correcto: fundamentos de programación, conceptos pequeños, luego proceda a la programación avanzada y sus conceptos generales cuando sean realmente beneficiosos y puedan comprenderse más fácilmente.

#### Unnamed Classes 

Básicamente, declara implicitamente la clase dentro del archivo .java 

Cuando un archivo fuente contiene al menos un método declarado fuera de la clase, el compilador colocará dichos métodos dentro de una clase sin nombre. Las clases, interfaces, registros y enumerations que se declaran en el archivo fuente están anidadas dentro de la clase sin nombre.

Dado que la clase no tiene nombre, no se puede crear una instancia de ella mediante programación. La única forma de crear una instancia es iniciarlo mediante un método principal. Es un error en tiempo de compilación si no existe tal método.