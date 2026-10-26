# Chiikawa Adventure

**Proyecto de Programación Avanzada — Primera entrega**  
**Base utilizada:** SpaceNav2024 (proyecto inicial proporcionado por el docente)  
**Tecnologías:** Java, LibGDX, Gradle y Eclipse  
**Integrantes:** [ Paula Henríquez, Karina Madrid y Mauricio Lavín]  
**Asignatura / docente / fecha:** [ICI 2241/ Leonardo Gonzalez - Claudio Cubillos / 25-10-2026]

## Estado del proyecto

**Primera versión de entrega (V6 del historial de desarrollo).** Se presenta una adaptación jugable de SpaceNav2024 con personajes seleccionables, ajustes de jugabilidad y una identidad visual y sonora inspirada en Chiikawa. Esta entrega no representa necesariamente la versión final del videojuego.

## Descripción y propuesta

**Chiikawa Adventure** es un videojuego de acción arcade en 2D desarrollado en Java con LibGDX. El jugador elige a Chiikawa, Hachiware o Usagi y debe esquivar obstáculos mientras lanza proyectiles mágicos para obtener puntos y superar rondas de dificultad creciente.

La propuesta consiste en transformar la experiencia espacial del proyecto base en un juego de estética **pixel art, kawaii y colores pastel**, conservando su mecánica central de movimiento, disparos, colisiones y supervivencia, pero incorporando personajes con atributos diferentes, nuevos recursos gráficos y efectos de sonido.

### Historia y ambientación

Los tres protagonistas se encuentran en un mundo de fantasía rosado donde aparecen obstáculos que amenazan su aventura. Para avanzar, deben esquivarlos o hacerlos desaparecer usando proyectiles mágicos. La temática de **Programación Avanzada** se incorpora de forma lúdica mediante el diseño propuesto para los obstáculos: esferas rosadas que representan los desafíos de la asignatura.

## Objetivo y reglas

* **Objetivo:** conseguir la mayor puntuación posible y avanzar tantas rondas como se pueda.
* El personaje se mueve por la pantalla para evitar los obstáculos.
* Puede disparar proyectiles hacia arriba; al acertar a un obstáculo, este desaparece y el jugador obtiene **10 puntos**.
* Chocar contra un obstáculo puede quitar una vida; el personaje dispone de un breve período de invulnerabilidad después de recibir daño.
* Al eliminar todos los obstáculos comienza una ronda nueva con más enemigos y mayor velocidad.
* La partida termina cuando el personaje pierde todas sus vidas; se muestra una pantalla de **Game Over** con el resultado.

## Personajes

|Personaje|Vidas iniciales|Velocidad de movimiento|Estilo|
|-|-:|-:|-|
|**Chiikawa**|3|320|Equilibrado|
|**Hachiware**|5|270|Resistente|
|**Usagi**|2|420|Rápido|

Las velocidades son valores internos del juego y se aplican al movimiento según el tiempo transcurrido entre cuadros.

## Controles

|Pantalla|Tecla|Acción|
|-|-|-|
|Menú principal|**Enter**|Ir a selección de personaje|
|Menú principal|**Esc**|Salir del juego|
|Selección|**1 / 2 / 3**|Elegir Chiikawa / Hachiware / Usagi|
|Selección|**Esc**|Volver al menú|
|Partida|**W, A, S, D** o **flechas**|Mover el personaje|
|Partida|**Espacio** (mantener)|Disparar|
|Partida|**P** o **Esc**|Pausar / reanudar|

## Tecnologías y bases utilizadas

* **Java:** lenguaje principal y programación orientada a objetos.
* **LibGDX:** framework para la lógica y representación del videojuego en 2D.
* **LWJGL3:** ejecución de la versión de escritorio.
* **Gradle:** configuración y gestión de compilación/dependencias del proyecto.
* **Eclipse IDE:** entorno utilizado para desarrollar y probar.
* **Git / GitHub:** control de versiones y registro de cambios.
* **SpaceNav2024:** código base entregado por el docente y adaptado al nuevo juego.

El proyecto integra elementos de orientación a objetos y los patrones **Singleton, Strategy, Template Method y Builder**, explicados con mayor detalle en el informe de la entrega.

## Historial de desarrollo

|Versión|Avance principal|
|-|-|
|**Base**|Proyecto SpaceNav2024 proporcionado por el docente.|
|**V1**|Correcciones de funcionamiento, control de movimiento, disparos y manejo de la partida.|
|**V2**|Implementación de Strategy, Template Method y Singleton.|
|**V3**|Incorporación del patrón Builder para construir obstáculos.|
|**V4**|Selección entre Chiikawa, Hachiware y Usagi.|
|**V5**|Estadísticas individuales e integración de sprites de los personajes.|
|**V6 — Primera entrega**|Personalización de menús, música, efectos de sonido, escenario y proyectiles; elaboración de recursos gráficos para los obstáculos.|

El historial detallado y las evidencias de commits están disponibles en el repositorio GitHub indicado al comienzo.

## Cómo ejecutar el juego en Eclipse

### Requisitos previos

1. **Eclipse IDE** con soporte para Java y Gradle (Buildship).
2. **JDK compatible con la configuración Gradle del proyecto** (revisar los archivos `build.gradle` / `gradle.properties`; la pauta de trabajo considera Java 8 u 11, pero se debe utilizar la versión efectiva configurada para esta copia).
3. Conexión a Internet la primera vez, si Gradle debe descargar dependencias.

### Importación

1. **Descomprimir el ZIP completo** en una carpeta del computador; no ejecutar las clases directamente desde el ZIP.
2. En Eclipse, ir a **File → Import… → Gradle → Existing Gradle Project**.
3. Seleccionar como directorio raíz la carpeta que contiene los archivos de configuración de Gradle del proyecto (incluido `settings.gradle` o equivalente).
4. Finalizar la importación y esperar a que Gradle sincronice las dependencias.
5. Verificar que aparezcan los módulos de código del juego (**core**) y de escritorio (**lwjgl3**).

### Ejecución

1. Abrir el módulo **lwjgl3** y localizar la clase `Lwjgl3Launcher.java` (en el paquete `puppy.code.lwjgl3`).
2. Hacer clic derecho en `Lwjgl3Launcher.java` → **Run As → Java Application**.
3. Si Eclipse no encuentra las imágenes o sonidos, revisar la **carpeta de trabajo (Working directory)** de la configuración de ejecución. Debe apuntar a la carpeta desde la cual LibGDX encuentra los recursos `assets` en la estructura entregada; normalmente se utiliza `assets` como directorio de trabajo en el lanzador de escritorio, según la configuración Gradle del proyecto.
4. Cuando aparezca el menú principal, presionar **Enter**, elegir personaje con **1, 2 o 3** y comenzar a jugar.

> \*\*Importante:\*\* no eliminar ni renombrar los archivos de `assets`. Las rutas de imágenes y sonidos están escritas en el código y deben coincidir exactamente con los nombres de archivo.

## Organización general del proyecto

```text
\[carpeta raíz del proyecto]/
├── README.md
├── assets/                    # Imágenes y archivos de audio del juego
├── core/                      # Lógica del juego, pantallas y clases Java
├── lwjgl3/                    # Lanzador para escritorio
├── build.gradle / settings.gradle / gradle.properties  # Según la estructura original
└── \[otros archivos de Gradle y configuración]
```

En Eclipse, algunos proyectos pueden visualizarse con nombres como `SpaceNav2024-core`, `SpaceNav2024-lwjgl3` y `SpaceNav2024-parent`, aunque correspondan a estos módulos.

## Alcance de esta primera entrega

**Incluido:** menú, selección de personajes, movimiento, disparos, vidas diferenciadas, puntuación, rondas, pausas, Game Over, sonidos personalizados y recursos gráficos adaptados.

**Pendiente de verificar en el ZIP final:** que los últimos recursos elaborados (en particular la esfera de “Programación Avanzada” y el sprite de proyectil seleccionado) estén efectivamente conectados en `PantallaJuego.java` y presentes en `assets`; que los nombres de archivos correspondan a los cargados por el código; y que la ejecución funcione en otro computador.

Para la explicación técnica completa, diagramas UML, justificación de patrones y evidencias de cumplimiento de la pauta, consultar el **informe de la primera entrega** que acompaña este proyecto.

\---

**Chiikawa Adventure — Primera entrega · Programación Avanzada**

