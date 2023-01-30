## Escenario de calidad QA-4.1: Procesamiento de mensajes entrantes con baja latencia

*El procesamiento de los mensajes entrantes debe realizarse con cierta latencia, para que permita realizar las interacciones con los usuarios en forma fluida.*

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Eventos (mensajes) entrantes esporádicos</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Canal/es de comunicación digital</td>
  </tr>
  <tr>
    <td><b>Environment</b></td>
    <td>Sistema</td>
  </tr>
  <tr>
    <td><b>Artifact</b></td>
    <td>Modo normal</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
    <ul>
        <li>Se procesan los mensajes entrantes</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>Latencia promedio (tiempo entre la llegada del estimulo y la respuesta del sistema) menor a 5 segs.</li>
    </ul>
    </td>
  </tr>
</table>