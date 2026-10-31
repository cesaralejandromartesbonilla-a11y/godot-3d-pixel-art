# 🗺️ Hoja de Ruta (Roadmap) — Godot 3D Pixel Art

Este documento define la trayectoria técnica, mejoras planificadas y ampliaciones arquitectónicas para el pipeline de renderizado Pixel Art 3D en Godot 4.

---

## 📌 Fase 1: Calibración Base y Estabilidad (Completado ✅)
- [x] Corrección de estructura de carpetas plana y eliminación de caché no versionable (`.godot`).
- [x] Configuración de archivo `.gitignore` estandarizado para Godot 4.
- [x] Shader de contornos basado en búfer de profundidad y normales.
- [x] Escena de demostración funcional con iluminación dinámica y malla rotatoria.

---

## 📌 Fase 2: Cuantización de Paletas y Tramado (Dithering) (En Progreso 🔄)
- [ ] **Soporte para LUTs (Look-Up Tables) de color**:
  - Permitir paletas clásicas retro (Game Boy, PICO-8, CGA, PlayStation 1, SNES).
  - Mapeo de color mediante textura 1D/2D sin pérdida de rendimiento en GPU.
- [ ] **Algoritmo de Dithering por Matriz Bayer**:
  - Integración de tramado ordenado $4 \times 4$ y $8 \times 8$ para simular gradientes de luz con número limitado de tonos.
- [ ] **Detección Oclusiva de Bordes Internos**:
  - Distinción entre contorno perimetral externo (silueta) y pliegues internos de la malla.

---

## 📌 Fase 3: Optimización y Compatibilidad Multiplataforma 🚀
- [ ] **Compatibilidad con el Renderer de Compatibilidad (GLES3 / WebGL 2)**:
  - Adaptación de lectura de profundidad para ejecuciones fluidas en exportaciones Web/HTML5 y móviles de gama baja.
- [ ] **Soporte para Múltiples Cámaras y Viewports**:
  - Componente reusable `PixelArtSubViewport` que encapsule la resolución virtual fija (e.g. 320x180, 480x270, 640x360) sin deformar la UI del juego.
- [ ] **Presets de Post-Procesado en Inspector**:
  - Creación de recursos personalizados `.tres` con perfiles configurados (e.g., `PS1_LoFi.tres`, `Retro_Arcade.tres`).
