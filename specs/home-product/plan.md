# Plan de implementación: Home y Product View

Alcance exclusivo: implementar Home y Product View conforme a [spec.md](spec.md), [CONTEXT.md](../../CONTEXT.md) y [DESIGN.md](../../DESIGN.md), respetando las demás vistas.

`DESIGN.md` presenta su dirección visual como propuesta. Este plan usa sus tokens y reglas como referencia documentada, sin atribuirles una ratificación que el documento no indica.

1. **Preparar la integración.** Revisar las rutas, los estilos y el shell común existente. Mantener el header y el footer coherentes en las cinco páginas. `CONTEXT.md` enumera logo, búsqueda y cuenta en la navbar; `DESIGN.md` describe marca, navegación y acceso al carrito, además de los tratamientos visuales comunes. Reutilizar la composición común acordada, sin fusionar ni descartar elementos por inferencia, y no modificar vistas ajenas.
2. **Aplicar el sistema visual común.** Usar los tokens de color de `DESIGN.md`; DM Serif Display para titulares y DM Sans para cuerpo, navegación y controles; `max-w-7xl`, escala de espaciado base de 4 px y paddings responsive de 16/24/32 px. Seguir las recetas `site-container`, `btn-primary`, `btn-secondary`, `form-control` y `product-card` donde correspondan. No crear configuración Tailwind ni dependencias nuevas si no son necesarias.
3. **Implementar Home.** Componer la presentación de marca, hero y dos listados horizontales de nuevos lanzamientos y más vendidos con el header/footer comunes. Las product cards e imágenes seguirán proporción 4:5 y la información disponible del producto.
4. **Implementar Product View.** Presentar en escritorio imagen e información en dos columnas, con la imagen aproximadamente a la mitad del ancho; apilar la composición en móvil. Incluir los datos, selectores, botón y descripción indicados en `spec.md` y `CONTEXT.md`, sin añadir comportamiento de carrito no especificado.
5. **Integrar y verificar.** Usar únicamente rutas existentes/acordadas; aplicar responsive mobile-first con breakpoints estándar de Tailwind, HTML semántico, estados de controles, foco visible y contraste del sistema de diseño. Comprobar criterios funcionales y visuales sin modificar páginas ajenas.

## Tokens y reglas visuales a respetar

| Token | Valor | Uso definido |
| --- | --- | --- |
| `brand-pine` | `#17483F` | Acción primaria, enlaces destacados, footer |
| `brand-coral` | `#B64D3C` | Acento y foco sobre fondo claro |
| `brand-ochre` | `#D7A13B` | Acento y foco sobre fondo oscuro |
| `page` | `#F7F8F4` | Fondo general |
| `surface` | `#FFFFFF` | Superficies y formularios |
| `surface-subtle` | `#EDF2EE` | Secciones secundarias y fondos suaves |
| `text-primary` | `#202522` | Texto principal y titulares |
| `text-secondary` | `#66716B` | Texto auxiliar y metadatos |
| `border` | `#D7DED8` | Bordes y separadores |
| `disabled-text` | `#646D67` | Texto deshabilitado |
| `success` / `success-bg` | `#286749` / `#EAF4EE` | Estado correcto |
| `warning` / `warning-bg` | `#795300` / `#FFF3D8` | Aviso |
| `error` / `error-bg` | `#A33131` / `#FCEBEC` | Error |
| `info` / `info-bg` | `#205A75` / `#EAF3F8` | Información |

- Seguir la jerarquía tipográfica y pesos de `DESIGN.md`; en particular, DM Serif Display 400 en H1-H3 y DM Sans en navegación, texto, botones y controles.
- Usar contenedor centrado `max-w-7xl`; padding horizontal de 16 px móvil, 24 px tablet y 32 px escritorio; escala Tailwind basada en 4 px (`1, 2, 3, 4, 6, 8, 12, 16, 20`) y separación entre secciones 48/64/80 px.
- Breakpoints estándar: `sm` 640, `md` 768, `lg` 1024 y `xl` 1280 px. La composición Product View usa dos columnas en escritorio y pila vertical en móvil.
- Product cards e imágenes: proporción 4:5, sin sombra/borde decorativo por defecto; no ocultar contenido en hover. Declarar dimensiones, texto alternativo y carga diferida solo fuera de la zona inicial.
- Botones: primaria verde pino con texto blanco; secundaria transparente/blanca con borde y texto verde pino; radio máximo 4 px y objetivo táctil mínimo 44 × 44 px. Estados hover, active y disabled según `DESIGN.md`.
- Foco `:focus-visible`: contorno 2 px con separación 2 px; coral en fondo claro y mostaza sobre fondo oscuro. Contraste mínimo WCAG AA (4,5:1 texto normal y 3:1 texto grande); estados no comunicados solo por color; respetar teclado y `prefers-reduced-motion`.
- Formularios: controles con etiqueta visible y receta `form-control`; altura mínima 48 px. Mantener validación y estados descritos en el sistema común sin inventar reglas de talla/cantidad.

## Pendiente real

- La fuente visual describe los patrones nombrados como recetas, no como clases/componentes ya implementados. El repositorio actual no contiene CSS/HTML que los defina; reutilizarlos si el shell/estilos compartidos del equipo los aporta. Si no existen, aplicar los valores documentados con utilidades Tailwind existentes, sin crear configuración o abstracciones compartidas nuevas por iniciativa propia.
- Las rutas concretas y cualquier dato de marca/producto no incluidos en las fuentes deben tomarse del equipo; no asignar destinos, contenidos o comportamiento de carrito por inferencia.
- Si no existe un shell común que resuelva la diferencia entre los elementos de header enumerados por `CONTEXT.md` y `DESIGN.md`, confirmar la composición con el equipo antes de implementarla.
