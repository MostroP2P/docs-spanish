# Clientes. Cómo uso Mostro

Para utilizar Mostro, es necesario acceder a través de un cliente específico. A continuación, abordaremos varios de ellos, los cuales te permitirán interactuar tanto con Mostrod como con tu contraparte en una operación. 

Los clientes de Mostro disponibles hasta el momento son:
- **[Mostro App](./mostro-mobile.md)** (operativo, beta): la aplicación oficial, para Android, iOS, Windows, macOS, Linux y la web.
- **[Mostro-cli](./mostro-cli.md)** (operativo): cliente desde línea de comandos.
- **[MostriX](./mostrix.md)** (operativo): cliente con interfaz TUI, que funciona en la terminal con una apariencia mejorada, con un modo para solvers de disputas.

La antigua app *Mostro Mobile* (versión 1) está obsoleta: usa la nueva Mostro App. Los solvers de disputas también tienen [Bosstro](https://github.com/MostroP2P/bosstro), una app de Android para resolver disputas; no sirve para operar.

Cada cliente tiene características particulares, por lo que los usuarios pueden elegir cuál utilizar según sus intereses y cambiar entre ellos cuando lo consideren conveniente. Los clientes son los encargados de crear, almacenar y gestionar las claves de Nostr de sus usuarios. Para conocer cómo los clientes manejan la privacidad de los usuarios lee [aquí](./privacy.md).

Aunque algunos clientes ya están en funcionamiento, se encuentran en constante desarrollo, con la implementación de nuevas funciones, mejoras de UX, corrección de errores, etc. Es posible que encuentres bugs; si esto sucede, por favor repórtalos, tu feedback es muy importante.

Desde la versión 0.19.0, los nodos de Mostro hablan solo el protocolo v2. Las versiones actuales de los tres clientes anteriores lo usan; los clientes antiguos que todavía usan NIP-59 gift wraps no pueden operar en los nodos actuales.

 **Nota:** Dos usuarios que utilicen diferentes clientes de Mostro pueden realizar intercambios de Sats; sin embargo, para la comunicación directa entre ellos, deben tener en cuenta qué tipo de mensajes aceptan sus respectivos clientes. Los clientes deben implementar este [peer-to-peer chat](https://mostro.network/protocol/chat.html) pero si un cliente aún no lo ha implementado, sus usuarios no podrán visualizar mensajes enviados desde un cliente que sí lo tenga implementado. De forma similar pudiera ocurrir con otras funcionalidades, los desarrolladores de cada cliente hacen su mayor esfuerzo por actualizarlos lo antes posible.

Mostro es un proyecto FOSS, por lo que cualquier persona interesada puede crear un cliente para interactuar con este. Te invitamos a desarrollar tu propio cliente o a colaborar en el desarrollo de los ya existentes para mejorar la experiencia de los intercambios de Bitcoin P2P sin KYC en Nostr!

Para conocer más detalles sobre ellos continúa leyendo esta documentación.
