<a name="top"></a>

<div align="center">
  <h2 align="center">Trabajo final - Diseño de Sistemas de Software I</h2>

  <p align="center">
    Trabajo realizado para el final de la cátedra Diseño de </br>
    Sistemas de Software como parte del Programa de Apoyo a la Graduación - UNICEN. 
</div>

</br>

### Contexto y objetivos del trabajo

<p>
  El objetivo del trabajo es seguir la metodología ADD (Attribute Driven Design) para realizar el diseño de un sistema de software.
  En particular, se toma de base un sistema basado en un caso real para refinar con ADD y obtener una arquitectura mejorada del mismo.
</p> 
<p>
  Este sistema es una especie de CRM / "call center" en base a canales de comunicación digital. El contexto completo desde el que se comienza el trabajo se encuentra en el siguiente <a href="https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-inputs/0.unrefined-design-inputs.md">link</a>.
</p>

### Resumen del proceso

<details>
<summary><h4><i>Situación de negocio / Contexto inicial</i></h4></summary>
<p>La empresa ya dispone de una plataforma tecnológica operativa que integra canales de comunicación y gestiona interacciones a través de un portal de clientes. Sin embargo, se entiende que este sistema, aunque funcional, presenta limitaciones que dificultan su capacidad para acompañar el crecimiento y la evolución deseados.</p>
<p>En respuesta, se decide diseñar un nuevo sistema arquitectónico que no sólo resuelva los desafíos actuales, sino que también establezca una base sólida para garantizar un crecimiento sostenible tanto del producto como de la empresa misma. Es por ello que se valora la performance, escalabilidad e interoperabilidad a la cabeza, como pilares fundamentales del diseño. Por el contexto de aplicación, la trazabilidad, fiabilidad y seguridad también son importantes.</p>
</details>

<details>
<summary><h4><i>¿Qué se propuso?</i></h4></summary>
<p>Mantener la arquitectura cliente-servidor y SOA, pero evolucionar hacia una arquitectura híbrida incorporando microservicios para los servicios que gestionan los flujos de mensajes entrantes y salientes, debido a que estos son los más críticos del sistema. A medida que aumentan el número de clientes, canales soportados, el volumen de mensajes y el procesamiento que estos requieren, los flujos de mensajes se vuelven cada vez más impredecibles y difíciles de gestionar, lo que puede afectar significativamente el rendimiento del sistema.</p>
<p>Dado que estos flujos de mensajes son altamente dinámicos y su carga es muy difícil de predecir, el diseño apuesta por una solución basada en microservicios para brindar mayor flexibilidad, escalabilidad horizontal y resiliencia. Esto asegura que el sistema pueda escalar automáticamente según las variaciones en la demanda, especialmente cuando se enfrenta a picos inesperados en el volumen de mensajes. Por otro lado, el resto de componentes del sistema que no enfrentan estas mismas fluctuaciones pueden seguir utilizando un enfoque SOA tradicional, permitiendo una estructura más sencilla y estable.</p>
<p>De esta manera, el sistema se divide en dos partes que evolucionan de manera independiente: el gateway de mensajería, que actúa como un integrador desacoplado del contexto de la aplicación, y el core, que, a través de su comunicación con el gateway, da soporte a los requerimientos específicos de la aplicación.</p>
<p>Este enfoque garantiza que los flujos de mensajes sean gestionados de forma eficiente y flexible, asegurando un escalado automático según sea necesario, y permitiendo que la plataforma crezca de manera constante y sostenible, sin comprometer el rendimiento ni la disponibilidad.</p>
</details>


### Índice del proceso ADD e iteraciones

- Design inputs:

  - [Unrefined Design Inputs](https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-inputs/0.unrefined-design-inputs.md)
  - [Refined Design Inputs](https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-inputs/1.review-design-inputs.md)
  - [QA Scenarios](https://github.com/ramaaorella/final_disenio/tree/main/add-process/design-inputs/qa-scenarios)

- Design iterations:

  - [Iteration 0](https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-iterations/iteration-0.md)
  - [Iteration 1](https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-iterations/iteration-1.md)
  - [Iteration 2](https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-iterations/iteration-2.md)

- Design outputs:
  - [Diagrama C&C de la arquitectura final]()
  - [Estrategia de escalado automático]()
  - [Flujo para integrar nuevos canales de comunicación]()

<p align="right">(<a href="#top">Volver al inicio</a>)</p>
