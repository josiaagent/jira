# Especificacion Tecnica: Recuperar Issue Jira

## Resumen Tecnico

Implementar una funcionalidad Python para recuperar un issue de Jira on-premise a partir de una clave o id. Debe reutilizar la configuracion y el cliente HTTP definidos para la conexion con Jira.

## Tecnologia

- Python como tecnologia por defecto.
- Version esperada: Python 3.10 o superior.
- Dependencias: reutilizar la decision tomada en la tarea de ping; preferir libreria estandar si es suficiente.

## Componentes Afectados

- Cliente Python de Jira.
- Funcion de recuperacion de issue.
- CLI o comando para solicitar un issue.
- Tests unitarios o de integracion simulada.
- Documentacion de uso.

## Diseno

Endpoint candidato:

- `GET <JIRA_BASE_URL>/rest/api/2/issue/{issueIdOrKey}`

La funcionalidad debe:

- Validar que se ha recibido un identificador de issue.
- Construir la URL de consulta de forma segura.
- Enviar autenticacion si esta configurada.
- Interpretar codigos HTTP relevantes.
- Normalizar la respuesta a una estructura simple.

Campos minimos de salida:

- `key`
- `summary`
- `status`
- `issue_type`

## Contratos

- Entrada:
  - `JIRA_BASE_URL`: URL base del servidor Jira.
  - `issue_id_or_key`: clave o id del issue.
  - Credenciales requeridas por el servidor.
  - Timeout opcional.
- Salida exitosa:
  - Objeto o JSON con datos basicos del issue.
- Salida con error:
  - Error de configuracion.
  - Error de autenticacion o permisos.
  - Issue no encontrado.
  - Error de red, timeout, TLS o HTTP inesperado.

## Persistencia y Datos

No hay persistencia. La respuesta del issue no debe guardarse localmente en esta tarea.

## Seguridad

- No incluir credenciales en codigo fuente.
- No imprimir tokens, passwords ni cabeceras de autorizacion.
- Sanitizar mensajes de error para evitar exponer datos sensibles.
- Evitar registrar el contenido completo del issue si puede contener informacion confidencial.

## Observabilidad

- Mensajes claros para consola.
- Codigos o tipos de error diferenciados.
- Posibilidad de activar salida mas detallada sin exponer secretos, si se implementa en el futuro.

## Validacion Tecnica

- Tests con respuesta exitosa simulada de Jira.
- Tests para 400, 401, 403, 404, 500 y timeout.
- Validacion manual contra Jira real cuando se disponga de acceso.
- Comprobar que no se imprimen secretos.

## Riesgos Tecnicos

- Riesgo: Campos personalizados o configuraciones de Jira pueden cambiar la forma de la respuesta.
- Riesgo: Permisos del usuario pueden impedir recuperar issues concretos.
- Riesgo: Reutilizar configuracion de la tarea de ping puede requerir ajustar el diseno comun del cliente.
