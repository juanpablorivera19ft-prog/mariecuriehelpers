[README.md](https://github.com/user-attachments/files/33445786/README.md)
# Marie Curie Helpers

Plataforma abierta para que estudiantes que faltan a clase (deportistas, enfermos o quienes no entendieron un tema) puedan ponerse al día con la grabación, un resumen generado con IA, material de práctica y una evaluación corta.

Proyecto del grado 10B · Prueba de concepto (PoC).

## Qué incluye

- **Inicio:** cuadrícula de clases y barra lateral por materia.
- **Video y resumen:** reproductor con onda de audio y resumen de la clase.
- **Subir archivos:** crea una clase nueva con "＋ Subir una clase nueva" o agrega archivos (audio, video, imágenes, PDF) en la pestaña **Archivos** de cada clase. Si subes un audio o video, se reproduce en "Video y resumen". Los archivos se guardan en el navegador (IndexedDB), no en un servidor.
- **Práctica:** videos y enlaces recomendados.
- **Evaluar:** preguntas de selección múltiple (A, B, C) con calificación.
- **Mi proceso:** calificación con caritas de 1 a 5.

Sin dependencias ni servidor: HTML, CSS y JavaScript puro.

## Cómo usarlo

Abre `index.html` en el navegador, o sírvelo con cualquier servidor estático:

```bash
python3 -m http.server 8000
```

Para publicarlo gratis, sube la carpeta a GitHub y activa GitHub Pages.

## Agregar clases reales

Edita `data.js`. Cada clase tiene materia, título, fecha, resumen, recursos y preguntas. Para usar audio real, pon el archivo en una carpeta `grabaciones/` y escribe `media: "grabaciones/mi-clase.mp3"`.

## Flujo de trabajo (pipeline)

```
Dispositivo (cámara + micrófono, a 2.2 m de altura)
   → Servidor recibe la grabación
   → Transcripción (p. ej. Whisper)
   → Resumen y preguntas con un modelo de IA
   → Se publican en este sitio (data.js o una API)
```

Esta PoC implementa la última parte (la interfaz). Los pasos de captura, transcripción y resumen se conectan reemplazando el contenido de `data.js` por una llamada a tu API.

## Roles del equipo

- Juan Andrés Niño: prueba de concepto de la cámara y el prototipo.
- Juan Pablo Rivera Duque: diseño del software y código abierto.
- Jerónimo Salazar Díaz: diseño del prototipo físico.

## Licencia

MIT. Ver `LICENSE`.
