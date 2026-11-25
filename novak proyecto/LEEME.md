# NOVAK: tienda virtual (versión mejorada)

Abre `index.html` con Live Server en Visual Studio Code (clic derecho → "Open with Live Server").
Todo funciona en el navegador con localStorage, sin servidor ni base de datos.

## Cuentas de prueba
| Rol | Correo | Clave |
|---|---|---|
| Cliente | cliente@novak.pe | cliente123 |
| Administrador | admin@novak.pe | admin123 |
| Otros 12 clientes de ejemplo | (se ven en Panel admin → Clientes) | novak123 |

## Páginas
- `index.html`: carrusel principal, categorías, ofertas con cuenta regresiva, "Encuentra tu fit", novedades y "Seleccionados para ti" (personalizado según las compras del cliente).
- `catalogo.html`: filtros por categoría, línea, talla, color, precio, ofertas y novedades. Admite enlaces como `?oferta=1`, `?cat=hoodies` o `?genero=mujer`.
- `producto.html?id=...`: ficha con 4 vistas (frente, espalda, lado izquierdo y lado derecho), colores, tallas con stock, guía de tallas, especificaciones y reseñas. El administrador ve además las estadísticas de la prenda.
- `carrito.html`: cantidades por talla y color, cupones, barra de envío gratis.
- `checkout.html`: pasarela de pago en 3 pasos (tarjeta con validación, Yape/Plin, PagoEfectivo, transferencia y contra entrega). Es una **demostración**: no cobra nada. Tarjeta aprobada: 4111 1111 1111 1111 · rechazada: 4000 0000 0000 0002.
- `cuenta.html`: pedidos con seguimiento, "Mi estilo", favoritos y datos.
- `admin.html`: Resumen (gráficos), Prendas (estadísticas por prenda), Clientes (perfil de compra de cada cliente), Pedidos (cambiar estado) y Ofertas y cupones.

## Fotos de las 4 vistas
Cada prenda trae una sola foto. Mientras falten las otras vistas, la ficha muestra una **vista referencial** marcada como tal. Para poner las fotos reales tienes dos opciones:
1. Copia las fotos en `img/` con este nombre: `<id>-espalda.jpg`, `<id>-izquierda.jpg`, `<id>-derecha.jpg` (ejemplo: `img/hoodies-08-espalda.jpg`). La página las detecta sola.
2. Desde el panel admin → Editar prenda → "Fotos: las 4 vistas" (ruta, enlace o subir foto).

## Cupones incluidos
NOVAK10 · BIENVENIDA15 (desde S/ 150) · GENZ20 (S/ 20 desde S/ 120) · ENVIOGRATIS

## Archivos JS
`datos.js` (catálogo y datos de ejemplo) → `app.js` (núcleo: carrito, favoritos, cabecera) → `estadisticas.js` (cálculos y gráficos) → `admin.js` (panel) → `tienda.js` (cada página).
Para volver a los datos iniciales: en la consola del navegador ejecuta `localStorage.clear()` y recarga.
