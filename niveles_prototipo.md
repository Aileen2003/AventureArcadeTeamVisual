# 🗺️ DISEÑO DE NIVELES — PROTOTIPO ARCADE

**Responsable:** Aileen · 💠 Rol: Diseñadora de flujo jugable / Prototipo arcade

---

## 🎯 Propósito del sistema de niveles

El juego no tiene niveles largos, sino **"runs" cortos e intensos**. Cada nivel funciona como una **carrera de supervivencia estilo arcade**, donde:

- El jugador **entra al templo**
- Recolecta **reliquias fragmentadas**
- **El templo reacciona** y cambia (más trampas, más velocidad)
- Al obtener lo suficiente, se **activa un portal**


![diseño](./image/diseño.png)

> _Nada se detiene. Si te quedas quieta, el templo te devora._

---

## 🧩 Estructura básica de un nivel

| Sección | Nombre | Mecánica principal | Elemento arcade |
|--------|--------|------------------|----------------|
| ✅ Entrada | **Umbral del Templo** | Introduce movimiento | Consejo arcade estilo VOZ DEL TEMPLO |
| 🔺 Zona A | **Pasaje de losas** | Pisos que caen al pisarlos | HUD suena alerta (futuro efecto) |
| 🔻 Zona B | **Corredor de lanzas** | Patrón rítmico de esquive | Marca sonora "¡NOW!" |
| 🔁 Zona C | **Curva del Eco** | Trampa dinámica (cambia ciclo) | Aparición de Orbe de Tiempo |
| 🌀 Salida | **Portal de Retorno** | Solo aparece si fragmentos = 3 | Animación tipo portal dorado |

---

## 📈 Dificultad progresiva tipo Arcade

Cada nivel aumenta en 3 aspectos:

- **Velocidad del desplazamiento**
- **Menos tiempo de reacción (HUD marca ⚠ símbolos)**
- **Más recompensas, pero más riesgo**

| Nivel | Velocidad | Trampas activas | Recompensa |
|------|:--------:|---------------|------------|
| 1 - Ruinas del Umbral | 🟢 Normal | 1 tipo de trampa | 📦 3 fragmentos |
| 2 - Santuario Caído | 🟡 Rápido | 2 trampas combinadas | 📦 5 fragmentos |
| 3 - Cámara de la Serpiente | 🔴 Muy rápido | 3 trampas aleatorias | 🌀 Portal doble / Bonus |

---

> 🎮 *Este documento sirve como guía de diseño arcade para que cada “run” tenga identidad propia. Aileen define el ritmo del juego y el impacto visual del HUD en cada sección.*
