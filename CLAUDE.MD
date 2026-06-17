# CLAUDE.MD

Instrucciones para Claude al trabajar en este repositorio.

## Enfoque Principal

Trabaja con Spec Driven Development (SDD). Antes de codificar cambios relevantes, convierte la peticion en una carpeta de tarea verificable.

Antes de comenzar cualquier tarea, genera o actualiza sus especificaciones. No empieces a implementar hasta que existan `functional-spec.md`, `technical-spec.md` y `tasks.md` dentro de la carpeta de la tarea.

Las tareas de este repositorio se implementan usando Python por defecto. Si una tarea requiere otra tecnologia, justificala en `technical-spec.md` antes de implementar.

Consulta tambien:

- `AGENTS.MD`
- `.agents/sdd-agent.md`

## Proceso

1. Inspecciona el repositorio y sus convenciones.
2. Crea o actualiza una carpeta de tarea en `task/<nombre-descriptivo>/`.
3. Genera o actualiza `functional-spec.md`, `technical-spec.md` y `tasks.md`.
4. Verifica que los tres ficheros describen la tarea antes de empezar.
5. Define requisitos, criterios de aceptacion y validacion.
6. Implementa solo lo necesario para cumplir la tarea.
7. Ejecuta pruebas o comprobaciones manuales.
8. Resume cambios, validacion y riesgos.

## Reglas Practicas

- No empieces por el codigo si el requisito es ambiguo.
- No comiences ninguna tarea sin haber creado primero sus especificaciones SDD.
- Usa Python por defecto para scripts, automatizaciones, pruebas y logica de aplicacion.
- Prefiere la libreria estandar de Python antes de anadir dependencias externas.
- Si falta informacion critica, pregunta.
- Si puedes avanzar con una asuncion razonable, documentala.
- Evita refactors no solicitados.
- Conserva el estilo del proyecto.
- No reviertas cambios que no hayas hecho.
- Manten la documentacion sincronizada con el comportamiento real.

## Estructura de Tarea SDD

Cada nueva tarea debe tener su propia carpeta:

```text
task/<nombre-descriptivo-de-la-tarea>/
```

El nombre debe ser descriptivo, corto, en minusculas y con guiones medios.

Dentro de cada carpeta genera siempre tres ficheros:

- `functional-spec.md`: requisitos funcionales, objetivos, alcance, criterios de aceptacion y casos borde.
- `technical-spec.md`: diseno tecnico, componentes afectados, contratos, datos, seguridad, observabilidad y validacion tecnica.
- `tasks.md`: checklist de tareas pequenas, estado y validaciones.

Estos tres ficheros son obligatorios antes de comenzar la implementacion.

## Formato de Especificacion Funcional

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

## Formato de Especificacion Tecnica

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

## Formato de Tareas

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

## Cierre de Tarea

Al terminar, informa de forma breve:

- Que se ha cambiado.
- Donde esta la carpeta de tarea.
- Donde estan las specs funcional y tecnica y el listado de tareas.
- Que validacion se ha ejecutado.
- Que queda pendiente, si aplica.
