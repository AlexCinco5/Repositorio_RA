# Portafolio de Realidad Aumentada - WebAR

Este repositorio contiene una colección de cuatro experiencias interactivas de Realidad Aumentada basadas en la web (WebAR). Desarrollado por Alejandro Cinco Prieto como parte de la licenciatura en Tecnologías de la Información y Negocios Digitales en la Universidad Anáhuac Oaxaca, el proyecto explora técnicas de rastreo de imágenes, mapeo facial de precisión y comprensión del entorno sin marcadores.

Se ha diseñado un menú principal (`index.html` en la raíz) para facilitar la navegación fluida entre los cuatro proyectos independientes.

## Estructura del Repositorio

El proyecto está organizado en carpetas modulares para mantener separados los recursos (modelos 3D, texturas, audios) y la lógica de cada actividad:

```
/
├── actividad1_qr/            # Minijuego AR activado por marcador
├── actividad2_filtro/        # Filtro facial reactivo con máscara 2D
├── actividad3_diademuertos/  # Mapeo facial 3D de precisión (Three.js)
├── actividad4_entorno/       # Videojuego AR de supervivencia (Sin marcadores)
├── index.html                # Menú principal de navegación
└── README.md                 # Documentación del proyecto

```

## Descripción de las Actividades

### Actividad 1: Atrapa los Cristales AR (`/actividad1_qr`)

Minijuego de recolección en Realidad Aumentada activado mediante un marcador personalizado (formato `.mind`).

* **Mecánica:** Los jugadores deben tocar cristales flotantes en 30 segundos. Los cristales blancos y rojos otorgan puntos, mientras que los verdes suman tiempo extra. Si un cristal cae al vacío, se aplica una penalización de tiempo.

* **Herramientas:** A-Frame, MindAR Image Tracking.

### Actividad 2: Filtro Facial Reactivo (`/actividad2_filtro`)

Un filtro AR de cámara frontal que ancla una máscara al rostro del usuario.

* **Mecánica:** Al abrir la boca, se detona un efecto de humo anclado a los extremos de la mascarilla y se reproduce una alerta sonora.

* **Herramientas:** A-Frame, MindAR Face Tracking.

### Actividad 3: Máscara de Día de Muertos (`/actividad3_diademuertos`)

Una mejora del mapeo facial utilizando la malla nativa (`Face Mesh`) para adaptar una textura plana (`mascara_base.png`) exactamente a las facciones del usuario.

* **Mecánica:** Utiliza histéresis matemática en los puntos de referencia faciales para detectar la apertura de la boca, activando pétalos flotantes (`petalos.png`) y sonido de fondo.

* **Herramientas:** Three.js nativo, MindAR Face Tracking.

### Actividad 4: Supervivencia AR (`/actividad4_entorno`)

Un videojuego de supervivencia en primera persona que no requiere marcadores físicos, utilizando los sensores giroscópicos del dispositivo móvil para explorar un entorno de 360 grados.

* **Mecánica:** El jugador debe defenderse de hordas de zombies que aparecen en ángulos aleatorios. Se implementa un HUD complejo con niveles, contador de oleadas, sistema de rachas y "boosters" especiales (daño doble y ataque nuclear) desbloqueables mediante puntuación.

* **Herramientas:** A-Frame, Three.js Raycaster (para la detección de colisiones de disparos).

## Instrucciones de Instalación y Ejecución

Dado que las experiencias de WebAR requieren acceso a la cámara y sensores del dispositivo móvil, las políticas de seguridad de los navegadores exigen que el proyecto se ejecute sobre un servidor local o bajo un dominio seguro (`HTTPS`).

1. **Clonar el repositorio:**

   ```
   git clone https://github.com/tu-usuario/tu-repositorio.git
   cd tu-repositorio
   
   ```

2. **Levantar un servidor local:**

   * *Opción A (VS Code):* Instala la extensión **Live Server** y haz clic en "Go Live" sobre el archivo `index.html` de la carpeta raíz.

   * *Opción B (Python):* Ejecuta en la terminal `python -m http.server 5500`.

   * *Opción C (Node.js):* Ejecuta `npx serve`.

3. **Probar en dispositivo móvil:**

   * Asegúrate de que tu PC y tu teléfono estén en la misma red Wi-Fi.

   * Accede desde el navegador de tu móvil a la IP local de tu computadora (ej. `http://192.168.x.x:5500`).

   * Concede los permisos de cámara y movimiento/orientación cuando el navegador lo solicite.

## Capturas de Pantalla

*(Reemplaza las rutas con capturas reales de tu proyecto funcionando en el teléfono)*

| 

| **Actividad 1** | **Actividad 2** | 
|  |  | 
| **Atrapa los Cristales** | **Filtro Reactivo** | 

| **Actividad 3** | **Actividad 4** | 
|  |  | 
| **Máscara Día de Muertos** | **Supervivencia AR** | 

## Herramientas y Tecnologías

* **Lenguajes:** HTML5, CSS3, JavaScript (ES6+).

* **Librerías AR/3D:** A-Frame (v1.4.2 / v1.8.0), Three.js (v0.160.0), MindAR (v1.2.5).

* **Modelado y Texturizado:** Blender (creación de máscaras y texturizado UV).

* **Asistencia de IA:** Se utilizó Google Gemini, OpenAI ChatGPT y DeepSeek como apoyo en la corrección de conflictos de versiones entre A-Frame y Three.js, estructuración de lógica matemática y optimización de código.

## Créditos y Licencias

Este proyecto utiliza recursos de terceros, distribuidos bajo licencias libres y de uso público:

* **Modelos 3D Genéricos:** Descargados desde [Poly Pizza](https://poly.pizza) bajo licencia **CC0** (Dominio Público).

* **Modelos 3D Personalizados:** Máscaras, texturas de la Catrina y configuraciones de la malla facial (Face Mesh) modelados internamente mediante **Blender**.

* **Efectos de Audio:** Archivos de sonido (disparos, interfaz, alertas, música de fondo) descargados desde [Pixabay](https://pixabay.com) bajo licencia **Royalty-Free** (libres de regalías).