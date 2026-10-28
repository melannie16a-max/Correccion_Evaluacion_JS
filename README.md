# TecnoStock

TecnoStock es una tienda web sencilla de productos tecnológicos. Permite consultar un catálogo, filtrar productos y administrar un carrito de compras desde el navegador.

## Funcionalidades

- Catálogo de productos con precio, categoría, descripción y disponibilidad.
- Búsqueda por nombre o descripción.
- Filtros por categoría y disponibilidad.
- Ordenamiento por precio, de menor a mayor o de mayor a menor.
- Carrito con controles para agregar, quitar y cambiar cantidades.
- Guardado del carrito en `localStorage`, para conservarlo al actualizar la página.
- Cálculo automático de subtotal y total. Se aplica un descuento del 10 % cuando el subtotal es igual o superior a $300.000 COP.
- Confirmación de pedido de demostración mediante un mensaje en pantalla; no procesa pagos reales.

## Cómo ejecutar

Como el catálogo se carga desde un archivo JSON, abre el proyecto con un servidor local en lugar de abrir `index.html` directamente.

Una opción es usar la extensión **Live Server** de Visual Studio Code y elegir **Open with Live Server** sobre `index.html`.

También puedes iniciar un servidor con Python desde la carpeta del proyecto:

```bash
python3 -m http.server 8000
```

Después visita <http://localhost:8000>.

## Estructura del proyecto

```text
.
├── index.html              # Página principal
├── css/
│   └── styles.css          # Estilos
├── data/
│   └── products.json       # Catálogo de productos
└── js/
    ├── app.js              # Inicialización, filtros y eventos
    ├── api.js              # Carga y validación del catálogo
    ├── cart.js             # Lógica del carrito y cálculos
    ├── storage.js          # Persistencia del carrito en el navegador
    └── components/         # Componentes de productos y carrito
```

## Catálogo

Los productos se encuentran en `data/products.json`. Cada producto incluye un identificador, nombre, categoría, precio en pesos colombianos, unidades disponibles, descripción y estado (`active`). Para que un producto se pueda agregar al carrito debe estar activo y tener inventario disponible.

## Tecnologías

- HTML
- CSS
- JavaScript con módulos ES y Web Components
- `localStorage` para guardar el carrito en el navegador