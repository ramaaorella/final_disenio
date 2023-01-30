## Escenario de calidad QA-1.2: Multicanalidad flujo saliente

*La plataforma debe tener la capacidad de enviar de manera uniforme mensajes a los distintos canales partícipes de la comunicación (entre aquellos disponibles).*

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Se envía un nuevo mensaje</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Usuario</td>
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
      <li>El sistema persiste el mensaje saliente</li>
      <li>El sistema envía el mensaje y notifica al emisor del mismo</li>
      <li>Se registra el mensaje saliente (logging)</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>Porcentaje de mensajes salientes correctamente procesados
    </ul>
    </td>
  </tr>
</table>