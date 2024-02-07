## Escenario de calidad QA-2.2: Soporte para distribuir servicios en ambientes diferentes

_Es deseable que el sistema permita desplegar fácilmente sus servicios en un ambiente cloud._

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Solicitud para operar en un nuevo entorno</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Desarrolladores</td>
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
      <li>Adaptar y migrar a la versión del servicio afectado para el nuevo entorno</li>
      <li>Los servicios del sistema se pueden instalar y ejecutar correctamente en el ambiente deseado</li>
      <li>La comunicación entre los servicios y otros componentes del sistema se mantiene sin problemas en el nuevo entorno</li>
      <li>Realizar una migración gradual del tráfico de usuarios/datos al nuevo entorno</li>
      <li>Eliminar el servicio original de manera controlada una vez completado el despliegue en el nuevo entorno</li>
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
