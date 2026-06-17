# Gestión de Disputas

Si tu contraparte no responde, sospechas de un intento de estafa, o surge un malentendido que no logran resolver, puedes iniciar una disputa.

## Cómo funciona

Cuando inicies una disputa, serás atendido por el administrador del nodo de Mostro que estés utilizando, o por una persona designada por dicho administrador (solver). Al abrir la disputa, Mostro te proporcionará un número de token único, y tu contraparte recibirá uno diferente. Ambos tokens serán revelados al administrador que gestione la disputa. Cuando el administrador se ponga en contacto contigo y con tu contraparte, te dirá cuál es tu token, lo que te permitirá verificar que es la persona designada y asegurarte de que no se trata de un impostor.

## Resolución

No hay un método estándar para resolver disputas en todos los nodos de Mostro. Cada administrador puede decidir cómo gestionar las disputas generadas en su nodo y qué pruebas solicitar a los usuarios para tomar la decisión más adecuada.

Cuando el administrador decida qué usuario tiene la razón, hará que Mostro libere los sats al usuario que corresponde. Los administradores no cobran ninguna tarifa extra por resolver disputas.

## Evidencia del chat

Durante una operación, el comprador y el vendedor se comunican a través de un chat cifrado de extremo a extremo. Este chat genera una "llave maestra compartida" que solo conocen ambas partes.

Si hay una disputa, cualquiera de las partes puede optar por compartir voluntariamente esta llave con el solver. Con ella, el solver puede acceder a una copia de la conversación que no puede ser alterada ni borrada. Esto permite resolver disputas de manera justa, exponiendo cualquier intento de engaño.
Para más detalles sobre cómo funciona este sistema de privacidad, consulta la sección de [Privacidad en Mostro](./privacy.md).

## Tiempos importantes

Las disputas no se abren automáticamente en ningún caso. Los usuarios involucrados deben iniciarlas antes de que expire la [hold invoice](./hold-invoice.md) que el vendedor ha pagado, de forma que el administrador tenga tiempo suficiente para solicitar pruebas a ambas partes y tomar una decisión adecuada.

El tiempo sigue corriendo desde que se aceptó la orden y no se detiene por abrir una disputa. El administrador debe resolverla antes de que el tiempo expire, por lo que los usuarios no deben esperar demasiado para iniciarla. Puedes leer más sobre los plazos de tiempo [aquí](./times.md).

## Depósito anti-abuso en disputas

Si operas en un nodo que exige un [depósito anti-abuso](./anti-abuse-bond.md), el administrador puede cobrar el depósito de quien haya actuado de mala fe al resolver la disputa. Parte de ese depósito se entrega a la contraparte honesta como compensación. Consulta [Depósito Anti-Abuso](./anti-abuse-bond.md) para conocer cómo funciona.
