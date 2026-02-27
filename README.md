# 🧬 BioTool Web Avanzada

> Suite bioinformática interactiva que implementa algoritmos clásicos de alineamiento de secuencias y transformación de cadenas, con visualización paso a paso directamente en el navegador.

---

## 📋 Descripción

**BioTool Web Avanzada** es una aplicación web de una sola página (SPA) que permite ejecutar y visualizar tres algoritmos fundamentales en bioinformática:

- **Needleman-Wunsch** — Alineamiento global de secuencias de ADN/proteínas.
- **Smith-Waterman** — Alineamiento local para identificar regiones conservadas.
- **Burrows-Wheeler Transform (BWT)** — Transformación de cadenas para compresión e indexación de genomas.

No requiere instalación, frameworks externos ni conexión a internet. Todo se ejecuta en el navegador con HTML, CSS y JavaScript puro.

---

## 🚀 Características

- ✅ **Needleman-Wunsch** con matriz de puntuación configurable (match, mismatch, gap), trazado del camino óptimo y alineamiento final.
- ✅ **Smith-Waterman** con detección del alineamiento local de mayor puntuación y resaltado de camino.
- ✅ **BWT Visualizada** en 5 pasos colapsables: adición de centinela → rotaciones cíclicas → ordenamiento lexicográfico → extracción de columna L → resultado final con estadísticas.
- ✅ Interfaz responsiva con tema oscuro para la sección BWT.
- ✅ Métricas de identidad, gaps, runs de compresión (RLE) y frecuencia de caracteres.
- ✅ Animaciones y código de colores por nucleótido para facilitar la lectura.

---

## 📁 Estructura del Proyecto

```
biotool-web/
└── bioweb.html        # Aplicación completa (HTML + CSS + JS en un único archivo)
```

---

## ▶️ Uso

### 1. Abrir directamente en el navegador

```bash
# Clona o descarga el repositorio
git clone https://github.com/usuario/biotool-web.git
cd biotool-web

# Abre el archivo en tu navegador preferido
open index.html         # macOS
start index.html        # Windows
xdg-open index.html     # Linux
```

No se necesita servidor web, ni Node.js, ni dependencias externas.

---

## 🧪 Algoritmos Implementados

### Needleman-Wunsch (Alineamiento Global)

Calcula el alineamiento óptimo entre dos secuencias completas usando programación dinámica.

| Parámetro | Descripción | Valor por defecto |
|-----------|-------------|-------------------|
| Match | Puntuación por coincidencia | `+1` |
| Mismatch | Penalización por sustitución | `-1` |
| Gap | Penalización por inserción/deleción | `-2` |

**Ejemplo de entrada:**
```
Secuencia 1: GATTACA
Secuencia 2: GCATGCU
```

---

### Smith-Waterman (Alineamiento Local)

Encuentra la subcadena con mayor similitud entre dos secuencias, ideal para detectar dominios conservados.

| Parámetro | Descripción | Valor por defecto |
|-----------|-------------|-------------------|
| Match | Puntuación por coincidencia | `+2` |
| Mismatch | Penalización por sustitución | `-1` |
| Gap | Penalización por hueco | `-2` |

**Ejemplo de entrada:**
```
Secuencia 1: TGTTACGG
Secuencia 2: GGTTGACTA
```

---

### Burrows-Wheeler Transform (BWT)

Transforma una cadena en una representación más compresible. Muestra el proceso completo en 5 pasos visuales interactivos.

**Ejemplo de entrada:**
```
Secuencia: BANANA
```
**Resultado:**
```
BWT(BANANA$) = BNN$AAA   |   Índice original: 1
```

---

## 🖥️ Interfaz de Usuario

| Sección | Tema | Descripción |
|---------|------|-------------|
| Needleman-Wunsch | Claro | Matriz dinámica con camino resaltado |
| Smith-Waterman | Claro | Submatriz local con traceback |
| BWT Transform | Oscuro (`#0d1117`) | Pipeline de 5 pasos colapsables |

---

## 🌐 Compatibilidad de Navegadores

| Navegador | Versión mínima |
|-----------|---------------|
| Google Chrome | 80+ |
| Mozilla Firefox | 75+ |
| Microsoft Edge | 80+ |
| Safari | 13.1+ |

---

## 🔧 Tecnologías Utilizadas

- **HTML5** — Estructura semántica de la aplicación.
- **CSS3** — Variables CSS, Grid, Flexbox, animaciones y diseño responsivo.
- **JavaScript (ES6+)** — Lógica de los algoritmos, manipulación del DOM y renderizado dinámico.
- **Google Fonts** — `JetBrains Mono` y `Sora` (cargadas desde CDN).

---

## 📐 Detalles Técnicos

### Complejidad Algorítmica

| Algoritmo | Tiempo | Espacio |
|-----------|--------|---------|
| Needleman-Wunsch | O(m × n) | O(m × n) |
| Smith-Waterman | O(m × n) | O(m × n) |
| BWT | O(n² log n) | O(n²) |

> `m` y `n` representan la longitud de las secuencias de entrada.

### Limitaciones Conocidas

- La BWT utiliza ordenamiento con `localeCompare`, apto para secuencias de nucleótidos (A, T, G, C) y proteínas en ASCII estándar.
- El rendimiento puede degradarse con secuencias mayores a ~500 caracteres en la visualización BWT (por la generación de tabla completa en el DOM).
- No se incluye la operación inversa (iBWT) en esta versión.

---

## 📄 Licencia

Este proyecto se distribuye bajo la licencia **MIT**. Consulta el archivo [LICENSE](LICENSE) para más información.

---

## 👤 Autor

**Kevin Daniel Peralta Oros**

> Desarrollado como herramienta educativa e interactiva para el estudio y enseñanza de algoritmos bioinformáticos.

---

## 🤝 Contribuciones

Las contribuciones son bienvenidas. Si deseas mejorar la herramienta:

1. Haz un fork del repositorio.
2. Crea una rama para tu funcionalidad: `git checkout -b feature/nueva-funcionalidad`
3. Realiza tus cambios y confirma: `git commit -m "feat: descripción del cambio"`
4. Envía un pull request.

---

*Última actualización: 2026*
