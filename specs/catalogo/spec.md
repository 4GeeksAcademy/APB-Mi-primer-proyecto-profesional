# Especificación: catálogo

## Objetivo y alcance

Crear `catalogo.html` en la raíz, donde `server.py` sirve las páginas estáticas, como vista navegable de catálogo para el prototipo. Seguir `AGENTS.md`, `CONTEXT.md`, `DESIGN.md` y la estructura visual de `docs/reference/base.html`, sin modificar ni sustituir esos documentos.

Esta especificación concreta la vista de catálogo. Los productos y precios son ejemplos visibles de demostración; no representan una oferta comercial real.

## Contenido y estructura

- Documento HTML5 en español, con título y descripción propios.
- Una cabecera y un pie que conserven el contenido, la estructura y el estilo de `docs/reference/base.html`.
- Un único `h1` descriptivo, una breve presentación y filtros visuales por categoría y talla antes del listado.
- Veinte tarjetas de productos variados, organizados entre calzado, camisas, pantalones y accesorios. Cada tarjeta muestra una imagen placeholder relacionada, nombre, categoría y precio de demostración en euros.
- Filtros deshabilitados y etiquetados con un aviso claro: son solo visuales y no filtran; no añadir JavaScript.
- Imágenes uniformes 4:5, con atributos `width` y `height`, texto alternativo descriptivo y carga diferida salvo la primera imagen.

## Responsive y accesibilidad

- Rejilla mobile-first de una columna en móvil, dos desde `md` (768 px) y cuatro desde `xl` (1280 px), de acuerdo con la petición de esta vista.
- Usar contenedor `max-w-7xl`, padding de la plantilla y tokens Tailwind definidos en la referencia. Mantener el foco visible, navegación por teclado, etiquetas de filtros y sin desbordamiento horizontal.
- La navegación incluye Inicio hacia `index.html` y Catálogo hacia `catalogo.html`; la página actual se identifica con `aria-current="page"`. Si `index.html` aún no existe, registrar la limitación: no crear una Home fuera del alcance.
- Mantener como pendientes los destinos no existentes de carrito, categorías, legal y contacto, igual que en la plantilla.

## Datos estructurados

- Usar microdatos Schema.org sin scripts: el listado como `OfferCatalog`; cada entrada como `CatalogItem`, enlazada a ese catálogo mediante `catalog` y a un `Product` mediante `item`.
- En cada `Product`, incluir únicamente datos visibles y disponibles en la demo: `name`, `image`, `category` y `offers`. Cada `Offer` muestra precio y moneda EUR.
- No inventar marca, referencia, tallas concretas, disponibilidad, reseñas, fechas de alta ni otros datos no confirmados.

## Límites

- No implementar búsqueda o filtros funcionales, carrito, ficha de producto, pedidos o pagos.
- No añadir JavaScript, frameworks, dependencias, backend ni CSS adicional innecesario.
- No modificar la navbar/footer de las demás vistas ni documentos generales; mantener la copia de la referencia coherente.
- Las imágenes son placeholders remotos; el diseño debe seguir indicando que los precios y productos son de demostración.
