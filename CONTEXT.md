# Especificaciones del proyecto

#### 1) Página de inicio (Home)

- **Barra superior (navbar)** con:
	- Logo
	- Barra de búsqueda
	- Menú de cuenta de usuario
- **Sección Hero** destacando productos especiales o campañas de la marca.
- Dos secciones con listados horizontales (*cards* de producto):
	- **Nuevos lanzamientos**
	- **Más vendidos**
- **Footer** con secciones:
	- **Categorías:** calzado, camisas, pantalones, accesorios
	- **Legal:** términos y condiciones, política de privacidad, sobre la marca
	- **Contacto**
- **La navbar y el footer se reutilizan** en todas las demás vistas.

#### 2) Catálogo

- Mantiene **navbar y footer**.
- Incluye una **barra de filtros** antes del listado:
	- Filtro por **categoría**
	- Filtro por **talla**
- Listado de productos en **rejilla (grid) 4×5** (20 productos visibles como referencia).

#### 3) Vista de producto

- Diseño en dos columnas:
	- **Izquierda:** foto del producto ocupando aproximadamente **la mitad del ancho**.
	- **Derecha:** información principal del producto:
		- Nombre
		- Código o referencia
		- Talla
		- Precio
		- Selector de cantidad
		- Botón **"Agregar al carrito"**
- Debajo, una sección de **descripción detallada**:
	- Materiales
	- Uso recomendado / escenarios donde se puede usar la prenda

#### 4) Carrito

- Vista completa del carrito (no un panel lateral).
- Listado de productos añadidos con:
	- Miniatura
	- Precio unitario
	- Cantidad
	- Total por producto
- Cuadro de totalización con:
	- Subtotal
	- Impuestos
	- Total
	- Botón **"Comprar"**
- Añadir **3 productos de ejemplo** para mostrar el comportamiento visual.

#### 5) Formulario de pago (Checkout)

Flujo en **3 pasos** ([referencia del flujo en 3 pasos](https://learn.4geeks.com/es/main-cohort/spain-aie-pt-6/syllabus/command-line-github-and-git/project/first-collaborative-project-tailwind-css?moduleId=2#flujo-en-3-pasos)):

1. **Datos personales**
2. **Dirección de entrega**
3. **Pago con tarjeta** (datos de tarjeta)
