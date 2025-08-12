Lorita - Godot 4 Prototype (Pixel art)
=====================================

Contenido del ZIP:
- project.godot
- scenes/
  - main.tscn
  - player.tscn
- scripts/
  - Player.gd
  - Enemy.gd
- assets/
  - lorita32.png
  - enemy32.png
  - seed16.png
- .github/workflows/build-apk.yml  (plantilla de GitHub Actions)
- README.md (este archivo)

Objetivo
--------
Prototipo básico listo para abrir en Godot 4. Incluye:
- Player con movimiento lateral y salto.
- Un enemigo simple (patrulla).
- Sprites sencillos en pixel art.
- Plantilla de workflow para compilar APK en GitHub Actions (requerirá ajustes, ver abajo).

Cómo abrir en Godot (local)
--------------------------
1. Instala Godot 4 (https://godotengine.org).
2. Abre Godot y elige 'Import' o 'Open' y selecciona la carpeta del proyecto (la que contiene project.godot).
3. Abre la escena 'res://scenes/main.tscn' y ejecuta (Play).

Sobre el APK y GitHub Actions
----------------------------
He incluido una plantilla de GitHub Actions en `.github/workflows/build-apk.yml`. La acción está pensada para:
- Instalar Godot (descarga la versión adecuada).
- Instalar Android SDK/NDK.
- Ejecutar la exportación usando plantillas de exportación de Godot.

**IMPORTANTE**: compilar APK en CI requiere:
- Las plantillas de exportación de Godot (export templates) disponibles para la versión usada.
- Configurar variables/secretos en GitHub (si se usan keystores o credenciales).
- Posibles ajustes a las rutas del SDK según cambios en GitHub Actions y en Godot.

Content of the workflow file is included in `.github/workflows/build-apk.yml` inside the ZIP.

Si quieres, puedo:
- Ajustar el workflow para usar un servicio específico (por ejemplo, GitHub Actions con una acción comunitaria conocida).
- Generar un APK yo mismo usando un runner — pero necesitarás ejecutar el workflow en tu cuenta de GitHub y descargar el APK.

Si deseas que yo prepare el repositorio en GitHub (con el workflow activo), necesitaré acceso para crear el repo o que me des permiso/confirmación para que te entregue los pasos exactos para subir y ejecutar.

¡Dime si quieres que te guíe paso a paso para ejecutar el workflow en GitHub y descargar el APK!


## Cómo usar el workflow en GitHub

1. **Subir el proyecto a GitHub**
   - Crea un nuevo repositorio en tu cuenta.
   - Sube todos los archivos del proyecto (incluyendo `.github/workflows/build-apk.yml`).

2. **Ejecutar el workflow**
   - En tu repositorio, ve a la pestaña **Actions**.
   - Selecciona **Build Godot Game**.
   - Haz clic en **Run workflow** y confirma.

3. **Descargar los builds**
   - Una vez termine, abre la ejecución y busca la sección **Artifacts**.
   - Ahí encontrarás un archivo llamado **lorita-game-builds.zip** que contiene:
     - `LoritaGame.apk` → Android (Debug, arm64-v8a).
     - `LoritaGame.exe` → Windows.
     - `LoritaGame.x86_64` → Linux.
