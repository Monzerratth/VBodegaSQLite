# Commit Leander

Cambios que hice:

- Las tarjetas de "Productos" y "Stock bajo" ahora son botones y abren el inventario filtrado por stock normal y stock bajo.
- Separé "Entradas y salidas" en dos botones: "Entradas" y "Salidas", cada uno con su historial.
- Agregué los informes PDF (entradas, salidas, stock normal, stock bajo e inventario completo). Se guardan en Descargas/InformesAlmacen.
- Archivos nuevos: InformePdf.java, HistorialMovimientosActivity.java y Movimiento.java.
- También toqué MenuActivity, InventarioActivity, DBHelper, los layouts y el manifest.

# commit Esteban

Cambios que hice:

- Implementé el registro de Ventas tratándolas como "Salidas" de stock en el sistema.
- Agregué transacciones seguras en la base de datos (SQLite). Ahora, al registrar una venta, el descuento del stock y el historial se guardan juntos; si algo falla, no se guarda nada para evitar errores en el inventario.
- Puse un bloqueo de seguridad directo en SQL para evitar el stock negativo. Si se intenta vender más cantidad de la que hay en bodega, la venta se bloquea y lanza el error de "Stock insuficiente".
- Ajusté el formulario para que, al elegir registrar una salida o venta, se bloquee el campo de "Proveedor" (porque no aplica) y se pida un "Motivo" (ej. "Venta").
- Archivos que toqué: DBHelper.java (para toda la lógica y seguridad de la base de datos) y MovimientosActivity.java (para el formulario e interfaz).

# Commit Catalina

Cambios que hice:

- Agregué el escáner de código de barras (EscanerActivity) con la cámara de Google Code Scanner. Busca el producto en la base de datos, muestra su stock y estado, y permite asociar el código a un producto o crear uno nuevo con ese código.
- Agregué el campo "Código de barras" al formulario de productos, con botón para escanearlo. Un código repetido se rechaza con un aviso.
- Agregué la ubicación de la empresa en el mapa (UbicacionActivity): ver la empresa en Google Maps, mi ubicación con la distancia en km y cómo llegar. El ADMIN puede editar las coordenadas.
- Hice la pantalla "Códigos de barras" (CodigosBarrasActivity): crear, leer, actualizar y eliminar el código de cada producto, con búsqueda y filtros.
- Hice la pantalla "Sucursales" (SucursalesActivity): crear, editar y eliminar sucursales con sus coordenadas (solo ADMIN). Todos pueden verlas en el mapa y pedir la ruta.
- Subí la base de datos a la versión 8 con la tabla SUCURSAL, y agregué datos de prueba y tests.
- Archivos nuevos: CodigosBarrasActivity.java, SucursalesActivity.java, Sucursal.java y los layouts de ambas pantallas.
- También toqué MenuActivity, DBHelper, el manifest, docs/datos_demo.sql y docs/esquema.sql.
- Pendiente: cambiar las coordenadas de ejemplo de la empresa (están en Santiago centro) y probar en un teléfono o emulador con Google Play Services.