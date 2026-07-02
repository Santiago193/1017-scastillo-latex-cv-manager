---
name: cv-en
description: Traduce un CV existente en LaTeX a otro idioma. Pide la carpeta del CV a traducir y el idioma destino, luego genera una nueva carpeta con el archivo .tex completamente traducido. Usar cuando tengas un CV y necesites su versión en otro idioma (inglés, francés, alemán, etc.) para postularte a ofertas internacionales.
---

## Tarea

1. Pregunta al usuario: **¿Qué carpeta de CV quieres traducir?** (muestra las carpetas disponibles dentro de `cvs/` para que elija)

2. Pregunta al usuario: **¿A qué idioma quieres traducirlo?** (inglés, francés, alemán, italiano, portugués, etc.)

3. Lee el archivo `Minimal-CV.tex` de la carpeta elegida.

4. Determina el sufijo de la nueva carpeta según el idioma (EN para inglés, FR para francés, DE para alemán, IT para italiano, PT para portugués, etc.). Crea la nueva carpeta en `cvs/` usando el nombre de la carpeta origen más el sufijo. Ejemplo: `CV_Empresa_FullStack` → `CV_Empresa_FullStack_EN`. Si ya existe, añade un número al final.

5. Copia toda la estructura de la carpeta origen (subcarpetas `icons/`, `flags/`, `images/` y todos sus archivos) a la nueva carpeta.

6. Traduce el contenido textual del `.tex` al idioma destino:
   - Títulos de sección (Experiencia, Educación, Habilidades, Idiomas, Proyectos, Referencias, etc.)
   - Descripciones de trabajos, proyectos y logros
   - Perfil profesional / resumen
   - Nombres de meses y formatos de fecha según el idioma destino
   - Mantén intactos todos los comandos LaTeX, rutas de archivos, nombres propios, nombres de empresas, tecnologías y URLs

7. Guarda el archivo traducido como `Minimal-CV.tex` en la nueva carpeta.

8. Confirma al usuario indicando la ruta de la nueva carpeta y recuérdales que pueden compilar con `xelatex Minimal-CV.tex` o subir a Overleaf.

- Sin preguntas innecesarias más allá de elegir la carpeta y el idioma
- Confirmar al usuario cuando termine con la ruta exacta del nuevo CV
