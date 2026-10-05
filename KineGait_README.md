# KineGait: Análisis Biomecánico de la Marcha en Tiempo Real 🚶‍♂️💻

KineGait es una herramienta web educativa y clínica, diseñada para el análisis espaciotemporal y cinemático de la marcha en 2D. Utiliza inteligencia artificial directamente en el navegador para detectar puntos anatómicos clave y calcular variables biomecánicas sin necesidad de equipos costosos, marcadores físicos o procesamiento en servidores externos.

Este proyecto fue desarrollado con un enfoque especial en la rehabilitación de miembros inferiores (esguinces, lesiones de rodilla, etc.), permitiendo cuantificar asimetrías y compensaciones mediante el cálculo del Índice de Simetría.

## 🎯 Características Principales

* **100% del lado del cliente (Privacidad total):** El video y los datos biométricos nunca abandonan el dispositivo del usuario. Todo se procesa localmente usando la CPU/GPU del equipo.

* **Sin instalaciones complejas:** Funciona en cualquier navegador moderno (recomendado Google Chrome o Microsoft Edge).

* **Métricas en Tiempo Real:** Cálculo de cadencia, ángulos de flexión de rodilla, inclinación del tronco y detección de contactos iniciales (Heel Strikes).

* **Resumen Clínico:** Generación automática de tablas comparativas (Lado Afectado vs Sano) e Índices de Simetría.

## 🛠️ Tecnologías y Dependencias (CDNs)

Este proyecto está construido en un único archivo (`index.html`) para máxima portabilidad, utilizando las siguientes librerías mediante CDN:

* **HTML5, CSS3 y JavaScript (Vanilla JS):** Estructura y lógica base.

* **Tailwind CSS:** Para un diseño de interfaz de usuario rápido, limpio y responsivo.

* **MediaPipe Pose (Google):** Modelo de Machine Learning ligero para la detección de la postura humana (33 landmarks) en tiempo real.

* **Chart.js:** Para la renderización de gráficos dinámicos en vivo y comparativas de resumen.

## 📁 Archivos del Proyecto

* `index.html`: Archivo único que contiene toda la estructura, estilos (vía Tailwind) y la lógica de procesamiento biomecánico y de interfaz.

## 🚀 Instrucciones de Ejecución Local

**⚠️ Importante:** Por políticas de seguridad de los navegadores web, el acceso a la cámara web (`getUserMedia`) **solo funciona bajo conexiones seguras (HTTPS)** o en **entornos de desarrollo local (`localhost`)**. Si abres el archivo HTML dándole doble clic directamente (ruta `file://...`), la cámara no se activará.

Para probarlo en tu computador, necesitas levantar un servidor local simple. Aquí tienes tres opciones fáciles:

### Opción 1: Visual Studio Code (Recomendado)

1. Instala el editor de código [Visual Studio Code](https://code.visualstudio.com/).

2. Ve a la pestaña de Extensiones y busca/instala **"Live Server"** (de Ritwick Dey).

3. Abre el archivo `index.html` en VS Code.

4. Haz clic derecho en el código y selecciona **"Open with Live Server"**. Se abrirá en tu navegador bajo `http://localhost:5500`.

### Opción 2: Usando Python (Si ya lo tienes instalado)

1. Abre tu terminal o línea de comandos.

2. Navega hasta la carpeta donde guardaste tu `index.html`.

3. Ejecuta el comando: `python -m http.server 8000`

4. Abre tu navegador y ve a `http://localhost:8000`.

### Opción 3: Usando Node.js

1. Abre tu terminal.

2. Navega a la carpeta del proyecto.

3. Ejecuta: `npx http-server`

4. Sigue el enlace `localhost` que te mostrará la terminal.

## 🌐 Instrucciones de Publicación en GitHub Pages (Gratis)

Para que tus pacientes, compañeros o profesores puedan usar la app desde sus celulares o computadores mediante un enlace, la forma más fácil es usar GitHub Pages.

1. **Crea una cuenta y un repositorio:**

   * Ve a [GitHub](https://github.com/) e inicia sesión.

   * Crea un nuevo repositorio (botón "New"). Llámalo, por ejemplo, `kinegait-app`.

   * Asegúrate de que esté configurado como **"Public"**. No marques la opción de añadir un README (lo subiremos ahora).

2. **Sube tus archivos:**

   * En la página principal de tu nuevo repositorio, haz clic en **"uploading an existing file"**.

   * Arrastra y suelta tus archivos `index.html` y este `README.md`.

   * Haz clic en **"Commit changes"** (guardar cambios).

3. **Activa GitHub Pages:**

   * En tu repositorio, ve a la pestaña **"Settings"** (Configuración).

   * En el menú lateral izquierdo, baja hasta encontrar **"Pages"**.

   * Donde dice "Source" (o "Build and deployment"), en el apartado "Branch", selecciona la rama **`main`** (o `master`) y la carpeta `/ (root)`.

   * Haz clic en **"Save"**.

4. **¡Listo!**

   * Espera unos 2 o 3 minutos. Recarga la página de "Settings > Pages" y verás un mensaje verde que dice *"Your site is live at \[TU_LINK\]"*. Ese es el enlace que debes compartir. Al estar alojado en GitHub, ya cuenta con el protocolo de seguridad HTTPS necesario para usar la cámara.

## ⚠️ Limitaciones y Aviso Clínico

Esta es una herramienta de screening rápido y apoyo educativo. Presenta limitaciones inherentes al análisis 2D con una sola cámara, como los errores por perspectiva o la oclusión de segmentos corporales. **No reemplaza el juicio clínico de un profesional de la salud ni equivale a un sistema de captura de movimiento tridimensional gold-standard (ej. Vicon o Qualisys).**