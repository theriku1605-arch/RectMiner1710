# RectMiner 0.1.0 — Minecraft Java 1.7.10 / Forge 10.13.4.1614

**Estado:** prototipo de código fuente, todavía no compilado ni probado dentro del juego. No se presenta como un JAR listo para instalar.

## Qué intenta hacer
- Mod de cliente; no añade bloques ni requiere instalar el mod en el servidor.
- NUMPAD 1: marca el punto A mirando un bloque.
- NUMPAD 2: marca el punto B mirando un bloque.
- NUMPAD 3: inicia/pausa el intento de minería automática.
- NUMPAD 0: parada de emergencia.
- Limita la selección a 12.000 bloques por seguridad.

## Limitaciones
Este es un prototipo inicial, no un pathfinder completo. Intenta acercarse a bloques sólidos de la caja seleccionada, mirar hacia ellos y romperlos con el controlador normal del juego. Puede atascarse ante desniveles, agua, lava, caídas, entidades o bloques inaccesibles. El servidor puede rechazar la rotura o sancionar automatización si sus reglas lo prohíben. No lo uses en servidores donde los bots/macros estén prohibidos.

## Compilar online con GitHub Actions
El proyecto incluye `.github/workflows/build.yml`, que intenta compilarlo usando Java 8 y Gradle 2.14.1.

1. Crea un repositorio en https://github.com/new.
2. Descomprime este ZIP y sube **el contenido** de la carpeta `RectMiner1710` al repositorio (incluida la carpeta oculta `.github/workflows`). Puedes usar la opción de subir archivos en la web de GitHub; asegúrate de que `.github/workflows/build.yml` se suba también.
3. Abre la pestaña **Actions** del repositorio.
4. Selecciona **Build RectMiner (Minecraft 1.7.10)** y pulsa **Run workflow**, o espera a que termine el flujo disparado al subir archivos a `main` o `master`.
5. Si termina en verde, abre esa ejecución, baja hasta **Artifacts** y descarga `RectMiner-1.7.10`. El JAR estará dentro del ZIP del artefacto.
6. Si falla, abre los registros de **Build mod** y comparte el error completo. ForgeGradle 1.2 es antiguo y puede fallar por dependencias o incompatibilidades; el workflow no garantiza una compilación exitosa hasta que una ejecución termine bien.

## Compilación local (opcional)
La toolchain antigua suele requerir Java 8 y Gradle 2.14.1. Desde esta carpeta ejecuta `gradle build`. El JAR, si compila, queda en `build/libs/`.
