# Privacidad en Mostro

## Privacidad en la comunicación del usuario con Mostro
La comunicación entre Mostrod y los usuarios se realiza a través de los [clientes de Mostro](./clients.md) mediante el protocolo v2 de Mostro: cada mensaje es un evento de Nostr firmado de tipo 14 cuyo contenido está cifrado con [NIP-44](https://github.com/nostr-protocol/nips/blob/master/44.md), de modo que solo el nodo puede leerlo. Para aumentar la privacidad, los clientes de Mostro generan automáticamente una nueva clave para cada orden que tomes o crees, y esa clave firma tus mensajes. Los relays pueden ver que una clave de un solo uso habla con un nodo de Mostro, pero no lo que dice, y las transacciones de compra y venta no pueden asociarse desde afuera a una sola persona.

Los clientes de Mostro no compartirán las claves privadas de los usuarios con un nodo de Mostro, y por consiguiente con su administrador, en ningún caso.

Desde la versión 0.19.0, los nodos de Mostro hablan solo el protocolo v2. Los clientes que todavía usan el protocolo antiguo (NIP-59 gift wraps) no pueden operar en ellos.

### Modo de reputación

Mostro ofrece a los usuarios la opción de operar en un `modo de reputación`, el predeterminado en la [Mostro App](./mostro-mobile.md). En este modo, tu cliente demuestra al nodo de Mostro que estés utilizando que la orden pertenece a tu clave de identidad fija. Esa prueba viaja dentro del mensaje cifrado, así que solo ese nodo la conoce. El nodo puede entonces asociarte una [reputación](./reputation.md) basada en las calificaciones que recibas de tus contrapartes tras completar operaciones. Tu clave de identidad no se comparte con otros usuarios ni se expone públicamente, y cada nueva orden sigue utilizando claves de un solo uso, protegiendo los detalles de cada intercambio ante un tercero.

### Modo de privacidad total

Para aquellos usuarios que priorizan la privacidad por encima de todo, Mostro ofrece el `modo de privacidad total`. En este modo, tu cliente no envía ninguna prueba de identidad al nodo de Mostro. Cada operación utiliza exclusivamente la clave de un solo uso generada para ese intercambio, de modo que el nodo no tiene forma de vincular las órdenes de un mismo usuario entre sí, ofreciendo un nivel máximo de anonimato.

Como en el `modo de privacidad total` no existe una clave fija asociada a ti, no es posible construir o mantener una reputación: no das ni recibes calificaciones, tu reputación aparece en 0 ante tus contrapartes y tus operaciones no se pueden [restaurar](./backup-restore.md) en otro dispositivo. Tampoco puedes [importar una reputación](./reputation-import.md).

En la Mostro App cambias entre ambos modos en *Cuenta → Privacidad*; la elección se conserva hasta que la cambies.

## Privacidad en la comunicación entre usuarios
La comunicación entre el comprador y el vendedor durante una operación se realiza directamente de cliente a cliente a través de un chat cifrado de extremo a extremo, integrado en los clientes de Mostro. Ambos clientes derivan una clave compartida mediante [Elliptic Curve Diffie-Hellman (ECDH)](https://mostro.network/protocol/chat.html#shared-key). Cada mensaje se cifra con NIP-44 y lo firma la clave de la operación del emisor, y luego se envuelve en un evento de tipo 14 dirigido a esa clave compartida. Esta "clave maestra compartida" es conocida solo por el comprador y el vendedor, y asegura que ni el nodo de Mostro en el que están haciendo el intercambio, ni terceros puedan leer ni inyectar mensajes. Además, como cada operación genera claves nuevas y únicas, la privacidad se mantiene intacta incluso entre transacciones con la misma contraparte.

En caso de [disputa](./disputes.md), esta clave compartida ofrece una solución efectiva: cualquiera de las partes puede optar por compartirla voluntariamente con el solver. Con ella, el solver puede descifrar únicamente la conversación de esa operación específica, accediendo a una copia inmutable de los mensajes, que no puede ser alterada ni borrada. Esto permite resolver disputas de manera justa y transparente, exponiendo cualquier intento de engaño sin comprometer la privacidad por defecto de los usuarios y solo revelando la información cuando sea necesario y consentido.

Algunos nodos usan a [Serbero](./disputes.md#serbero-el-asistente-automático), un asistente automático de disputas. Si le escribes durante una disputa, tus mensajes son procesados por un servicio automatizado que usa el operador del nodo.

## Otros detalles

- Las notificaciones push no llevan contenido: solo avisan a tu dispositivo de que hay algo para ver en la app.
- Si conectas una billetera mediante Nostr Wallet Connect (NWC), su cadena de conexión permanece en tu dispositivo.
- Importar tu reputación desde otro origen vincula tus cuentas en ambos lados. Consulta [Importar tu reputación](./reputation-import.md).
