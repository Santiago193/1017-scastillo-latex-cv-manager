---
name: adaptar-cv
description: Adapta el curriculum base del usuario a una oferta de trabajo específica, creando una nueva carpeta en cvs/ con el CV personalizado. Usar cuando el usuario quiera adaptar su CV a una oferta, postularse a un trabajo, crear un CV para una empresa, o aumentar las probabilidades de ser seleccionado para una posición.
---

## Tarea

Sigue estos pasos en orden:

### Paso 1 — Verificar que existe el molde

- Lee el archivo `datos/cv-molde.md`
- Si NO existe o está vacío, detente y dile al usuario:
  > "No encontré tu molde de datos. Ejecuta el comando `/molde-cv` primero para preparar tu información base."
- Si existe y tiene datos, continúa.

### Paso 2 — Verificar que el molde tiene datos suficientes

- Revisa que al menos los campos de Nombre, Perfil Profesional, Habilidades Técnicas y Experiencia o Proyectos estén completos.
- Si están mayormente vacíos, avisa al usuario:
  > "Tu molde está casi vacío. Usa `/llenar-molde` para completar tu información antes de adaptar el CV."
- Si tiene datos suficientes, continúa.

### Paso 3 — Crear la nueva carpeta del CV

- Lista las carpetas dentro de `cvs/` para determinar el siguiente número correlativo (001, 002, 003…).
  - Cuenta cuántas carpetas existen actualmente y suma 1 para el nuevo número.
  - Formato del número: 3 dígitos con ceros a la izquierda (001, 002, etc.)
- Pide al usuario el nombre corto de la empresa o posición (si aún no lo mencionó).
- Construye el nombre de carpeta: `<NNN><empresa-o-puesto>` en minúsculas sin espacios, usando guiones si hace falta. Ejemplos: `001dinners`, `002ndeveloper`, `003backenddev`.
- Copia recursivamente toda la carpeta `cvs/CV_Metrica_FullStack/` a `cvs/<nueva-carpeta>/`.
  - Usa el comando: `Copy-Item -Recurse cvs/CV_Metrica_FullStack cvs/<nueva-carpeta>`

### Paso 4 — Pedir la oferta de trabajo

Pregunta al usuario:
> "Perfecto. Ahora pega aquí la oferta de trabajo (descripción del puesto, requisitos, tecnologías buscadas, nombre de la empresa, etc.) y esperaré tu respuesta antes de continuar."

Espera la respuesta del usuario antes de continuar.

### Paso 5 — Adaptar el CV a la oferta

Con la oferta recibida, edita el archivo `cvs/<nueva-carpeta>/Minimal-CV.tex` aplicando estas reglas **usando solo la información disponible en `datos/cv-molde.md`** — no inventar ni agregar información falsa:

- **Título / Enfoque (header):** Ajusta el título debajo del nombre para que coincida con el rol buscado. Usa términos de la oferta si el perfil lo respalda.
- **Perfil Profesional:** Reescribe el párrafo destacando las tecnologías y habilidades que la oferta menciona y que el candidato posee. Usa palabras clave de la oferta.
- **Habilidades Técnicas:** Reordena las habilidades poniendo primero las más relevantes para la oferta. No elimines habilidades, solo reordena y reorganiza por relevancia.
- **Experiencia:** Si hay experiencias, resalta en las descripciones los aspectos más alineados con la oferta (sin cambiar hechos, solo énfasis).
- **Proyectos:** Si hay proyectos relevantes para la oferta, ponlos primero. Si algún proyecto es claramente irrelevante y hay poco espacio, puede omitirse (solo si hay más de 2 proyectos).
- **No toques:** referencias, logros, educación, idiomas, contacto, ni la estructura/formato LaTeX.

### Paso 6 — Confirmar al usuario

Al finalizar, informa:
> "✅ CV adaptado creado en `cvs/<nueva-carpeta>/`
> Compila `Minimal-CV.tex` con XeLaTeX o overleaf para generar el PDF."

Indica brevemente los 2-3 cambios principales que hiciste al CV para esa oferta.
