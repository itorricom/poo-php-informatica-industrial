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
