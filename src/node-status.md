# ¿Funciona un nodo de Mostro?

Antes de operar, o cuando algo tarda más de lo normal, puedes revisar el estado de los principales nodos de Mostro en la página pública de estado:

**[status.mostro.network](https://status.mostro.network)**

Cada minuto, cada nodo publica en Nostr un reporte de salud firmado. La página lee esos reportes directamente de los relays, los verifica en tu navegador y compara el nodo de Lightning de cada nodo con exploradores de bloques públicos.

| Color | Significado |
|---|---|
| 🟢 Operativo | El nodo reporta que está sano y supera las comprobaciones independientes. |
| 🟡 Degradado | Algo no está del todo bien, o el nodo está en mantenimiento. |
| 🔴 Caído | El nodo reporta un problema grave, su nodo de Lightning está atrasado respecto a la cadena, o dejó de reportar. |
| ⚪ Sin monitorear | El nodo está listado pero todavía no se comprueba. |

Debajo de cada nodo puedes ver los últimos 90 días. Verde significa que el nodo funciona hasta donde se puede saber; no garantiza que todas las operaciones salgan bien.

## Mantenimiento

Un nodo en mantenimiento no acepta órdenes ni tomas nuevas, pero las operaciones que ya están abiertas todavía pueden completarse, cancelarse o disputarse. Los operadores lo activan para trabajos planificados. Los nodos también lo activan por sí solos cuando su nodo de Lightning se desincroniza, y lo desactivan cuando se recupera.

## Si tus sats se retrasan

Si el propio nodo de Lightning del nodo tiene un problema, Mostro no abandona tu pago: espera y paga automáticamente cuando el problema se resuelve, y ese retraso no cuenta como un pago fallido de tu parte. Si el nodo permanece en rojo por mucho tiempo, contacta a su operador (consulta [Soporte y Contacto](./support-and-contacts.md)).

## Comparar nodos en la app

En la [Mostro App](./mostro-mobile.md), *Configuración → Red → Nodo Mostro* muestra el estado, la tarifa y el depósito de cada nodo, y *Acerca de → Nodo conectado* muestra los límites, monedas y tiempos del nodo que usas.
