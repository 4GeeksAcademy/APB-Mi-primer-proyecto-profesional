# Plan de implementación: Home y Vista de producto

Alcance: implementar exclusivamente Home y Vista de producto, respetando [spec.md](spec.md), el sistema común del equipo y las vistas de otros compañeros.

1. Revisar la spec y, si están disponibles, `CONTEXT.md`, `DESIGNN.md` o `DESIGN.md`, `docs/reference/base.html` y la navegación existente. Identificar los elementos comunes reutilizables y las rutas ya definidas; no inventar componentes ni rutas. Si estas fuentes no están disponibles, dejar pendientes las decisiones de diseño común, componentes y destinos de navegación.
2. Implementar Home con la navegación/header y footer comunes, la presentación de marca y propuesta, el hero destacado, nuevos lanzamientos y productos más vendidos.
3. Implementar Vista de producto con imagen, nombre, referencia, precio, selección de talla y cantidad, botón «Agregar al carrito», descripción, materiales y usos recomendados; conservar navegación/header y footer comunes.
4. Enlazar ambas vistas con las demás vistas usando la navegación y las rutas definidas por el proyecto. No añadir un flujo de carrito ni otro comportamiento que no esté especificado.
5. Adaptar ambas vistas a móvil, tablet y escritorio con HTML semántico y Tailwind CSS, siguiendo el sistema visual común.
6. Verificar los criterios de aceptación de ambas vistas y confirmar que no se modificaron vistas fuera del alcance.

## Pendiente del equipo

- Confirmar el sistema visual, la estructura y los componentes comunes, además de las rutas y destinos de navegación, a partir de la documentación compartida cuando esté disponible. No fijar decisiones propias para sustituir esa información.
