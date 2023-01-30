## Escenario de calidad QA-2.2: Soporte para distribuir servicios en ambientes diferentes

*Es deseable que el sistema permita desplegar fácilmente sus servicios en un ambiente cloud.*

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Solicitud para operar en un nuevo entorno</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Desarrollador</td>
  </tr>
  <tr>
    <td><b>Environment</b></td>
    <td>Runtime; Organización de desarrollo no original</td>
  </tr>
  <tr>
    <td><b>Artifact</b></td>
    <td>Componentes / Infraestructura del sistema</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
    <ul>
        <li>Migrar a ambiente cloud una versión del servicio afectado</li>
        <li>Migrar tráfico de usuarios/datos de forma gradual</li>
        <li>Quitar el servicio local original una vez que el se haya realizado el deploy completo.</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>MTTC (Mean Time to Change)</li>
    </ul>
    </td>
  </tr>
</table>