# Tarifas y Límites de Intercambios

Cada operador de un nodo de Mostro puede establecer sus propias tarifas (fees) y límites por operación, lo que fomenta la competencia entre distintos nodos y permite a los usuarios seleccionar el que mejor se ajuste a sus necesidades.

## Tarifas

La tarifa del nodo se divide por la mitad entre el comprador y el vendedor en cada transacción completada. El porcentaje exacto depende del nodo de Mostro que utilices: la mayoría de los nodos comunitarios cobran entre 0.5% y 1% en total.

Por ejemplo, un nodo con una tarifa del 1% cobra 0.5% al comprador y 0.5% al vendedor. La [Mostro App](./mostro-mobile.md) muestra la tarifa **total** de cada nodo, en *Configuración → Red → Nodo Mostro* y en *Acerca de → Nodo conectado*. Cuando pagas la hold invoice como vendedor, la app te dice cuántos sats de ella corresponden a la tarifa.

Resolver una [disputa](./disputes.md) no tiene ningún costo extra. El [depósito anti-abuso](./anti-abuse-bond.md) que piden algunos nodos no es una tarifa: lo recuperas cuando operas de buena fe.

## Límites

Cada nodo también define los montos mínimos y máximos en sats permitidos por operación. Puedes verlos en la app en *Acerca de → Nodo conectado* (*Orden mínima* y *Orden máxima*), y la app comprueba tu orden contra ellos antes de publicarla.

## Múltiples nodos de Mostro

Mostro está diseñado para ser un sistema descentralizado donde múltiples operadores pueden correr sus propios nodos. Esto significa que:

- Hay competencia entre nodos para ofrecer el mejor servicio
- Cada operador define sus propias tarifas, límites y monedas aceptadas
- Los usuarios eligen libremente en qué nodo operar
- Si un nodo deja de funcionar, otros siguen disponibles

Puedes comprobar si un nodo está funcionando en la [página de estado](./node-status.md).

## Contribución al desarrollo

Cada nodo de Mostro contribuye automáticamente un porcentaje de sus ganancias al fondo de desarrollo del proyecto. Esta contribución sale de las ganancias del operador, no se cobra extra a los usuarios.

Este sistema garantiza la sostenibilidad del desarrollo de Mostro de forma transparente: todas las contribuciones se publican como eventos en Nostr y pueden ser verificadas por cualquiera.

Para más detalles sobre cómo funciona este sistema, puedes leer el artículo completo: [Financiamiento sostenible para el desarrollo de Mostro](https://mostro.network/blog/es/dev-fee-sostenibilidad)
