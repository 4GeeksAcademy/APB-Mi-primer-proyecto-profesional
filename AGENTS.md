# Instrucciones para trabajar en el proyecto

## Lectura inicial

- Lee `CONTEXT.md` y `DESIGN.md` antes de modificar el proyecto.
- Revisa los archivos y la configuración existentes antes de proponer una estructura nueva.
- El enunciado del ejercicio es la fuente de los requisitos obligatorios. Los documentos distinguen esos requisitos de las propuestas pendientes de confirmar.
- Mantén estos documentos coherentes cuando se acuerden cambios. No conviertas una propuesta en una decisión confirmada sin indicarlo.

## Objetivo y límites técnicos

- Desarrolla un prototipo visual y navegable de una tienda de ropa para una marca con sede en Francia.
- Usa exclusivamente HTML y Tailwind CSS. El enunciado admite CSS adicional compartido si resulta necesario.
- No añadas JavaScript de aplicación, React, Vue, Angular, otros frameworks de interfaz, backend, bases de datos ni pasarelas de pago.
- Reutiliza la configuración de Tailwind del repositorio. No cambies las herramientas ni añadas dependencias por iniciativa propia si el ejercicio puede resolverse con lo existente.
- Entrega al menos cinco archivos HTML: inicio, catálogo, producto, carrito y checkout. Enlázalos entre sí con rutas que funcionen en el entorno de publicación.
- El prototipo debe mostrar el recorrido de compra. Las operaciones que requieren lógica dinámica se representan con estados de ejemplo y navegación HTML; no se presentan como operaciones reales.

## Reglas de implementación

- Usa HTML semántico: `header`, `nav`, `main`, `section`, `article`, `footer` y `form` cuando correspondan.
- Mantén una navbar y un footer con el mismo contenido, aspecto y destinos en las cinco vistas.
- Al compartir cabecera y pie mediante HTML estático, actualiza sus copias en todas las páginas. No añadas un sistema de componentes o un motor de plantillas solo para evitar esa duplicación.
- Usa Tailwind de forma coherente para estilos, espaciado y responsive. Evita estilos inline y CSS adicional innecesario.
- Conserva un único `h1` descriptivo por página y una jerarquía de encabezados clara.
- Añade etiquetas a los campos, textos alternativos a las imágenes y foco visible. Asegura navegación por teclado y contraste legible.
- Prioriza el diseño móvil y adapta las cinco páginas a tablet y escritorio. Evita desbordamiento horizontal de la página.
- Las listas horizontales de la Home pueden tener desplazamiento dentro de su propio contenedor si todos los productos siguen siendo accesibles.
- Mantén coherencia entre los productos mostrados: referencia, nombre, talla, imagen y precio.
- En carrito, usa importes de demostración con cálculos consistentes. Documenta los supuestos de impuestos; no inventes un tratamiento fiscal real.
- En checkout, usa etiquetas y validación nativa de HTML cuando proceda. No envíes, almacenes ni solicites para pruebas datos reales de tarjeta. Indica que el pago es una demostración.

## SEO y rendimiento

- Mantén el contenido principal y los enlaces en el HTML para que sean indexables.
- Usa `lang` coherente con el idioma del contenido y un `title` y una descripción específicos por página.
- Incluye datos estructurados Schema.org donde tengan sentido, por ejemplo `Organization` en inicio y `Product` en producto. Para mantener el alcance sin scripts, se propone microdatos HTML.
- Los datos estructurados deben corresponder al contenido visible. No inventes reseñas, valoraciones, disponibilidad ni datos corporativos.
- Optimiza las imágenes y declara sus dimensiones. Aplica carga diferida a imágenes fuera de la zona inicial cuando corresponda.
- Comprueba la URL pública con PageSpeed Insights: el enunciado pide al menos 80 puntos, idealmente más de 90. Conserva una captura real del resultado para la entrega.
- No inventes resultados de pruebas ni puntuaciones.

## Git y colaboración

- Trabaja en una rama por vista o funcionalidad, por ejemplo `feature/home` o `feature/catalogo`. No desarrolles directamente en `main`.
- Haz commits frecuentes con mensajes descriptivos y un cambio lógico por commit.
- Actualiza la rama con los cambios de `main` antes de abrir la pull request, respetando el flujo del equipo.
- Abre una pull request por rama antes de integrarla en `main`; describe el cambio y las comprobaciones realizadas.
- Resuelve los conflictos con la otra persona. No hagas force-push ni sobrescribas su trabajo sin consenso.
- No inventes contribuciones, commits, revisiones o pull requests para aparentar trabajo colaborativo.

## Comprobaciones antes de entregar

1. Verifica que existen al menos cinco archivos HTML y que se puede recorrer inicio → catálogo → producto → carrito → checkout.
2. Revisa todas las especificaciones por vista de `CONTEXT.md`.
3. Comprueba navbar y footer en las cinco páginas, rutas, imágenes, semántica y formularios.
4. Revisa móvil, tablet y escritorio; como referencia, usa anchos de 375, 768 y 1440 px.
5. Comprueba uso de teclado, etiquetas, texto alternativo y foco visible.
6. Comprueba que no se han añadido tecnologías fuera del alcance y que el prototipo distingue las simulaciones de las operaciones reales.
7. Ejecuta las comprobaciones existentes que sean pertinentes. No añadas una infraestructura de pruebas para este prototipo estático.
8. Una vez publicada la web, ejecuta PageSpeed Insights y guarda la captura del resultado, por ejemplo `pagespeed-result.png`.
9. Resume qué cambió, qué se comprobó y qué queda pendiente. Si una comprobación no se pudo ejecutar, dilo expresamente.
