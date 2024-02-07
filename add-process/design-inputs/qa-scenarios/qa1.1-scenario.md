## Escenario de calidad QA-1.1: Multicanalidad flujo entrante

_La plataforma debe tener la capacidad de recibir, procesar y tratar de manera uniforme mensajes provenientes de distintos canales._

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>El canal con el que se interopera envía un nuevo mensaje al sistema.</td>
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
      <li>El sistema detecta y registra el mensaje entrante utilizando un sistema de logging</li>
      <li>El sistema formatea el mensaje bajo un formato estándar que permite un procesamiento uniforme</li>
      <li>El sistema trata el mensaje según su contenido, canal de origen y destino</li>
      <li>El sistema enruta el mensaje y notifica al usuario receptor del mismo</li>
      <li>El mensaje es marcado para persistencia asincrónica en la base de datos del sistema</li>
    </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>Porcentaje de mensajes recibidos correctamente</li>
      <li>Porcentaje de mensajes procesados correctamente</li>
      <li>Porcentaje de mensajes entregados con éxito</li>
    </ul>
    </td>
  </tr>
</table>
