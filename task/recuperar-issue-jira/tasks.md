# Tareas: Recuperar Issue Jira

## Plan de Implementacion

- [ ] T-001: Reutilizar o crear cliente Jira comun para llamadas HTTP.
- [ ] T-002: Implementar validacion de clave o id de issue.
- [ ] T-003: Implementar llamada a `/rest/api/2/issue/{issueIdOrKey}`.
- [ ] T-004: Normalizar respuesta a datos basicos del issue.
- [ ] T-005: Implementar salida CLI para mostrar issue consultado.
- [ ] T-006: Manejar errores de configuracion, autenticacion, permisos, no encontrado, timeout y HTTP inesperado.
- [ ] T-007: Anadir tests unitarios con respuestas HTTP simuladas.
- [ ] T-008: Documentar uso y variables necesarias.

## Validacion

- [ ] Ejecutar tests automaticos relevantes.
- [ ] Probar ejecucion con configuracion incompleta.
- [ ] Probar ejecucion con issue invalido.
- [ ] Probar ejecucion con issue inexistente.
- [ ] Probar ejecucion contra servidor Jira real si se dispone de acceso.
- [ ] Comprobar que no se imprimen credenciales.

## Estado

- Pendiente.
