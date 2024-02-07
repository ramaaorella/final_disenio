## Escenario de calidad QA-6.1: Robustez y tolerancia a fallos del sistema

_Ante fallas en los componentes del sistema (por ej., en ciertos servicios, por timeout), el sistema debe continuar operando y minimizar la exposición de estas fallas hacia otros componentes (efecto cascada) o hacia a los usuarios._

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Un componente o servicio del sistema experimenta una falla</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Software: servicio externo, un componente interno o condiciones adversas en el entorno de ejecución</td>
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
        <li>El sistema detecta la falla en el componente o servicio afectado</li>
        <li>Se genera un registro de la falla (logging)</li>
        <li>Se activa un mecanismo de recuperación para aislar la falla y prevenir su propagación a otros componentes o servicios</li>
        <li>El sistema continúa operando con la menor interrupción posible, garantizando la disponibilidad continua para otros servicios y usuarios (modo degradado)</li>
        <li>Se reporta la falla a los administradores</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
      <ul>
        <li>MTTD (Mean time to detect fault)</li>
        <li>MTTR (Mean time to repair)</li>
        <li>Proporción de servicios que continúan operando sin verse afectados por la falla</li>
      </ul>
    </td>
  </tr>
</table>
