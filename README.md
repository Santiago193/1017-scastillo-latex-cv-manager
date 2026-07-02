# CV Builder con Kiro

Sistema para gestionar y adaptar tu curriculum vitae usando Kiro como asistente. El flujo está diseñado para mantener toda tu información en un único molde central y generar versiones personalizadas del CV para cada oferta de trabajo, sin repetir datos ni modificar el original.

El CV base usa LaTeX (plantilla Minimal-CV) y se compila con XeLaTeX, LuaLaTeX u Overleaf.

---

## Estructura del proyecto

```
├── datos/
│   ├── cv-molde.md           # Tu información base (única fuente de verdad) — no se sube al repo
│   └── cv-molde-ejemplo.md   # Ejemplo con datos ficticios para referencia
├── cvs/
│   ├── CV_Metrica_FullStack/ # CV base usado como plantilla LaTeX
│   ├── 001empresa/           # CV adaptado para oferta 1
│   ├── 001empresa_EN/        # CV traducido al inglés
│   └── 002empresa/           # CV adaptado para oferta 2
├── original/                 # Plantilla LaTeX original sin modificar
└── .kiro/skills/             # Skills (comandos) de Kiro
```

---

## Comandos disponibles

### `/llenar-molde`
Guía al usuario para completar `datos/cv-molde.md` sección por sección de forma conversacional. Hace las preguntas de a una, espera las respuestas y va guardando el archivo a medida que avanza.

**Úsalo cuando:** quieras completar o actualizar tu información base por primera vez.

---

### `/importar-cv`
Extrae la información de un CV existente (`.tex`, `.pdf`, `.md`, `.docx`) y llena automáticamente `datos/cv-molde.md`. Solo pregunta por los campos que no encontró en el CV original.

**Úsalo cuando:** ya tengas un CV hecho y quieras migrarlo al sistema sin escribir todo desde cero.

---

### `/agregar-experiencia`
Agrega nuevas entradas al molde: proyectos, experiencia laboral, habilidades, logros, referencias o idiomas. Hace las preguntas necesarias y escribe el bloque en la sección correcta del molde.

**Úsalo cuando:** consigas un nuevo trabajo, termines un proyecto, ganes un premio, o quieras actualizar cualquier sección del molde.

---

### `/adaptar-cv`
Toma tu molde como base, crea una nueva carpeta en `cvs/` con numeración automática (001, 002, 003…), pide la oferta de trabajo y adapta el CV para maximizar las chances de quedar seleccionado. Ajusta el título, perfil profesional, orden de habilidades y énfasis en experiencia/proyectos según lo que busca la empresa.

**Úsalo cuando:** quieras postularte a una oferta de trabajo específica.

> **Importante:** solo usa información real del molde. Nunca inventa ni agrega datos falsos.

---

### `/cv-en`
Traduce un CV existente al idioma que elijas. Pide la carpeta del CV a traducir y el idioma destino (inglés, francés, alemán, italiano, etc.), copia la estructura completa y genera un nuevo `Minimal-CV.tex` con todo el contenido textual traducido, manteniendo intactos los comandos LaTeX, nombres propios y tecnologías.

**Úsalo cuando:** tengas un CV y necesites su versión en otro idioma para postularte a ofertas internacionales.

---

### `/crear-skill`
Crea una nueva skill de Kiro con la estructura correcta. Pregunta el nombre, qué debe hacer y los pasos, y genera la carpeta `.kiro/skills/<nombre>/SKILL.md` lista para usar.

**Úsalo cuando:** quieras automatizar una tarea nueva o agregar un comando personalizado al sistema.

---

## Flujo recomendado

```
Primera vez
    └── /importar-cv      (si tienes un CV previo en .tex, .pdf, .md, .docx)
        o /llenar-molde   (si empiezas desde cero)

Mantener el molde actualizado
    └── /agregar-experiencia   (nuevo trabajo, proyecto, logro, habilidad, etc.)

Postularte a una oferta
    └── /adaptar-cv   → pegar oferta → compilar PDF

Necesitas el CV en otro idioma
    └── /cv-en   → elegir carpeta → elegir idioma → compilar PDF
```

---

## Compilar el PDF

Cada carpeta en `cvs/` contiene un `Minimal-CV.tex`. Para generar el PDF:

- **Overleaf:** sube la carpeta y compila desde la interfaz web
- **Local:** `xelatex Minimal-CV.tex` o `lualatex Minimal-CV.tex`

Asegúrate de que las carpetas `icons/`, `flags/` e `images/` estén junto al `.tex` al compilar.
