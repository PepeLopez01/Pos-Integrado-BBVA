# PoS Integrado

PoS Integrado se comunica con la terminal a través de un cable USB conectado directamente a la terminal. Planificada la evolución para conectarse a través de una base y desde esta hasta la terminal a través de bluetooth.

Para ello facilitamos una librería de integración, y mediante las funcionalidades de esta, interactuar con el PoS.

### Ventajas
- El sistema de caja se comunica directamente con la terminal, evitando el ingreso manual de datos en la terminal. 
- La caja tendrá la capacidad de obtener información de las transacciones realizadas por la terminal.
- La comunicación entre caja y terminal es punto a punto via USB.

### Funcionalidades
- [Manejo de puertos](Funcionalidades/Puertos.md)
- [Prueba de comunicación](Funcionalidades/ComTest.md)
- [Venta](Funcionalidades/Venta.md).
- [Venta con QR](Funcionalidades/VentaQR.md) + pago con transferencias.
- [Anulación](Funcionalidades/Anulacion.md).
- [Cierre de lote](Funcionalidades/cierreLote.md).
- [Devolución](Funcionalidades/Devolucion.md).
- [Consulta de último cierre de lote](Funcionalidades/consultaCierre.md).
- [Consulta de última transacción](Funcionalidades\consultaUltTransaccion.md).
- [Consulta de tarjetas](Funcionalidades/consultaTarjetas.md) disponibles para operar.
- [Consulta de planes](Funcionalidades/consultaPlanes.md) a aplicar por tarjeta.


### Herramientas y Aplicaciones
- [Libreria de integración](./Aplicaciones/Libreria/).
- [TestVpi](./Aplicaciones/testVpi/).
- [Billetera Integra](./Aplicaciones/Billetera/) (Billetera de pruebas QR estático).
- [Demo de integración](./Aplicaciones/DemoIntegraciónVpiPc/).
- [Drivers](./Aplicaciones/Drivers/)

### Diferencias
- No admite multicomercio.
- No permite Pre Autorizaciones.
- No permite transacciones offline.
- No hay anulación de devoluciones.



