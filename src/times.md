# Tiempo de Intercambio

Mostro está diseñado para que los intercambios de bitcoin por monedas fiat sean rápidos, por lo que se recomienda utilizar métodos de pago fiat instantáneos.

Cada operador de un nodo de Mostro puede establecer sus plazos de tiempo para cada etapa del intercambio, lo que fomenta la competencia entre nodos de Mostro y permite a los usuarios seleccionar el que mejor se ajuste a sus necesidades. En la [Mostro App](./mostro-mobile.md) puedes ver los tiempos del nodo que usas en *Acerca de → Nodo conectado* (*Expiración*) y en *Acerca de → Datos técnicos del nodo*. La pantalla de la operación también muestra una cuenta regresiva para cada paso.

Las cifras siguientes son valores típicos; consulta tu nodo para conocer los exactos.

Al publicar una oferta, esta suele permanecer en el libro de órdenes *24 horas* (algunos nodos mantienen las órdenes hasta 72 horas). Si nadie la toma durante ese tiempo, se eliminará automáticamente.

Una vez que alguien toma una oferta, suele tener *15 minutos* para pagar la hold invoice si es el vendedor, o proporcionar una invoice si es el comprador. Si no cumple con su parte en ese tiempo, la orden se volverá a publicar automáticamente. Pero si cumple, luego la contraparte tendrá el mismo tiempo para completar su acción correspondiente (pagar la [hold invoice](./hold-invoice.md) o proporcionar una factura, según su rol en el intercambio). Si este no lo hace, la orden será cancelada y no se republicará.

Después de que el vendedor paga la hold invoice y el comprador proporciona su factura, tienen tiempo para concretar el intercambio hasta poco antes de que expire la [hold invoice](./hold-invoice.md) que Mostro le proporcionó al vendedor. Ese tiempo se mide en bloques de Bitcoin, que llegan cada 10 minutos en promedio. En la mayoría de los nodos la hold invoice dura 144 bloques (aproximadamente 1 día) y Mostro interviene unas 20 horas después de que el vendedor pagó; en los nodos con hold invoices más largas, como el nodo predeterminado de la app (aproximadamente 2 días), Mostro interviene después de unas 46 horas. Durante este tiempo, el comprador debe enviar el pago en fiat y el vendedor liberar los Sats al confirmar la recepción del fiat. Por esta razón, se recomienda utilizar únicamente métodos de pago fiat instantáneos.

Si el intercambio no se ha completado cuando Mostro interviene:

- Si el comprador no ha marcado el fiat como enviado, Mostro cancela la orden y los Sats son devueltos a la wallet del vendedor.
- Si el comprador ya marcó el fiat como enviado, Mostro [abre una disputa automáticamente](./disputes.md#disputa-automática), para que un administrador pueda resolverla en el poco tiempo que queda antes de que expire la hold invoice.

Dentro de este período de validez, los usuarios pueden finalizar satisfactoriamente el intercambio, [cancelarlo](./cancelling-an-order.md) cooperativamente, o abrir una [disputa](./disputes.md). Luego de que la [hold invoice](./hold-invoice.md) expire, Mostro no tiene capacidad de intervenir en esa orden.

Si ambos participantes de una operación están en línea y utilizan métodos de pago fiat inmediatos, las transacciones pueden completarse de forma casi instantánea.
