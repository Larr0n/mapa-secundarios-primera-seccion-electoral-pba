# Mapa de Secundarios - Primera Sección Electoral (PBA)

Plataforma web minimalista y estética para visualizar, filtrar y analizar datos de establecimientos educativos de nivel secundario en la Primera Sección Electoral de la Provincia de Buenos Aires. Diseñado para facilitar la toma de decisiones políticas y el análisis territorial.

**Creado por:** [Pedro Larrondo](https://www.instagram.com/pedro.larrond0/)

**Fuente de datos:** Los datos utilizados en este mapa fueron extraídos del [Catálogo de Datos Abiertos de la Provincia de Buenos Aires](https://catalogo.datos.gba.gob.ar/dataset/establecimientos-educativos).

---

## ✨ Características

- **Mapa interactivo** motorizado por Leaflet.js.
- **Límites territoriales exactos** de los municipios mediante trazado de polígonos GeoJSON.
- **Filtrado dinámico** por municipio y búsqueda por nombre de establecimiento.
- **Exportación a Excel (.xlsx)** automatizada, conservando filtros, formateo de tabla y ordenamiento de datos mediante ExcelJS.
- **Estadísticas en tiempo real** (cantidad de establecimientos, matrícula total, municipios involucrados).
- **Panel lateral** con listado de establecimientos sincronizado bidireccionalmente con el mapa.
- **Diseño UI/UX renovado** con tipografías personalizadas (Poppins, Roboto, Courier New) y una paleta de colores institucional sólida (#39195b).
- **Popups informativos unificados** con detalles exactos de cada establecimiento (Modalidad, Matrícula, Varones/Mujeres, etc.).

## 📁 Estructura del Proyecto

```text
.
├── index.html                              # Página principal y lógica de la aplicación
├── Dataset/
│   ├── dataset_filtrado.csv                # Base de datos procesada de secundarios
│   └── municipios_seleccionados.geojson    # Polígonos con límites administrativos
├── Recursos/
│   └── icon.ico                            # Ícono de la pestaña del navegador
└── README.md                               # Este archivo de documentación

## 🛠️ Requisitos

Al ser una aplicación 100% *Client-Side* (Frontend), no requiere bases de datos ni backend complejo. Solo se necesita un navegador web moderno con soporte para:

* ES6 JavaScript
* CSS Flexbox
* Fetch API (para leer el CSV y el GeoJSON)

## 🚀 Instalación y Uso Local

### 1. Clonar el repositorio

```bash
git clone [https://github.com/tu-usuario/mapa-educativo-pba.git](https://github.com/tu-usuario/mapa-educativo-pba.git)
cd mapa-educativo-pba

```

### 2. Servir localmente

Por medidas de seguridad de los navegadores (CORS), no se puede abrir el archivo `index.html` directamente haciendo doble clic si este hace peticiones `fetch` a archivos locales (como el `.csv` o `.geojson`). Necesitas levantar un servidor HTTP simple.

**Con Python 3:**

```bash
python -m http.server 8000

```

**Con Node.js (http-server):**

```bash
npx http-server

```

Luego abre en tu navegador: `http://localhost:8000`

## 🖱️ Interfaz y Funcionalidades

### 1. Panel Lateral Izquierdo

* **Búsqueda:** Encuentra escuelas escribiendo parte de su nombre.
* **Filtros:** Aísla la vista seleccionando un municipio específico.
* **Descarga:** Genera un archivo Excel (`.xlsx`) estructurado con los datos que estás viendo en pantalla en ese momento.
* **Métricas:** Observa cómo cambian los totales de matrícula según tus filtros.
* **Listado:** Navega por las tarjetas de las escuelas; al hacer clic en una, el mapa "viajará" automáticamente hacia ese punto.

### 2. Mapa Interactivo

* Los círculos representan cada escuela secundaria.
* Al hacer clic en un punto, se abre un **Popup** con estilo de tarjeta flotante detallando dirección, contacto y distribución de la matrícula.
* El fondo gris claro resalta los límites celestes exactos de cada partido de la Primera Sección Electoral.


## 💻 Tecnologías Utilizadas

* **Estructura y Estilos:** HTML5, CSS3.
* **Fuentes:** Google Fonts (Poppins, Roboto).
* **Lógica Interactiva:** Vanilla JavaScript (ES6).
* **Motor Geográfico:** [Leaflet.js](https://leafletjs.com/) (v1.9.4).
* **Mapas Base:** CartoDB (Light All).
* **Exportación de Datos:** [ExcelJS](https://github.com/exceljs/exceljs) (v4.3.0).

## 📄 Licencia

Proyecto de código abierto. Libre para uso, modificación y distribución.
