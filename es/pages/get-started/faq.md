---
title: "Preguntas frecuentes"
summary: "Preguntas técnicas sobre el protocolo, la construcción de aplicaciones, los nodos, la gobernanza y la seguridad."
weight: 40
---

:::aside
Qué es 42 Chain, cómo se relaciona con Infinite Drive, quién lo desarrolla, tus llaves y este sitio: [preguntas generales →](site:/faq)
:::

## El protocolo {#protocol}

:::faq[¿Puedo mantener datos reservados?]
Sí. Los datos reservados se quedan fuera de la cadena, y en la red se registra solo su huella. [Qué va dentro y fuera de la cadena](/build/applications#application)
:::

:::faq[¿Qué son un drop y una cup?]
Dos nombres de medida de Improbability. Un **drop** es la fracción más pequeña y la denominación base de la red (`drop`, y `tdrop` en la red de pruebas): la unidad tiene 18 decimales, así que una unidad completa son 10¹⁸ drops. **Cup** es el nombre coloquial de una unidad completa, que se usa para hablar de cantidades sin repetir «Improbability». En billeteras y exploradores, la unidad aparece siempre con su símbolo, 42. [Drops y cups](/protocol/fees#drops-and-cups)
:::

:::faq[¿Cuánto tarda una transacción en ser definitiva?]
Un bloque, unos segundos. CometBFT confirma cada bloque de forma definitiva, sin reorganizaciones: una vez confirmada, una transacción no puede revertirse. El tiempo por bloque se ve en vivo en la [Consola](console:/status).
:::

:::faq[¿Con qué otras redes se conecta?]
Con las redes compatibles con IBC con las que se establece una conexión. Cada red comprueba por sí misma lo que ocurre en la otra, sin intermediarios. [Interoperabilidad](/protocol/interoperability)
:::

## Construir {#build}

:::faq[¿Qué herramientas de desarrollo puedo usar?]
Las del ecosistema EVM: Solidity, Hardhat, Foundry, Remix, Ethers.js, Viem y billeteras como MetaMask. Solo necesitas el chain ID y una dirección RPC. [Conectarse](/get-started/connect)
:::

:::faq[¿Puedo publicar un contrato que ya escribí para la EVM?]
Sí. Un contrato escrito para la EVM puede publicarse en la red sin cambios en su código.
:::

:::faq[¿Qué diferencia hay entre la red principal y la red de pruebas?]
En la red principal, las transacciones tienen efecto real. La red de pruebas sirve para desarrollar y probar, y usa unidades de prueba sin uso fuera de ella.
:::

:::faq[¿Cómo obtengo unidades de prueba?]
Desde un faucet de la red de pruebas: un servicio que entrega unidades de prueba gratis. [Directorio de proveedores](/get-started/connect#providers)
:::

## Nodos, validadores y delegación {#nodes}

:::faq[¿Qué necesito para operar un nodo?]
Un servidor Linux estándar. Los requisitos de cada tipo de nodo están en la guía de nodos de la documentación. [Operar un nodo](/operate/nodes)
:::

:::faq[¿Cómo se convierte un nodo en validador?]
El nodo se registra como validador con una transacción que incluye unidades en staking. Después, solo entra al conjunto activo si está entre los validadores con más poder de voto.
:::

:::faq[¿Qué es la delegación?]
Una cuenta elige un validador y le delega unidades. Esas unidades aumentan el poder de voto del validador, siguen siendo de quien las delega y comparten las penalizaciones del validador. [Delegación](/protocol/consensus#delegation)
:::

## Gobernanza {#governance}

:::faq[¿Cómo se deciden los cambios al protocolo?]
Por los votos registrados en la cadena. Cualquiera puede presentar una propuesta dejando un depósito, también quienes desarrollan el software. Los validadores y las personas que les delegan unidades la votan durante un período fijo, y la red aplica el cambio solo si lo aprueban. [Gobernanza](/protocol/governance)
:::

## Seguridad {#security}

:::faq[¿Qué pasa si pierdo mi llave privada?]
Pierdes el acceso a tu cuenta. El protocolo no tiene ningún mecanismo para restablecer una llave privada.
:::

:::faq[¿Cómo reporto una vulnerabilidad?]
En privado, a los mantenedores del código, nunca en un espacio público. [Reportar una vulnerabilidad](/open-source/security#report)
:::

## Proveedores {#providers}

:::faq[¿Los servicios de terceros que aparecen en la documentación están respaldados por el proyecto?]
No. Los proveedores de RPC y de exploradores que se listan en la documentación son independientes, y cada uno responde por su servicio. Que aparezcan en el sitio no implica respaldo.
:::
