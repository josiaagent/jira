# AGENTS.MD

Instrucciones para agentes que trabajen en este repositorio.

## Modo de Trabajo

Usa Spec Driven Development (SDD) para cambios funcionales, arquitectura, integraciones, automatizaciones y refactors con impacto observable.

El agente SDD principal esta definido en:

- `.agents/sdd-agent.md`

Regla obligatoria: antes de comenzar cualquier tarea, genera o actualiza sus especificaciones. No empieces a implementar hasta que existan `functional-spec.md`, `technical-spec.md` y `tasks.md` dentro de la carpeta de la tarea.

Las tareas de este repositorio se implementan usando Python por defecto. Cualquier excepcion debe justificarse en `technical-spec.md`.

## Flujo Obligatorio para Cambios No Triviales

1. Leer primero `README.md`, este archivo y cualquier tarea SDD existente.
2. Crear o actualizar una carpeta de tarea antes de comenzar cualquier trabajo.
3. Generar o actualizar `functional-spec.md`, `technical-spec.md` y `tasks.md`.
4. Definir criterios de aceptacion verificables.
5. Implementar en pasos pequenos.
6. Ejecutar validaciones relevantes.
7. Dejar constancia de decisiones, asunciones y riesgos.

## Ubicacion Obligatoria de Tareas

Cada nueva tarea debe vivir en una carpeta propia dentro de:

- `task/<nombre-descriptivo-de-la-tarea>/`

El nombre debe ser descriptivo, corto, en minusculas y con guiones medios. No uses espacios.

Cada carpeta de tarea debe contener estos tres ficheros:

- `functional-spec.md`
- `technical-spec.md`
- `tasks.md`

Estos tres ficheros son un prerrequisito. Si no existen, la primera accion del agente debe ser crearlos antes de tocar codigo o ejecutar la tarea.

## Plantilla de Especificacion Funcional

Archivo: `task/<nombre>/functional-spec.md`

```markdown
# Especificacion Funcional: <nombre>

## Contexto

## Objetivos

## Fuera de Alcance

## Requisitos Funcionales

## Requisitos No Funcionales

## Criterios de Aceptacion

## Casos Borde

## Decisiones y Asunciones
```

## Plantilla de Especificacion Tecnica

Archivo: `task/<nombre>/technical-spec.md`

```markdown
# Especificacion Tecnica: <nombre>

## Resumen Tecnico

## Tecnologia

## Componentes Afectados

## Diseno

## Contratos

## Persistencia y Datos

## Seguridad

## Observabilidad

## Validacion Tecnica

## Riesgos Tecnicos
```

## Plantilla de Listado de Tareas

Archivo: `task/<nombre>/tasks.md`

```markdown
# Tareas: <nombre>

## Plan de Implementacion
- [ ] T-001: ...
- [ ] T-002: ...

## Validacion
- [ ] Ejecutar tests relevantes.
- [ ] Comprobar criterios de aceptacion.
- [ ] Revisar documentacion afectada.

## Estado
```

## Criterios de Calidad

- Mantener los cambios acotados al objetivo.
- Preferir convenciones existentes del repositorio.
- Usar Python como tecnologia por defecto para scripts, automatizaciones, pruebas y logica de aplicacion.
- No introducir dependencias sin justificarlo en la especificacion tecnica.
- Preferir la libreria estandar de Python cuando sea suficiente.
- No modificar archivos no relacionados.
- No borrar cambios de usuario.
- Documentar cualquier comportamiento nuevo.
- Anadir o actualizar tests cuando exista comportamiento verificable.
- Actualizar `tasks.md` con el estado real de la tarea.

## Validacion

Antes de finalizar, intenta ejecutar los comandos disponibles del proyecto. Si no hay comandos definidos, indica claramente que no existen pruebas automatizadas detectadas y describe la validacion manual realizada.

## Respuesta Final Esperada

Resume:

- Carpeta de tarea creada o actualizada.
- Specs funcional, tecnica y listado de tareas.
- Archivos modificados.
- Validacion ejecutada.
- Pendientes o riesgos relevantes.
