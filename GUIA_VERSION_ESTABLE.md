# SpaceNav2024 — Versión estable 1 (antes de Chiikawa)

## Alcance
Se conservan los gráficos, la nave, los proyectiles, los asteroides, las tres vidas, el puntaje, las rondas y el récord en memoria. **Esta entrega todavía no incluye los patrones GM-6 a GM-9 ni los personajes Chiikawa.**

## Cambios realizados
1. Movimiento de la nave con WASD/flechas mientras se mantiene presionada la tecla, normalizado para diagonal.
2. Velocidades por segundo usando `delta` (nave, balas y asteroides).
3. Tiempo de invulnerabilidad tras impactos medido en segundos, con parpadeo.
4. Disparo continuo controlado por un intervalo de 0,22 segundos.
5. Una sola lista de asteroides; comprobación de pares con `i < j`.
6. Eliminación segura de balas y asteroides mediante iteradores.
7. Texturas y efectos cargados una vez por pantalla y liberados en `dispose()`.
8. Coordenadas fijas 1200x800, cámara y `FitViewport` para adaptar el área de juego al tamaño de la ventana.
9. Pantalla de menú, marcador, pausa, pantalla de derrota y reintento más claros.
10. La dificultad aumenta dentro de la misma pantalla al superar cada ronda, sin recargar los sonidos.

## Controles
- **Enter** (o clic desde el menú): jugar.
- **WASD o flechas:** desplazarse (mantener presionado).
- **Espacio:** disparar (mantener presionado).
- **P o Escape:** pausar / reanudar.
- **Game Over:** Enter = nueva partida; M = volver al menú.

## Ejecución (PC)
1. Instalar JDK compatible con el proyecto y una IDE con Gradle (por ejemplo Eclipse).
2. Importar la carpeta que contiene `settings.gradle` como proyecto Gradle.
3. Ejecutar `puppy.code.lwjgl3.Lwjgl3Launcher` o `./gradlew lwjgl3:run` (en Windows `gradlew.bat lwjgl3:run`).
4. Gradle puede requerir conexión para descargar sus dependencias la primera vez.

## Estado de comprobación
- Se examinó el código fuente y se modificaron las siete clases principales.
- **No se ha comprobado la compilación ni la ejecución en este entorno**: el wrapper intentó descargar Gradle 8.10.1 y falló por falta de acceso a la red. Se requiere ejecutar el proyecto localmente antes de dar por finalizada la validación.

## Pruebas manuales sugeridas
1. Iniciar el juego con Enter y verificar que se dibujen 10 asteroides.
2. Mantener presionadas las 4 direcciones y comprobar que no sale de la pantalla.
3. Mantener dos direcciones y comparar velocidad diagonal.
4. Mantener Espacio y comprobar disparos continuos.
5. Presionar P y verificar que movimiento y marcador se congelen; volver a presionar P.
6. Destruir todos los asteroides y verificar que la siguiente ronda se cree sin perder vidas o puntos.
7. Chocar, verificar que resta una vida y que hay invulnerabilidad temporal.
8. Perder las tres vidas, comprobar Game Over y reiniciar.
9. Redimensionar la ventana, verificar que el encuadre no se deforme.
10. Reiniciar varias veces y verificar que música y sonidos no se superpongan.

## Siguiente fase
Tras validar esta base, implementar el selector de Chiikawa, Hachiware y Usagi, Strategy, Template Method, Builder y Singleton, más UML e informe GM-1 a GM-10.
