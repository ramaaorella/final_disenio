## Escenario de calidad QA-5.1: Escalabilidad horizontal del sistema

_Ante un crecimiento en el número de clientes soportados, o en el número de mensajes enviados por los usuarios/canales, o incluso en el tipo de procesamiento a realizar sobre los mensajes, el sistema debe poder responder de manera adecuada. En caso que la carga sea demasiado alta, el sistema debe poder configurarse fácilmente con mayores recursos en el ambiente cloud._

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
        <li>Los administradores del sistema detectan un aumento significativo en la carga</li>
        <li>Se realiza una configuración fácil y rápida para agregar recursos (físicos y/o en ambiente cloud) al sistema</li>
        <li>El sistema detecta el aumento en la carga y responde dinámicamente haciendo uso de los nuevos recursos, sin degradación significativa del rendimiento</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
      <ul>
        <li>Tiempo promedio para configurar y desplegar nuevos recursos no debe tomar más de más de 30 minutos a 2 horas</li>
        <li>Capacidad para realizar la configuración sin interrupciones significativas en la disponibilidad del servicio</li>
      </ul>
    </td>
  </tr>
</table>
