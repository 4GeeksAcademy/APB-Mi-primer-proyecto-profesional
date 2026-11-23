# Plan: catálogo

## Objetivo

Implementar la vista estática `catalogo.html` en la raíz y documentar el trabajo como funcionalidad independiente, respetando la referencia compartida y los límites del prototipo.

## Pasos

1. Reutilizar la estructura visual y los textos comunes de `docs/reference/base.html`; establecer rutas de raíz para Inicio y Catálogo, sin inventar destinos para enlaces pendientes.
2. Añadir título, presentación, filtros visuales accesibles y 20 productos de ejemplo con placeholders 4:5, precios EUR y carga diferida salvo la primera imagen.
3. Marcar el catálogo con `OfferCatalog` y cada entrada con `CatalogItem` que contiene un `Product` y una `Offer`, evitando datos no visibles o no confirmados.
4. Verificar cantidad de artículos, microdatos, imágenes y enlaces existentes; comprobar el diff y registrar limitaciones (Home ausente y viewport visual no comprobado si no hay navegador disponible).

## Criterios de aceptación

- [x] `catalogo.html` conserva la cabecera y el pie de la referencia y tiene un único `h1`.
- [x] Los filtros etiquetados están antes de una rejilla de 20 productos.
- [x] La rejilla declara 1/2/4 columnas en móvil/tablet/escritorio; las imágenes conservan proporción y dimensiones.
- [x] Microdatos coherentes con el contenido visible usan `OfferCatalog`, `CatalogItem`, `Product` y `Offer`.
- [x] El enlace de Catálogo funciona en la raíz; Inicio apunta a `index.html`, cuya página aún no existe.
- [x] No se agrega JavaScript de aplicación ni se presentan filtros como funcionales.

La comprobación automática de estructura pasó. Quedan pendientes la revisión visual en navegador y la navegación recíproca una vez creada la Home.
