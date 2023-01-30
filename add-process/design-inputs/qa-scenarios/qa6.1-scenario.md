## Escenario de calidad QA-6.1: Robustez y tolerancia a fallos del sistema

*Ante fallas en los componentes del sistema (por ej., en ciertos servicios, por timeout), el sistema debe continuar operando y minimizar la exposición de estas fallas hacia otros componentes (efecto cascada) o hacia a los usuarios.*

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Fallas en componentes del sistema</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Software</td>
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
        <li>Detectar falla</li>
        <li>Registrar falla (logging)</li>
        <li>Reportar falla</li>
        <li>Recuperar falla u operar a pesar de la falla hasta resolverla (modo degradado)</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
      <ul>
        <li>MTTD (Mean time to detect fault)</li>
        <li>MTTR (Mean time to repair)</li>
      </ul>
    </td>
  </tr>
</table>