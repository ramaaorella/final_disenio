## Escenario de calidad QA-7.1: Roles de usuario

_El acceso al sistema y su operación debe realizarse mediante roles autorizados._

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Intento no autorizado de acceder a dashboards, reportes u otras herramientas exclusivas para algunos tipos de usuarios de la plataforma</td>
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
        <li>Se implementa un mecanismo para reconocer patrones de alta demanda inexplicable a la información protegida</li>
        <li>Si se detecta una actividad sospechosa, se informa a los administradores del sistema</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td><b>Response measure</b></td>
    <td>
      <ul>
        <li>Registro de los intentos de acceso no autorizado para auditoría</li>
        <li>Probabilidad de detectar un ataque respecto al porcentaje de actividades sospechosas detectadas</li>
      </ul>
    </td>
  </tr>
</table>
