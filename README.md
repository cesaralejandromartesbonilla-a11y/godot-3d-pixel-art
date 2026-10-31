# 🎨 Godot 4 — 3D Pixel Art & Outline Post-Processing Pipeline

Pipeline visual completo en **Godot 4** para renderizar gráficos 3D en tiempo real con estética estilizada **Pixel Art Retro**, filtrado de profundidad y sombreado con contornos (*edge detection outline*).

---

## 🌟 Características Principales

- **Shader de Contornos Basado en Pantalla (`outline.gdshader`)**:
  - Detección de bordes basada en disparidad de profundidad (*depth buffer*) y normales de superficie.
  - Grosor de contorno y color configurables en tiempo real sin requerir mallas duplicadas invertidas.
- **Renderizado Pixel Art en Tiempo Real**:
  - Downsampling y ajuste de resolución interna manteniendo nitidez en la relación de aspecto.
  - Compatibilidad nativa con el renderer Vulkan / Forward Plus y Mobile de Godot 4.
- **Escena de Demostración Integrada (`main.tscn`)**:
  - Iluminación dinámica controlada por `DirectionalLight3D.gd`.
  - Malla poligonal de prueba (`models/icosphere.glb`) con rotación procedural continua (`scripts/spin.gd`).

---

## 📂 Estructura del Proyecto

```text
godot-3d-pixel-art/
├── models/
│   ├── icosphere.glb           # Modelo 3D de prueba
│   └── icosphere.glb.import
├── scripts/
│   └── spin.gd                 # Script de rotación procedural
├── DirectionalLight3D.gd       # Control y órbita de luz direccional
├── outline.gdshader            # Post-processing shader de bordes y pixelación
├── main.tscn                   # Escena principal con viewport y post-proceso
├── project.godot               # Configuración del motor Godot 4
├── README.md                   # Documentación general
└── ROADMAP.md                  # Hoja de ruta técnica y próximas mejoras
```

---

## 🚀 Requisitos y Uso

1. **Versión de Godot**: Godot Engine 4.0 o superior (compatible con Godot 4.2+ / 4.3+ / 4.5+).
2. **Ejecución**:
   - Abre Godot y selecciona **Importar**.
   - Navega a la carpeta del proyecto y selecciona el archivo `project.godot`.
   - Presiona `F5` para ejecutar la escena `main.tscn`.

---

## ⚙️ Parámetros del Shader de Contorno

Dentro del inspector de Godot, en el material que usa `outline.gdshader`, se pueden calibrar los siguientes parámetros:

| Parámetro | Tipo | Descripción |
| :--- | :--- | :--- |
| `outline_color` | `Color` | Color del trazo perimetral exterior. |
| `depth_threshold` | `float` | Sensibilidad a cambios de distancia en la cámara. |
| `normal_threshold` | `float` | Sensibilidad a ángulos abruptos entre polígonos. |
| `pixel_size` | `int` | Factor de escala para el efecto pixelado retro. |

---

## 📄 Licencia

Este proyecto se distribuye bajo la licencia MIT. Consulta el archivo [LICENSE](LICENSE) para más detalles.
