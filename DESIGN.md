# Sistema de diseño

## Alcance y estado de las decisiones

Este documento define una base visual común para Inicio, Catálogo, Producto, Carrito y Checkout. No implementa esas vistas.

El briefing de `AGENTS.md` establece los requisitos obligatorios: prototipo de una tienda de ropa, HTML y Tailwind CSS, cinco páginas navegables, cabecera y pie coherentes, diseño responsive y accesible, y operaciones dinámicas representadas como demostración. No define marca, logotipo, colores ni tipografías.

Por eso, las decisiones estéticas de este documento son una **propuesta de diseño** para usar como base común. No se debe inventar un nombre de marca, una historia corporativa, productos, precios o funcionalidades para completar la identidad visual. Los datos visibles de cada página deben proceder del briefing acordado.

## Dirección visual

Estética editorial contemporánea para una tienda de moda: fotografía de producto clara y protagonista, tipografía con carácter en titulares, interfaz sobria y detalles de color cálidos. El conjunto debe sentirse cuidado y actual, sin apariencia de panel administrativo ni decoración que compita con las prendas.

- Usar fondos claros y superficies limpias; reservar el verde pino para acciones y elementos de marca, y coral y mostaza para acentos puntuales.
- Evitar degradados, sombras decorativas, contenedores anidados y tarjetas con aspecto de panel flotante.
- Mantener una densidad cómoda para comparar productos y leer importes, tallas y formularios.
- No añadir insignias comerciales, valoraciones, descuentos, disponibilidad o mensajes promocionales si no están respaldados por el contenido del proyecto.

## Paleta

La siguiente paleta es propuesta. Los nombres semánticos son la referencia; evitar elegir colores distintos por página.

| Token | Valor | Uso |
| --- | --- | --- |
| `brand-pine` | `#17483F` | Acción primaria, enlaces destacados y fondo del footer. |
| `brand-coral` | `#B64D3C` | Acento, foco sobre fondos claros y estados que necesiten énfasis. |
| `brand-ochre` | `#D7A13B` | Acento gráfico y foco sobre fondos oscuros; no usar texto blanco encima. |
| `page` | `#F7F8F4` | Fondo general. |
| `surface` | `#FFFFFF` | Formularios y superficies que necesiten separarse del fondo. |
| `surface-subtle` | `#EDF2EE` | Secciones secundarias, campos deshabilitados y fondos de estado suaves. |
| `text-primary` | `#202522` | Texto principal y titulares. |
| `text-secondary` | `#66716B` | Texto auxiliar, etiquetas secundarias y metadatos. |
| `border` | `#D7DED8` | Bordes, separadores y contornos de controles. |
| `disabled-text` | `#646D67` | Texto deshabilitado sobre `surface-subtle`. |
| `success` / `success-bg` | `#286749` / `#EAF4EE` | Confirmaciones y estados correctos. |
| `warning` / `warning-bg` | `#795300` / `#FFF3D8` | Avisos y estados que requieren atención. |
| `error` / `error-bg` | `#A33131` / `#FCEBEC` | Errores de campo y mensajes de error. |
| `info` / `info-bg` | `#205A75` / `#EAF3F8` | Información neutral. |

El texto normal debe alcanzar contraste WCAG AA: mínimo 4,5:1; texto grande, mínimo 3:1. Verificar los pares de color usados realmente, especialmente botones, foco y mensajes. No comunicar un estado solo mediante color: acompañarlo de texto y, cuando corresponda, un símbolo accesible.

## Tipografía y jerarquía

Tipografías propuestas: **DM Serif Display** para titulares editoriales y **DM Sans** para navegación, cuerpo, controles y datos. Cargar solo los pesos necesarios, con `font-display: swap` si se usan fuentes web, y declarar alternativas locales para que la página siga siendo legible sin conexión. No usar texto de interfaz en mayúsculas sostenidas ni espaciado negativo entre letras.

| Elemento | Móvil | Escritorio | Peso / interlineado |
| --- | --- | --- | --- |
| H1 | 32 px | 48 px | DM Serif Display 400; 1,15. |
| H2 | 28 px | 36 px | DM Serif Display 400; 1,2. |
| H3 | 22 px | 24 px | DM Serif Display 400; 1,25. |
| H4 y título de bloque | 18 px | 20 px | DM Sans 600; 1,3. |
| Texto principal | 16 px | 16 px | DM Sans 400; 1,5. |
| Texto secundario | 14 px | 14 px | DM Sans 400; 1,45. |
| Etiqueta / metadato | 12 px | 12 px | DM Sans 500 o 600; 1,35. |
| Botón | 14 px | 14 px | DM Sans 600; 1,4. |

Los tamaños cambian en puntos de ruptura discretos; no escalar tipografía con unidades de viewport. Mantener un solo H1 descriptivo por página y una jerarquía semántica continua.

## Espaciado y layout

- Usar una escala base de 4 px: `1` = 4, `2` = 8, `3` = 12, `4` = 16, `6` = 24, `8` = 32, `12` = 48, `16` = 64 y `20` = 80 px. Preferir la escala de espaciado estándar de Tailwind.
- Ancho máximo del contenido: **1280 px** (`max-w-7xl`), centrado con márgenes automáticos.
- Padding horizontal del contenedor: 16 px en móvil, 24 px en tablet y 32 px en escritorio amplio.
- Separación entre secciones: 48 px en móvil, 64 px en tablet y 80 px en escritorio. Reducirla en bloques densos de formularios o resumen.
- Cuadrícula del catálogo: 2 columnas en móvil, 3 en tablet y 4 en escritorio amplio; separación de 12, 16 y 24 px respectivamente.
- En escritorio, la ficha de producto puede repartir imagen y datos en dos columnas. Carrito y checkout pueden usar contenido principal más resumen lateral; en móvil, apilar y mantener el resumen cerca de la acción relacionada. Estas son reglas de composición, no funcionalidades nuevas.
- Usar `min-width: 0` donde el contenido de una cuadrícula pueda desbordar. Ninguna vista debe provocar desplazamiento horizontal de la página.

## Cabecera y navegación

La cabecera debe ser la misma en las cinco páginas: marca a la izquierda, navegación principal y acceso al carrito a la derecha en escritorio. En móvil puede distribuirse en dos filas para conservar enlaces visibles y objetivos táctiles suficientes; no depender de un menú interactivo que requiera JavaScript.

- Altura de referencia: 72 px en escritorio y 64 px en móvil, con padding horizontal alineado al contenedor.
- Fondo `surface`, borde inferior de 1 px `border`; sin sombra persistente.
- Enlaces en DM Sans 14 px / 500. Página actual indicada con subrayado o borde inferior y `aria-current="page"`, no solo con cambio de color.
- Marca enlazada a Inicio. Mantener etiquetas y destinos idénticos en todas las copias estáticas del header.
- El foco de teclado debe quedar visible y no ocultarse bajo una cabecera fija. No fijar la cabecera a pantalla salvo decisión posterior del equipo.

## Footer

El footer debe repetir contenido, orden y destinos en las cinco páginas. Usar fondo `brand-pine`, texto blanco y enlaces con contraste suficiente. Disponer enlaces en columnas en escritorio y en una columna o grupos apilados en móvil.

- Padding vertical de referencia: 48 px en móvil y 64 px en escritorio.
- Títulos de grupo: DM Sans 14 px / 600; enlaces y texto auxiliar: 14 px / 400.
- Separadores con una variante clara de bajo contraste que conserve la legibilidad; enlaces con subrayado en hover y foco visible.
- Incluir únicamente información y enlaces definidos por el equipo; no inventar redes sociales, dirección, contacto o políticas.

## Botones e interacción

Todos los botones y enlaces de acción deben tener texto claro, un área táctil de al menos 44 × 44 px y estados perceptibles. Usar iconos solo como complemento o cuando el significado sea inequívoco; los controles solo con icono necesitan nombre accesible y tooltip si su función no es evidente.

| Variante | Tratamiento |
| --- | --- |
| Primaria | Fondo `brand-pine`, texto blanco, radio de 4 px. Reservar para la acción principal del bloque. |
| Secundaria | Fondo transparente o `surface`, borde `brand-pine`, texto `brand-pine`. |
| Enlace / terciaria | Sin caja; texto subrayado al hover y foco, área de interacción suficiente. |
| Destructiva | Usar `error` solo para una acción destructiva que ya exista en el alcance. |

- Hover: transición de color breve, alrededor de 150 ms; no depender de animación para comunicar estado.
- Active: oscurecer ligeramente el fondo o aplicar una variación de borde, sin desplazar el layout.
- Focus: `:focus-visible` con contorno de 2 px y separación de 2 px; coral sobre fondos claros y mostaza sobre verde oscuro. El contorno no debe quedar recortado.
- Disabled: atributo `disabled` cuando proceda, texto `disabled-text`, fondo `surface-subtle`, sin hover y cursor no permitido. No simular deshabilitado solo reduciendo opacidad.
- Respetar `prefers-reduced-motion` y no animar cambios que dificulten la lectura.

## Productos e imágenes

Las cards de producto deben ser ligeras, sin sombra ni borde por defecto. Usar imagen arriba y, debajo, nombre, variante o referencia si corresponde, talla cuando sea visible y precio. La información debe conservar la misma referencia, nombre, imagen y precio entre las vistas.

- Imagen en proporción **4:5**, ancho completo, `object-fit: cover`; mantener un encuadre consistente entre productos.
- No poner el texto principal encima de la fotografía. Si se muestra un borde, usar `border` y radio máximo de 4 px.
- Hover de escritorio discreto; no ocultar información ni acciones esenciales hasta el hover.
- Declarar `width` y `height`, usar formatos optimizados y `loading="lazy"` en imágenes fuera de la zona inicial. La imagen principal visible al cargar no debe tener carga diferida.
- Escribir texto alternativo descriptivo para el contenido de la imagen; usar `alt=""` solo en imágenes puramente decorativas.

## Formularios y mensajes

- Colocar etiqueta visible encima del campo; no usar el placeholder como sustituto de la etiqueta.
- Inputs y selects: altura mínima de 48 px, padding horizontal de 12 px, texto de 16 px, fondo blanco, borde de 1 px y radio de 4 px.
- Estado normal: borde `border`; hover: borde `text-secondary`; foco: borde `brand-pine` y contorno visible de 2 px; error: borde `error` y mensaje asociado, además de `aria-invalid` cuando proceda.
- El texto de ayuda y los errores se muestran junto al campo y se asocian programáticamente. No eliminar el indicador visual de foco del navegador sin reemplazarlo.
- Mensajes de éxito, aviso, error e información usan los pares de color definidos arriba, texto explícito y un icono solo como refuerzo.
- Mantener validación nativa de HTML cuando corresponda. En Checkout, el pago se presenta como demostración y nunca se solicitan datos reales de tarjeta, conforme a `AGENTS.md`.

## Responsive y accesibilidad

Implementar mobile-first y validar como mínimo a 375, 768 y 1440 px. Usar los breakpoints estándar de Tailwind (`sm` 640, `md` 768, `lg` 1024, `xl` 1280 px), no introducir otros sin necesidad comprobada.

- Móvil: una columna para formularios y resúmenes; catálogo en dos columnas; cabecera y footer apilables; targets táctiles de al menos 44 px.
- Tablet: conservar dos columnas cuando el contenido lo permita; catálogo en tres columnas desde `md` si las tarjetas siguen siendo legibles.
- Escritorio: limitar el ancho de lectura, usar cuatro columnas de producto desde `xl` y aprovechar columnas laterales solo para resúmenes o composición de producto.
- Mantener orden de lectura y foco igual al orden visual. No usar `order` para cambiarlo de forma incoherente.
- Garantizar navegación completa con teclado, estados de foco visibles, etiquetas asociadas, enlaces descriptivos, textos alternativos y contraste AA.
- Permitir zoom de página y reflujo sin pérdida de contenido. Revisar textos largos, importes y controles para evitar solapamientos.

## Convenciones de Tailwind y reutilización

- Mantener HTML semántico y clases Tailwind coherentes. Aplicar utilidades mobile-first, los breakpoints estándar y los valores de la escala definida aquí.
- Reutilizar la versión/configuración disponible en el repositorio. El README menciona Tailwind CSS v4 por CDN como opción; no añadir dependencias, cambiar herramientas ni crear configuración en esta fase.
- Evitar estilos inline, clases arbitrarias repetidas y `@apply` como sistema general. Si la implementación necesita tokens de marca compartidos, definirlos una sola vez en la hoja global que acuerde el equipo, usando el mecanismo compatible con la configuración existente; no duplicar hexadecimales entre páginas.
- No crear componentes, JavaScript o motor de plantillas para compartir header/footer: el proyecto requiere HTML estático. Mantener sus copias sincronizadas.
- Recetas de clases a repetir de forma consistente: `site-container` (ancho máximo y padding horizontal), `btn-primary`, `btn-secondary`, `form-control`, `product-card` y `status-message`. Son nombres de patrones, no componentes ya implementados; cualquier extracción a clases CSS compartidas requiere una hoja global existente o una necesidad confirmada.
- Para color de texto, fondo, borde y foco, seguir siempre los tokens de la tabla. Para radios usar 4 px como máximo en botones, campos y tarjetas; evitar sombras salvo separación funcional indispensable.

## Coherencia entre vistas

1. Usar el mismo contenedor, paleta, escala tipográfica, header y footer en las cinco páginas.
2. Mantener consistentes las referencias, nombres, tallas, imágenes y precios de cada producto.
3. Reservar el verde pino para acciones principales; no cambiar el color de la acción principal entre páginas.
4. Mantener etiquetas, navegación, botones, formularios y estados con los mismos tamaños y tratamientos.
5. Hacer que la página actual se identifique en navegación y que el recorrido Inicio → Catálogo → Producto → Carrito → Checkout sea comprensible con enlaces HTML.
6. Representar en la interfaz los estados dinámicos como ejemplos de demostración, sin insinuar que se procesan pedidos o pagos reales.
7. Si el equipo acuerda otra dirección visual, actualizar primero este documento y luego aplicar el cambio de forma consistente a las cinco vistas.
