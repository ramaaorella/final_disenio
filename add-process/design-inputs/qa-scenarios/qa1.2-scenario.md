## Escenario de calidad QA-1.2: Multicanalidad flujo saliente

_La plataforma debe tener la capacidad de enviar de manera uniforme mensajes a los distintos canales partícipes de la comunicación (entre aquellos disponibles)._

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Un operador genera un mensaje de respuesta que debe ser transmitido al usuario a través del canal correspondiente</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Usuario (operador)</td>
  </tr>
  <tr>
    <td><b>Environment</b></td>
    <td>Sistemas (canales) con los que interoperar se descubrirán en tiempo de ejecución</td>
  </tr>
  <tr>
    <td><b>Artifact</b></td>
    <td>Sistema</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
    <ul>
      <li>El sistema recibe el mensaje de respuesta generado por el operador</li>
      <li>Se registra el mensaje saliente (logging)</li>
      <li>El sistema formatea el mensaje saliente de manera adecuada para el canal de destino</li>
      <li>El sistema enruta y transmite el mensaje al canal de destino para que sea entregado al usuario correspondiente</li>
      <li>El mensaje es marcado para persistencia asincrónica en la base de datos del sistema</li>
    </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>Porcentaje de mensajes salientes registrados</li>
      <li>Porcentaje de mensajes salientes correctamente procesados</li>
      <li>Porcentaje de mensajes salientes con confirmación de entrega</li>
    </ul>
    </td>
  </tr>
</table>
