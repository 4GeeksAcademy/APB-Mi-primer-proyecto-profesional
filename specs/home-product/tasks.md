# Tareas: Home y Vista de producto

## Preparación e integración común

- [ ] Revisar `spec.md` y las fuentes de verdad comunes que estén disponibles (`CONTEXT.md`, `DESIGNN.md`/`DESIGN.md` y `docs/reference/base.html`). Resultado: requisitos y convenciones aplicables identificados; si faltan fuentes, las decisiones de diseño común quedan pendientes.
- [ ] Identificar la navegación, las rutas y los elementos comunes existentes que puedan reutilizarse en Home y Vista de producto. Resultado: puntos de integración localizados sin modificar vistas ajenas; rutas, destinos o componentes no documentados quedan pendientes y no se inventan.

## Home

- [ ] Integrar en Home la navegación/header y el footer comunes. Resultado: la vista conserva la estructura compartida del proyecto.
- [ ] Presentar la marca y la propuesta de la tienda usando el contenido definido por el equipo. Resultado: ambas quedan visibles en Home sin inventar datos.
- [ ] Crear la sección principal (hero) con el producto o la campaña destacada definida para la tienda. Resultado: Home contiene el hero requerido.
- [ ] Incorporar la sección de nuevos lanzamientos con los productos definidos por el equipo. Resultado: la sección requerida está presente y usa contenido disponible.
- [ ] Incorporar la sección de productos más vendidos con los productos definidos por el equipo. Resultado: la sección requerida está presente y usa contenido disponible.
- [ ] Integrar en el footer la información de tienda disponible en las fuentes comunes. Resultado: Home muestra el footer requerido sin inventar información.

## Vista de producto

- [ ] Integrar la navegación/header y el footer comunes en la Vista de producto. Resultado: la vista conserva los elementos compartidos del proyecto.
- [ ] Mostrar imagen, nombre, código/referencia y precio del producto seleccionado. Resultado: los cuatro datos requeridos aparecen en la vista.
- [ ] Mostrar la descripción detallada, los materiales y los usos recomendados/escenarios definidos para el producto. Resultado: cada contenido requerido se presenta sin inventar datos.
- [ ] Añadir controles que permitan seleccionar talla y cantidad. Resultado: ambos valores se pueden seleccionar; las opciones y reglas no se inventan.
- [ ] Incluir el botón «Agregar al carrito». Resultado: el botón requerido está presente; su efecto posterior no se presupone.

## Requisitos transversales y verificación

- [ ] Conectar la navegación de Home y Vista de producto con las demás vistas usando únicamente rutas y destinos definidos por el proyecto. Resultado: navegación integrada sin crear rutas por suposición.
- [ ] Adaptar Home y Vista de producto a móvil, tablet y escritorio, usando Tailwind CSS y respetando el sistema visual común. Resultado: ambas vistas cumplen la adaptación responsive indicada en la spec.
- [ ] Usar HTML semántico en ambas vistas. Resultado: el marcado cumple el requisito explícito de la spec; no se atribuyen criterios de accesibilidad adicionales no definidos.
- [ ] Revisar todos los criterios de aceptación de `spec.md` para ambas vistas. Resultado: cada criterio está comprobado y el trabajo no modifica vistas ajenas ni añade funcionalidades fuera del alcance.
