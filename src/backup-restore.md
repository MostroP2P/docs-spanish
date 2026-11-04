# Backup y Restauración de Cuenta

Tu identidad en Mostro se basa en una clave privada que los clientes generan automáticamente cuando creas tu cuenta. Esta clave se representa como una frase de 12 palabras (seed phrase) que debes guardar de forma segura.

## Por qué es importante el backup

Sin un backup de tu frase de 12 palabras, podrías perder:

- Acceso a trades activos: si cambias de dispositivo o reinstalas la app durante un intercambio, no podrás continuar la operación
- Tu reputación: las calificaciones que has acumulado están asociadas a tu identidad; sin backup, empezarías desde cero
- Historial: no podrás recuperar información de operaciones anteriores

## Cómo hacer backup

En la [Mostro App](./mostro-mobile.md), ve a *Cuenta → Palabras secretas* y toca **Mostrar palabras**. La app te guía en tres pasos: anota las 12 palabras en papel, toca tres de ellas para comprobar que las anotaste bien, y listo. Hasta que lo hagas, la app te lo recuerda con un banner *Asegura tu reputación*.

La app no incluye tus claves en el backup en la nube de tu teléfono ni en la transferencia de dispositivo, así que las 12 palabras son la única forma de recuperar tu cuenta en un dispositivo nuevo.

Otros [clientes de Mostro](./clients.md) tienen su propia forma de mostrar tu frase de 12 palabras. Consulta su documentación.

Lo importante es:

- Anotar las 12 palabras en el orden correcto
- Guardarlas en un lugar seguro y privado
- No compartirlas con nadie
- No almacenarlas en texto plano en dispositivos conectados a internet

## Restaurar tu cuenta

Si necesitas cambiar de dispositivo, reinstalar la app, o usar un cliente diferente, puedes restaurar tu identidad importando tu frase de 12 palabras.

Al restaurar:

- Recuperas tu identidad y reputación
- Puedes continuar trades que estaban activos
- Accedes desde cualquier cliente de Mostro compatible

En la Mostro App, ve a *Cuenta → Importar usuario de Mostro* e ingresa tus 12 palabras. La app consulta al nodo que usas por tus órdenes y operaciones y las reconstruye. La restauración funciona por nodo: cuando cambias a otro nodo, la app restaura también lo que tienes allí. Antes de importar, si el usuario actual todavía tiene operaciones en curso, la app te avisa que *"Este usuario todavía tiene sats en juego"*.

Si usabas la antigua app Mostro Mobile, puedes importar las mismas 12 palabras en la nueva Mostro App: ambas usan las mismas claves. Termina primero cualquier operación abierta en la app antigua.

## Importante: Modo de privacidad total

Si operas en [modo de privacidad total](./privacy.md), las órdenes creadas en ese modo no se pueden recuperar al restaurar tu cuenta. Solo las órdenes creadas en modo de reputación pueden ser restauradas.

Esto se debe a que en el modo de privacidad total no existe una clave fija asociada a tu identidad, por lo que Mostro no puede vincular esas operaciones con tu cuenta restaurada.

## Recomendaciones

- Haz el backup apenas crees tu cuenta, antes de tu primera operación
- Verifica que anotaste las palabras correctamente antes de necesitarlas
- Considera tener más de una copia en lugares seguros diferentes
- Nunca compartas tu frase con nadie, ni siquiera con el soporte de Mostro
- Si valoras poder recuperar trades activos, usa el modo de reputación
