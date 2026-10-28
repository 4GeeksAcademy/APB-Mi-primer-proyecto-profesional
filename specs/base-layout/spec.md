# Especificación de la plantilla HTML común

## Objetivo y alcance

Definir una plantilla de referencia para Inicio, Catálogo, Producto, Carrito y Checkout. Su futura ubicación será `docs/reference/base.html`. Esta especificación no implementa la plantilla ni las cinco vistas.

Fuentes: `CONTEXT.md` establece el contenido obligatorio; `AGENTS.md`, los límites técnicos y de calidad; `DESIGN.md`, las reglas comunes y una propuesta visual todavía pendiente de confirmar.

La petición confirma HTML estático, Tailwind CSS v4 por CDN, navbar, footer y un `main` vacío. No confirma una marca ni convierte las propuestas estéticas en decisiones definitivas.

## Estructura del documento

- Documento HTML5 con codificación UTF-8 y viewport responsive, sin impedir el zoom.
- Atributo `lang` coherente con el idioma visible. El idioma comercial definitivo queda pendiente; no se deduce de la sede francesa de la marca.
- `title` y descripción identificativos de la referencia. Al copiarla, cada vista debe sustituirlos por metadatos propios antes de publicarse.
- Orden de lectura: enlace de salto al contenido, `header` con `nav`, un único `main` y `footer`.
- El `main` tendrá un identificador estable como destino del salto y permanecerá vacío: sin encabezados, secciones, productos, ejemplos ni texto de relleno.
- La referencia no incluirá un `h1` genérico. Cada página final añadirá exactamente un `h1` descriptivo dentro de su contenido.
- El layout ocupará como mínimo la altura de la ventana y mantendrá el footer después del contenido, sin posicionamiento fijo ni solapamientos cuando el `main` esté vacío.

## Tailwind y límites técnicos

- Cargar Tailwind CSS v4 mediante su CDN oficial para navegador (`https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4`). Este script de infraestructura es la única excepción necesaria a la ausencia de scripts; no autoriza JavaScript de aplicación.
- No añadir instalaciones, herramientas de compilación, frameworks, componentes, motores de plantillas ni nuevas dependencias.
- Usar utilidades Tailwind mobile-first y reutilizar cualquier configuración compatible que exista al implementar. No crear una configuración adicional por iniciativa propia.
- Evitar estilos inline y CSS adicional innecesario. Si los tokens visuales requieren CSS compartido, acordar primero su ubicación y mecanismo compatible con v4; no duplicar valores entre páginas.
- No implementar búsqueda real, autenticación, carrito dinámico, pedidos, pagos ni envío o almacenamiento de datos.
- La dependencia de red del CDN debe constar como limitación del prototipo; no se promete funcionamiento estilizado sin conexión ni un resultado de rendimiento sin medirlo.

## Navbar común

- Incluir marca o logotipo enlazado a Inicio, navegación principal, búsqueda, acceso o menú de cuenta y acceso al carrito.
- Conservar el mismo contenido, orden, aspecto, etiquetas y destinos en las cinco vistas. Solo cambiará el indicador de página actual cuando corresponda.
- No inventar nombre, logotipo ni recursos de marca. Su contenido definitivo queda pendiente de aportación o aprobación del equipo.
- La navegación debe permitir llegar a Inicio y Catálogo; el carrito tendrá un acceso identificable. Producto y Checkout forman parte del recorrido de compra, sin obligación de añadirlos como enlaces principales.
- La búsqueda tendrá etiqueta accesible y campo de tipo búsqueda. Búsqueda y cuenta se presentarán inequívocamente como demostración cuando no tengan destino o comportamiento real; no enviar consultas, credenciales ni datos personales.
- No mostrar controles que aparenten funcionar sin ofrecer un comportamiento HTML definido o un estado de demostración explícito. Para un menú desplegable, usar solo mecanismos nativos accesibles sin JavaScript o mantener sus opciones visibles.
- En escritorio, situar la marca a la izquierda y navegación y carrito a la derecha, con espacio suficiente para búsqueda y cuenta. En móvil, permitir varias filas y conservar todos los accesos sin depender de un menú JavaScript.
- En cada vista final, señalar el enlace actual mediante `aria-current="page"` y subrayado o borde, no solo color. La referencia no fingirá ser una de las cinco vistas.
- No fijar la cabecera a pantalla salvo acuerdo posterior.

## Footer común

- Repetir exactamente contenido, orden, aspecto y destinos en las cinco vistas.
- Incluir los grupos obligatorios: Categorías (calzado, camisas, pantalones y accesorios), Legal (términos y condiciones, política de privacidad y sobre la marca) y Contacto.
- No inventar textos legales, dirección, correo, teléfono, redes sociales ni información corporativa.
- Definir con el equipo los destinos de categorías, legal y contacto antes de convertirlos en enlaces. Mientras falten, mantener las etiquetas como texto no interactivo con su estado pendiente, sin enlaces vacíos ni destinos ficticios.
- Organizar los grupos en columnas en escritorio y apilarlos en móvil, manteniendo el orden de lectura.

## Base visual y responsive

Las siguientes referencias proceden de la propuesta de `DESIGN.md`; aplicarlas como base provisional, sin presentarlas como identidad aprobada. Cualquier cambio acordado debe reflejarse también en ese documento.

- Contenedor compartido centrado, ancho máximo de 1280 px (`max-w-7xl`) y padding horizontal de 16 px en móvil, 24 px desde `md` y 32 px desde `xl`.
- Usar la escala de espaciado de Tailwind y sus breakpoints estándar: `sm` 640, `md` 768, `lg` 1024 y `xl` 1280 px.
- Cabecera con fondo `surface` y borde inferior `border` de 1 px, sin sombra persistente. Alturas orientativas de 64 px en móvil y 72 px en escritorio; permitir crecimiento si los controles necesitan varias filas.
- Footer con fondo `brand-pine`, texto blanco y padding vertical orientativo de 48 px en móvil y 64 px en escritorio.
- Paleta de referencia: `page` #F7F8F4, `surface` #FFFFFF, `brand-pine` #17483F, `brand-coral` #B64D3C, `brand-ochre` #D7A13B, `text-primary` #202522 y `border` #D7DED8. Los demás tokens se consultan en `DESIGN.md` cuando sean necesarios.
- Tipografía propuesta: DM Sans para navegación, cuerpo y controles; DM Serif Display para los titulares que añadan las vistas. No cargar recursos o pesos sin uso; usar alternativas locales y `font-display: swap` si se aprueban fuentes web.
- Navegación de 14 px y peso 500; títulos del footer de 14 px y peso 600; enlaces del footer de 14 px y peso 400. Campos de búsqueda con texto de 16 px y altura mínima de 48 px.
- Sin degradados, sombras decorativas ni secciones convertidas en tarjetas flotantes. Radios de controles de hasta 4 px.
- Evitar desbordamientos, recortes y solapamientos a 375, 768 y 1440 px, incluyendo textos largos y zoom. No usar tamaños tipográficos ligados al ancho del viewport.

## Accesibilidad y navegación estática

- Usar landmarks semánticos, nombres accesibles para las zonas de navegación y etiquetas asociadas a los campos. El placeholder no sustituye una etiqueta.
- Permitir recorrer enlaces y controles con teclado en el mismo orden que el visual. El enlace de salto será visible al recibir foco y permitirá llegar al `main`.
- Mantener foco visible con contorno de referencia de 2 px y separación de 2 px: coral sobre fondos claros y mostaza sobre verde oscuro, verificando el contraste real.
- Garantizar contraste WCAG AA: al menos 4,5:1 en texto normal y 3:1 en texto grande. No comunicar estados solo mediante color.
- Mantener objetivos táctiles de al menos 44 × 44 px. Los iconos sin texto necesitan nombre accesible y, si son ambiguos, ayuda visible al pasar el puntero o recibir foco.
- Si se aporta un logotipo de imagen, declarar dimensiones y alternativa adecuada; no diferir su carga si aparece en la zona inicial.
- Respetar `prefers-reduced-motion` si se añaden transiciones. No animar elementos imprescindibles para comprender la navegación.
- Resolver rutas tanto desde `docs/reference/base.html` como desde cada página final y comprobarlas en el entorno de publicación. No asumir que una ruta relativa puede copiarse sin ajustarla ni fijar nombres de página todavía no acordados.
- Reutilizar la referencia mediante copias HTML estáticas sincronizadas; no mediante componentes o inclusiones dinámicas.
- No añadir datos estructurados genéricos con información inventada. Los microdatos pertinentes se incorporarán en las vistas correspondientes cuando exista contenido confirmado.

## Pendientes antes de implementar

- Marca, logotipo, idioma visible y aprobación o ajuste de la propuesta visual.
- Nombres y ubicación de las cinco páginas, y destinos de categorías, legal, contacto y cuenta.
- Representación HTML concreta de búsqueda y cuenta como demostración, sin ampliar su alcance funcional.
- Mecanismo compartido de tokens y carga de fuentes si resultan necesarios y son aprobados.

## Criterios de aceptación de la futura plantilla

1. Existe `docs/reference/base.html` con HTML semántico, metadatos, Tailwind v4 por CDN, navbar y footer; el único `main` no contiene contenido.
2. La cabecera incluye marca, navegación, búsqueda, cuenta y carrito; el pie incluye todos los grupos y etiquetas requeridos.
3. No hay JavaScript de aplicación, dependencias añadidas, contenido de las vistas ni datos corporativos inventados. Las operaciones no implementadas se distinguen como demostración o pendientes y no envían datos.
4. Navbar y footer pueden copiarse a las cinco vistas conservando coherencia y ajustando únicamente rutas relativas, metadatos y estado de navegación cuando proceda.
5. Se comprueban manualmente teclado, salto al contenido, foco, etiquetas, contraste y reflujo en 375, 768 y 1440 px, sin desplazamiento horizontal de la página.
6. Se verifican la carga del CDN y los destinos reales de enlaces en el entorno de publicación; las etiquetas sin destino confirmado no aparentan ser enlaces funcionales.
7. El recorrido Inicio → Catálogo → Producto → Carrito → Checkout se verificará al implementar las vistas, no se atribuirá a la referencia vacía.
8. PageSpeed Insights y su captura real corresponden a la entrega publicada. No se declaran comprobados ni se inventan puntuaciones en esta fase documental.