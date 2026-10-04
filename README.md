# Wiki de mis historias

Sitio estático (HTML + CSS + JS) para publicar en **GitHub Pages**. No necesitas instalar nada.

## Cómo publicarlo
1. Sube todo el contenido de esta carpeta a tu repositorio de GitHub.
2. En el repositorio: **Settings > Pages > Deploy from a branch > main / (root)**.
3. En un par de minutos tendrás el link `https://TU-USUARIO.github.io/TU-REPO/`.

> No abras `index.html` con doble clic: el navegador bloquea la carga de los `.json`.
> Para probar en tu PC usa la extensión **Live Server** de VS Code.

## Qué editar (todo está en `data/`)
| Archivo | Para qué sirve |
|---|---|
| `config.json` | Título, bienvenida, imagen de fondo del inicio y redes |
| `noticias.json` | Actualizaciones (la más reciente sale primero) |
| `historias.json` | Tus historias: enlaces (Wattpad, YouTube), época, orden cronológico, conexiones y posición en el mapa |
| `personajes.json` | Personajes de todas las historias |
| `media.json` | Openings, canciones y videos |

### Agregar una historia
Copia un bloque de `historias.json` y cambia `id`, `titulo`, etc.
- `orden`: número para la cronología (1 = la primera).
- `conexiones`: historias relacionadas (se dibuja una línea en el mapa). Forma simple: `["estrellas"]`. Con aviso de lectura:
  `{ "id": "estrellas", "tipo": "antes", "nota": "Lee primero esta." }`
  Valores de `tipo`: `antes` (Léela antes), `despues` (Léela después), `paralela`, `relacionada`. La nota se muestra en el panel del mundo.
- `mapa`: `x` e `y` en % (0 a 100) para colocar el mundo en el mapa. Si lo omites se coloca solo.

### Agregar un personaje
Copia un bloque de `personajes.json`. El campo `historia` debe coincidir con el `id` de una historia; así aparece en su lista.
- `opiniones`: una entrada por cada personaje del que opina. `dialogos` es una lista: pon 1 frase o varias.
- `target_id` puede ser un personaje de otra historia.

### Videos de YouTube
En `media.json`, si el enlace es `https://www.youtube.com/watch?v=ABC123xyz_9`, pon `"youtube_id": "ABC123xyz_9"`. Se abre en un reproductor dentro de la página y la miniatura se toma sola. Si dejas `youtube_id` vacío, abre el `url` en otra pestaña.

## Imágenes (carpeta `imagenes/`)
- `fondos/`: fondo del inicio (`inicio.jpg`) y fondos por historia. Se ven semitransparentes.
- `historias/`: icono redondo (cuadrado, 256x256) y portada (16:9).
- `personajes/`: avatar cuadrado (256x256).
- `arte/`: arte grande del personaje, ideal PNG con fondo transparente y vertical (aprox. 1000x1400).

Si falta una imagen, la página muestra un cuadro con las iniciales, así que no se rompe.
