# Perfumería Monterrey

Sitio web de una sola página para Perfumería Monterrey — Elixir Parfum.
HTML estático, sin dependencias ni build. Se publica tal cual.

## Contenido del repo

```
index.html         Página completa (CSS y JS incluidos, logo en base64)
hero.mp4           Video de fondo de la portada — 8 s, loop, sin audio
hero.webm          Misma toma en VP9, para navegadores que lo prefieran
hero-poster.jpg    Imagen fija mientras carga el video
```

## Publicar con GitHub Pages

1. Sube estos archivos a la raíz del repositorio.
2. En GitHub: **Settings → Pages → Source: Deploy from a branch**, rama `main`, carpeta `/ (root)`.
3. En un par de minutos queda en `https://<usuario>.github.io/<repo>/`.

Para dominio propio, agrega un archivo `CNAME` con tu dominio y apunta el DNS a GitHub Pages.

## El video de la portada

Loop de 8 s a 1280x720, sin corte visible al repetirse. Bruma dorada, motas de polvo y un barrido de luz. Sin audio.

- Arranca solo, en silencio y en bucle (`autoplay muted loop playsinline`).
- Se pausa cuando la portada sale de pantalla, para ahorrar batería.
- Si el navegador bloquea el autoplay, arranca al primer toque o scroll.
- Si el sistema del visitante tiene activado *reducir movimiento*, se muestra sólo la imagen fija.
- Lleva encima un velo oscuro: el texto blanco mantiene **7.2:1** de contraste (WCAG AAA) incluso en el fotograma más brillante.

Para cambiarlo por metraje real, reemplaza los tres archivos conservando los nombres. Recomendado: 8–12 s, sin audio, menos de 3 MB, tomas oscuras.

## Editar el contenido

**Productos** — al final de `index.html`, en los arreglos `topVentas` y `novedades`:

| Campo | Significado |
|-------|-------------|
| `n`   | Nombre del producto |
| `insp`| Línea descriptiva ("Inspirado en…") |
| `r`   | Número de reseñas |
| `p`   | Precio en MXN |
| `a`   | Precio anterior (`0` = sin descuento) |
| `etq` | Etiqueta: `Nuevo`, `Top ventas`, `Agotándose` o vacío |

**Imágenes de producto** — hoy son gráficos SVG generados por la función `frasco()`. Sustitúyela por etiquetas `<img>` cuando tengas fotos reales.

**Colores** — variables CSS al inicio del archivo (`--oro`, `--negro`, `--crema`, …).

**Logo** — incrustado en base64 (portada, sección de misión, pie y favicon).

## Antes de publicar

> **Cifras y textos de ejemplo.** Los datos de la página son ficticios: 180 mil clientes, 12,400 reseñas, los testimonios, las sucursales y los precios. Reemplázalos por información real — publicar cifras falsas puede constituir publicidad engañosa ante la PROFECO.

> **Marcas de terceros.** Los nombres del tipo "Inspirado en Baccarat Rouge 540" son marcas registradas de otras empresas. Es práctica común en el sector de alternativas, pero conlleva riesgo legal. Conviene revisarlo con un abogado antes de vender.
