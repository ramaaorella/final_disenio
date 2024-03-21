## Escenario de calidad QA-6.2: Preservación de los mensajes

_El sistema debe preservar todos los mensajes, y en particular no debe perder ninguno de los mensajes entrantes. La trazabilidad del procesamiento de mensajes también es importante._

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Mensaje con el que operar en componente del sistema</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Canal de comunicación digital / Componente del sistema</td>
  </tr>
  <tr>
    <td><b>Environment</b></td>
    <td>Modo normal</td>
  </tr>
  <tr>
    <td><b>Artifact</b></td>
    <td>Componente del sistema</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
      <ul>
        <li>Registrar el mensaje (logging).</li>
        <li>Encolar mensaje para su procesamiento</li>
        <li>Registrar comienzo transacción (logging)</li>
        <li>Operar con mensaje</li>
        <li>Registrar fin transacción, sea exitosa o no (logging)</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
      <ul>
        <li>Porcentaje de mensajes entrantes recibidos</li>
        <li>Porcentaje de mensajes persistidos</li>
        <li>Análisis completo de la trazabilidad de los mensajes a través del registro (log)</li>
      </ul>
    </td>
  </tr>
</table>
