# Especificación: Home y Vista de producto

## 1. Objetivo

Definir los requisitos funcionales y los límites de la parte del proyecto asignada a Juliana: las vistas Home y Vista de producto. Esta especificación documenta el briefing proporcionado y no define comportamientos que este no indique.

## 2. Alcance

Incluye exclusivamente:

- La página principal de la tienda online (Home).
- La vista que presenta el detalle de un producto seleccionado.
- La navegación, cabecera/header y footer comunes que estas vistas deben mantener o integrar.

Quedan fuera de alcance las demás vistas del proyecto y cualquier cambio en ellas. Esta entrega es una especificación; no incluye implementación HTML ni CSS.

## 3. Fuentes y reglas de interpretación

- Fuente funcional: requisitos «1. Home» y «3. Vista de producto» del briefing del proyecto proporcionado para este ejercicio.
- La estructura, el diseño y los componentes comunes definidos por el equipo deben respetarse. Cuando existan `CONTEXT.md`, `DESIGNN.md` o `DESIGN.md`, y `docs/reference/base.html`, se utilizarán como fuentes de verdad para la implementación, conforme al briefing.
- Los detalles que el briefing no concreta se consideran pendientes de definición por el equipo; esta especificación no les asigna valores ni comportamientos por inferencia.

## 4. Home

### 4.1 Estructura y componentes

Home debe funcionar como página principal de la tienda online e incluir:

1. La navegación/header común, coherente con el resto del proyecto.
2. Una presentación visual de la marca y de la propuesta de la tienda.
3. Una sección principal (hero) con un producto o una campaña destacada.
4. Una sección de nuevos lanzamientos.
5. Una sección de productos más vendidos.
6. El footer con la información correspondiente de la tienda.

La presentación y el orden visual de los elementos deben respetar el sistema visual y los componentes comunes definidos por el equipo. El briefing no especifica composición, cantidad de elementos ni diseño interno de las secciones.

### 4.2 Contenido

- Marca y propuesta de la tienda.
- Producto o campaña que se quiera destacar en el hero.
- Productos correspondientes a nuevos lanzamientos.
- Productos correspondientes a más vendidos.
- Información de la tienda para el footer.

El briefing no proporciona textos, productos, imágenes, datos de marca ni contenido concreto para el footer; deben proceder de las fuentes comunes o de los datos acordados por el equipo.

## 5. Vista de producto

### 5.1 Estructura y componentes

La vista debe mostrar en detalle el producto seleccionado e incluir:

1. La navegación/header común.
2. La imagen del producto.
3. El nombre del producto.
4. El código o referencia.
5. El precio.
6. Un control que permita seleccionar la talla.
7. Un control que permita seleccionar la cantidad.
8. El botón «Agregar al carrito».
9. Una descripción detallada del producto.
10. Información sobre los materiales.
11. Información sobre el uso recomendado o los escenarios de uso.
12. El footer común del proyecto.

La estructura visual debe respetar los componentes y el sistema visual compartidos por el equipo. El briefing no establece una disposición específica de estos elementos.

### 5.2 Contenido

La vista presenta la información del producto seleccionado y los campos enumerados en la sección 5.1. El briefing no proporciona valores de producto ni define el formato de los datos.

## 6. Navegación entre vistas

- La navegación de Home debe permitir acceder a las diferentes partes o vistas del proyecto.
- La Vista de producto debe permitir navegar correctamente hacia y desde las demás vistas del proyecto.
- Ambas vistas deben mantener la navegación/header común del proyecto.
- Las rutas, los destinos concretos, las etiquetas de navegación y el mecanismo de retorno no están especificados en el briefing; deben integrarse según la estructura común acordada por el equipo.

## 7. Responsive

Home y Vista de producto deben ser responsive y funcionar en móvil, tablet y escritorio. El briefing no define anchos de breakpoint, cambios de composición ni reglas de adaptación específicas; estos deben seguir el sistema común del equipo.

## 8. Accesibilidad y HTML semántico

- Ambas vistas deben utilizar HTML semántico.
- El briefing no aporta criterios adicionales de accesibilidad ni especifica un estándar, interacciones de teclado, requisitos para imágenes, foco, contraste o tecnologías de asistencia. No se agregan aquí como criterios funcionales; deberán acordarse en las directrices comunes del proyecto si son aplicables.

## 9. Requisitos técnicos

- El desarrollo de ambas vistas debe utilizar HTML semántico y Tailwind CSS.
- La estructura, el diseño y los componentes deben ser coherentes con el sistema visual común del proyecto.
- No se fija versión, método de instalación/configuración ni convención de clases de Tailwind; deben seguir lo que defina el equipo en sus documentos comunes.
- El briefing no indica requisitos de Schema.org. Por tanto, esta especificación no exige marcado Schema.org.

## 10. Criterios de aceptación

### Home

- [ ] Funciona como página principal de la tienda online.
- [ ] Incluye la navegación/header coherente con el proyecto.
- [ ] Presenta visualmente la marca y la propuesta de la tienda.
- [ ] Incluye un hero con un producto o una campaña destacada.
- [ ] Incluye secciones de nuevos lanzamientos y productos más vendidos.
- [ ] Incluye un footer con la información correspondiente de la tienda.
- [ ] La navegación permite acceder a las diferentes partes o vistas del proyecto.
- [ ] Funciona en móvil, tablet y escritorio.
- [ ] Utiliza HTML semántico y Tailwind CSS, y respeta el sistema visual definido por el equipo.

### Vista de producto

- [ ] Muestra en detalle el producto seleccionado.
- [ ] Presenta imagen, nombre, código/referencia y precio del producto.
- [ ] Permite seleccionar talla y cantidad.
- [ ] Incluye el botón «Agregar al carrito».
- [ ] Presenta descripción detallada, materiales y uso recomendado/escenarios.
- [ ] Mantiene la navegación/header y el footer comunes del proyecto.
- [ ] Permite navegar correctamente hacia y desde las demás vistas del proyecto.
- [ ] Funciona en móvil, tablet y escritorio.
- [ ] Utiliza HTML semántico y Tailwind CSS, y respeta los componentes y el sistema visual definidos por el equipo.

## 11. Restricciones y aspectos pendientes

- El alcance de esta parte se limita a Home y Vista de producto; no se deben modificar las vistas asignadas a otros compañeros.
- No se deben implementar requisitos o funcionalidades no indicados en el briefing.
- Se deben respetar la estructura, el diseño y los componentes comunes que cree el equipo.
- La especificación no prescribe el comportamiento posterior al clic en «Agregar al carrito», las reglas de validación de talla o cantidad, ni la persistencia o el flujo del carrito; esos detalles no están definidos en el briefing.
- Tampoco se especifican rutas, datos concretos, cantidades de productos, diseño interno de componentes o breakpoints.
- `CONTEXT.md`, `DESIGNN.md`/`DESIGN.md` y `docs/reference/base.html` todavía no están disponibles en el repositorio y deberán consultarse para la implementación cuando existan.
