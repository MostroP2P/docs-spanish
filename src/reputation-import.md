# Importar tu reputación

Si ya operaste en [@lnp2pBot](https://t.me/lnp2pbot) o en otro nodo de Mostro, no tienes que empezar de cero. Puedes llevar la reputación que ganaste allí al nodo de Mostro que usas ahora.

## Qué se transfiere

Viajan tres datos contigo:

- cuántas calificaciones recibiste,
- tu calificación promedio,
- la fecha de tu primera operación.

El origen los firma en un pequeño evento de Nostr, llamado atestación, dirigido a tu identidad de Mostro. Es válida por 7 días. El nodo en el que importas suma esos datos a la reputación que ya tienes allí. Tus contrapartes ven una sola calificación, un solo número de reseñas y una sola fecha de "operando desde". Nada indica que un dato fue importado.

> **Ejemplo:** tienes 2 calificaciones con promedio 4.5 en un nodo de Mostro e importas 214 calificaciones con promedio 4.87 desde lnp2pBot. Tus contrapartes en ese nodo ahora ven cerca de 4.87 con 216 calificaciones, y operando desde la más antigua de tus dos primeras operaciones (aquí, la primera en lnp2pBot).

## Antes de empezar

- Usa una versión reciente de la [Mostro App](./mostro-mobile.md).
- Usa el **modo de reputación** (*Cuenta → Privacidad*). En el [modo de privacidad total](./privacy.md) no hay una identidad que lleve la reputación, así que los botones de importar están deshabilitados.
- [Haz backup de tus 12 palabras](./backup-restore.md). Tu reputación está ligada a tu identidad.
- Selecciona un nodo que acepte importaciones de ese origen. No todos lo hacen: cada operador decide en qué orígenes confía. Si el nodo no importa, la app te lo indica: *"Este Mostro no importa reputación."*

## Desde lnp2pBot

El bot exporta tu reputación si tu cuenta tiene al menos **10 operaciones completadas** y **5 calificaciones recibidas**, y no está bloqueada.

1. En la Mostro App, abre *Configuración → Red → Nodo Mostro* y selecciona el nodo donde quieres tu reputación.
2. Ve a *Configuración → Red → Reputación* y toca **Importar reputación**.
3. Anota la clave pública (npub) que muestra la pantalla y toca **Obtenerla de lnp2pBot**. Telegram abre un chat privado con el bot.
4. La primera vez, el bot muestra el npub al que exportará. Comprueba que sea exactamente el que muestra tu app y toca **Confirmar y exportar**. Esto vincula tu cuenta del bot con esa identidad de Mostro.
5. El bot envía dos mensajes: un resumen y la atestación en sí. Copia el **segundo mensaje completo**.
6. De vuelta en la app, pégalo en *"Pega la reputación que recibiste"* y toca **Comprobar**. La app muestra quién la emitió y tus datos, por ejemplo *"★ 4.87 · 214 calificaciones · desde …"*.
7. Toca **Importar en este Mostro**. La app confirma: *"Tu reputación se importó."*

> **Consejo:** Abre el enlace desde la app, en un dispositivo que tenga Telegram. Abrir el bot a mano no funciona: el bot necesita el enlace que construye la app, que lleva tu identidad.

Si más adelante necesitas otra copia, por ejemplo para importar en un segundo nodo, repite los pasos. El bot envía una nueva atestación para la misma identidad sin pedirte confirmar otra vez.

## Desde otro nodo de Mostro

También puedes llevar la reputación que ganaste en un nodo de Mostro (A) a otro (B). El nodo A debe ofrecer la exportación y el nodo B debe confiar en el nodo A.

1. Selecciona el nodo A. Ve a *Configuración → Red → Reputación → Exportar mi reputación* y toca **Exportar mi reputación**. Deja vacío el campo de autorización.
2. Confirma la identidad en *"¿Exportar a esta identidad?"* con **Exportar**. La app indica que tu reputación está lista y es válida por 7 días.
3. Selecciona el nodo B en *Configuración → Red → Nodo Mostro*.
4. Abre *Configuración → Red → Reputación → Importar reputación*. La atestación ya está rellenada y comprobada.
5. Toca **Importar en este Mostro**.

El nodo A exporta solo la reputación que ganaste **en el nodo A**: al menos 10 operaciones completadas y 5 calificaciones recibidas allí. La reputación que importaste al nodo A no vuelve a viajar.

## Importar en varios nodos

- Tienes que importar por separado en cada nodo donde quieras tu reputación.
- La misma atestación sirve en varios nodos mientras sea válida (7 días). Después de una importación exitosa la app borra su copia, así que conserva el texto copiado o simplemente exporta de nuevo.
- En cada nodo puedes importar **una vez desde cada origen**: por ejemplo, una vez desde lnp2pBot y una vez desde otro nodo de Mostro.

## Si cambias de identidad

- **Restaurar las mismas 12 palabras** te devuelve la misma identidad. No hay nada que hacer.
- **Mudarte a una identidad nueva:** tu reputación en el origen está ligada a tu identidad anterior. Con la identidad anterior activa, ve a *Reputación → Mudarse a una identidad nueva*, ingresa el npub nuevo y toca **Firmar para este Mostro** (o **Firmar para lnp2pBot** si vino del bot). Copia la autorización, válida por una hora. Luego, con la identidad nueva activa, pégala en el campo de exportación (Mostro) o en el chat del bot (lnp2pBot).
- **Si perdiste la identidad anterior**, solo el operador del nodo (o los administradores de lnp2pBot) puede mudarla, después de comprobar que eres tú.

## Qué debes saber

- **Importar vincula dos cuentas.** El origen sabe a qué identidad de Mostro llegó tu reputación, y el nodo en el que importas sabe de qué cuenta viene. Con lnp2pBot, Telegram también lo ve. Si no quieres que esas cuentas queden vinculadas, no importes.
- **No puedes deshacerlo**, y agota ese origen para tu identidad en ese nodo.
- **Es una instantánea.** Las calificaciones que recibas después en el origen no se suman.
- **Solo tú puedes usarla.** Una atestación está dirigida a tu identidad: si alguien más la copia, no puede importarla.

## Mensajes que puedes ver

| Mensaje | Qué significa |
|---|---|
| Este Mostro no importa reputación. | El nodo que seleccionaste tiene la importación desactivada. Elige otro nodo. |
| Este Mostro no acepta reputación de ese origen. | El nodo no confía en el origen que firmó tu atestación. |
| Este Mostro no exporta reputación. | El nodo que seleccionaste no ofrece la exportación. |
| Tu cuenta todavía no puede exportar su reputación… | Aún no tienes 10 operaciones completadas y 5 calificaciones recibidas en ese origen. |
| La reputación solo se puede mover desde una cuenta que la conserva… | Estás en modo de privacidad total. Cambia al modo de reputación. |
| Esta reputación expiró. Pídela de nuevo a su origen. | Tiene más de 7 días. Consigue una nueva. |
| Esta reputación se emitió para otra identidad distinta de la que estás usando. | Cambiaste de identidad después de obtenerla. Usa la identidad para la que se emitió, o consulta "Si cambias de identidad". |
| Esta reputación ya se importó en este Mostro. | Ya importaste desde ese origen en este nodo. |
| Tu reputación allí ya está ligada a otra identidad… | Consulta "Si cambias de identidad". |
