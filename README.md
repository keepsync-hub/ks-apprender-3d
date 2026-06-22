# ks-apprender-3d

**Aprender Jugando 3D** — versión en primera persona (POV 3D) del juego educativo
*Aprender Jugando*. Conserva **exactamente las mismas reglas** que la versión 2D
(aldeanos que dan pistas, las palabras como moneda y arma, tienda, combate, jefe
con palabras de letras faltantes, logros, repaso espaciado y viaje entre islas);
lo único que cambia es que ahora **recorres el mapa en 3D**, en primera persona.

Todo vive en un único archivo: [`index.html`](index.html). Ábrelo en el navegador.

## Jugar

- **Avanzar / retroceder:** `▲ ▼` del pad o `W` / `S`
- **Girar:** `◀ ▶` del pad o `A` / `D`
- **Mirar alrededor:** arrastra (ratón o dedo) sobre el mundo 3D
- **Interactuar:** acércate a un personaje y pulsa `E` o el botón dorado
- **Menú de viaje:** `M` · **Cerrar diálogos:** `Esc`
- **En los retos:** `1`–`4` para elegir respuesta, `Enter` para continuar

El progreso se guarda solo en `localStorage`.

## Tecnología

- Render 3D con [Three.js](https://threejs.org/) (cargado por CDN).
- Mundo voxel construido a partir de la rejilla de tiles de cada isla
  (agua, césped, arena, camino, nieve). Los aldeanos/jefes son *sprites*
  con emojis que siempre miran a la cámara.
- **Estética Minecraft**: bloques de pasto/tierra con texturas pixeladas
  generadas en `<canvas>` (verde arriba, tierra a los lados), un personaje
  cúbico tipo **Steve** en tercera persona con animación de caminado, y
  **animales** (mobs cúbicos) que deambulan por el bioma. Todo procedural,
  sin assets externos.

## Añadir contenido (mismo modelo data-driven que la 2D)

El juego sigue siendo 100% data-driven. Para sumar un módulo nuevo, copia un
objeto isla dentro del array `ISLANDS` en `index.html`: define `map` (rejilla de
tiles), `spawn`, `vocab` y `objects` (maestros, repaso, tienda, enemigos y jefe).
No hace falta tocar el motor 3D: la isla se construye automáticamente desde su
`map`.
