# Tareas: plantilla HTML común

Basadas en [spec.md](spec.md) y en [el plan](../base.layout/plan.md). Las casillas marcadas corresponden a cambios implementados o comprobaciones realizadas; no implican validación visual cuando esta sigue pendiente.

## 1. Preparación y decisiones

- [x] Comprobar la rama de trabajo y conservar los cambios existentes.
- [ ] Confirmar el idioma visible de la plantilla.
- [ ] Confirmar la marca y el recurso de logotipo, sin inventarlos.
- [ ] Acordar nombres y ubicaciones de las cinco páginas.
- [ ] Confirmar los destinos de categorías, legal, contacto y cuenta.
- [ ] Acordar cómo presentar búsqueda y cuenta como demostración sin enviar datos.
- [ ] Confirmar o ajustar la propuesta visual de `DESIGN.md` y actualizarlo si se acuerdan cambios.
- [ ] Revisar la configuración existente y acordar tokens compartidos y fuentes si hacen falta, sin añadir herramientas.

## 2. Estructura HTML

- [x] Crear `docs/reference/base.html` como documento HTML5.
- [x] Declarar UTF-8 y viewport responsive sin impedir el zoom.
- [x] Declarar `lang="es"` para el texto de referencia en español; el idioma comercial definitivo sigue pendiente.
- [x] Añadir título y descripción propios de la referencia.
- [x] Incluir la carga de Tailwind v4 mediante su CDN oficial para navegador.
- [x] Añadir el enlace de salto al contenido.
- [x] Añadir `header` y `nav` semánticos.
- [x] Añadir un único `main` vacío con identificador como destino del salto.
- [x] Añadir `footer` después del contenido.
- [x] Configurar altura mínima de ventana y layout flexible para mantener el footer después del contenido sin posicionamiento fijo.

## 3. Navbar común

- [ ] Añadir la marca enlazada a Inicio cuando exista un destino confirmado.
- [ ] Añadir los accesos a Inicio y Catálogo con sus rutas confirmadas.
- [ ] Añadir el acceso al carrito.
- [x] Añadir el campo de búsqueda deshabilitado con etiqueta y aviso de demostración, sin envío de datos.
- [x] Añadir un menú de cuenta nativo con `details` y `summary`, sin autenticación ni JavaScript.
- [x] Configurar la cabecera para permitir varias filas en móvil y conservar las etiquetas de navegación.
- [x] No marcar la referencia como página actual; reservar `aria-current` para las vistas correspondientes.

La marca se muestra como texto pendiente. Inicio, Catálogo y Carrito son etiquetas no interactivas hasta confirmar sus destinos. La representación propuesta de búsqueda y cuenta aún requiere aprobación del equipo.

## 4. Footer común

- [x] Añadir Categorías: calzado, camisas, pantalones y accesorios.
- [x] Añadir Legal: términos y condiciones, política de privacidad y sobre la marca.
- [x] Añadir el grupo Contacto sin inventar datos corporativos.
- [x] Usar texto no interactivo con estado pendiente donde no haya un destino confirmado.
- [x] Configurar los grupos apilados en móvil y en columnas desde tablet.

## 5. Estilos y accesibilidad

- [x] Aplicar el contenedor centrado de hasta 1280 px y padding horizontal de 16, 24 y 32 px según breakpoint.
- [x] Aplicar provisionalmente la paleta, DM Sans, espaciado y bordes propuestos mediante Tailwind.
- [ ] Permitir que textos y controles refluyan sin solaparse ni causar desbordamiento horizontal.
- [x] Configurar enlaces y controles con un área táctil de al menos 44 × 44 px.
- [x] Añadir estados de hover y foco visible sin depender solo del color.
- [x] Revisar en el HTML nombres accesibles de navegación y controles, y asociación de etiquetas.
- [ ] Declarar dimensiones y alternativa adecuada del logotipo si se usa una imagen.
- [x] Evitar animaciones y transiciones, sin introducir movimiento que requiera adaptación.

Los tokens se declaran una sola vez en un bloque `@theme` de la referencia, sin atributos `style` ni una herramienta de compilación nueva. DM Sans se solicita con pesos 400, 500 y 600, `display=swap` y alternativas locales. Ambos mecanismos son provisionales y deben acordarse antes de replicar la plantilla. No se ha añadido una imagen de logotipo porque no existe un recurso confirmado.

## 6. Comprobaciones de la referencia

- [x] Revisar estructura HTML, idioma y metadatos mediante inspección y análisis con el parser estándar de Python.
- [x] Confirmar que el `main` sigue vacío y no hay un `h1` genérico.
- [x] Comprobar que la URL del CDN responde con HTTP 200 y sirve JavaScript de Tailwind v4.
- [ ] Comprobar que carga Tailwind v4 por CDN.
- [ ] Recorrer los enlaces y controles con teclado en orden coherente.
- [ ] Comprobar que el salto al contenido y el foco visible funcionan.
- [x] Calcular contraste AA en los pares de color declarados para texto y foco: texto normal entre 4,72:1 y 15,57:1; foco entre 4,78:1 y 5,10:1.
- [ ] Revisar distribución y ausencia de desbordamientos a 375 px.
- [ ] Revisar distribución y ausencia de desbordamientos a 768 px.
- [ ] Revisar distribución y ausencia de desbordamientos a 1440 px.
- [ ] Revisar reflujo con zoom y textos largos.
- [ ] Verificar los destinos reales de enlaces desde la referencia en el entorno de publicación.
- [x] Confirmar que no hay JavaScript de aplicación, envíos de datos ni nuevas dependencias instaladas.
- [x] Registrar qué se comprobó y qué sigue pendiente, sin inventar resultados.

No se han creado archivos de pruebas ni instalado dependencias. Se verificaron también identificadores únicos, referencias internas, asociación del aviso de búsqueda y ausencia de estilos inline. La comprobación HTTP no demuestra que Tailwind o las fuentes se rendericen en un navegador. Las pruebas visuales, de teclado, zoom y carga real quedan pendientes: no hay Playwright, Puppeteer ni navegador automatizable disponible entre las herramientas comprobadas.

El validador CSS del editor informa `Unknown at rule @theme`. Se conserva esta directiva propia de Tailwind v4 dentro de `style type="text/tailwindcss"`, que debe procesar el CDN; no es una regla de CSS nativo. Su procesamiento efectivo queda incluido en la comprobación pendiente en navegador. No se ha silenciado el diagnóstico mediante cambios de configuración.

## Resultado frente a la especificación

- **Criterio 1:** implementado en [la referencia HTML](../../docs/reference/base.html), con metadatos, CDN, header/nav, footer y un único `main` vacío.
- **Criterio 2:** contenido y controles de demostración presentes; pendiente completar marca y accesos con destinos confirmados. No hay enlaces ficticios.
- **Criterio 3:** comprobado por inspección y análisis HTML: único script de infraestructura, sin lógica de aplicación ni envío de datos. No hay contenido de producto ni datos corporativos inventados.
- **Criterio 4:** referencia estática preparada; la coherencia de las cinco copias no se puede comprobar antes de crearlas.
- **Criterio 5:** estilos responsive y foco implementados, y contraste calculado; falta validación real de teclado, reflujo y los tres anchos en navegador.
- **Criterio 6:** CDN accesible desde este entorno; carga en navegador y destinos publicados pendientes. Las etiquetas sin destino no son enlaces.
- **Criterios 7 y 8:** recorrido de compra y PageSpeed reservados para las vistas publicadas, fuera de esta implementación.

**Estado global: cumplimiento parcial.** Para cerrar la plantilla faltan decisiones del equipo, destinos reales y comprobaciones en navegador. No se presentan como terminadas las tareas que dependen de ello.

## 7. Al integrar las cinco vistas

Estas tareas son posteriores a la plantilla y no autorizan implementar las páginas en esta fase.

- [ ] Copiar navbar y footer conservando contenido, orden, aspecto y destinos.
- [ ] Ajustar las rutas relativas de cada copia según su ubicación.
- [ ] Sustituir los metadatos de referencia y añadir un `h1` descriptivo por página.
- [ ] Indicar la página actual con `aria-current` y un indicador visual que no dependa solo del color.
- [ ] Comprobar el recorrido Inicio → Catálogo → Producto → Carrito → Checkout.
- [ ] Ejecutar PageSpeed Insights sobre la web publicada y guardar una captura real para la entrega.