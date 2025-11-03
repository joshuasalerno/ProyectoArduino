<h1 align="center">🎮 Arduino Leonardo → Nintendo Switch (Auto Battle Bot)</h1>
<p align="center">
  Automatización de inputs HID para completar 1000 combates en <strong>Pokémon Leyendas ZA</strong>
</p>

---

## 🧠 Descripción del proyecto
En *Pokémon Leyendas ZA* existe un objetivo opcional que exige completar **1000 combates Pokémon**.  
Hacerlo manualmente es extremadamente repetitivo, así que desarrollé un sistema que permite **automatizar este proceso** usando un **Arduino Leonardo** programado como un **mando HID compatible con Nintendo Switch**.

El resultado es un bot totalmente autónomo que:
- Envía inputs HID reales a la consola  
- Repite una secuencia de combate en bucle  
- Permite a tu personaje luchar automáticamente  
- Funciona solo colocándote frente al camarero del restaurante y teniendo un Pokémon de nivel alto

Es un proyecto perfecto para demostrar:

✅ control de hardware  
✅ programación de microcontroladores  
✅ manejo de HID USB a bajo nivel  
✅ diseño de lógica automatizada  

---

## 🔧 Tecnologías y librerías utilizadas

### **Hardware**
- Arduino **Leonardo** (microcontrolador ATmega32u4 con USB nativo)

### **Librerías principales**
- **LUFA** (Lightweight USB Framework for AVRs) — para implementar el dispositivo HID  
- **Joystick.h** — descriptor personalizado del mando de Switch  
- **Bounce2** — gestión del "debounce" digital  

### **Conceptos involucrados**
- Reportes HID USB personalizados  
- Arquitectura de un “controller emulation”  
- Tiempos, loops y estados de secuencia  
- Manipulación de bitmasks  
- Debug y pruebas sobre hardware físico  

---

## 🔁 ¿Cómo funciona la automatización?

El Arduino envía una secuencia repetida de inputs:

1. Mantener **ZL**  
2. Pulsar **A** + ZL  
3. Soltar **A** (mantener ZL)  
4. Soltar **ZL**

Con pausas (`STEP_DELAY_MS`) entre cada paso.  
Esto simula perfectamente un combate rápido en bucle.

