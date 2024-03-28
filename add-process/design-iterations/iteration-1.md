<a name="top"></a>

<p align="right">
  <a href="https://github.com/ramaaorella/final_disenio#proceso-add-e-iteraciones"> Volver al índice</a> 
  &nbsp;&nbsp;|&nbsp;&nbsp;
  <a href="https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-iterations/iteration-2.md"><i>>> <ins>Siguiente documento:</ins> Iteración 2</i></a>
</p>

## Iteración 1

### Iteration goal

En esta primera iteración, se decide comenzar a refinar el sistema a partir de los dos principales casos de uso: el flujo de mensajes entrantes (<a href="https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-inputs/1.review-design-inputs.md#primary-functional-requirements">UC-2</a>) y el flujo de mensajes salientes (<a href="https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-inputs/1.review-design-inputs.md#primary-functional-requirements">UC-3</a>). Este enfoque permite refinar e instanciar los componentes necesarios para respaldar esta funcionalidad, para luego abordar los escenarios de calidad implicados. Para ello, se tomará como base la arquitectura inicial nocional, considerando además las implicaciones de las tecnologías utilizadas en el prototipo (que se consideran una restricción organizacional -<a href="https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-inputs/1.review-design-inputs.md#constraints">CON-1</a>-, al entender que el equipo de desarrollo se encuentra familiarizado con las mismas), de forma de poder alinearse con los recursos disponibles y las habilidades del equipo de desarrollo.

Para evitar que la iteración se limite sólo a la instanciación de componentes y asignación de responsabilidades, se aprovechan estos casos de uso como oportunidad para evaluar la satisfacción de uno de los escenarios de calidad relacionados (<a href="https://github.com/ramaaorella/final_disenio/blob/main/add-process/design-inputs/qa-scenarios/qa4.1-scenario.md">QA-4.1</a>), que ha sido identificado como prioritario. De esta manera, no sólo se aborda el diseño en cuanto a la implementación de la funcionalidad, sino también se busca garantizar desde el principio la calidad en ese flujo de mensajes para cumplir con las expectativas del sistema.

<p align="right">(<a href="#top">Volver al inicio</a>)</p>

### Elements of the System to Refine

En esta primera iteración, se refinarán dos componentes críticos del sistema: el Gateway de mensajería y las capas de servicios del Core, que incluye los servicios de integración, servicios de negocio y servicios de acceso a datos. La elección de centrarse en estos elementos se basa en su papel fundamental para gestionar eficazmente el flujo de mensajes entrantes y salientes, lo que, a su vez, permite satisfacer los drivers y objetivos de esta iteración.

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
      <td rowspan="3">UC-2, UC-3</td>
      <td>Comunicación sincrónica o asincrónica entre componentes (Gateway de mensajería-Core y Core-Frontend)</td>
      <td>Considerando la naturaleza del flujo de mensajes entre el Gateway de mensajería, el Core y el Frontend, es crucial decidir el tipo de comunicación que mejor se adapte a las necesidades del sistema. La comunicación sincrónica garantiza una respuesta inmediata antes de que el remitente pueda continuar con su ejecución, lo que puede ser beneficioso para sincronización y confirmaciones de mensajes, pero puede aumentar la complejidad y el riesgo de bloqueo. En contraste, la comunicación asincrónica permite un procesamiento más fluido y mejora la escalabilidad y la tolerancia a fallos, aunque puede introducir latencia y requerir sincronización adicional.</td>
    </tr>
    <tr>
      <td>Comunicación sincrónica o asincrónica entre servicios</td>
      <td>Al igual que entre componentes, la comunicación entre servicios puede tratarse de una comunicación sincrónica o asincrónica. A diferencia que en el caso anterior, debe considerarse la dependencia potencial entre servicios al decidir el tipo de comunicación, ya que se puede requerir sincronicidad para garantizar la integridad y coherencia del sistema. Es importante tener en cuenta que cada enfoque tiene sus propias ventajas y desventajas, y por ello, es necesario evaluar el tipo de comunicación en función de las necesidades específicas de cada interacción entre servicios.</td>
    </tr>
    <tr>
      <td>Gestión de la persistencia de mensajes como parte del procesamiento</td>
      <td>La integración de la persistencia como parte del procesamiento de mensajes presenta ventajas en términos de eficiencia y consistencia de datos al garantizar la integridad de los mismos. Sin embargo, esta integración puede aumentar la latencia del procesamiento. Por otro lado, desacoplar la persistencia del procesamiento intrínseco del mensaje simplifica el diseño y mejora la velocidad de procesamiento, aunque puede introducir posibles problemas de consistencia y riesgos de pérdida de datos en caso de fallos del sistema.</td>
    </tr>
    <tr>
      <td>UC-2</td>
      <td>Visualización de mensajes entrantes en tiempo real o diferido</td>
      <td>Dado que la forma de visualización de mensajes entrantes no está especificada como parte de los requisitos, surge la disyuntiva de cómo mostrar esos mensajes entrantes. Las notificaciones en tiempo real se plantean como una opción para alinearse con la funcionalidad comúnmente esperada en sistemas de mensajería, lo cual permite una experiencia inmediata y una respuesta rápida. Sin embargo, esta elección puede incrementar la carga del sistema y la latencia de procesamiento, ya que el sistema debe encargarse de mostrar las notificaciones tan pronto como llegan. Por otro lado, utilizar un enfoque de visualización diferido reduce la carga del sistema y la latencia, ya que permite que el sistema desacople esta funcionalidad y realice las notificaciones de manera no inmediata, aunque genere una experiencia de usuario menos fluida.</td>
    </tr>
    <tr>
      <td rowspan="3">QA-4.1</td>
      <td>Priorizar mensajes de usuarios en línea</td>
      <td>La priorización de mensajes de usuarios en línea se considera como una estrategia para mejorar la latencia del sistema al garantizar que los mensajes críticos se procesen y entreguen de manera más rápida, lo que puede resultar en una experiencia de usuario más fluida. Sin embargo, es importante tener en cuenta que esta priorización puede aumentar la carga de trabajo y la necesidad de recursos para su gestión. Además, existe el riesgo de que otros usuarios no prioritarios experimenten una degradación en su experiencia, ya que sus mensajes podrían no recibir una respuesta tan rápida como la de los mensajes prioritarios.</td>
    </tr>
    <tr>
      <td>Optimización latencia red</td>
      <td>La optimización de la latencia de red puede mejorar la velocidad de entrega de mensajes y la capacidad de respuesta del sistema, lo que puede conducir a una mejor experiencia del usuario. Sin embargo, al implementar estrategias para reducir los tiempos de transmisión y recepción de mensajes, como el uso de protocolos de comunicación livianos, la minimización de la sobrecarga mediante la eliminación de información innecesaria en los mensajes y el aprovechamiento de técnicas de almacenamiento en caché, es crucial mantener un equilibrio con otros aspectos fundamentales del sistema, como la integridad y la completitud de la información transmitida, así como el uso eficiente de los recursos disponibles.</td>
    </tr>
    <tr>
      <td>Reducción de la sobrecarga mediante co-locate</td>
      <td>La co-locación de recursos es una estrategia que puede reducir significativamente la latencia y mejorar la eficiencia del sistema en sistemas distribuidos al minimizar la sobrecarga de red y los tiempos de comunicación entre componentes. Al alojar componentes relacionados en la misma infraestructura física o virtual, se reduce la latencia inherente a las comunicaciones entre nodos, lo que puede resultar en una mejora notable en la capacidad de respuesta del sistema y en la experiencia del usuario. Sin embargo, esta estrategia puede aumentar la complejidad de la gestión de recursos y la dependencia entre componentes, lo que podría introducir riesgos adicionales en la operación del sistema y dificultar su escalabilidad a largo plazo.</td>
    </tr>
  </tbody>
</table>

<p align="right">(<a href="#top">Volver al inicio</a>)</p>

