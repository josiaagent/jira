# Especificacion Funcional: Recuperar Issue Jira

## Contexto

Tras validar la conectividad con Jira, se necesita recuperar la informacion de un issue concreto pasando su identificador o clave de Jira. Esta funcionalidad servira como base para futuras operaciones de consulta.

## Objetivos

- Recuperar un issue desde Jira on-premise usando su clave o id.
- Devolver informacion util del issue de forma estructurada.
- Informar errores de forma clara cuando el issue no exista o no sea accesible.

## Fuera de Alcance

- Crear, actualizar o borrar issues.
- Busquedas JQL.
- Recuperacion masiva de issues.
- Sincronizacion local o persistencia.
- Interfaz grafica.

## Requisitos Funcionales

- RF-001: La funcionalidad debe recibir una clave o id de issue Jira.
- RF-002: La funcionalidad debe conectarse al servidor Jira configurado.
- RF-003: La funcionalidad debe consultar el issue solicitado.
- RF-004: La funcionalidad debe devolver al menos clave, resumen, estado y tipo de issue cuando esten disponibles.
- RF-005: La funcionalidad debe informar si el issue no existe, no es accesible o la autenticacion falla.
- RF-006: La configuracion sensible debe obtenerse desde variables de entorno o mecanismo equivalente, no desde codigo fijo.

## Requisitos No Funcionales

- RNF-001: La solucion debe implementarse en Python.
- RNF-002: La llamada debe tener timeout.
- RNF-003: La salida debe poder usarse desde consola y ser facil de extender a formato estructurado.
- RNF-004: No debe exponer credenciales en errores, logs ni salida estandar.

## Criterios de Aceptacion

- CA-001: Dado un issue existente y accesible, cuando se consulte por su clave o id, entonces se debe mostrar la informacion basica del issue.
- CA-002: Dado un issue inexistente, cuando se consulte, entonces se debe informar que no se ha encontrado.
- CA-003: Dadas credenciales invalidas o permisos insuficientes, cuando se consulte el issue, entonces se debe informar el error de acceso de forma controlada.
- CA-004: Dada configuracion incompleta, cuando se ejecute la consulta, entonces se debe indicar que falta configuracion requerida.

## Casos Borde

- Clave de issue con formato invalido.
- Issue existente pero sin permisos para el usuario configurado.
- Respuesta con campos inesperados o personalizados.
- Jira con API REST en version antigua.
- Timeout o fallo de red durante la consulta.
- Certificado TLS interno o autofirmado.

## Decisiones y Asunciones

- Asuncion: La clave de issue tendra formato similar a `PROY-123`, aunque Jira tambien permite ids numericos.
- Asuncion: La autenticacion sera necesaria para recuperar issues en la mayoria de entornos on-premise.
- Decision: Esta tarea depende conceptualmente de la configuracion de conexion definida para el ping, pero se mantiene como tarea separada.
