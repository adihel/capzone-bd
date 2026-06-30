CapZone_Base de Datos capzone_db

Este repositorio contiene el script SQL para la creación, inicialización y analítica de la base de datos de CapZone, una tienda en línea especializada en gorras.
1. acá encontramos 6 tablas principales, una de usuarios, una de productos, una de categorías, una de pedidos, detalles de pedido y mensajes de contacto

usuarios: Registra a los clientes (nombre, correo único, contraseña, teléfono y fecha de registro).
Categorías: Clasifica los tipos de gorras (Snapback, Dad Hat, Trucker, Beanie).
productos: Catalogo de gorras con su precio, inventario actual.
pedidos: Cabecera de la compra. Almacena el usuario que compra, la fecha, el estado (`Pendiente`, `Procesado`, `Enviado`) y el total.
detalle_pedidos: Detalle de cada compra. Conecta los pedidos con los productos para guardar cantidades y precios unitarios históricos.
mensajes_contacto: Almacena las consultas enviadas por los usuarios desde el formulario de soporte de la web.

2. Datos de Prueba Incluidos (Inserts)

Acá tenemos los inserts de manera random para categorías, productos, usuarios, pedidos y mensajes de contactos 
4 Categorías de gorras 
10 Productos en inventario
3 Usuarios de prueba con contraseñas simuladas.
3 Pedidos con detalles para verificar el movimiento financiero.
2 Mensajes de contacto  en la bandeja de entrada.

3. Procedimientos Almacenados  y reportes.

Historial de Compras sp_ReporteComprasUsuario.
Muestra lo que ha comprado un usuario específico.
Se hace para Juntar los datos de usuarios, pedidos y productos.
Se usa  para mostrarle al cliente su historial de pedidos en su perfil de la app.
Registro de Pedidos Seguro  sp_RegistrarPedidoCompleto.
Procesa una compra de principio a fin de forma segura y automática en una sola transacción.
 1. Verifica que el producto exista y tenga inventario suficiente.
 2. Crea la cabecera del pedido y calcula el total de la compra.
 3. Registra el detalle del producto comprado.
 4. Descuenta automáticamente las unidades vendidas del inventario de productos.

Ranking de Clientes 
Me muestra una lista con el nombre de cada usuario, cuántos pedidos ha hecho en total y cuanto dinero que ha gastado.
Sirve para que los administradores identifiquen fácilmente a sus clientes más fieles.
