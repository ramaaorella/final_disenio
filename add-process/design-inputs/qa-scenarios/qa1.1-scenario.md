## Escenario de calidad QA-1.1: Multicanalidad flujo entrante

*La plataforma debe tener la capacidad de recibir, procesar y tratar de manera uniforme mensajes provenientes de distintos canales.*

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>El canal con el que se interopera envía un nuevo mensaje y es recibido por el sistema.</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Canal de comunicación digital</td>
  </tr>
  <tr>
    <td><b>Environment</b></td>
    <td>Sistema conocido antes del tiempo de ejecución</td>
  </tr>
  <tr>
    <td><b>Artifact</b></td>
    <td>Sistema</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
    <ul>
      <li>Se registra el mensaje recibido (logging)</li>
      <li>El sistema persiste el mensaje entrante</li>
      <li>El sistema formatea mensaje entrante bajo un formato estándar que permita procesarlos de manera uniforme</li>
      <li>El sistema trata el mensaje y notifica al usuario receptor del mismo</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>Porcentaje de mensajes recibidos</li>
      <li>Porcentaje de mensajes formateados correctamente</li>
    </ul>
    </td>
  </tr>
</table>