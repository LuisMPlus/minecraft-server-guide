# 📖 Guía de Comandos del Servidor Minecraft

Guía completa de comandos y utilidades para jugadores y administradores del servidor.

---

## 🛋️ 1. GSit (Sentarse, Acostarse y Poses)

El plugin permite interactuar con el entorno y otros jugadores mediante animaciones y poses.

### Comandos principales:
| Comando | Descripción |
| :--- | :--- |
| `/sit` | Te sienta en el suelo o bloque donde estás parado. |
| `/lay` | Te acuesta boca arriba en el suelo (*¡cuenta para pasar la noche con Sleeper!*). |
| `/crawl` | Te pone en modo gateo (ideal para túneles y pasajes de 1 bloque de altura). |
| `/bellyflop` | Te lanza de panza al suelo. |
| `/spin` | Hace que tu personaje empiece a girar sobre su propio eje. |
| `/legsup` | Te acuesta boca arriba con las piernas hacia arriba. |

### Interacción con clic derecho:
* **Escaleras y losas:** Haz clic derecho con la **mano vacía** sobre cualquier escalera, losa o alfombra para sentarte de forma natural.
* **Sentarse sobre jugadores:** Haz clic derecho con la mano vacía sobre otro jugador para subirte a sus hombros.
* **Cómo levantarse:** Presiona la tecla **Shift** (agacharse) para ponerte de pie o soltar a los pasajeros.

### Opciones personales:
* `/sit toggle` — Activa o desactiva la capacidad de sentarte automáticamente al hacer clic derecho.
* `/sit playertoggle` — Activa o desactiva que otros jugadores puedan sentarse sobre ti.
* `/crawl toggle` — Activa o desactiva la opción de empezar a gatear al agacharte dos veces seguidas.

---

## 🖼️ 2. ImageFrame (Imágenes Personalizadas en Cuadros)

Permite colocar imágenes reales desde enlaces de internet en mapas dentro de marcos (`Item Frames`).

> [!NOTE]
> En modo supervivencia, necesitarás en tu inventario la cantidad de **mapas vacíos** correspondiente a las dimensiones que elijas (ej: 2×2 requiere 4 mapas vacíos, 3×2 requiere 6 mapas vacíos).

### Comandos de uso:
| Comando | Descripción |
| :--- | :--- |
| `/imageframe create <nombre> <URL> <ancho> <alto>` | Crea un cuadro con la imagen del enlace indicado. *(Alias corto: `/if create` o `/frame create`)* |
| `/imageframe get <nombre>` | Te entrega nuevamente los mapas del cuadro si ya lo habías creado antes. |
| `/imageframe list` | Muestra la lista de cuadros que has creado. |
| `/imageframe info <nombre>` | Muestra detalles del cuadro (tamaño, URL, fecha). |
| `/imageframe delete <nombre>` | Elimina un cuadro creado por ti. |
| `/imageframe clone <nombre>` | Duplica un cuadro existente. |

### Ejemplo práctico:
1. Consigue 4 mapas vacíos en tu inventario.
2. Ejecuta:
   ```text
   /imageframe create micuadro https://i.imgur.com/ejemplo.png 2 2
   ```
3. Coloca 4 marcos (*Item Frames*) en la pared formando un cuadrado de 2×2.
4. Coloca los mapas generados en los marcos para ver tu imagen completa.

### 💡 Marcos Invisibles:
Arroja una **Poción de Invisibilidad** arrojadiza sobre marcos tirados en el suelo para convertirlos en **marcos invisibles** (ideal para que la imagen quede directamente sobre la pared sin que se note el borde de madera).

---

## 😄 3. GEmote (Emoticonos y Animaciones)

Muestra emociones y expresiones en el chat y sobre tu personaje.

| Comando | Descripción |
| :--- | :--- |
| `/gemote` o `/emote` | Abre el menú visual interactivo con todos los emotes disponibles. |
| `/emote <nombre>` | Reproduce directamente un emoticono específico. |

---

## 🌙 4. Sleeper (Pasar la Noche)

El servidor requiere que al menos el **50% de los jugadores conectados** duerma para avanzar al día siguiente.

* **Cómo dormir:**
  * Puedes dormir acostándote en una **cama**.
  * O bien usando el comando `/lay` de GSit en cualquier lugar si te agarra la noche fuera de base.
* **Comandos:**
  * `/sleep` — Muestra el estado actual del sueño (cuántos jugadores están durmiendo y cuántos faltan).
  * `/sleep vote yes` / `/sleep vote no` — Permite votar si se activa una votación para saltar la noche.

---

## 🪦 5. SimpleGraves (Tumbas)

Cuando mueres, todos tus objetos y tu experiencia quedan protegidos dentro de una tumba para que no se pierdan ni desaparezcan (*despawn*).

| Comando | Descripción |
| :--- | :--- |
| `/grave` | Muestra una lista de tus tumbas activas y las coordenadas exactas `(X, Y, Z)` de tu muerte (*las tumbas no expiran*). |

* Al llegar a tu tumba, haz clic derecho sobre ella para recuperar automáticamente todos tus ítems y armadura equipada.

---

## 🎭 6. SkinsRestorer (Cambio de Skins)

Permite ponerte la skin que quieras, tanto para cuentas oficiales como no oficiales.

| Comando | Descripción |
| :--- | :--- |
| `/skin <nombre_usuario>` | Aplica la skin del jugador de Minecraft indicado. |
| `/skin url <URL_PNG>` | Aplica una skin directamente desde una URL pública de imagen. |
| `/skin clear` | Vuelve a tu skin predeterminada. |
| `/skin update` | Actualiza la skin si el jugador la cambió recientemente en Mojang. |

---

## ⚙️ 7. Comandos de Administración (Solo OPs)

### 🌍 Chunky (Pregeneración del Mundo):
* `chunky world world` — Selecciona el Overworld.
* `chunky spawn` — Centra el punto en el spawn.
* `chunky radius 3500` — Fija el radio a 3.500 bloques (área cuadrada total de 7.000 × 7.000 bloques). *(Para un cuadrado de 5.000 usa radio `2500`)*.
* `chunky start` — Comienza la pregeneración de chunks.
* `chunky progress` — Muestra el porcentaje y chunks generados.
* `chunky pause` / `chunky continue` — Pausa o reanuda la tarea.
* `chunky cancel` — Cancela la tarea en curso.

### 🛡️ CoreProtect (Inspección y Rollback contra Destrozos):
* `/co inspect` o `/co i` — Activa el modo inspector. Haz clic izquierdo en un bloque o clic derecho en un cofre/puerta para ver quién lo rompió, puso o modificó y a qué hora.
* `/co rollback u:<jugador> t:<tiempo>` — Revierte todas las acciones de un jugador en un tiempo determinado (ej: `/co rollback u:Fulanito t:2h r:20`).
* `/co restore u:<jugador> t:<tiempo>` — Restaura los cambios revertidos si cometiste un error.
