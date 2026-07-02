---
name: crear-skill
description: Crea una nueva skill de Kiro CLI con la estructura correcta. Usar cuando el usuario quiera crear un nuevo comando /nombre o automatizar una tarea repetible.
---

## Tarea

Cuando se invoque esta skill, pregunta al usuario:

1. **¿Cómo se llamará la skill?** (este nombre se convierte en el comando `/nombre`, solo minúsculas, números y guiones)
2. **¿Qué debe hacer?** (descripción de la tarea que realizará)
3. **¿Cuáles son los pasos concretos que debe ejecutar?**

Con esas respuestas, crea la siguiente estructura:

```
.kiro/skills/<nombre>/
└── SKILL.md
```

## Reglas para generar el SKILL.md

El archivo generado debe seguir este formato exacto:

```
---
name: <nombre-de-la-skill>
description: <descripción clara de qué hace y cuándo activarla. Incluir "Usar cuando...">
---

## Tarea

<instrucciones claras y paso a paso de lo que debe hacer el agente>

- Sin preguntas innecesarias
- Confirmar al usuario cuando termine
```

## Reglas generales

- El `name` en el frontmatter debe coincidir exactamente con el nombre de la carpeta
- La `description` determina cuándo Kiro activa la skill automáticamente — debe ser específica e incluir palabras clave relevantes
- Las instrucciones deben ser accionables y directas
- Si la skill necesita crear archivos con contenido extenso, ese contenido va dentro del mismo `SKILL.md` en una sección separada
- Una skill = una carpeta = un `SKILL.md`, nada más dentro de la carpeta

## Estructura de referencia

```
.kiro/skills/
├── crear-skill/
│   └── SKILL.md    ← esta skill
├── molde-cv/
│   └── SKILL.md
└── <nueva-skill>/
    └── SKILL.md
```
