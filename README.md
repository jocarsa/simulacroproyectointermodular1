# Tienda Online de Tecnología (Flask + SQLite)

**Autor:** José Vicente Carratalá Sanchis
**Año:** 2025 · **Versión:** 1.0
**Repositorio:** `simulacroproyectointermodular1`

Una tienda online **básica y didáctica** que muestra productos tecnológicos desde una base de datos **SQLite** y los renderiza en una página **Flask** con diseño responsivo. Ideal como punto de partida para prácticas de integración backend–frontend.

---

## ✨ Características

* Conexión automática a **SQLite** (`tiendaonline.db`).
* Lectura de la tabla **`productos`** y renderizado dinámico (nombre, descripción, imagen y precio).
* Interfaz HTML con **CSS embebido** y diseño adaptable.
* Cabecera, navegación, listado de productos y pie de página.
* Botón “**Añadir al carrito**” (placeholder sin lógica aún).

---

## 🧱 Tecnologías

* **Python 3.10+**
* **Flask**
* **SQLite3**
* HTML5 + CSS (embebido)
* Estructura de ficheros estáticos: `/static/img/`

---

## 📦 Estructura del proyecto (propuesta)

```
simulacroproyectointermodular1/
├─ app.py                  # Aplicación Flask (ruta '/')
├─ tiendaonline.db         # Base de datos SQLite (generada por ti)
├─ /static/
│  └─ /img/                # Imágenes de productos (p.ej. lenovo.jpg)
├─ README.md               # Este archivo
└─ requirements.txt        # Dependencias (Flask)
```

> **Nota:** En el código actual, el HTML se construye como cadena dentro de la vista. En futuras versiones se recomienda usar **templates Jinja2**.

---

## 🗃️ Esquema de base de datos

Tabla esperada: **`productos`**

| Campo         | Tipo                  | Detalle                             |
| ------------- | --------------------- | ----------------------------------- |
| `id`          | `INTEGER PRIMARY KEY` | Clave primaria autoincremental      |
| `nombre`      | `TEXT`                | Nombre del producto                 |
| `descripcion` | `TEXT`                | Descripción corta                   |
| `imagen`      | `TEXT`                | Nombre de archivo en `/static/img/` |
| `precio`      | `REAL`                | Precio (decimal)                    |

### SQL de creación + datos de ejemplo

```sql
-- Crear tabla
CREATE TABLE IF NOT EXISTS productos (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  nombre TEXT NOT NULL,
  descripcion TEXT,
  imagen TEXT,
  precio REAL NOT NULL
);

-- Insertar ejemplo
INSERT INTO productos (nombre, descripcion, imagen, precio) VALUES
('Portátil Lenovo IdeaPad', 'Portátil con procesador Ryzen 5 y 16GB RAM', 'lenovo.jpg', 799.99),
('Ratón Logitech MX Master 3S', 'Ratón inalámbrico ergonómico con 8 botones', 'mxmaster3s.jpg', 119.90),
('Monitor LG 27” QHD', 'Panel IPS 27” 2560x1440, 75Hz, FreeSync', 'lg27qhd.jpg', 229.00);
```

Coloca las imágenes referenciadas (p. ej. `lenovo.jpg`) en `static/img/`.

---

## ▶️ Puesta en marcha

1. **Clona** el repositorio:

   ```bash
   git clone https://github.com/jocarsa/simulacroproyectointermodular1.git
   cd simulacroproyectointermodular1
   ```

2. **Crea y activa** un entorno virtual (opcional pero recomendado):

   ```bash
   python -m venv .venv
   # Linux/macOS
   source .venv/bin/activate
   # Windows
   .venv\Scripts\activate
   ```

3. **Instala dependencias**:

   ```bash
   pip install -U pip
   pip install flask
   # opcional: pip freeze > requirements.txt
   ```

4. **Crea la base de datos** `tiendaonline.db` y la tabla `productos` (ver SQL anterior).

5. **Estructura de imágenes**:

   * Crea la carpeta `static/img/` y añade tus imágenes (`lenovo.jpg`, etc.).

6. **Ejecuta la app**:

   ```bash
   python app.py
   ```

   Abre: [http://127.0.0.1:5000/](http://127.0.0.1:5000/)

---

## 🌐 Rutas

* `/` → Página principal con el listado de productos.

---

## 📌 Uso didáctico

Este proyecto está planteado para **enseñar**:

* Conexión a SQLite desde Python.
* Ejecución de consultas y renderizado dinámico en Flask.
* Organización básica de recursos estáticos (imágenes).

---

## 🧭 Próximos pasos / Roadmap

* [ ] Implementar **carrito de compras** (sesión/cookies, añadir/eliminar).
* [ ] **Templates Jinja2** (separar HTML de la vista).
* [ ] **Blueprints** y estructura modular.
* [ ] **Búsqueda** y **paginación** de productos.
* [ ] Gestión de **usuarios** (registro/login, roles).
* [ ] Panel **admin** (CRUD de productos).
* [ ] Validación de formularios y subida de imágenes.
* [ ] Tests unitarios/funcionales (pytest).

---

## 🔒 Consideraciones

* Sanitiza entradas si añades formularios.
* No expongas la DB en producción.
* Usa variables de entorno para config sensibles (cuando existan).

---

## 🤝 Contribuir

1. Crea un fork.
2. Crea una rama: `git checkout -b feature/nueva-funcionalidad`
3. Commit: `git commit -m "Añade X"`
4. Push: `git push origin feature/nueva-funcionalidad`
5. Abre un Pull Request.

---

## 👤 Autor

**José Vicente Carratalá Sanchis**
Proyecto educativo de integración **Flask + SQLite**.

---

## 📄 Licencia

Este proyecto se distribuye con licencia **MIT** (o la que definas). Añade un archivo `LICENSE` si procede.
