---
name: agregar-experiencia
description: Agrega nuevas entradas al CV del usuario como proyectos, habilidades, logros, referencias, notas o experiencia laboral, siguiendo la estructura del molde. Usar cuando el usuario quiera agregar un proyecto, agregar habilidad, agregar tecnología, agregar logro, agregar referencia, agregar experiencia, o añadir algo nuevo al CV.
---

## Tarea

Ayuda al usuario a agregar una nueva entrada a su archivo `datos/cv-molde.md` de forma conversacional, preguntando de a una pregunta a la vez.

### Paso 1 — Verificar que el molde esté lleno

- Lee el archivo `datos/cv-molde.md`.
- Si **no existe**, indica:
  > "No encontré `datos/cv-molde.md`. Primero debes ejecutar `/llenar-molde` para completar tu información base."
  Detente aquí.
- Si existe pero está **mayormente vacío** (los campos clave como Nombre, Correo, Perfil no tienen valor), indica:
  > "El molde existe pero parece que aún no está lleno. Te recomiendo ejecutar `/llenar-molde` primero."
  Detente aquí.

### Paso 2 — Preguntar qué sección quiere agregar

Pregunta al usuario:

> "¿Qué quieres agregar? Elige una opción:
> 1. Proyecto
> 2. Experiencia laboral
> 3. Habilidades técnicas
> 4. Logro o premio
> 5. Referencia
> 6. Idioma
> 7. Nota adicional"

Espera la respuesta antes de continuar.

### Paso 3 — Llenar el mini-molde de la sección elegida

Según la opción elegida, usa el mini-molde correspondiente de la sección **Mini-Moldes** de este archivo.

Haz **una pregunta a la vez**, espera la respuesta, y luego pasa a la siguiente. No lances todas las preguntas juntas.

Ejemplo:
- "¿Cuál es el nombre del proyecto?" → espera respuesta
- "¿En qué año o rango de fechas lo desarrollaste?" → espera respuesta
- Y así sucesivamente hasta completar todos los campos del mini-molde.

Si un campo no aplica, el usuario puede responder "no aplica" o dejarlo en blanco.

### Paso 4 — Agregar la entrada al archivo

- Una vez recopilados todos los datos, agrega el nuevo bloque al final de la sección correspondiente en `datos/cv-molde.md`.
- Usa el formato exacto del mini-molde, numerando el bloque de forma incremental (Proyecto 3, Experiencia 3, etc.).
- Confirma al usuario:
  > "✓ Agregado correctamente a `datos/cv-molde.md`. ¿Quieres agregar algo más?"

- Sin preguntas innecesarias
- Confirmar al usuario cuando termine

---

## Mini-Moldes

### Proyecto

```
--- Proyecto N ---
Nombre:
Año / Rango de fechas:
Estado (En desarrollo / Finalizado / En curso):
Descripción:
Tecnologías usadas:
Repositorio backend:
Repositorio frontend:
URL demo / deploy:
```

### Experiencia laboral

```
--- Experiencia N ---
Empresa:
Rol / Cargo:
Fecha inicio:
Fecha fin:
Estado (En curso / Finalizado):
Descripción:
Tecnologías usadas:
```

### Habilidades técnicas

```
Dominio principal:
Bases de datos:
Servidores / Deploy:
DevOps / Herramientas:
Frontend:
Otros / Extras:
```

> Nota: Esta sección no se duplica, se actualiza. Pregunta campo por campo cuáles quiere modificar o agregar.

### Logro o premio

```
--- Logro N ---
Año:
Título del logro:
Evento / Organización:
URL certificado / publicación:
```

### Referencia

```
--- Referencia N ---
Nombre:
Cargo / Rol:
Institución:
Teléfono:
Correo:
```

### Idioma

```
--- Idioma N ---
Idioma:
Nivel:
Certificación (si aplica):
```

### Nota adicional

```
Notas: <texto libre del usuario>
```

> Nota: Esta sección se concatena al contenido existente en Notas, no se reemplaza.
