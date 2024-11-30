<a name="top"></a>

<p align="right">
  <a href="https://github.com/ramaaorella/final_disenio#proceso-add-e-iteraciones"> Volver al índice</a> 
  &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-iterations/iteration-3.md"><i>>> <ins>Siguiente documento:</ins> Iteración 3</i></a>
</p>

## Iteración 2

### Iteration goal

En esta segunda iteración, se abordan los escenarios de calidad que continúan siendo de mayor prioridad: el primero, relacionado con el rendimiento del sistema en el procesamiento de mensajes, buscando garantizar una alta capacidad de procesamiento (throughput) (<a href="https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-inputs/qa-scenarios/qa4.2-scenario.md">QA-4.2</a>), y el segundo, centrado en la escalabilidad horizontal del sistema (<a href="https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-inputs/qa-scenarios/qa5.1-scenario.md">QA-5.1</a>).

Para alcanzar estos objetivos, se supone un escenario de alta carga de trabajo, donde el sistema debe enfrentar una demanda considerable, por encima de la normal. Esto permite evaluar las estrategias existentes y realizar los ajustes pertinentes en la configuración y diseño de los componentes, con el objetivo de mejorar el rendimiento y escalabilidad del sistema sin comprometer la calidad de los servicios. El objetivo principal es asegurar que el sistema pueda cumplir con los requisitos de rendimiento y escalabilidad establecidos, incluso bajo condiciones de alta carga, garantizando así una experiencia de usuario óptima y una operación eficiente del sistema.

<p align="right">(<a href="#top">Volver al inicio</a>)</p>

### Elements of the System to Refine

En esta segunda iteración, se llevará a cabo una revisión de los componentes críticos del sistema, centrándose nuevamente en el Gateway de mensajería y las capas de servicios del Core. Aunque estos elementos ya fueron refinados en la iteración anterior para cumplir con los casos de uso específicos de los flujos de mensajes, su importancia central en la arquitectura y su influencia en el rendimiento y la escalabilidad del sistema demandan una revisión en esta segunda iteración. Es fundamental asegurar que estos componentes estén debidamente preparados para cumplir con los estándares de rendimiento y escalabilidad establecidos.

<p align="right">(<a href="#top">Volver al inicio</a>)</p>

### Design concepts and considerations

<table>
   <thead>
    <tr>
      <th>Related drivers</th>
      <th>Design considerations</th>
      <th>Rationale and Assumptions</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>QA-4.2</td>
      <td>Selección del protocolo de comunicación entre el Gateway de mensajería y el Core</td>
      <td>La elección del protocolo de comunicación debe considerar la necesidad de manejar entornos de alta concurrencia y gran volumen de mensajes. Si bien debe tratarse de un protocolo liviano (<a href="https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-outputs/adrs/adr-005.md">ADR-005</a>) que permita una transmisión eficiente y rápida de mensajes, debe buscarse un protocolo de mensajería cuyo modelo de comunicación permita optimizar el throughput del sistema y evitar posibles cuellos de botella en el procesamiento del Core, dado que podrían afectar negativamente el rendimiento de todo el sistema.</td>
    </tr>
    <tr>
      <td>QA-4.2, QA-5.1</td>
      <td>Introducir concurrencia mediante la paralelización de tareas</td>
      <td>La paralelización de tareas se considera como una estrategia clave para mejorar el rendimiento del sistema al distribuir la carga de trabajo entre múltiples recursos. Esta estrategia puede aplicarse a dos niveles: dentro de los servicios, permitiendo ejecutar múltiples tareas simultáneamente y contribuyendo así a aumentar el throughput del Core y reducir los tiempos de respuesta; y a nivel de replicación de servicios, aprovechando la capacidad que el sistema debe tener de escalar horizontalmente, lo que permite distribuir la carga entre múltiples instancias de servicios u otros elementos de la arquitectura. Sin embargo, es importante tener en cuenta que esta estrategia puede introducir complejidad adicional en el diseño e implementación del sistema, así como posibles problemas de concurrencia y sincronización que deben ser gestionados cuidadosamente para garantizar un funcionamiento adecuado.
      </td>
    </tr>
    <tr>
      <td rowspan="2">QA-5.1</td>
      <td>Encapsulamiento de los servicios en contenedores vs. Enfoques tradicionales de despliegue y gestión de servicios.</td>
      <td>Evaluar el uso de contenedores para encapsular servicios, lo que proporciona portabilidad y aislamiento, pero puede aumentar la complejidad operativa y el overhead de gestión. Comparar con enfoques tradicionales de despliegue y gestión de servicios para determinar la mejor opción en términos de eficiencia y mantenibilidad.</td>
    </tr>
    <tr>
      <td>Orquestación de contenedores y escalado dinámico vs. Gestión manual de la escalabilidad.</td>
      <td>Considerar la orquestación de contenedores como una solución para gestionar la escalabilidad horizontal del sistema. Esto puede facilitar el despliegue y la gestión de aplicaciones en entornos cloud, pero también puede requerir recursos adicionales y un aprendizaje significativo para la configuración y operación adecuadas.</td>
    </tr>
    <tr>
      <td>QA-4.2, QA-5.1</td>
      <td>Implementación de estrategias de escalado automático y balanceo de carga</td>
      <td>Evaluar estrategias de escalado automático y balanceo de carga para garantizar un rendimiento óptimo del sistema. Si bien esto puede mejorar la capacidad de respuesta y la disponibilidad de los servicios, también puede introducir complejidad en la configuración y la gestión, así como un riesgo de costos adicionales asociados con el consumo de recursos en la nube.</td>
    </tr>
    <tr>
      <td rowspan="2">QA-5.1</td>
      <td>Manejo estático vs. dinámico de conexiones en un entorno escalable</td>
      <td>Dada la potencial escalabilidad del sistema, surge la disyuntiva sobre cómo gestionar eficientemente las conexiones entre componentes y servicios en un entorno escalable. Una opción comúnmente considerada es el uso de Service Discovery, un mecanismo que permite a los componentes descubrir automáticamente la ubicación y disponibilidad de los servicios en la red, eliminando la necesidad de configuraciones estáticas. Si bien esto puede facilitar la escalabilidad al permitir la adición y eliminación transparente de instancias de servicios, también introduce complejidad adicional en la configuración y operación del sistema, en comparación con el manejo estático de conexiones, el cual puede ofrecer una mayor predictibilidad y simplicidad en la gestión de la infraestructura.</td>
    </tr>
    <tr>
      <td>Centralización de la información de los chat real-time en un entorno escalable</td>
      <td>Ante la perspectiva de un escenario donde un gran número de operadores interactúan simultáneamente con clientes a través de chats en tiempo real, se plantea la necesidad de evaluar la escalabilidad de la solución propuesta mediante WebSockets. Se debe analizar si la arquitectura de WebSockets es capaz de escalar horizontalmente para satisfacer la demanda creciente de conexiones concurrentes y de los mensajes, o si se requiere una estrategia adicional para centralizar y gestionar de manera efectiva la información de los chats en un entorno escalable. La centralización de la información de los chats podría facilitar la administración y el monitoreo del sistema, así como mejorar la capacidad de respuesta y la experiencia del usuario.</td>
    </tr>
    <tr>
      <td>QA-4.2, QA-5.1</td>
      <td>Command Query Responsibility Segregation (CQRS) para optimizar transacciones en base de datos</td>
      <td>Dado que el sistema podría manejar un gran volumen de mensajes y se tiene como objetivo maximizar el throughput en un entorno escalable, resulta conveniente evaluar la conveniencia de separar las operaciones de lectura de las operaciones de escritura para optimizar el rendimiento y la eficiencia de las transacciones con la base de datos. En un sistema que maneja naturalmente grandes volúmenes de datos que requieren persistencia, el procesamiento rápido y eficaz de solicitudes y consultas puede ser crucial para garantizar la capacidad de respuesta del sistema y mantener una experiencia fluida para los usuarios. Evaluar la implementación del patrón CQRS (Command Query Responsibility Segregation) podría permitir una gestión más eficiente de las transacciones con la base de datos, lo que contribuiría a mejorar la escalabilidad y el rendimiento general del sistema.</td>
    </tr>
  </tbody>
</table>

<p align="right">(<a href="#top">Volver al inicio</a>)</p>
