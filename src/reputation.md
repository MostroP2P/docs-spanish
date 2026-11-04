# Sistema de Reputación

Al completar exitosamente una compra o venta de Sats, Mostro te pedirá que califiques a tu contraparte, y tu contraparte también te evaluará a ti. El sistema de reputación utiliza una puntuación de 5 estrellas, donde 1 estrella representa la calificación más baja y 5 estrellas la más alta, permitiéndote valorar la experiencia de la transacción.

La reputación en Mostro se calcula de manera iterativa, combinando la media y la desviación estándar de las calificaciones y operaciones exitosas. Esto significa que, durante tus primeras transacciones, incluso si recibes calificaciones máximas, tu reputación inicial no será muy alta, sino que aumentará progresivamente a medida que acumules más operaciones exitosas con buenas evaluaciones.   
Ese cálculo está basado en: [https://math.stackexchange.com/questions/2148877/iterative-calculation-of-mean-and-standard-deviation](https://math.stackexchange.com/questions/2148877/iterative-calculation-of-mean-and-standard-deviation).

## Dónde vive tu reputación

Tu reputación la guarda cada nodo de Mostro, para tu identidad, y solo en [modo de reputación](./privacy.md#modo-de-reputación): en el modo de privacidad total no das ni recibes calificaciones. En la [Mostro App](./mostro-mobile.md) puedes ver tu propia reputación en el nodo que usas en *Cuenta*. Si cambias a otro nodo, empiezas con la reputación que tengas allí.

## Llevar tu reputación contigo

Si ganaste reputación en [@lnp2pBot](https://t.me/lnp2pbot) o en otro nodo de Mostro, puedes importarla al nodo que usas ahora, siempre que ese nodo confíe en el origen. Tus contrapartes verán entonces tu reputación de ambos lugares combinada. Consulta [Importar tu reputación](./reputation-import.md).
