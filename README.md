# Patrones de Diseño de Software

## Tabla de Contenido

- [Introducción a los Patrones de Diseño](#introduccion-patrones-diseno)
  - [¿Qué son los Patrones de Diseño?](#que-son-patrones-diseno)
  - [Historia: El "Gang of Four" (GoF)](#historia-gof)
  - [Beneficios de Usar Patrones de Diseño](#beneficios-patrones-diseno)
  - [Cómo y Cuándo Usar Patrones](#como-cuando-usar-patrones)

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

<a id="historia-gof"></a>
### Historia: El "Gang of Four" (GoF)

<a id="beneficios-patrones-diseno"></a>
### Beneficios de Usar Patrones de Diseño

<a id="como-cuando-usar-patrones"></a>
### Cómo y Cuándo Usar Patrones

---

<a id="principios-buenas-practicas"></a>
## Principios de Diseño y Buenas Prácticas de Código

<a id="principios-solid"></a>
### Principios SOLID

<a id="srp"></a>
#### Single Responsibility Principle (SRP)

<a id="ocp"></a>
#### Open/Closed Principle (OCP)

<a id="lsp"></a>
#### Liskov Substitution Principle (LSP)

<a id="isp"></a>
#### Interface Segregation Principle (ISP)

<a id="dip"></a>
#### Dependency Inversion Principle (DIP)

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
