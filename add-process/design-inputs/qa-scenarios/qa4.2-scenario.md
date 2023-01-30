## Escenario de calidad QA-4.2: Procesamiento de mensajes entrantes con alto throughtput

*El throughput del sistema a la hora de procesar mensajes, ya sea en los flujos entrantes como salientes, no debe incidir gravemente en la performance.*

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Eventos (mensajes) entrantes esporádicos / Mensajes salientes</td>
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
    <td>Modo normal / sobrecarga</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
    <ul>
        <li>Se procesan los eventos (priorizando los entrantes sin impedir el procesamiento de mensajes salientes)</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>Throughput</li>
    </ul>
    </td>
  </tr>
</table>