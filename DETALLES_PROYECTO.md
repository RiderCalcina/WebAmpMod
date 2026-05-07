# Manual Técnico y de Personalización - WebAmpMod

Este documento está diseñado para ayudarte a modificar el reproductor a tu gusto.

## 📂 Organización de Archivos
El proyecto está estructurado para que los recursos sean fáciles de encontrar:
- `assets/music/`: Coloca aquí tus archivos `.mp3`.
- `assets/skins/`: Coloca aquí tus archivos de skin `.wsz`.
- `assets/images/`: Contiene el fondo (`bgrnd.jpg`), la carátula móvil (`bgluis.jpg`) y el icono del sitio (`winamp.ico`).

## 🎵 Cómo añadir nueva música
1. Sube tu archivo a la carpeta `assets/music/`.
2. Abre `index.html` y busca la sección `const tracks`.
3. Añade un nuevo bloque siguiendo este formato:
   ```javascript
   {
     metaData: { artist: "Nombre Artista", title: "Nombre Canción" },
     url: "assets/music/tu_archivo.mp3",
     duration: 200 // duración en segundos (opcional)
   },
   ```

## 🎨 Cómo añadir nuevas Skins
1. Sube el archivo `.wsz` a `assets/skins/`.
2. Puedes descargar miles de skins en: [skins.webamp.org](https://skins.webamp.org/) (Actualmente el proyecto cuenta con 20 skins precargadas).
3. En `index.html`, busca la constante `const skins`.
3. Añade la ruta del archivo a la lista:
   ```javascript
   const skins = [
     "assets/skins/mi_nueva_skin.wsz",
     // ... otras skins
   ];
   ```

## 📱 Funcionamiento en Móviles
Para garantizar que la música no se corte al bloquear el teléfono:
- **Media Session API**: Sincroniza el reproductor con el sistema operativo para permitir controles (Play/Pause/Next) desde la pantalla de bloqueo.
- **Wake Lock**: Solicita permiso al navegador para mantener el hilo de ejecución activo.
- **Silent Audio**: Reproduce un archivo de silencio imperceptible para "engañar" al sistema y evitar que suspenda el proceso de audio.

## 🔧 Ajustes de Interfaz
En la sección `<style>` de `index.html` puedes modificar:
- **Escalado**: Cambia `transform: scale(1.3)` para hacer el reproductor más grande o pequeño.
- **Fondo**: Cambia `background-image: url(...)` en el `body` para usar una imagen diferente.

## 🔗 Enlaces de interés
- Documentación Webamp: [webamp.org](https://webamp.org)
- Repositorio Winamp Skins: [museum.webamp.org](https://museum.webamp.org)
