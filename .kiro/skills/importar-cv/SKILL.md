---
name: importar-cv
description: Llena el archivo datos/cv-molde.md extrayendo información de un CV existente del usuario. Usar cuando el usuario tenga un CV previo y quiera importarlo, transferir su CV, llenar el molde desde un CV existente, o migrar su información desde otro CV.
---

## Tarea

Extrae la información de un CV existente del usuario y llena `datos/cv-molde.md` con ella, preguntando solo cuando falten datos.

### Paso 1 — Verificar que el molde existe

- Busca el archivo `datos/cv-molde.md`.
- Si **no existe**, indica:
  > "No encontré `datos/cv-molde.md`. Primero ejecuta `/molde-cv` para crear la estructura base."
  Detente aquí.

### Paso 2 — Preguntar el nombre del usuario

Pregunta:
> "¿Cuál es tu nombre completo tal como aparece en tu CV original?"

Espera la respuesta. Usarás este nombre para buscar el CV y para identificar al usuario durante todo el proceso.

### Paso 3 — Localizar el CV original

- Busca en el workspace archivos que puedan ser el CV del usuario: `.tex`, `.pdf`, `.md`, `.docx`, `.txt`, o carpetas con su nombre.
- Si encuentras más de uno, pregunta al usuario cuál usar.
- Lee el contenido del archivo encontrado.

### Paso 4 — Extraer y llenar lo que puedas

- Recorre cada sección del molde (`datos/cv-molde.md`) e intenta mapear la información extraída del CV.
- **Regla estricta: no inventes ni supongas datos.** Solo escribe lo que está explícitamente en el CV.
- Llena todos los campos que puedas con la información disponible.

### Paso 5 — Preguntar por lo que falta, de a uno

- Por cada campo que no pudiste llenar porque no estaba en el CV, pregunta al usuario **de a una pregunta a la vez**.
- Espera la respuesta antes de pasar al siguiente campo faltante.
- Si el usuario responde "no aplica" o similar, deja el campo en blanco.
- Ejemplo:
  > "No encontré tu número de teléfono en el CV. ¿Cuál es?"
  → espera respuesta → siguiente campo faltante

### Paso 6 — Guardar y confirmar

- Una vez completados todos los campos posibles, guarda el archivo `datos/cv-molde.md` con toda la información recopilada.
- Confirma al usuario:
  > "✓ El molde fue llenado con la información de tu CV. Puedes revisarlo en `datos/cv-molde.md`."

- Sin preguntas innecesarias
- Confirmar al usuario cuando termine
