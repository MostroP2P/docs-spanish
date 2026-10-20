# Gestión de Disputas

Si tu contraparte no responde, sospechas de un intento de estafa, o surge un malentendido que no logran resolver, puedes iniciar una disputa.

## Cómo funciona

Cuando inicies una disputa, serás atendido por el administrador del nodo de Mostro que estés utilizando, o por una persona designada por dicho administrador (solver). Cuando un solver toma la disputa, Mostro te envía a ti y a tu contraparte un mensaje con la clave pública de ese solver, para que tu cliente sepa con quién hablar en el chat de la disputa. Sigue solo las instrucciones del solver que Mostro asignó: cualquier otra persona que te escriba sobre la disputa puede ser un impostor.

## Resolución

No hay un método estándar para resolver disputas en todos los nodos de Mostro. Cada administrador puede decidir cómo gestionar las disputas generadas en su nodo y qué pruebas solicitar a los usuarios para tomar la decisión más adecuada.

Cuando el administrador decida qué usuario tiene la razón, hará que Mostro libere los sats al usuario que corresponde. Los administradores no cobran ninguna tarifa extra por resolver disputas.

## Evidencia del chat

Durante una operación, el comprador y el vendedor se comunican a través de un chat cifrado de extremo a extremo. Este chat genera una "llave maestra compartida" que solo conocen ambas partes.

Si hay una disputa, cualquiera de las partes puede optar por compartir voluntariamente esta llave con el solver. Con ella, el solver puede acceder a una copia de la conversación que no puede ser alterada ni borrada. Esto permite resolver disputas de manera justa, exponiendo cualquier intento de engaño.
Para más detalles sobre cómo funciona este sistema de privacidad, consulta la sección de [Privacidad en Mostro](./privacy.md).

## Tiempos importantes

Los usuarios involucrados deben iniciar la disputa con bastante anticipación a que expire la [hold invoice](./hold-invoice.md) que el vendedor ha pagado, de forma que el administrador tenga tiempo suficiente para solicitar pruebas a ambas partes y tomar una decisión adecuada.

El tiempo sigue corriendo desde que se aceptó la orden y no se detiene por abrir una disputa. El administrador debe resolverla antes de que el tiempo expire, por lo que los usuarios no deben esperar demasiado para iniciarla. Puedes leer más sobre los plazos de tiempo [aquí](./times.md).

## Disputa automática

Mostro abre una disputa por su cuenta en un único caso: el comprador marcó el fiat como enviado, el vendedor no ha liberado los Sats y la [hold invoice](./hold-invoice.md) está por expirar.

Poco antes de que expire la hold invoice, Mostro revisa la orden. Si todavía está esperando que el vendedor libere los Sats, Mostro abre una disputa para que un administrador pueda decidir mientras los Sats siguen bloqueados. Sin esa disputa, la hold invoice expiraría y los Sats volverían al vendedor, aunque el comprador ya hubiera enviado el fiat.

Lo que debes saber sobre esta disputa automática:

- Se registra a nombre del comprador, porque lo que está en juego es su pago. El comprador la verá como una disputa propia, y el vendedor la verá como una disputa abierta por su contraparte.
- Funciona como cualquier otra disputa: un administrador o solver la toma y atiende a ambas partes.
- El administrador tiene muy poco tiempo para resolverla antes de que expire la hold invoice: 12 bloques con la configuración por defecto. En teoría son 120 minutos, porque se mina un bloque cada 10 minutos en promedio, pero los bloques no llegan a intervalos fijos, así que ese tiempo puede ser mayor o menor. Si ese tiempo se agota, los Sats vuelven al vendedor y Mostro ya no puede intervenir. No esperes a la disputa automática: si tu contraparte deja de responder, abre tú la disputa lo antes posible.
- Si el comprador nunca marcó el fiat como enviado, Mostro no abre una disputa. Cancela la orden antes de que expire la hold invoice, y los Sats vuelven al vendedor.

## Depósito anti-abuso en disputas

Si operas en un nodo que exige un [depósito anti-abuso](./anti-abuse-bond.md), el administrador puede cobrar el depósito de quien haya actuado de mala fe al resolver la disputa. Parte de ese depósito se entrega a la contraparte honesta como compensación. Consulta [Depósito Anti-Abuso](./anti-abuse-bond.md) para conocer cómo funciona.
