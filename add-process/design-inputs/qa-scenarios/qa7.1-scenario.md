## Escenario de calidad QA-7.1: Roles de usuario

*El acceso al sistema y su operación debe realizarse mediante roles autorizados.*

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Intento no autorizado de acceder a dashboards, reportes u otras herramientas exclusivas para los administradores de la plataforma</td>
  </tr>
  <tr>
    <td><b>Stimulus source</b></td>
    <td>Usuario (identificado/no identificado)</td>
  </tr>
  <tr>
    <td><b>Environment</b></td>
    <td>Sistema online (totalmente operativo)</td>
  </tr>
  <tr>
    <td><b>Artifact</b></td>
    <td>Datos producidos y consumidos por el sistema para la administración y monitoreo del mismo</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
      <ul>
        <li>Bloquear el acceso a esa información</li>
        <li>Registrar intento de acceso (logging) con la identidad del usuario</li>
        <li>Se informa al usuario del bloqueo</li>
        <li>Reconocer si se trata de una alta demanda inexplicable a la información protegida e informar a los administradores del sistema</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
      <ul>
        <li>Probabilidad de detectar un ataque</li>
      </ul>
    </td>
  </tr>
</table>
