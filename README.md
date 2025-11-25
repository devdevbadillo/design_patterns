# Patrones de Diseño de Software

## Tabla de Contenido

- [Introducción a los Patrones de Diseño](#introduccion-patrones-diseno)
  - [¿Qué son los Patrones de Diseño?](#que-son-patrones-diseno)
  - [Historia: El "Gang of Four" (GoF)](#historia-gof)
  - [Beneficios de Usar Patrones de Diseño](#beneficios-patrones-diseno)
  - [¿Cuándo usar patrones de diseño?](#como-cuando-usar-patrones)

- [Principios de Diseño y Buenas Prácticas de Código](#principios-buenas-practicas)
  - [Principios SOLID](#principios-solid)
    - [Single Responsibility Principle (SRP)](#srp)
    - [Open/Closed Principle (OCP)](#ocp)
    - [Liskov Substitution Principle (LSP)](#lsp)
    - [Interface Segregation Principle (ISP)](#isp)
    - [Dependency Inversion Principle (DIP)](#dip)
  - [Acrónimos y Filosofías de Desarrollo](#acronimos-filosofias)
    - [KISS (Keep It Simple, Stupid)](#kiss)
    - [YAGNI (You Aren't Gonna Need It)](#yagni)
    - [DRY (Don't Repeat Yourself)](#dry)
    - [Principio de la Mínima Sorpresa](#minima-sorpresa)
    - [Boy Scout Rule](#boy-scout-rule)
  - [Code Smells (Malos Olores del Código)](#code-smells)
    - [¿Qué son y por qué importan?](#que-son-code-smells)
    - [Clasificación de Code Smells](#clasificacion-code-smells)
      - [Bloaters (Infladores)](#bloaters)
        - [Long Method](#long-method)
        - [Large Class](#large-class)
        - [Primitive Obsession](#primitive-obsession)
        - [Long Parameter List](#long-parameter-list)
        - [Data Clumps](#data-clumps)
      - [Object-Orientation Abusers (Abusadores de OO)](#oo-abusers)
        - [Switch Statements](#switch-statements)
        - [Temporary Field](#temporary-field)
        - [Refused Bequest](#refused-bequest)
        - [Alternative Classes with Different Interfaces](#alternative-classes)
      - [Change Preventers (Preventores de Cambio)](#change-preventers)
        - [Divergent Change](#divergent-change)
        - [Shotgun Surgery](#shotgun-surgery)
        - [Parallel Inheritance Hierarchies](#parallel-inheritance)
      - [Dispensables (Dispensables)](#dispensables)
        - [Lazy Class](#lazy-class)
        - [Duplicated Code](#duplicated-code-smell)
        - [Speculative Generality](#speculative-generality)
        - [Dead Code](#dead-code)
        - [Comments (Excesivos o Mal Usados)](#comments-code-smell)
      - [Couplers (Acopladores)](#couplers)
        - [Feature Envy](#feature-envy)
        - [Inappropriate Intimacy](#inappropriate-intimacy)
        - [Message Chains](#message-chains)
        - [Middle Man](#middle-man)
    - [Herramientas para Detectar Code Smells](#herramientas-code-smells)
  - [Anti-Patrones](#anti-patrones)
    - [¿Qué son y por qué evitarlos?](#que-son-anti-patrones)
    - [Ejemplos Comunes (God Object, Spaghetti Code, Magic Strings)](#ejemplos-anti-patrones)

- [Patrones Creacionales](#patrones-creacionales)
  - [Propósito](#proposito-creacionales)
  - [Singleton](#singleton)
    - [Problema que Resuelve](#problema-singleton)
    - [Implementación (Eager, Lazy, Thread-Safe, Doble Bloqueo)](#implementacion-singleton)
    - [Uso y Anti-Patrones](#uso-anti-patrones-singleton)
  - [Factory Method](#factory-method)
    - [Problema que Resuelve](#problema-factory-method)
    - [Estructura](#estructura-factory-method)
    - [Ejemplo Práctico](#ejemplo-factory-method)
  - [Abstract Factory](#abstract-factory)
    - [Problema que Resuelve](#problema-abstract-factory)
    - [Estructura](#estructura-abstract-factory)
    - [Ejemplo Práctico](#ejemplo-abstract-factory)
    - [Diferencias con Factory Method](#diferencias-factory-method)
  - [Builder](#builder)
    - [Problema que Resuelve](#problema-builder)
    - [Estructura](#estructura-builder)
    - [Ejemplo Práctico](#ejemplo-builder)
  - [Prototype](#prototype)
    - [Problema que Resuelve](#problema-prototype)
    - [Estructura (Clonación Superficial vs. Profunda)](#estructura-prototype)
    - [Ejemplo Práctico](#ejemplo-prototype)

- [Patrones Estructurales](#patrones-estructurales)
  - [Propósito](#proposito-estructurales)
  - [Adapter](#adapter)
    - [Problema que Resuelve](#problema-adapter)
    - [Estructura (Adaptador de Clase vs. Adaptador de Objeto)](#estructura-adapter)
    - [Ejemplo Práctico](#ejemplo-adapter)
  - [Bridge](#bridge)
    - [Problema que Resuelve](#problema-bridge)
    - [Estructura](#estructura-bridge)
    - [Ejemplo Práctico](#ejemplo-bridge)
  - [Composite](#composite)
    - [Problema que Resuelve](#problema-composite)
    - [Estructura](#estructura-composite)
    - [Ejemplo Práctico (Árboles, Menús)](#ejemplo-composite)
  - [Decorator](#decorator)
    - [Problema que Resuelve](#problema-decorator)
    - [Estructura](#estructura-decorator)
    - [Ejemplo Práctico (IO en Java, Cafetería)](#ejemplo-decorator)
    - [Diferencias con Herencia](#diferencias-herencia-decorator)
  - [Facade](#facade)
    - [Problema que Resuelve](#problema-facade)
    - [Estructura](#estructura-facade)
    - [Ejemplo Práctico](#ejemplo-facade)
  - [Flyweight](#flyweight)
    - [Problema que Resuelve](#problema-flyweight)
    - [Estructura (Estado Intrínseco vs. Extrínseco)](#estructura-flyweight)
    - [Ejemplo Práctico (Objetos de Gráficos, Juegos)](#ejemplo-flyweight)
  - [Proxy](#proxy)
    - [Problema que Resuelve](#problema-proxy)
    - [Estructura](#estructura-proxy)
    - [Ejemplo Práctico (Proxy Virtual, Remoto, de Protección)](#ejemplo-proxy)
    - [Diferencias con Adapter y Decorator](#diferencias-proxy)

- [Patrones de Comportamiento](#patrones-comportamiento)
  - [Propósito](#proposito-comportamiento)
  - [Chain of Responsibility](#chain-of-responsibility)
    - [Problema que Resuelve](#problema-chain-of-responsibility)
    - [Estructura](#estructura-chain-of-responsibility)
    - [Ejemplo Práctico (Manejadores de Eventos, Loggers)](#ejemplo-chain-of-responsibility)
  - [Command](#command)
    - [Problema que Resuelve](#problema-command)
    - [Estructura](#estructura-command)
    - [Ejemplo Práctico (Operaciones Deshacer/Rehacer, Colas de Trabajo)](#ejemplo-command)
  - [Iterator](#iterator)
    - [Problema que Resuelve](#problema-iterator)
    - [Estructura](#estructura-iterator)
    - [Ejemplo Práctico](#ejemplo-iterator)
  - [Mediator](#mediator)
    - [Problema que Resuelve](#problema-mediator)
    - [Estructura](#estructura-mediator)
    - [Ejemplo Práctico (Interfaces Gráficas, Controladores de Tráfico)](#ejemplo-mediator)
  - [Memento](#memento)
    - [Problema que Resuelve](#problema-memento)
    - [Estructura](#estructura-memento)
    - [Ejemplo Práctico (Guardar/Cargar Estado de Juego)](#ejemplo-memento)
  - [Observer](#observer)
    - [Problema que Resuelve](#problema-observer)
    - [Estructura (Sujeto y Observador)](#estructura-observer)
    - [Ejemplo Práctico (Eventos UI, Notificaciones)](#ejemplo-observer)
    - [Implementación en Java (`java.util.Observer` vs. `PropertyChangeSupport`)](#implementacion-observer-java)
  - [State](#state)
    - [Problema que Resuelve](#problema-state)
    - [Estructura](#estructura-state)
    - [Ejemplo Práctico (Máquinas de Estado, Comportamiento Contextual)](#ejemplo-state)
  - [Strategy](#strategy)
    - [Problema que Resuelve](#problema-strategy)
    - [Estructura](#estructura-strategy)
    - [Ejemplo Práctico (Algoritmos Intercambiables, Ordenación)](#ejemplo-strategy)
    - [Diferencias con State](#diferencias-strategy-state)
  - [Template Method](#template-method)
    - [Problema que Resuelve](#problema-template-method)
    - [Estructura](#estructura-template-method)
    - [Ejemplo Práctico (Algoritmos de Construcción, Flujos de Trabajo)](#ejemplo-template-method)
  - [Visitor](#visitor)
    - [Problema que Resuelve](#problema-visitor)
    - [Estructura (Visitante y Elemento Visitado)](#estructura-visitor)
    - [Ejemplo Práctico (Operaciones en Estructuras de Objetos)](#ejemplo-visitor)

- [Otros Patrones Importantes y Conceptos](#otros-patrones-importantes)
  - [Inyección de Dependencias (DI) / Inversion of Control (IoC)](#inyeccion-dependencias)
    - [¿Qué son?](#que-son-di-ioc)
    - [Beneficios](#beneficios-di-ioc)
    - [Ejemplo (Spring Framework)](#ejemplo-di-ioc)
  - [MVC (Model-View-Controller)](#mvc-patron)
    - [Concepto y Componentes](#concepto-componentes-mvc)
    - [Variantes (MVP, MVVM)](#variantes-mvc)
  - [DAO (Data Access Object)](#dao)
    - [Propósito](#proposito-dao)
    - [Estructura y Beneficios](#estructura-beneficios-dao)
  - [DTO (Data Transfer Object)](#dto)
    - [Propósito y Uso](#proposito-uso-dto)
  - [Service Layer (Capa de Servicio)](#service-layer)
    - [Propósito y Rol](#proposito-rol-service-layer)
  - [Repository Pattern](#repository-pattern)
    - [Diferencias con DAO](#diferencias-repository-dao)

<a id="introduccion-patrones-diseno"></a>
## Introducción a los Patrones de Diseño

<a id="que-son-patrones-diseno"></a>
### ¿Qué son los Patrones de Diseño?
Los patrones de diseño **son soluciones probadas y reutilizables a problemas comunes** que surgen en el desarrollo de software. Se puede pensar en ellos como `"recetas"` o `"plantillas"` que **describen cómo resolver ciertos problemas** de diseño de manera elegante y eficiente.

> [!NOTE]
> 
> No son código que se pueda copiar y pegar directamente, sino más bien **son conceptos y estructuras que se adaptan a un contexto específico**.

<a id="historia-gof"></a>
### Historia: El "Gang of Four" (GoF)
En 1994, cuatro autores publicaron el libro que cambiaría la industria del software:

- `"Design Patterns: Elements of Reusable Object-Oriented Software"`

Los cuatro autores (Gang of Four):
  * Erich Gamma
  * Richard Helm
  * Ralph Johnson
  * John Vlissides

`Antes del libro`: Los desarrolladores **resolvían los mismos problemas una y otra vez**, cada uno a su manera, **sin un lenguaje común para discutir soluciones**.

`El aporte del GoF`: Identificaron, nombraron y documentaron **23 patrones de diseño** agrupados en tres categorías:
  1. `Creacionales (5)`: Cómo crear objetos
  2. `Estructurales (7)`: Cómo componer objetos y clases
  3. `De comportamiento (11)`: Cómo interactúan objetos y clases

Este libro **estableció un vocabulario universal en el desarrollo de software**. Ahora, cuando alguien dice "usemos un Singleton" o "esto es un Observer", todos los desarrolladores entienden inmediatamente de qué se habla.

<a id="beneficios-patrones-diseno"></a>
### Beneficios de Usar Patrones de Diseño

1. `Soluciones probadas`
- No se reinventa la rueda. **Se usan soluciones que han funcionado en miles de proyectos** durante décadas.

2. `Código más mantenible`
Los patrones promueven:

> - `Bajo acoplamiento`: Los componentes son más independientes
> - `Alta cohesión`: Cada clase tiene una responsabilidad clara
> - `Flexibilidad`: Es más fácil hacer cambios sin romper todo

3. `Mejores diseños`
- Te ayudan a anticipar problemas futuros y **crear arquitecturas escalables desde el principio**.

<a id="como-cuando-usar-patrones"></a>
### ¿Cuándo usar patrones de diseño?

> Cuándo SÍ usar patrones:

1. El problema coincide con el patrón
- La solución del patrón encaja **naturalmente** en el contexto del problema

2. Se anticipan cambios
- Esto es, cuando se sabe que cierta **parte del código cambiará frecuentemente**
- Se necesita flexibilidad para **futuras extensiones**

3. La complejidad lo justifica
- La solución con el patrón es más simple que sin él


> Cuándo NO usar patrones:

1. Sobreingeniería (Overengineering)
- Añadir complejidad innecesaria a problemas simples

2. Forzar un patrón
- Intentar hacer que tu problema encaje en un patrón

3. No entiendes el patrón
- Usarlo porque "es lo que se debe hacer" sin comprender realmente cómo funciona

---

<a id="principios-buenas-practicas"></a>
## Principios de Diseño y Buenas Prácticas de Código

<a id="principios-solid"></a>
### Principios SOLID
SOLID es un acrónimo de **cinco principios de diseño orientado a objetos** creados para *hacer el software más comprensible, flexible y mantenible*.

<a id="srp"></a>
#### Single Responsibility Principle (SRP)
**Cada clase debe tener una única responsabilidad o propósito**. 

> [!IMPORTANT]
> 
> - Si una clase tiene demasiadas responsabilidades, entonces, **cualquier cambio en una de esas responsabilidades puede afectar las demás**.
> 
> - Una clase debe tener solo `un "motivo para ser modificada"`. **Si múltiples stakeholders** (usuario, sistema de reportes, bases de datos, etc...) **necesitan cambiar la misma clase, viola SRP**.

- Ejemplo: Violación de SRP
```java []
class User{

  private String name;
  private String email;

  // Getters & Setters
  // ...

  // Responsabilidad 1: Validación sobre el email
  public Boolean isValidEmail(String email) {
    // Lógica para validar si es un email válido...
  }

  // Responsabilidad 2: Persistencia en base de datos
  public void saveUser(User newUser) {
    // Código para guardar al usuario en la DB...
  }

  // Responsabilidad 3: Envío de emails
  public void sendWelcomeEmail(String addressee) {
    // Código para enviar email...
  }

  // Responsabilidad 4: Generación de reportes
  public Object generateUserReport(Object data) {
    // Código para la generación de algún reporte del usuario (métricas de uso, gatos semanales, etc)...
  }
}

```

- Problemas:

> 1. Si cambia el sistema de base de datos, se modifica la clase User
> 2. Si cambia el servicio de email, se modifica la clase User
> - Esto hace que se viole el principio de SRP


- Ejemplo: Aplicando SRP
```java []
class User{

  private String name;
  private String email;

  // Getters & Setters
  // ...

}


class UtilsValidators{

  public static Boolean isValidEmail(String email) {
    // Lógica para validar si es un email válido...
  }


  // Otros métodos para validaciones ... 

}

class UserRepository{

  public void saveUser(User newUser) {
    // Código para guardar al usuario en la DB...
  }

  // Otros método que permite las operaciones sobre la entidad del Usuario...

}

class EmailService{

  public void sendWelcomeEmail(String addressee) {
    // Código para enviar email...
  }

  // Otros métodos para diferentes emails ... 

}

class UserReportService{

  public Object generateUserReport(Object data) {
    // Código para la generación del reporte para las métricas de uso u otra escenario
  }

  // Otros métodos para diferentes reportes del usuario ... 

}

```

- Beneficios
  
> 1. Cada clase es más fácil de entender
> 2. Los cambios están aislados. Por ejemplo: Sí se cambia el servicio externo para enviar emails, el cambio solo es dentro de su clase.
> 3. Permite el código reutilizable. 

<a id="ocp"></a>
#### Open/Closed Principle (OCP)

El principio de abierto/cerrado fue acuñado por **Bertrand Meyer** en su libro `Object Oriented Software Construction`, quien lo definió de la siguiente manera

- Las entidades de software (**clases, módulos, funciones, etc**) deben de estar **abierta para su extensión, pero cerradas para su modificación**.

 Años despues, Bob Martin amplió la definición de la siguiente manera:

- El comportamiento de **un sistema debería de ser capaz de ser extendido sin necesidad de modificar dicho sistema**.

> [!IMPORTANT]
> El objetivo principal del principio de abierto/cerrado es **diseñar soluciones que tomen en cuenta los cambios que se puedan dar en el futuro** y estructurar las soluciones para que se puedan agregar cambios sin afectar el código existente.

Por ejemplo, un sistema integrado de desarrollo (IDE) permite agregar plugins siempre y cuando cada extensión siga las reglas definidas para su implementación. Es decir, el sistema se encuentra abierto para su extensión mediante plugins pero no para la modificación de las funciones centrales del IDE.


> Escenario

Supongamos que se tiene que realizar el módulo de pasarelas de pagos. Inicialmente el proyecto solo tendrá el acceso de pagos con tarjeta de crédito o de débito. 

Con estos requerimientos, el desarrollador implementa el siguiente código:

```java []
class CardPayment{
  private String holder;
  private String cardNumber;
  private String provider;
  private Double amount;

  // constructors

  // getters && setters
}

class ProccessPayment{
  public static void processPayment(CardPayment card){
    // código para procesar el pago
  }
}
```

Inicialmente el código satisface el requerimiento del sistema, pero, pasan los meses y el negocio crece a tal punto que se necesita ampliar la pasarelas de pagos para ampliar el segmento de mercado. Así nace la nueva necesidad de integrar pagos con Paypal y Apple Pay. 

Con ello se genera un conflicto, pues, el método que contiene la lógica que maneja el procesamiento de pagos está atado a trabajar con tarjetas de crédito o de débito y no con provedores como Paypal y ApplePay. Por lo qué, **se tendría que modificar el core de la funcionalidad** para satisfacer esta necesidad *(se rompe el principio de open/closed)*.

> Siguiendo el principio de Open/Closed

```java []
interface ProccessPayment{
  public void processPayment();
}

class PayPalPayment implements ProccessPayment{
  // Atributos
  
  // constructors

  // getters && setters

  // Implementación de cómo procesar el pago de acuerdo con el provedor de PayPal
}

class CardPayment implements ProccessPayment{
  // Atributos
  
  // constructors

  // getters && setters

  // Implementación de cómo procesar el pago de acuerdo con el tipo de tarjeta (debido, credito) y su provedor (bbva, santander, etc)
}

class ApplePayment implements ProccessPayment{
  // Atributos
  
  // constructors

  // getters && setters

  // Implementación de cómo procesar el pago de acuerdo con el provedor de ApplePay
}
```

De esta manera, el sistema esta abierto a extender nuevos procesos de pagos ya sean con Stripe, OpenPay, etc. Todo esto sin afectar el core de funcionalidades de procesamiento de pagos ya establecidos.

Funciones que usan punteros de referencia a clases base deben de poder usar objetos de clases derivadas sin saberlo.

<a id="lsp"></a>
#### Liskov Substitution Principle (LSP)

Esté principio es el más técnico de todos y hace referencia al correcto uso de la herencia. 

Robert C. Martin `redefinió` el concepto dado por Liskov (es la forma más adoptada por los desarrolladores) de la siguiente manera:

> Funciones que usan punteros de referencia a clases base deben de poder usar objetos de clases derivadas sin saberlo.

En muchas ocasiones los desarrolladores piensan que este principio tiene como objetivo el buscar que una clase hija tenga una relación de *"is a"* o *"es de"* de una clase padre. Por ejemplo no puede haber herencia entre Coche y Motor porque un Motor no es un Coche . Sin embargo sí puede haber relación de herencia entre Rectangulo y Cuadrado ya que un Cuadrado es un rectangulo. Lo cierto es que este no es el objetivo del principio, pues, va más allá en la práctica.

En la práctica, esto significa que cuando se está usando herencia, las clases derivadas `(subtipos)` deben ser capaces de sustituir a sus clases base `(supertipos)` sin que el código cliente (el código que usa la clase base) **sepa que ha ocurrido una sustitución o tenga que manejar un comportamiento inesperado**.

> La clase hija debe cumplir con el contrato de la clase padre. Esto incluye:
>
> 1. No violar precondiciones (requerimientos) en los métodos sobrescritos.
> 
> 2. No debilitar postcondiciones (garantías) en los métodos sobrescritos.
>
> 3. No lanzar excepciones inesperadas.

Supongamos que tenemos una clase base `Rectangulo`.

```java []
class Rectangulo{
  private Double weight;
  private Double height;

  public void setWeight(Double w){
    this.weight = w;
  }

  public void setHeight(Double h){
    this.height = h;
  }

  public Double calcularArea(){
    return weight * height;
  }
}
```

Ahora creamos la clase `Cuadrado` que hereda de `Rectangulo`, porque matemáticamente, **un cuadrado es un rectángulo con lados iguales**.

```java []
class Cuadrado extends Rectangulo {
    public void setWeight(w) {
        this.weight = w;
        this.height = w; // ¡También cambia el alto!
    }

    public void setHeight(h) {
        this.weight = h; // ¡También cambia el ancho!
        this.height = h;
    }
}
```

Para mantener la propiedad de lados iguales en el `Cuadrado`, **necesitamos sobrescribir** (o, en este caso, implementar con lógica especial) **los métodos de su clase base**.

Consideremos una función que trabaja con un Rectangulo:

```java []

public class Test{

  public static void testCalcularArea(Rectangulo r){
      r.setWeight(5);
      r.setHeight(4);
      assert(r.calcularArea() == 20); // True
  }

  public static final void main(final String[] args){
    Rectangulo r = new Rectangulo();
    testCalcularArea(r); // True;

    Cuadrado c = new Cuadrado();
    testCalcularArea(c); // False;

    //   r.setWeight(5); -> c.height = 5, c.weight = 5
    //   r.setWeight(4); -> c.height = 4, c.weight = 4 -> calcularArea() = 16
  }

}
```

El subtipo (`Cuadrado`) alteró el comportamiento esperado (el "contrato") del supertipo (`Rectangulo`), **violando el LSP**.

<a id="isp"></a>
#### Interface Segregation Principle (ISP)

Esté principio **trata sobre la cohesión y el acoplamiento en las interfaces dentro de nuestro sistemaa**. La idea central es sencilla: *"Los clientes no deberían verse obligados a depender de interfaces que no utilizan"*.

En otras palabras, es mejor tener varias interfaces específicas y pequeñas, en lugar de una sola que intente hacer de todo.

Para ilustrar la violación del principio, imaginemos que estamos en el desarrollo de E-commerce y estámos creando una sola interfaz `IOrderProcessor` que se encargue de **todo** tipo de pedidos.

Cómo se ha mencionado, está interface se va a encargar de procesar todo tipo de pedidos. De está manera, salen algunos comportamientos por naturaleza, por ejemplo: Si es un pedido de artículo físico, entonces, se tiene que enviar el pedido por paquetería y si es un pedido de algo digital (Ej. Licencia de Microsoft), entonces, se tiene que generar firmas para integridad del software o licencias para su uso.

Bajo este análisis, entonces, nuestra interface `IOrderProcessor` quedaría plasmada del siguiente modo:

```java []
public interface IOrderProcessor{
    void processPayment();    // Para ambos
    void sendPackage();       // Para físicos
    void generateLicense();   // Para digitales
}
```

Supongamos que se han divido las ventas en diferentes secciones, quizás Zapatos, Electrónicos, Software, etc. De tal manera que cada sección de venta tenga que implementar su forma de procesar sus ordenes.

```java []
public class ShoesSection implements IOrderProcessor{

    public void processPayment(){
        // Lógica real de pago...
    }

    public void sendPackage(){
        // Lógica real de envío...
    }

    // Estamos obligados a tener esto aquí.
    public void generateLicense(){ 
        throw new NotImplementedException("¡Los zapatos no son software!");
    }

}
```

De está manera estamos violando el principio de Segregación de Interfaces, ya que nos vemos obligados a implementar métodos que no se utiliza dentro de ámbitos específicos. El Principio de Segregación de Interfaces nos dice que debemos romper esa interfaz gigante en interfaces más pequeñas y específicas.

> Solución


```java []
public interface IPaymentProcessor {
    void processPayment();
}


public interface IPhysicalOrder {
    void sendPackage();
}

public interface IDigitalOrder {
    void generateLicense(); 
}

public class ShoesSection implements IPhysicalOrder, IPaymentProcessor{

    public void processPayment(){
        // Lógica real de pago...
    }

    public void sendPackage(){
        // Lógica real de envío...
    }
}
```

Al separarlas completamente, logramos que sean **independientes entre sí**. Esto nos da la libertad de *"mezclar y combinar"*. Esto permite tener un software con un bajo acoplamiento y una alta cohesíon.

<a id="dip"></a>
#### Dependency Inversion Principle (DIP)

De los principios SOLID suele ser el que marca la diferencia entre un código rígido y uno flexible y escalable.

La definición formal (propuesta por Robert C. Martin) establece dos reglas:

> 1. Los módulos de alto nivel no deben depender de módulos de bajo nivel. Ambos deben depender de abstracciones.
>
> 2. **Las abstracciones no deben depender de los detalles**. Los detalles (`implementaciones concretas`) deben depender de las abstracciones.

Supongamos que se está construyendo un sistema de notificaciones dentro de un E-commerce. Cuando alguien compra, se le quiere enviar una confirmación.

<a id="acronimos-filosofias"></a>
### Acrónimos y Filosofías de Desarrollo

<a id="kiss"></a>
#### KISS (Keep It Simple, Stupid)

<a id="yagni"></a>
#### YAGNI (You Aren't Gonna Need It)

<a id="dry"></a>
#### DRY (Don't Repeat Yourself)

<a id="minima-sorpresa"></a>
#### Principio de la Mínima Sorpresa

<a id="boy-scout-rule"></a>
#### Boy Scout Rule

<a id="code-smells"></a>
### Code Smells (Malos Olores del Código)

<a id="que-son-code-smells"></a>
#### ¿Qué son y por qué importan?

<a id="clasificacion-code-smells"></a>
#### Clasificación de Code Smells

<a id="bloaters"></a>
##### Bloaters (Infladores)

<a id="long-method"></a>
###### Long Method

<a id="large-class"></a>
###### Large Class

<a id="primitive-obsession"></a>
###### Primitive Obsession

<a id="long-parameter-list"></a>
###### Long Parameter List

<a id="data-clumps"></a>
###### Data Clumps

<a id="oo-abusers"></a>
##### Object-Orientation Abusers (Abusadores de OO)

<a id="switch-statements"></a>
###### Switch Statements

<a id="temporary-field"></a>
###### Temporary Field

<a id="refused-bequest"></a>
###### Refused Bequest

<a id="alternative-classes"></a>
###### Alternative Classes with Different Interfaces

<a id="change-preventers"></a>
##### Change Preventers (Preventores de Cambio)

<a id="divergent-change"></a>
###### Divergent Change

<a id="shotgun-surgery"></a>
###### Shotgun Surgery

<a id="parallel-inheritance"></a>
###### Parallel Inheritance Hierarchies

<a id="dispensables"></a>
##### Dispensables (Dispensables)

<a id="lazy-class"></a>
###### Lazy Class

<a id="duplicated-code-smell"></a>
###### Duplicated Code

<a id="speculative-generality"></a>
###### Speculative Generality

<a id="dead-code"></a>
###### Dead Code

<a id="comments-code-smell"></a>
###### Comments (Excesivos o Mal Usados)

<a id="couplers"></a>
##### Couplers (Acopladores)

<a id="feature-envy"></a>
###### Feature Envy

<a id="inappropriate-intimacy"></a>
###### Inappropriate Intimacy

<a id="message-chains"></a>
###### Message Chains

<a id="middle-man"></a>
###### Middle Man

<a id="herramientas-code-smells"></a>
#### Herramientas para Detectar Code Smells

<a id="anti-patrones"></a>
### Anti-Patrones

<a id="que-son-anti-patrones"></a>
#### ¿Qué son y por qué evitarlos?

<a id="ejemplos-anti-patrones"></a>
#### Ejemplos Comunes (God Object, Spaghetti Code, Magic Strings)

---

<a id="patrones-creacionales"></a>
## Patrones Creacionales

<a id="proposito-creacionales"></a>
### Propósito

<a id="singleton"></a>
### Singleton

<a id="problema-singleton"></a>
#### Problema que Resuelve

<a id="implementacion-singleton"></a>
#### Implementación (Eager, Lazy, Thread-Safe, Doble Bloqueo)

<a id="uso-anti-patrones-singleton"></a>
#### Uso y Anti-Patrones

<a id="factory-method"></a>
### Factory Method

<a id="problema-factory-method"></a>
#### Problema que Resuelve

<a id="estructura-factory-method"></a>
#### Estructura

<a id="ejemplo-factory-method"></a>
#### Ejemplo Práctico

<a id="abstract-factory"></a>
### Abstract Factory

<a id="problema-abstract-factory"></a>
#### Problema que Resuelve

<a id="estructura-abstract-factory"></a>
#### Estructura

<a id="ejemplo-abstract-factory"></a>
#### Ejemplo Práctico

<a id="diferencias-factory-method"></a>
#### Diferencias con Factory Method

<a id="builder"></a>
### Builder

<a id="problema-builder"></a>
#### Problema que Resuelve

<a id="estructura-builder"></a>
#### Estructura

<a id="ejemplo-builder"></a>
#### Ejemplo Práctico

<a id="prototype"></a>
### Prototype

<a id="problema-prototype"></a>
#### Problema que Resuelve

<a id="estructura-prototype"></a>
#### Estructura (Clonación Superficial vs. Profunda)

<a id="ejemplo-prototype"></a>
#### Ejemplo Práctico

---

<a id="patrones-estructurales"></a>
## Patrones Estructurales

<a id="proposito-estructurales"></a>
### Propósito

<a id="adapter"></a>
### Adapter

<a id="problema-adapter"></a>
#### Problema que Resuelve

<a id="estructura-adapter"></a>
#### Estructura (Adaptador de Clase vs. Adaptador de Objeto)

<a id="ejemplo-adapter"></a>
#### Ejemplo Práctico

<a id="bridge"></a>
### Bridge

<a id="problema-bridge"></a>
#### Problema que Resuelve

<a id="estructura-bridge"></a>
#### Estructura

<a id="ejemplo-bridge"></a>
#### Ejemplo Práctico

<a id="composite"></a>
### Composite

<a id="problema-composite"></a>
#### Problema que Resuelve

<a id="estructura-composite"></a>
#### Estructura

<a id="ejemplo-composite"></a>
#### Ejemplo Práctico (Árboles, Menús)

<a id="decorator"></a>
### Decorator

<a id="problema-decorator"></a>
#### Problema que Resuelve

<a id="estructura-decorator"></a>
#### Estructura

<a id="ejemplo-decorator"></a>
#### Ejemplo Práctico (IO en Java, Cafetería)

<a id="diferencias-herencia-decorator"></a>
#### Diferencias con Herencia

<a id="facade"></a>
### Facade

<a id="problema-facade"></a>
#### Problema que Resuelve

<a id="estructura-facade"></a>
#### Estructura

<a id="ejemplo-facade"></a>
#### Ejemplo Práctico

<a id="flyweight"></a>
### Flyweight

<a id="problema-flyweight"></a>
#### Problema que Resuelve

<a id="estructura-flyweight"></a>
#### Estructura (Estado Intrínseco vs. Extrínseco)

<a id="ejemplo-flyweight"></a>
#### Ejemplo Práctico (Objetos de Gráficos, Juegos)

<a id="proxy"></a>
### Proxy

<a id="problema-proxy"></a>
#### Problema que Resuelve

<a id="estructura-proxy"></a>
#### Estructura

<a id="ejemplo-proxy"></a>
#### Ejemplo Práctico (Proxy Virtual, Remoto, de Protección)

<a id="diferencias-proxy"></a>
#### Diferencias con Adapter y Decorator

---

<a id="patrones-comportamiento"></a>
## Patrones de Comportamiento

<a id="proposito-comportamiento"></a>
### Propósito

<a id="chain-of-responsibility"></a>
### Chain of Responsibility

<a id="problema-chain-of-responsibility"></a>
#### Problema que Resuelve

<a id="estructura-chain-of-responsibility"></a>
#### Estructura

<a id="ejemplo-chain-of-responsibility"></a>
#### Ejemplo Práctico (Manejadores de Eventos, Loggers)

<a id="command"></a>
### Command

<a id="problema-command"></a>
#### Problema que Resuelve

<a id="estructura-command"></a>
#### Estructura

<a id="ejemplo-command"></a>
#### Ejemplo Práctico (Operaciones Deshacer/Rehacer, Colas de Trabajo)

<a id="iterator"></a>
### Iterator

<a id="problema-iterator"></a>
#### Problema que Resuelve

<a id="estructura-iterator"></a>
#### Estructura

<a id="ejemplo-iterator"></a>
#### Ejemplo Práctico

<a id="mediator"></a>
### Mediator

<a id="problema-mediator"></a>
#### Problema que Resuelve

<a id="estructura-mediator"></a>
#### Estructura

<a id="ejemplo-mediator"></a>
#### Ejemplo Práctico (Interfaces Gráficas, Controladores de Tráfico)

<a id="memento"></a>
### Memento

<a id="problema-memento"></a>
#### Problema que Resuelve

<a id="estructura-memento"></a>
#### Estructura

<a id="ejemplo-memento"></a>
#### Ejemplo Práctico (Guardar/Cargar Estado de Juego)

<a id="observer"></a>
### Observer

<a id="problema-observer"></a>
#### Problema que Resuelve

<a id="estructura-observer"></a>
#### Estructura (Sujeto y Observador)

<a id="ejemplo-observer"></a>
#### Ejemplo Práctico (Eventos UI, Notificaciones)

<a id="implementacion-observer-java"></a>
#### Implementación en Java (`java.util.Observer` vs. `PropertyChangeSupport`)

<a id="state"></a>
### State

<a id="problema-state"></a>
#### Problema que Resuelve

<a id="estructura-state"></a>
#### Estructura

<a id="ejemplo-state"></a>
#### Ejemplo Práctico (Máquinas de Estado, Comportamiento Contextual)

<a id="strategy"></a>
### Strategy

<a id="problema-strategy"></a>
#### Problema que Resuelve

<a id="estructura-strategy"></a>
#### Estructura

<a id="ejemplo-strategy"></a>
#### Ejemplo Práctico (Algoritmos Intercambiables, Ordenación)

<a id="diferencias-strategy-state"></a>
#### Diferencias con State

<a id="template-method"></a>
### Template Method

<a id="problema-template-method"></a>
#### Problema que Resuelve

<a id="estructura-template-method"></a>
#### Estructura

<a id="ejemplo-template-method"></a>
#### Ejemplo Práctico (Algoritmos de Construcción, Flujos de Trabajo)

<a id="visitor"></a>
### Visitor

<a id="problema-visitor"></a>
#### Problema que Resuelve

<a id="estructura-visitor"></a>
#### Estructura (Visitante y Elemento Visitado)

<a id="ejemplo-visitor"></a>
#### Ejemplo Práctico (Operaciones en Estructuras de Objetos)

---

<a id="otros-patrones-importantes"></a>
## Otros Patrones Importantes y Conceptos

<a id="inyeccion-dependencias"></a>
### Inyección de Dependencias (DI) / Inversion of Control (IoC)

<a id="que-son-di-ioc"></a>
#### ¿Qué son?

<a id="beneficios-di-ioc"></a>
#### Beneficios

<a id="ejemplo-di-ioc"></a>
#### Ejemplo (Spring Framework)

<a id="mvc-patron"></a>
### MVC (Model-View-Controller)

<a id="concepto-componentes-mvc"></a>
#### Concepto y Componentes

<a id="variantes-mvc"></a>
#### Variantes (MVP, MVVM)

<a id="dao"></a>
### DAO (Data Access Object)

<a id="proposito-dao"></a>
#### Propósito

<a id="estructura-beneficios-dao"></a>
#### Estructura y Beneficios

<a id="dto"></a>
### DTO (Data Transfer Object)

<a id="proposito-uso-dto"></a>
#### Propósito y Uso

<a id="service-layer"></a>
### Service Layer (Capa de Servicio)

<a id="proposito-rol-service-layer"></a>
#### Propósito y Rol

<a id="repository-pattern"></a>
### Repository Pattern

<a id="diferencias-repository-dao"></a>
#### Diferencias con DAO
