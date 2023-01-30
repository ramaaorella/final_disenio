## Escenario de calidad QA-5.1: Escalabilidad horizontal del sistema

*Ante un crecimiento en el número de clientes soportados, o en el número de mensajes enviados por los usuarios/canales, o incluso en el tipo de procesamiento a realizar sobre los mensajes, el sistema debe poder responder de manera adecuada. En caso que la carga sea demasiado alta, el sistema debe poder configurarse facilmente con mayores recursos en el ambiente cloud.*

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Se agregan mayores recursos al sistema (físicos y/o en ambiente cloud)</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Empresa</td>
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
        <li>El sistema realiza sus operaciones de forma normal (sin necesidad en entrar en modo de sobrecarga).</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
      <ul>
        <li>La mejora en la respuesta del sistema debe equipar el promedio histórico de performance (en términos de latencia y throughput).</li>
      </ul>
    </td>
  </tr>
</table>