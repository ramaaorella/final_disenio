## Escenario de calidad QA-4.2: Procesamiento de mensajes entrantes con alto throughtput

_El throughput del sistema a la hora de procesar mensajes, ya sea en los flujos entrantes como salientes, no debe incidir gravemente en la performance._

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>El sistema recibe múltiples eventos (mensajes) entrantes de forma esporádica y proveniente de varios canales / El sistema debe enviar múltiples mensajes salientes a distintos canales de comunicación digital</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Canal/es de comunicación digital (tanto "interno/s" como externo/s)</td>
  </tr>
  <tr>
    <td><b>Environment</b></td>
    <td>Modo normal / sobrecarga</td>
  </tr>
  <tr>
    <td><b>Artifact</b></td>
    <td>Sistema</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
    <ul>
      <li>El sistema debe procesar eficientemente los eventos (mensajes) entrantes y salientes, asegurando un flujo constante y fluido de mensajes a través del sistema</li>
      <li>Escalado dinámico para manejar cargas pico de mensajes sin degradación significativa del rendimiento</li>
    </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>Throughput: cantidad de mensajes que pueden ser procesados en el intervalo de 1 min, asegurando un índice controlado y constante</li>
      <li>El rendimiento del sistema no debe verse gravemente impactado frente al escalado dinámico (se deben mantener las métricas controladas con su valor promedio)</li>
    </ul>
    </td>
  </tr>
</table>
