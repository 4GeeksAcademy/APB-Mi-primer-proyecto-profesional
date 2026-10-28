# Plan: plantilla HTML común

## Objetivo

Crear `docs/reference/base.html` como referencia estática para las cinco páginas, siguiendo `../base-layout/spec.md`, `CONTEXT.md`, `DESIGN.md` y `AGENTS.md`. Este plan no implementa la plantilla ni las vistas.

## Pasos

1. **Confirmar los datos pendientes.** Acordar marca, logotipo, idioma y destinos de navegación, así como la representación de búsqueda y cuenta como demostración. Mantener la propuesta visual de `DESIGN.md` como provisional; no inventar identidad, contacto ni enlaces. Comprobar la rama y la configuración existente antes de modificar archivos.
2. **Crear la estructura HTML.** Añadir HTML5, UTF-8, viewport, idioma y metadatos de referencia. Cargar Tailwind v4 mediante `https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4`. Incluir enlace de salto al contenido, `header` con `nav`, un único `main` vacío con identificador y `footer`. No añadir un `h1` genérico ni contenido de las vistas.
3. **Completar los elementos comunes.** Preparar navbar con marca, Inicio, Catálogo, búsqueda, cuenta y carrito. Incluir en el footer Categorías (calzado, camisas, pantalones y accesorios), Legal (términos y condiciones, política de privacidad y sobre la marca) y Contacto. Usar solo destinos confirmados; mostrar como texto pendiente lo que no tenga destino. Aplicar utilidades mobile-first, contenedor de 1280 px, espaciado, foco y reglas visuales de `DESIGN.md`, con cabecera adaptable y footer apilado en móvil.
4. **Comprobar la referencia.** Revisar estructura HTML, `main` sin contenido, carga del CDN y destinos reales de enlaces. Comprobar teclado, salto al contenido, etiquetas, foco y contraste, además de ausencia de solapamientos y desbordamientos a 375, 768 y 1440 px. Registrar las limitaciones sin atribuir pruebas no realizadas.

## Límites

- No implementar las cinco vistas, componentes, backend, búsqueda real, autenticación ni operaciones de compra.
- No añadir JavaScript de aplicación ni dependencias; el script de infraestructura de Tailwind por CDN es la única excepción.
- No enviar ni almacenar datos mediante los controles de demostración.
- No añadir infraestructura de pruebas. PageSpeed Insights y su captura quedan para la entrega publicada.
- Mantener sincronizadas las futuras copias HTML de navbar y footer, ajustando rutas relativas y página actual cuando corresponda.

## Resultado esperado

Una plantilla en `docs/reference/base.html` con navbar y footer comunes, accesibles y responsive, Tailwind v4 por CDN y un `main` vacío listo para recibir el contenido de cada vista.