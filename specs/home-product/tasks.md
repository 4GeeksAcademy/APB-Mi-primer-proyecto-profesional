# Tareas: Home y Vista de producto

La dirección visual de `DESIGN.md` está presentada allí como propuesta; estas tareas la toman como referencia documentada, sin convertirla en una decisión formalmente ratificada.

## Preparación e integración común

- [ ] Revisar `spec.md`, `CONTEXT.md` y `DESIGN.md`; comprobar si existe una plantilla base común. Resultado: requisitos funcionales y visuales aplicables identificados antes de implementar.
- [ ] Localizar el shell de navegación/footer, las rutas existentes, los estilos globales y las recetas compartidas (`site-container`, `btn-primary`, `btn-secondary`, `form-control`, `product-card`). Resultado: reutilizaciones confirmadas sin modificar vistas ajenas ni inventar rutas o componentes; si no hay shell común, resolver con el equipo la diferencia entre los elementos de header enumerados en `CONTEXT.md` y `DESIGN.md`.
- [ ] Aplicar en Home y Product View los tokens de color de `DESIGN.md` sin redefinirlos por página. Resultado: acciones, fondos, textos, bordes y estados usan los tokens acordados, incluidos `brand-pine`, `brand-coral`, `brand-ochre`, `page`, `surface`, `surface-subtle`, tokens de texto/borde y estados.
- [ ] Aplicar la tipografía DM Serif Display a titulares y DM Sans a cuerpo, navegación y controles, siguiendo jerarquía y pesos de `DESIGN.md`. Resultado: tipografía consistente con las demás páginas.
- [ ] Aplicar `site-container`/su receta existente con ancho `max-w-7xl`, centrado y padding horizontal 16/24/32 px. Resultado: ambas vistas respetan el contenedor común.
- [ ] Usar la escala de espaciado Tailwind basada en 4 px y las separaciones de sección 48/64/80 px definidas en `DESIGN.md`. Resultado: espaciado consistente, sin valores de diseño inventados.
- [ ] Reutilizar las recetas nombradas donde correspondan y estén disponibles; si no existen, usar las utilidades Tailwind existentes para los valores documentados. Resultado: no se añaden dependencias, configuración Tailwind ni abstracciones compartidas innecesarias.

## Home

- [ ] Integrar en Home el header común de las cinco páginas, conservando la composición y destinos acordados por el equipo. Resultado: header coherente con el shell común, considerando los elementos enumerados en `CONTEXT.md` y el tratamiento descrito en `DESIGN.md`, sin añadir, fusionar ni eliminar elementos por inferencia.
- [ ] Presentar la marca y la propuesta de la tienda usando el contenido definido por el equipo. Resultado: ambas quedan visibles en Home sin inventar datos.
- [ ] Crear la sección principal (hero) con el producto o la campaña destacada definida para la tienda. Resultado: Home contiene el hero requerido.
- [ ] Incorporar los listados horizontales de nuevos lanzamientos y más vendidos definidos en `CONTEXT.md`. Resultado: ambas secciones contienen product cards con imagen 4:5 y datos disponibles; las imágenes conservan dimensiones y texto alternativo.
- [ ] Integrar el footer común de las cinco páginas con las secciones de categorías (calzado, camisas, pantalones, accesorios), legal (términos, privacidad, sobre la marca) y contacto. Resultado: orden y destinos coinciden con el footer compartido; no se inventan datos de contacto.

## Vista de producto

- [ ] Integrar en Product View el mismo header y footer comunes que Home y las otras páginas. Resultado: contenido, orden, destinos y tratamiento visual se mantienen consistentes.
- [ ] Componer Product View en dos columnas en escritorio, con la imagen a aproximadamente la mitad del ancho, y apilar imagen e información en móvil. Resultado: composición coincide con `CONTEXT.md` y la regla responsive de `DESIGN.md`.
- [ ] Mostrar imagen principal, nombre, referencia, talla, precio, selector de cantidad y botón «Agregar al carrito» en el bloque de información. Resultado: campos requeridos visibles y ordenados sin inventar comportamiento de carrito.
- [ ] Mostrar debajo la descripción detallada, materiales y uso recomendado/escenarios proporcionados para el producto. Resultado: contenido completo y basado en datos del equipo.
- [ ] Aplicar proporción de imagen 4:5, declarar dimensiones, usar texto alternativo descriptivo y no diferir la carga de la imagen principal visible. Resultado: imagen consistente y accesible.
- [ ] Aplicar `form-control` a talla/cantidad y `btn-primary` al CTA; usar `btn-secondary` solo en acciones secundarias ya definidas. Resultado: controles y botón respetan los patrones de diseño sin añadir acciones.

## Requisitos transversales y verificación

- [ ] Implementar responsive mobile-first con breakpoints estándar Tailwind `sm` 640, `md` 768, `lg` 1024 y `xl` 1280 px; comprobar al menos 375, 768 y 1440 px. Resultado: contenido legible, sin solapamiento ni scroll horizontal de página.
- [ ] Usar HTML semántico y mantener un H1 descriptivo por vista y jerarquía continua. Resultado: estructura de lectura clara.
- [ ] Aplicar estados de botones y controles: hover, active, focus-visible y disabled según `DESIGN.md`; foco de 2 px/offset 2 px con coral en fondos claros y mostaza sobre fondos oscuros; objetivos táctiles de al menos 44 × 44 px. Resultado: estados perceptibles y navegación por teclado usable.
- [ ] Verificar contraste AA, etiquetas visibles de controles, texto alternativo y que los estados no dependan solo del color; respetar `prefers-reduced-motion`. Resultado: requisitos de accesibilidad del sistema de diseño aplicados.
- [ ] Usar solo Tailwind y la configuración/dependencias existentes. Resultado: no se agrega dependencia ni configuración nueva innecesaria.
- [ ] Revisar todos los criterios de aceptación de `spec.md` y comprobar que Home/Product View conservan datos de producto consistentes y no cambian otras vistas. Resultado: alcance respetado y criterios comprobados.
