# Teórica 7 (SIN) - 11/2/2026

## **Tema: Metodologías de Desarrollo de Sistemas**
### Recordemos
#### Metodologías de desarrollo se definen como:
Métodos que indican cómo hacer más eficiente el desarrollo de sistemas de información. Para ello suelen estructurar en fases la vida de dichos
sistemas con el fin de facilitar su planificación, desarrollo y mantenimiento.

Las cuales deben definir: Objetivos, fases, tareas, productos y responsables.

#### Objetivo:
Brindar una visión integral y práctica de patrones y metodologías de desarrollo aplicados en proyectos reales y entornos de producción modernos.

### 5.- Metodología SCRUM
Se basa en el supuesto de que el proceso de desarrollo es impredecible y que los requisitos pueden y deben cambiarse durante el proceso.

### 6.- Modelo Vista Controlador
#### ¿Qué es MVC?

* **Modelo:** Backend con lógica de datos y negocio.
* **Vista:** Frontend o interfaz gráfica de usuario (GUI).
* **Controlador:** Cerebro que maneja la interacción del usuario y la comunicación entre Modelo y Vista.

Permite que las aplicaciones sean escalables, mantenibles y fáciles de expandir.

El concepto lo propuso Trygve Reenskaug como una forma de desarrollar el GUI de aplicaciones de escritorio.

#### Otros ejemplos aplicados:

* **Frameworks Modernos:** Next.js utiliza patrones similares para renderizado. Spring Boot es usado en microservicios fintech.
* **Microservicios en Fintech:** Empresas emergentes en el sector fintech están utilizando Spring Boot con MVC para dividir grandes aplicaciones en servicios modulares.

### 7.- Encapsulación de lógica de negocios en APIs
Consiste en aislar la lógica de negocio dentro de una **API** (Application Programming Interface), permitiendo que distintos clientes
(web, móvil, IoT) accedan a las funcionalidades del sistema de forma centralizada y segura.

#### Ejemplos aplicados:
* **Sector Fintech:** Empresas como Stripe encapsulan lógica en APIs RESTful.
* **E-commerce:** Shopify expone APIs que gestionan procesos críticos como inventario, pedidos y pagos.

### 8.- Metodología Kanban
#### Metodología Kanban es:
Una metodología ágil basada en la visualización del flujo de trabajo mediante tableros, limitando el trabajo en curso y fomentando la mejora
continua.

#### Ejemplos aplicados:

* **Herramientas Digitales:** Jira.
* **Colaboración en Equipos Distribuidos:** Trello y Asana.

### 9.- Desarrollo Orientado a Prueba (TDD)
#### Desarrollo Orientado a Prueba (TDD)
TDD (Test-Driven Development) es una práctica en la que se escriben pruebas unitarias antes del desarrollo del código, guiando el diseño y
asegurando la funcionalidad desde el inicio.

**Ciclo TDD**
1. **Escribir una prueba:** Diseñar una prueba que inicialmente falle.
2. **Implementar el código mínimo:** Escribir el código necesario para que la prueba pase.
3. **Refactorizar:** Mejorar y optimizar el código manteniendo las pruebas exitosas.

#### Ventajas del TDD (Test-Driven Development)
Reducción de errores y mayor calidad del código.

#### Ejemplos aplicados:
* **Integración en Pipelines CI/CD:** Herramientas como Jest en JavaScript y JUnit en Java.
* **Proyectos Open Source:** Muchos proyectos en GitHub utilizan TDD.

### 10.- Principios SOLID en OOP
#### ¿Qué es SOLID en OOP?
Acrónimo de cinco principios esenciales para la Programación Orientada a Objetos (OOP):

1.  Responsabilidad única (Single Responsibility Principle).
2.  Abierto-Cerrado (Open-Closed Principle).
3.  Sustitución de Liskov (Liskov Substitution Principle)|(Establece que las subclases deber ser sustituibles por sus clases base).
4.  Segregación de interfaz (Interface Segregation Principle).
5.  Inversión de dependencia (Dependency Inversion Principle).

#### Ejemplos aplicados:
* **Diseño Modular en Microservicios**
* **Integración con Dependency Injection:** Frameworks como Spring en Java promueven arquitecturas basadas en inyección de dependencias.

#### Conclusiones:

* La separación de responsabilidades (MVC y SOLID) es esencial para construir sistemas escalables.
* La encapsulación de lógica en APIs mejora la seguridad e interoperabilidad entre plataformas.
* Scrum, Kanban y TDD son fundamentales para la gestión ágil y la calidad del software.

### Introducción a la Ruta Crítica en Proyectos de Software
#### CPM
**El Método del Camino Crítico (CPM)** es una técnica para identificar tareas que determinan la duración total del proyecto. Las tareas críticas tienen **holgura cero**; cualquier retraso afecta el proyecto global.

#### Pasos Generales para Obtener la Ruta Crítica

* **Listar todas las actividades del proyecto**
* **Estimar la duración de cada tarea:** Basarse en datos históricos, estudios de mercado o experiencia previa.
* **Determinar las dependencias entre actividades:** Especificar cuáles tareas deben completarse antes de iniciar otras.
* **Construir el diagrama de red:** Representar las tareas y sus dependencias en un diagrama (por ejemplo, en forma de nodos y flechas).
* **Realizar el cálculo del pase hacia adelante y hacia atrás:**
   * **Pase hacia adelante (Forward Pass):** Calcula la fecha de inicio más temprana (ES) y la fecha de finalización más temprana (EF) para cada actividad.
   * **Pase hacia atrás (Backward Pass):** Determina la fecha de inicio más tardía (LS) y la fecha de finalización más tardía (LF) sin retrasar el proyecto.
 * **Determinar la holgura de cada actividad:** La diferencia entre LS y ES (o LF y EF). Las actividades con holgura cero están en la ruta crítica.

#### Variables de Cálculo de la Ruta Crítica
* **ES (Early Start - Inicio Temprano)**
* **EF (Early Finish - Finalización Temprana)**

EF=ES+Duración de la actividad.

* **LS (Late Start - Inicio Tardío)**
* **LF (Late Finish - Finalización Tardía)**

LS=LF-Duración de la actividad.

#### Cálculo y Significado

* **Pase Hacia Adelante:** Se calculan ES y EF para cada actividad, partiendo desde el inicio del proyecto y avanzando en función de las dependencias. Este cálculo indica cuando es posible empezar y terminar cada actividad en condiciones óptimas.
* **Pase Hacia Atrás:** Se calculan LS y LF partiendo desde la fecha de finalización del proyecto y retrocediendo. Esto muestra el margen máximo que tiene cada actividad sin afectar la fecha final del proyecto.
* **Holgura (Slack) - Margen de Retraso**: La holgura de una actividad se determina como la diferencia entre su LS y ES (o entre LF y EF).

Holgura=LS-ES=LF-EF.

Una holgura de cero indica que la actividad está en la ruta crítica, es decir, no puede retrasarse sin afectar la duración total del proyecto.

#### Ejemplo sobre ¿Cómo Obtener la Ruta crítica de un Proyecto en el Desarrollo de Software o SI?

**Nombre del SI:**
>"Desarrollo de una aplicación de gestión de tareas para equipos de trabajo remotos"

**Objetivo:** Permitir la administración de proyectos, asignación de tareas, seguimiento de progreso y comunicación interna en tiempo real.

#### Listado de Actividades, Duraciones y Dependencias

| ID  | ACTIVIDAD                               | DURACIÓN (DÍAS) | DEPENDENCIAS |
| --- | --------------------------------------- | --------------- | ------------ |
| T1  | Recolección de Requerimientos           | 10              | -            |
| T2  | Análisis y Validación de Requerimientos | 5               | T1           |
| T3  | Diseño del Sistema (Arquitectura)       | 8               | T2           |
| T4  | Diseño de UI/UX                         | 7               | T2           |
| T5  | Diseño de Base de Datos                 | 6               | T2           |
| T6  | Implementación del Backend              | 15              | T3, T5       |
| T7  | Desarrollo del Frontend                 | 12              | T4           |
| T8  | Integración de Módulos                  | 5               | T6, T7       |
| T9  | Pruebas del Sistema                     | 10              | T8           |
| T10 | Despliegue y Documentación              | 4               | T9           |

#### Cálculo del **Pase Hacia Adelante** y **Hacia Atrás**

| ID  | Duración | ES | EF | LS | LF | Holgura | ¿Ruta Crítica? |
| --- | -------- | -- | -- | -- | -- | ------- | -------------- |
| T1  | 10       | 0  | 10 | 0  | 10 | 0       | **SÍ**         |
| T2  | 5        | 10 | 15 | 10 | 15 | 0       | **SÍ**         |
| T3  | 8        | 15 | 23 | 15 | 23 | 0       | **SÍ**         |
| T4  | 7        | 15 | 22 | 19 | 26 | 4       | No             |
| T5  | 6        | 15 | 21 | 17 | 23 | 2       | No             |
| T6  | 15       | 23 | 38 | 23 | 38 | 0       | **SÍ**         |
| T7  | 12       | 22 | 34 | 26 | 38 | 4       | No             |
| T8  | 5        | 38 | 43 | 38 | 43 | 0       | **SÍ**         |
| T9  | 10       | 43 | 53 | 43 | 53 | 0       | **SÍ**         |
| T10 | 4        | 53 | 57 | 53 | 57 | 0       | **SÍ**         |

**Identificación de la Ruta Crítica**

* Por lo tanto, la **ruta crítica** es: **T1 → T2 → T3 → T6 → T8 → T9 → T10** con una duración total del proyecto de **57 días**.

#### Beneficios de obtener la ruta crítica en el desarrollo de Proyectos de Software

* a) Planificación Precisa
* b) Control y Seguimiento
* c) Toma de Decisiones