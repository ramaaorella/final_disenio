## Escenario de calidad QA-2.1: Modularización para fácil manteniemiento

*El sistema debe lo suficientemente modularizado para permitir modificar cada uno de los servicios en los que se descompone, sin afectar o minimizando el impacto sobre otros servicios o sobre los almacenamientos de datos; además de reducir el costo.*

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Solicitud de corrección de error / Solicitud para modificar calidad de un servicio</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Desarrollador</td>
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
        <li>Aislar los servicios afectados</li>
        <li>Modificar el código</li>
        <li>Probar e integrar la modificación</li>
        <li>Hacer deploy de la modificación</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
    <ul>
      <li>Costo en términos de artefactos afectados</li>
      <li>MTTR (Mean time to repair)</li>
    </ul>
    </td>
  </tr>
</table>