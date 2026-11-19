# Programador de Mensajes

App de escritorio para **Mac y Windows** que programa mensajes de WhatsApp desde tu propio número.
Todo queda en tu computador: sin nube, sin cuentas y sin costo.

**🌐 Página de descargas:** <https://sach1988.github.io/programador-de-mensajes/>
**⬇️ Instaladores:** [Releases](https://github.com/sach1988/programador-de-mensajes/releases/latest)

| Sistema | Archivo |
|---|---|
| Mac con Apple Silicon (M1, M2…) | `Programador-de-Mensajes-mac-arm64.dmg` |
| Mac con Intel | `Programador-de-Mensajes-mac-x64.dmg` |
| Windows 10 y 11 (64 bits) | `Programador-de-Mensajes-win-x64.exe` |

> Los instaladores aparecen en la sección Releases con cada versión publicada. Si aún no ves ninguna, la primera está en preparación.

## Qué hace

- **Hora en lenguaje natural:** escribe «mañana 8am», «en 2 horas» o «lunes 9:30», o elige fecha y hora en el calendario.
- **Mensajes que se repiten:** cada día, semana, mes o año (cumpleaños, recordatorios).
- **Plantillas** para los textos que repites y **adjuntos** (imágenes o archivos de hasta 15 MB).
- **Contactos:** favoritos, alias, **fecha del último mensaje** (con filtro de inactividad), **etiquetas con color** y acciones sobre varios contactos a la vez (ocultar, mostrar, etiquetar). Todo vive solo en la app; tu WhatsApp no cambia.
- **Ver los últimos mensajes** de un chat antes de programar (solo lectura).
- **Segundo plano:** al cerrar la ventana sigue en la bandeja del sistema enviando tus mensajes. Puede iniciarse con el computador y te avisa si algo falla.
- **Privado:** mensajes, contactos y sesión se guardan solo en tu equipo, con copia automática diaria.

## Instalar

La app **no está firmada** con un certificado de pago, por eso el sistema pide confirmación la primera vez.

**Mac**
1. Abre el `.dmg` y arrastra la app a *Aplicaciones*.
2. Ábrela. macOS dirá «No se abrió…»: pulsa **Listo** (no «Mover al basurero»).
3. Ve a **Ajustes del Sistema → Privacidad y seguridad**, baja hasta *Seguridad* y pulsa **Abrir de todos modos** junto a «Programador de Mensajes»; confirma con tu contraseña o Touch ID. Solo hace falta la primera vez.
4. Alternativa por Terminal: `xattr -cr "/Applications/Programador de Mensajes.app"` y vuelve a abrirla.
5. En macOS 14 o anterior basta con clic derecho sobre la app → **Abrir** → **Abrir**.

**Windows**
1. Ejecuta el instalador `.exe`.
2. Si aparece «Windows protegió tu PC»: **Más información** → **Ejecutar de todas formas**.

Necesita **Chrome o Edge** (Edge ya viene con Windows). Si no encuentra ninguno, descarga Chrome una sola vez al primer arranque.

## Primeros pasos

1. Abre la app y escanea el código QR desde WhatsApp → *Ajustes* → *Dispositivos vinculados* → *Vincular dispositivo*.
2. Espera a que termine de sincronizar (la primera vez puede tardar unos minutos; no cierres la sesión ni la app).
3. Elige un contacto, escribe el mensaje, indica cuándo enviarlo y pulsa **Programar**.

## Preguntas frecuentes

- **¿Qué pasa si el computador está apagado a la hora del mensaje?** La app debe estar encendida. Si estuvo apagada y la hora pasó hace más de 15 minutos, el mensaje queda «vencido» y tú decides si enviarlo o borrarlo. Con «Iniciar con el sistema» arranca sola.
- **¿Se suben mis datos a algún lado?** No. La app solo se comunica con WhatsApp, como WhatsApp Web.
- **¿Puede WhatsApp bloquearme la cuenta?** Usa una librería no oficial que se conecta como WhatsApp Web. Para uso personal y pocos mensajes a contactos que te conocen el riesgo es bajo, pero existe. No la uses para spam ni envíos masivos.
- **¿Dónde quedan mis datos?** Mac: `~/Library/Application Support/Programador de Mensajes`. Windows: `%APPDATA%\Programador de Mensajes`.
- **¿Cómo la desinstalo?** Mac: arrastra la app a la papelera. Windows: *Configuración → Aplicaciones*. Para borrar también tus datos, elimina la carpeta de arriba.

## Aviso

Proyecto independiente. **No está afiliado, asociado, autorizado ni respaldado por WhatsApp LLC ni por Meta Platforms, Inc.**
WhatsApp es una marca registrada de WhatsApp LLC. El software se ofrece «tal cual», sin garantías; úsalo con responsabilidad
y respetando los términos de WhatsApp.

---

## Sobre este repositorio (mantenimiento)

Este repositorio aloja **solo la página web y los instaladores**; el código de la app es privado.

- `index.html` es toda la página (HTML, CSS y JS sin dependencias; publicada con GitHub Pages desde `main`, carpeta raíz).
  Consulta la API pública de GitHub (`/releases/latest`) y activa cada botón con su archivo; si no hay release muestra
  «Vuelve pronto», y si la API no responde usa los enlaces directos `/releases/latest/download/<archivo>`.
- La constante `REPO` al inicio del `<script>` apunta a este repositorio: cámbiala si lo renombras.
- `assets/` contiene el icono y las capturas de la app (con datos de ejemplo).
- **Las releases no se crean a mano:** el CI del repositorio privado de la app compila los instaladores en Mac y Windows
  al subir una etiqueta (`v3.1.0`, …) y los publica aquí. Para eso necesita el secreto `RELEASES_TOKEN` en el repo privado
  (token con permiso *Contents: Read and write* solo sobre este repositorio).
