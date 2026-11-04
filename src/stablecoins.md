# Monedas estables y Bitcoin en otras redes

Algunos nodos de Mostro te permiten intercambiar sats de Lightning por **monedas estables en dólares** o por **bitcoin en otras redes**, además de las monedas locales. Los sats de Lightning siempre son uno de los lados de la operación. El otro lado se paga directamente entre ustedes dos, en la red indicada en la orden.

| Código | Qué es | Monto de la orden en |
|---|---|---|
| `USDT` | Tether USD | monedas (como dólares) |
| `USDC` | USD Coin | monedas (como dólares) |
| `DOC` | Dollar on Chain, en Rootstock | monedas (como dólares) |
| `BTC` | Bitcoin on-chain | sats |
| `LBTC` | L-BTC en la red Liquid | sats |
| `RBTC` | RBTC en Rootstock | sats |

Usos típicos: pasar entre Lightning y Liquid o Rootstock (un swap), conseguir bitcoin on-chain a cambio de sats de Lightning, o comprar y vender sats por dólares sin un banco.

## Qué nodos las ofrecen

Solo los nodos cuyo operador las habilitó. La [Mostro App](./mostro-mobile.md) (versión 2.1.2 o posterior) muestra estos códigos en la lista de monedas bajo **Stablecoins** y **Bitcoin en otras redes**, pero solo los que acepta el nodo seleccionado. Puedes comparar nodos en *Configuración → Red → Nodo Mostro* y en *Acerca de*.

## Cómo funciona el precio

- **Las monedas estables** valen un dólar cada una, así que una orden en USDT se cotiza exactamente igual que una orden en USD. La [prima o descuento](./fees-and-limits.md) funciona igual.
- **BTC, LBTC y RBTC** se cuentan 1:1 en sats. Una orden por 100,000 significa 100,000 sats de ese activo (0.001 RBTC). A precio de mercado, la prima es el precio del swap: si vendes sats de Lightning en una orden por 100,000 sats de RBTC con una prima del 1%, bloqueas 99,000 sats de Lightning y recibes 100,000 sats de RBTC. En la app ingresas estos montos en sats.
- Si un nodo acepta un código pero no lo cotiza a precio de mercado, la app te avisa: *"Este nodo no cotiza {code} a precio de mercado. Indica un monto fijo en sats."* (con el código en lugar de `{code}`).

La [tarifa](./fees-and-limits.md) habitual de Mostro se aplica además, como en cualquier operación.

## El método de pago es la red

El método de pago de la orden indica en qué red se paga el activo: por ejemplo `USDT (Tron)`, `USDT (Ethereum)`, `USDC (Base)`, `DOC (Rootstock)`, `BTC (On-chain)`, `LBTC (Liquid)` o `RBTC (Rootstock)`. Una orden puede listar varias redes; acuerden en el chat cuál usarán. Mostro no verifica la red ni la dirección.

## Paso a paso

**Si vendes sats** (recibes el activo):

1. Paga la [hold invoice](./hold-invoice.md) como en cualquier operación.
2. Comparte tu dirección de recepción en el chat de la operación. Asegúrate de que sea una dirección de la red que acordaron.
3. Cuando el comprador marque el pago como enviado, comprueba con el ID de transacción que pegó en el chat que llegó el monto completo **y que está confirmado**.
4. Solo entonces toca **Liberar sats**.

**Si compras sats** (envías el activo):

1. Envía el activo **en la red exacta** de la orden, a la dirección que el vendedor compartió en el chat. Tú pagas la comisión de red: el vendedor debe recibir el monto completo.
2. Pega el ID de transacción en el chat. Es tu prueba si hay una [disputa](./disputes.md). Para Liquid, pega el enlace de la transacción **sin cegar** (unblinded): Liquid oculta el monto, y ese enlace se lo muestra al vendedor y al solver.
3. Toca **Ya envié el pago**.

## Reglas de seguridad

- **Red equivocada, fondos perdidos.** Una moneda estable enviada en una red distinta a la de la dirección puede perderse para siempre.
- **Las transferencias no se pueden deshacer.** Mostro solo retiene el lado de Lightning; nunca ve ni verifica la otra transferencia.
- **Espera la confirmación.** Nunca liberes con una transferencia sin confirmar.
- **Cuida el reloj.** Tienes el mismo tiempo que en cualquier operación (consulta [Tiempo de Intercambio](./times.md)). Usa una comisión de red suficiente para que la transferencia se confirme a tiempo; una transacción on-chain barata puede tardar horas.
- **Las monedas estables pueden perder su paridad.** Se asume que su precio es de un dólar. Si una se aleja mucho de eso, piénsalo dos veces antes de operar con ella.

## Disputas

Si algo sale mal, abre una [disputa](./disputes.md) como de costumbre. Aquí no hay estado de cuenta bancario: el solver comprueba el ID de la transacción (o el enlace de Liquid sin cegar) en un explorador de bloques de esa red. Por eso es importante pegarlo en el chat.

## Otros clientes

[mostro-cli](./mostro-cli.md) y [MostriX](./mostrix.md) por ahora solo pueden crear estas órdenes a precio fijo y no muestran los montos de BTC, LBTC y RBTC en sats. Las versiones anteriores de la app tienen la misma limitación.
