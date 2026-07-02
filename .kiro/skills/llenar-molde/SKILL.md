---
name: llenar-molde
description: Guía al usuario para llenar paso a paso el archivo datos/cv-molde.md con su información personal y profesional. Usar cuando el usuario quiera completar su CV, llenar el molde, rellenar sus datos, o preparar su información para el CV.
---

## Tarea

Ayuda al usuario a llenar el archivo `datos/cv-molde.md` de forma conversacional, sección por sección.

### Paso 1 — Verificar que existe el molde

- Busca el archivo `datos/cv-molde.md` en el workspace.
- Si **no existe**, informa al usuario:
  > "No encontré el archivo `datos/cv-molde.md`. Primero debes ejecutar `/molde-cv` para crear la estructura base."
  Detente aquí y no continúes hasta que el archivo exista.

### Paso 2 — Leer el contenido del molde

- Lee el archivo `datos/cv-molde.md` completo.
- Identifica todas las secciones y campos que están vacíos o con texto de ejemplo/placeholder.

### Paso 3 — Hacer preguntas al usuario, poco a poco

- Recorre el molde sección por sección, **no todo de golpe**.
- Por cada sección, haz las preguntas relevantes de forma natural y conversacional.
- Espera la respuesta del usuario antes de pasar a la siguiente sección.
- Ejemplo de orden típico:
  1. Datos personales (nombre, email, teléfono, ubicación, etc.)
  2. Perfil profesional o resumen
  3. Experiencia laboral (empresa por empresa)
  4. Educación
  5. Habilidades y tecnologías
  6. Idiomas
  7. Proyectos destacados (si aplica)
  8. Otros campos que encuentres en el molde

### Paso 4 — Ir actualizando el archivo

- Después de recibir las respuestas de cada sección, actualiza inmediatamente esa parte en `datos/cv-molde.md`.
- Confirma al usuario qué se guardó antes de continuar con la siguiente sección.

### Paso 5 — Confirmar al terminar

- Cuando todas las secciones estén llenas, informa al usuario:
  > "✓ El molde está completo. Tu información quedó guardada en `datos/cv-molde.md` y está lista para generar el CV."

- Sin preguntas innecesarias
- Confirmar al usuario cuando termine
