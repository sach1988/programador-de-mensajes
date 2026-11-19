# Programador de Mensajes: página de descargas

Sitio web (estático, sin build) con los botones de descarga de **Programador de Mensajes** para Mac y Windows.
Los instaladores se publican en las [Releases](../../releases) de este mismo repositorio.

> Proyecto independiente. No está afiliado, asociado ni respaldado por WhatsApp LLC ni por Meta.

## Cómo funciona

- `index.html` es toda la página (HTML + CSS + JS, sin dependencias). Consulta la API pública de GitHub
  (`/releases/latest`) y activa cada botón con el archivo correspondiente:
  - `Programador-de-Mensajes-mac-arm64.dmg` (Mac Apple Silicon)
  - `Programador-de-Mensajes-mac-x64.dmg` (Mac Intel)
  - `Programador-de-Mensajes-win-x64.exe` (Windows)
- Si todavía no hay release muestra «Vuelve pronto»; si la API no responde, usa los enlaces directos
  `/releases/latest/download/<archivo>`.
- La constante `REPO` al inicio del `<script>` apunta a este repositorio: cámbiala si lo renombras.

## Publicar la web (GitHub Pages)

1. Sube estos archivos a la rama `main`.
2. *Settings → Pages → Build and deployment*: **Deploy from a branch**, rama `main`, carpeta `/ (root)`.
3. La página queda en `https://<usuario>.github.io/<repositorio>/`.

## Publicar una versión

Las releases las crea automáticamente el CI del repositorio privado de la app al subir una etiqueta
(`v3.1.0`, …): compila los instaladores en Mac y Windows y los adjunta aquí. No se suben a mano.
El CI necesita el secreto `RELEASES_TOKEN` (un token con permiso *Contents: Read and write* sobre este repo).
