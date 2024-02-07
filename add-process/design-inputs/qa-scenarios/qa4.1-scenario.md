## Escenario de calidad QA-4.1: Procesamiento de mensajes entrantes con baja latencia

_El procesamiento de los mensajes entrantes debe realizarse con cierta latencia, para que permita realizar las interacciones con los usuarios en forma fluida._

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Eventos (mensajes) entrantes esporádicos que provienen a través de los canales de comunicación digital</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Mensajes en canal/es de comunicación digital</td>
  </tr>
  <tr>
    <td><b>Environment</b></td>
    <td>Modo normal</td>
  </tr>
  <tr>
    <td><b>Artifact</b></td>
    <td>Sistema</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
    <ul>
      <li>Procesamiento inmediato y prioritario de los mensajes entrantes</li>
      <li>Se garantiza que los usuarios en línea experimenten la menor latencia posible</li>
    </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>Latencia promedio (tiempo entre la llegada del estimulo y la respuesta del sistema) menor a 5 segs.</li>
      <li>Jitter (variación en el tiempo de procesamiento) controlado y consistente</li>
      <li>Miss rate (eventos que no logran procesarse dentro de la latencia esperada de 5 segs.)</li>
    </ul>
    </td>
  </tr>
</table>
