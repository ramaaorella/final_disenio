## Escenario de calidad QA-6.1: Preservación de los mensajes

*El sistema debe preservar todos los mensajes, y en particular no debe perder ninguno de los mensajes entrantes. La trazabilidad del procesamiento de mensajes también es importante.*

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Mensaje entrante con el que operar en componente del sistema</td>
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
        <li>En caso de que la fuente de estímulo sea directamente el canal de comunicación digital, registrar el mensaje entrante (logging).</li>
        <li>Registrar comienzo transacción (logging)</li>
        <li>Operar con mensaje</li>
        <li>Registrar fin transacción, sea exitosa o no. (logging)</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
      <ul>
        <li>Porcentaje de mensajes entrantes recibidos</li>
        <li>Porcentaje de mensajes persistidos</li>
        <li>Se debe poder analizar toda la trazabilidad de los mensajes en el log.</li>
      </ul>
    </td>
  </tr>
</table>
