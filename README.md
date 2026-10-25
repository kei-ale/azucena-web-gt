# Azucena 🩺

**Sitio web educativo sobre diabetes tipo 2**, pensado para personas adultas mayores (50+). Explica la enfermedad, los medicamentos, el uso del glucómetro y las emergencias con palabras sencillas, cápsulas cortas, juegos y un chat guiado.

Es un proyecto **autocontenido**: todo el HTML, CSS y JavaScript vive en un solo archivo (`index.html`), sin frameworks, sin build step y sin backend.

---

## Contenido

- [Demo rápida](#demo-rápida)
- [Características](#características)
- [Secciones del sitio](#secciones-del-sitio)
- [Cápsulas educativas](#cápsulas-educativas)
- [Juegos](#juegos)
- [Chat educativo](#chat-educativo)
- [Infografías y video](#infografías-y-video)
- [Estructura del proyecto](#estructura-del-proyecto)
- [Cómo ejecutarlo](#cómo-ejecutarlo)
- [Publicarlo en GitHub Pages](#publicarlo-en-github-pages)
- [Personalizar el contenido](#personalizar-el-contenido)
- [Tecnología](#tecnología)
- [Accesibilidad](#accesibilidad)
- [Persistencia de datos](#persistencia-de-datos)
- [Aviso importante](#aviso-importante)

---

## Demo rápida

Abra `index.html` en cualquier navegador moderno (Chrome, Edge, Firefox o Safari). No requiere instalación ni servidor.

> Las tipografías se cargan desde Google Fonts. Sin conexión, el sitio sigue funcionando con las fuentes del sistema.

---

## Características

- **4 secciones navegables:** Inicio, Aprender, Juegos y Chat.
- **10 cápsulas educativas** con contenido, consejos y advertencias.
- **4 juegos** con instrucciones, temporizador, comodines y estrellas.
- **Chat por temas** con más de 30 respuestas y búsqueda por palabras clave.
- **Botón SOS** siempre visible, con números de emergencia.
- **Progreso guardado** en el navegador (cápsulas vistas, estrellas y mejores puntajes).
- **Tamaño de letra ajustable** (14 px a 24 px) que se recuerda entre visitas.
- **Sonido activable/desactivable**, generado con Web Audio API (sin archivos de audio).
- **Vibración** en móvil al responder.
- **Diseño responsive** y respeto por `prefers-reduced-motion`.
- **Sin dependencias externas** salvo Google Fonts.

---

## Secciones del sitio

| Sección | Qué contiene |
|---|---|
| **Inicio** | Bienvenida, estadísticas de progreso, acceso a la siguiente cápsula, juegos y chat. |
| **Aprender** | Listado de las 10 cápsulas y vista de detalle con infografía, contenido y acciones. |
| **Juegos** | Los 4 juegos con pantalla de instrucciones antes de empezar. |
| **Chat** | Asistente "Azucena" con menú de temas, burbujas de conversación y búsqueda libre. |

---

## Cápsulas educativas

| # | Cápsula | Tema | Infografía |
|---|---|---|---|
| 1 | Que es la diabetes tipo 2 | Insulina, causas y control | ✅ `Que es la diabetes tipo 2.jpeg` |
| 2 | Mis metas de control | Cifras de glucosa, HbA1c y presión | — |
| 3 | Alimentacion y el plato | Método del plato y bebidas | ✅ `Alimentacion y el plato.jpeg` |
| 4 | Mis medicamentos | Metformina, semaglutida, insulina y más | ✅ `Mis medicamentos.jpeg` |
| 5 | Azucar baja (hipoglucemia) | Señales y regla del 15 | — |
| 6 | Cuidado de los pies | Revisión diaria y calzado | — |
| 7 | Ejercicio y movimiento | Meta de 150 minutos semanales | — |
| 8 | Rinones, higado y presion | Complicaciones silenciosas | — |
| 9 | Dias de enfermedad | Qué hacer con gripe, vómitos o diarrea | — |
| 10 | Vivir con diabetes | Bienestar emocional y apoyo | — |

Cada cápsula incluye secciones con explicación, listas, **Consejo** y **Cuidado**, además de un juego relacionado cuando aplica.

---

## Juegos

| Juego | Descripción | Preguntas |
|---|---|---|
| **Semáforo del azúcar** | Clasificar valores del glucómetro en bajo / en meta / alto. | 6 |
| **Arme su plato** | Ubicar alimentos en el plato saludable. | 8 |
| **¿Cómo se toma mi medicina?** | Elegir la forma correcta de usar cada medicamento. | 7 |
| **¿Qué hago si…?** | Resolver situaciones reales del día a día. | 6 |

Cada partida incluye temporizador de 20 segundos, comodín **50/50**, comodín **Pista**, puntaje y calificación de 1 a 3 estrellas.

---

## Chat educativo

El chat funciona **sin servidor ni IA externa**. Las respuestas están escritas en el propio código y se navegan con botones o escribiendo palabras clave.

Temas principales: qué es la diabetes, metas, HbA1c, exámenes, glucómetro, medicamentos (metformina, semaglutida, empagliflozina, glibenclamida, insulina), hipoglucemia, riñones, hígado, presión, alimentación, ejercicio, pies, días de enfermedad y apoyo emocional.

Incluye un aviso legal visible: la información es educativa y **no reemplaza** la consulta médica.

---

## Infografías y video

### Infografías

Cada cápsula busca automáticamente una imagen en la misma carpeta del HTML con **el nombre exacto de la cápsula + `.jpeg`**:

```
Que es la diabetes tipo 2.jpeg
Alimentacion y el plato.jpeg
Mis medicamentos.jpeg
```

- Si la imagen existe, aparece la sección **Infografía** con su pie de foto.
- Si **no** existe, la sección se oculta por completo (no se muestra un recuadro vacío).
- Para agregar una infografía a otra cápsula, solo copie el archivo `.jpeg` con el nombre exacto del título.

> El nombre debe coincidir con el campo `title` de la cápsula en `CAPSULES`. Los espacios se codifican automáticamente.

### Video

La sección **Video** está habilitada únicamente en la cápsula **Mis medicamentos**. La URL aún no está definida, por lo que se muestra un recuadro de *"Video pendiente"*.

Para agregarla, busque en `index.html` el comentario:

```js
/* ============================================================
   >>> AGREGA AQUI LA URL DEL VIDEO DE "MIS MEDICAMENTOS" <<<
   ============================================================ */
video:{
  url:'', // <-- PEGA AQUI LA URL DEL VIDEO
  title:'Video: Como tomar metformina'
},
```

Pegue un enlace normal de YouTube (`https://www.youtube.com/watch?v=...`) o uno tipo `embed`. El código convierte el enlace automáticamente.

---

## Estructura del proyecto

```
pag/
├── index.html                          # Sitio completo (HTML + CSS + JS)
├── Que es la diabetes tipo 2.jpeg      # Infografía de la cápsula 1
├── Alimentacion y el plato.jpeg        # Infografía de la cápsula 3
├── Mis medicamentos.jpeg               # Infografía de la cápsula 4
├── README.md                           # Este archivo
├── deepseek_markdown_20261024_e69f68.md # Brief técnico de referencia
└── deepseek_html_20261024_f2f1d4.html.bak # Respaldo de una versión anterior
```

---

## Cómo ejecutarlo

### Opción 1: abrir el archivo

Doble clic en `index.html`. Funciona directamente desde el sistema de archivos.

### Opción 2: servidor local (recomendado para probar rutas)

```bash
# Python 3
python -m http.server 8000

# o con Node.js
npx serve .
```

Luego abra `http://localhost:8000`.

> Con `file://` las imágenes también cargan correctamente, pero un servidor local reproduce mejor el comportamiento de producción.

---

## Publicarlo en GitHub Pages

1. Suba el repositorio a GitHub.
2. Vaya a **Settings → Pages**.
3. En *Source*, seleccione la rama `main` y la carpeta `/ (root)`.
4. Guarde y espere unos minutos: el sitio quedará en `https://<usuario>.github.io/<repositorio>/`.

El archivo debe llamarse `index.html` y las imágenes `.jpeg` deben quedar en la misma carpeta.

---

## Personalizar el contenido

Todo se edita dentro del `<script>` de `index.html`.

| Qué cambiar | Dónde buscar |
|---|---|
| Cápsulas (título, resumen, contenido, juego relacionado) | `const CAPSULES = [` |
| Pie de foto de cada infografía | campo `infographic:{caption:'...'}` |
| Video de "Mis medicamentos" | comentario `AGREGA AQUI LA URL DEL VIDEO` |
| Juegos (preguntas, respuestas, explicaciones) | `const GAMES = {` |
| Temas y respuestas del chat | `const N = {` y `const MENU` |
| Números de emergencia | `const EMERG` |
| Colores y tipografías | variables CSS en `:root` |
| Límites de tamaño de letra | funciones de los botones `A+` / `A-` (`Math.min(24, …)` y `Math.max(14, …)`) |

### Agregar una cápsula nueva

```js
{
  id:'mi-capsula', icon:'X', title:'Mi capsula',
  summary:'Resumen corto.',
  infographic:{caption:'Pie de foto opcional'},
  sections:[
    {h:'Titulo de seccion', p:'Explicacion.', tip:'Consejo opcional.'}
  ],
  relatedGame:null
}
```

Si además crea `Mi capsula.jpeg` en la carpeta, la infografía aparecerá sola.

---

## Tecnología

- **HTML5 + CSS3 + JavaScript vanilla (ES6)** en un solo archivo.
- **Google Fonts:** *Atkinson Hyperlegible* (texto) y *Baloo 2* (títulos).
- **Web Audio API** para los sonidos de acierto, error, clic y victoria.
- **Vibration API** para respuesta háptica en móvil.
- **localStorage** para guardar el progreso.
- **Sin** frameworks, bundlers, backend ni base de datos.

---

## Accesibilidad

- Tipografía de alta legibilidad (*Atkinson Hyperlegible*), diseñada para baja visión.
- Botones grandes, alto contraste y áreas táctiles amplias.
- Control de tamaño de letra persistente (14–24 px).
- Etiquetas `aria-label`, `aria-pressed`, `role="tab"` y texto para lectores de pantalla (`.sr-only`).
- Estados `:focus-visible` bien definidos para navegación con teclado.
- Animaciones reducidas automáticamente con `prefers-reduced-motion`.
- Lenguaje sencillo, sin tecnicismos innecesarios.

---

## Persistencia de datos

El progreso se guarda solo en el navegador del usuario (no se envía a ningún servidor):

| Clave | Contenido |
|---|---|
| `azu-capsulesViewed` | IDs de cápsulas vistas |
| `azu-totalStars` | Estrellas acumuladas |
| `azu-bestScores` | Mejor puntaje por juego |
| `azu-fs` | Tamaño de letra elegido |

Si el usuario borra los datos del navegador, el progreso se reinicia.

---

## Aviso importante

Este sitio ofrece **educación general** basada en los Estándares de Atención en Diabetes de la ADA 2026. **No sustituye** el diagnóstico, tratamiento ni consejo de un médico o farmacéutico.

Los números de emergencia mostrados corresponden a Guatemala: **Bomberos Voluntarios 122**, **Bomberos Municipales 123** y **Cruz Roja 125**. Ajústelos si el sitio se usa en otro país.

---

Hecho con cariño para que aprender sobre diabetes sea más fácil. 💚
