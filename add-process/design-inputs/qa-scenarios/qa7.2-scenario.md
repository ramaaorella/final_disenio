## Escenario de calidad QA-7.1: Confidencialidad de los canales de comunicación

_El sistema debe garantizar que no se comparte información entre distintos clientes._

<table>
  <tr>
    <td><b>Stimulus</b></td>
    <td>Intento no autorizado de acceder a mensajes que no le corresponden como receptor o de enviar mensajes u hacer uso de canales ajenos</td>
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
    <td>Servicios del sistema</td>
  </tr>
  <tr>
    <td><b>Response</b></td>
    <td>
      <ul>
        <li>Bloquear el acceso a los servicios cuando se trate de canales de comunicación que no le correspondan, permitiendo sólo el uso legítimo de los mismos</li>
        <li>Registrar intento de acceso (logging) con la identidad del usuario a canales ajenos</li>
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
