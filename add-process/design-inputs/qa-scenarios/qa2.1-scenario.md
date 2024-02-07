## Escenario de calidad QA-2.1: Modularización para fácil manteniemiento

_El sistema debe lo suficientemente modularizado para permitir modificar cada uno de los servicios en los que se descompone, sin afectar o minimizando el impacto sobre otros servicios o sobre los almacenamientos de datos; además de reducir el costo._

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Solicitud de corrección de error / Solicitud para modificar calidad de un servicio</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Desarrolladores, equipo de mantenimiento</td>
  </tr>
  <tr>
    <td><b>Environment</b></td>
    <td>Design time; Organización de desarrollo no original</td>
  </tr>
  <tr>
    <td><b>Artifact</b></td>
    <td>Servicio/s del sistema</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
    <ul>
      <li>Los desarrolladores acceden al servicio específico que requiere modificaciones</li>
      <li>Se realizan las modificaciones necesarias en el servicio afectado</li>
      <li>Se prueba que las modificaciones no introduzcan nuevos errores y que el servicio modificado funcione según lo esperado</li>
      <li>Se integra la modificación al sistema, sin afectar el funcionamiento de otros servicios</li>
    </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>Número de artefactos afectados</li>
      <li>Número de impactos en artefactos adyacentes</li>
      <li>MTTR (Mean time to repair)</li>
    </ul>
    </td>
  </tr>
</table>
