# Depósito Anti-Abuso

El depósito anti-abuso (*anti-abuse bond*) es un mecanismo opcional que algunos nodos de Mostro utilizan para hacer los intercambios más seguros. La idea es sencilla: al entrar en una operación pones en garantía una pequeña cantidad de Sats que recuperas por completo si actúas de buena fe, pero que pierdes si intentas estafar a tu contraparte o incumples tu parte del trato. De esta forma, el estafador pone su propio dinero en riesgo, lo que desalienta el abuso y aumenta la seguridad de los intercambios en Mostro.

## Un nodo con depósito o sin depósito

No todos los nodos de Mostro exigen un depósito anti-abuso. Es una función que cada administrador decide activar o no en su nodo, así que eres tú quien elige si prefieres operar en un Mostro que lo exige o en uno que no.

Cada nodo que lo active define sus propias reglas: a quién se lo pide (a quien crea la orden, a quien la toma, o a ambos) y de cuánto es. El monto suele ser un porcentaje pequeño del valor de la orden (por ejemplo, un 1%) con un mínimo en Sats, pero ese porcentaje lo decide cada nodo.

> **Consejo:** Puedes consultar si el nodo que estás usando exige un depósito anti-abuso —y de cuánto sería— desde tu propio cliente de Mostro. Por ejemplo, en [Mostro Mobile](./mostro-mobile.md) puedes ir a la sección *Acerca de* y revisar esos detalles del nodo antes de operar.

## ¿En qué se diferencia del escrow?

El depósito es completamente independiente del [escrow de la operación](./hold-invoice.md). Se trata de una segunda hold invoice: tus Sats quedan únicamente "bloqueados" en tu billetera, no se gastan. Si todo va bien, se "desbloquean" y vuelven a ti sin haber salido nunca de tu wallet. No se mezcla ni se descuenta del monto del intercambio.

## ¿Cuándo recupero mi depósito?

Recuperas el 100% de tu depósito siempre que cumplas tu parte: cuando completas la operación con éxito o, simplemente, cuando no cometes ninguna trampa ni incumples lo acordado. Por ejemplo:

- Completas el intercambio correctamente.
- Cancelas la orden de forma cooperativa.
- Surge una disputa y el administrador no determina que hayas actuado de mala fe.

En condiciones normales el depósito no representa ningún costo: vuelve íntegro a tu billetera, igual que los Sats bloqueados en una hold invoice.

## ¿Cuándo puedo perderlo?

> **Importante:** Solo pierdes tu depósito si abusas del sistema. Hay dos situaciones:
>
> 1. **Por decisión en una disputa.** Un administrador (solver), tras revisar las pruebas, determina que actuaste de mala fe e instruye a Mostro a cobrar tu depósito.
> 2. **Por incumplir tu parte y dejar correr el tiempo.** Si tomas o creas una orden y luego no respondes ni continúas con el intercambio (no pagas, no envías el fiat, no entregas tu factura a tiempo), dejas vencer el plazo que te correspondía. Esto solo aplica si el nodo activó esa política.

## ¿A dónde van los Sats del depósito cobrado?

Cuando se cobra un depósito, los Sats se reparten entre el nodo —que así financia el trabajo de resolver [disputas](./disputes.md) y de mantener el servicio— y tu contraparte honesta, como compensación por el perjuicio. La proporción de ese reparto la define cada nodo y es pública, de modo que puedes conocerla antes de operar.

## Ejemplos

> **Ejemplo — Un comprador que intenta estafar.** Alice vende Sats y Bob los compra en un nodo que exige depósito anti-abuso. Bob nunca envía el dinero fiat acordado, pero aun así le insiste a Alice para que le libere los Sats.
>
> Alice abre una [disputa](./disputes.md) y le presenta al administrador las pruebas de que nunca recibió el pago. El administrador comprueba que Alice tiene la razón, cancela la orden —los Sats del escrow vuelven a Alice— y cobra el depósito de Bob, que estaba intentando estafarla. Como compensación, Alice recibe la mitad de los Sats del depósito de Bob; la otra mitad queda para el nodo. Bob pierde su depósito por haber intentado abusar del sistema.

> **Ejemplo — Un spammer que ensucia el libro de órdenes.** Imagina a un usuario malintencionado que quiere llenar el libro de órdenes con ofertas que nunca piensa completar. En un nodo que exige depósito anti-abuso, para crear cada orden tiene que bloquear un depósito. Si alguien toma una de sus órdenes y él no responde ni continúa con el intercambio, deja vencer el plazo y pierde el depósito de esa orden. Así, llenar el libro de ofertas falsas le sale caro y deja de ser rentable.

## Si te corresponde el depósito de tu contraparte

Si tu contraparte pierde su depósito y a ti te toca una parte, tu cliente te pedirá una factura para enviarte esos Sats. Dispones de un plazo definido por el nodo (por ejemplo, 15 días) para reclamarla; si lo dejas pasar, pierdes el derecho a cobrar esa parte. Por eso conviene atender la solicitud de tu cliente cuando aparezca.
