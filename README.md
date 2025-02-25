# Abstracción
¿Qué es la abstracción en la programación orientada a objetos?
¡Abstracción! Un término esencial en la programación orientada a objetos que nos facilita pensar y desarrollar software de forma organizada y eficiente. Imagina que estás construyendo un edificio: antes de poner un ladrillo, necesitas un plan sólido. Igual en programación, buscamos entender y diseñar el resultado final antes de embarcarnos en el proceso de codificación. La abstracción consiste en aislar los elementos críticos que requerimos y concentrarse en lo que realmente importa al definir el comportamiento de nuestras clases e interfaces.

¿Cómo aplicar la abstracción con interfaces?
Las interfaces en PHP proporcionan una forma poderosa de definir el contrato de lo que nuestras clases deben implementar. Veamos un ejemplo del proceso paso a paso:

<?php
interface StoreInterface {
    // Declaramos lo que queremos como el resultado final
    public function save();
}

Al crear una interface, declaramos métodos, pero no los implementamos. Esto obliga a las clases que implementen esta interface a definir su comportamiento específico.
Ahora, añadamos una clase que implemente esta interface:

<?php
class Database implements StoreInterface {
    public function save() {
        // Lógica de almacenamiento en base de datos
    }
}

Este es un ejemplo claro de cómo las interfaces ayudan a definir qué métodos son necesarios y dejan que las clases se encarguen de los detalles. Si una clase decide implementar una interface, está obligada a implementar todos sus métodos, tal como un contrato legal. La programación no es diferente: cumple o enfrentas errores.

Qué papel juegan las clases abstractas?
Las clases abstractas son otro componente clave en la abstracción. A diferencia de las interfaces, pueden tener métodos con lógica predefinida. Sin embargo, al igual que con las interfaces, puedes declarar métodos abstractos que las subclases deben implementar.

<?php
// Creamos una clase abstracta
abstract class Base {
    abstract public function store();
    
    public function get() {
        // Código que puede ser reutilizado por las subclases
    }
}

Las clases que hereden de Base deben implementar el método store. Aquí tienes un ejemplo de cómo una subclase se extendería de una abstract class:
<?php 

class SomeStore extends Base {
    public function store() {
        // Implementación específica para el método abstracto
    }
}

Las clases abstractas permiten estructurar la funcionalidad común mientras obligan a las subclases a completar ciertas funcionalidades específicas.

¿Cómo podemos utilizar la abstracción en clases comunes?
Finalmente, la abstracción no se limita a interfaces o clases abstractas. También puedes aplicarla en clases "normales", organizando tu código para encapsular de manera efectiva información y métodos relevantes.

<?php

class Auth {
    private $email;
    private $password;
    
    public function login() {
        // Lógica de autenticación
    }
    
    public function validate() {
        // Métodos de validación
    }
}
Aquí, el concepto de abstracción se manifiesta al definir claramente lo que la clase Auth necesita para funcionar (atributos y métodos necesarios), sin preocuparse inicialmente por los detalles de implementación.

La abstracción en programación orientada a objetos es más que un concepto; es una práctica que promueve el orden y la claridad en el desarrollo de software. ¡Sigue explorando y aplicando estas técnicas, y observa cómo tu código se transforma en una obra maestra organizada! No olvides crear tus propios ejemplos y compartir tus descubrimientos para seguir fomentando el aprendizaje y el intercambio de ideas.


# Alcance o Encapsulamiento
¿Qué es el alcance en programación orientada a objetos?
Entender el alcance en programación es clave para cualquier desarrollador que busque crear aplicaciones robustas y seguras. El alcance define la accesibilidad de propiedades y métodos dentro de una clase, asegurando la integridad de los datos y evitando modificaciones no autorizadas. Este concepto se relaciona estrechamente con el encapsulamiento, también conocido como el principio de ocultación. Veamos cómo se implementa en PHP.

¿Cómo se definen los tipos de alcance?
En PHP, existen tres tipos principales de alcance:

Público: Los elementos definidos como públicos son accesibles desde cualquier punto del código. Esto significa que tanto las clases como otros archivos pueden acceder a estos elementos.

Protegido: Estos elementos solo pueden ser accedidos por la clase que los define y sus subclases. Es una forma efectiva de permitir que las clases derivadas interactúen con ciertos datos sin exponerlos completamente.

Privado: Los elementos privados son accesibles exclusivamente dentro de la clase que los declara. Ni siquiera las subclases pueden acceder a estos métodos o propiedades.

Un ejemplo concreto sería definir diferentes alcances para las propiedades y constantes dentro de una clase de usuario:

class User {
    public const PAGINACION = 25;
    public $username;
    protected $email;
    private $password;
}

¿Cómo se implementa el encapsulamiento?
El encapsulamiento es un pilar de la programación orientada a objetos que busca proteger los datos y funciones de una clase de su modificación externa. Al definir propiedades y métodos con diferentes niveles de acceso, logramos un control preciso sobre cómo y dónde pueden ser utilizados esos elementos. Veamos cómo podríamos utilizar este concepto en una clase:

class User {
    public $username;
    protected $email;
    private $password;

    public function obtenerNombreDeUsuario() {
        // Código para obtener el nombre de usuario
    }
}

¿Por qué es importante la definición del alcance?
Definir correctamente el alcance es crucial por varias razones:

Integridad de los datos: Al restringir el acceso a ciertos datos, podemos evitar modificaciones no autorizadas que podrían llevar a inconsistencias o errores en el sistema.

Seguridad: Elementos como contraseñas deben estar protegidos (o privatizados) para que no puedan ser alterados directamente desde fuera del sistema.

Mantenimiento: Un código con un buen uso del encapsulamiento es más fácil de mantener y entender, ya que limita la complejidad al ocultar detalles innecesarios para otras partes del sistema.
¿Cuándo usar cada tipo de alcance?
El uso de alcances depende de las necesidades específicas del sistema y el diseño del software:

Usa public cuando necesites que una propiedad o método sea accesible desde cualquier parte.
Opta por protected cuando quieras que la funcionalidad sea visible y modificable por clases derivadas, pero no por clases externas.
Elige private cuando el atributo o método no deba ser visto ni alterado más que dentro de su propia clase.

En resumen, comprender el alcance y el encapsulamiento es fundamental para cualquier programador que desee escribir código limpio, eficiente y seguro. Elegir adecuadamente el tipo de acceso correcto puede marcar la diferencia entre una aplicación vulnerable y una aplicación auditada y estable.