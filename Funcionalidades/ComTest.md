# Prueba de comunicación

## YA SE PUSO UNA PROPUESTA PENDIENTE REVISAR CON JENNER

Para verificar que la comunicación entre la terminal y la caja esté establecida de manera correcta, la Librería de integración implementa un mecanismo de Keep Alive. Este se dispara de forma automática cada 500 ms y es gestionado internamente por la Librería, por lo que la caja no necesita invocarlo ni ve cada ejecución: únicamente recibe el retorno final de la función.

En cada ciclo, el Keep Alive mantiene activa la conexión con la terminal y obtiene dos valores independientes:

transactionStatus: estado de la transacción en curso (PENDING, CONFIRMING, SUCCESS, ERROR).
terminalStatus: estado de la terminal (BUSY, IDLE).

Las operaciones de transacción (PURCHASE, VOID, REFUND) responden inicialmente con Command_accepted, y su resultado definitivo se obtiene a través del Keep Alive y de Query(transactionId).

Existen dos métodos que se pueden implementar para chequear la comunicación.

Para verificar que la comunicación entre la terminal y la caja este establecida de manera correcta, se puede utilizar el método vpiTestConnection de la librería de integración.

Int vpiTestConnection()
Por otro lado, con el método vpiGetVersion podemos identificar que tipo de PoS está conectada a la caja.

Int vpiGetVersion(vpiVersionOut_t* output)
Este recibe una estructura de salida, vpiVersionOut_t:

typedef struct GETVERSION_OUT {
	WORD version;  // Mensaje de respuesta de version 
} vpiVersionOut_t;
Para indentificar el PoS, lo hacemos dependiendo del parametro version de la estrutura de retorno.

    Version         -----  version 
    Legacy          -----       1
    Interprete      -----       2
## Posibles Retorno del Método
Los posibles valores de retorno para ambos métodos son los siguientes:

VPI_OK
VPI_FAIL 
VPI_TIMEOUT_EXP

En la sección [códigos de respuesta](../Libreria/codigosRespuesta.md) de la librería de integración se pueden ver la tabla de valores para estas respuestas



#### Otros enlaces
- [Principal](../README.md).
- [Manejo de puertos](./Puertos.md)
- [Prueba de comunicación](./ComTest.md)
- [Venta](./Venta.md).
- [Venta + Extracción](./Venta+Extracción.md).
- [Venta con QR](./VentaQR.md) + pago con transferencias.
- [Anulacion](./Anulacion.md)
- [Cierre de lote](./cierreLote.md).
- [Devolución](./Devolucion.md).
- [Consulta de último cierre de lote](./consultaCierre.md).
- [Consulta de última transacción](./consultaUltTransaccion.md).
- [Consulta de tarjetas](./consultaTarjetas.md) disponibles para operar.
- [Consulta de planes](./consultaPlanes.md) a aplicar por tarjeta.
