# NETWORK PROTOCOLS

| ETHERNET | IP | TCP | HTTP |
| :--- | :--- | :--- | :--- |
| El protocolo ethernet gobierna la tarjeta de red NIC, dentro de la misma red. | El protolo IP rige la comunicación desde el origen hasta el destino, pasando por todos los routes o switcs intermedios, para eso sirve la IP. | El protocolo de control de trasmisión, garantiza que la información viaje con integridad, que las tramas se puedan verificar antes de unirlas y que si sea la información integra, si hay algo diferente, descarta. | El **protocolo de transferencia de hipertexto** Rige el intercambio o transferencia de HTML, el lenguaje de marcado de Hipertexto. 

Entender los protocolos nos dará una mayor comprensión de las redes. Entender como viaja la información de un lugar a otro, por medio de qué viaja y cómo se garantiza la seguridad de los paquetes o tramas. 

## MODELO TCP/IP o PILA DE PROTOCOLOS 
| APLICATION | TRANSPORT | INTERNET | NETWORK ACCES |
| :--- | :--- | :--- | :--- |
| HTTP utiliza el protocolo de aplicación o comunicación de hipertexto | TCP se comunica por medio de la capa de TRASPORTE, y garantiza que el mensaje llegue de forma confiable |IP se comunica por medio del protocolo INTERNET. bien sea en la misma red o atravesando la red de redes INTERNET | ETHERNET se comunica por medio de la capa de acceso a la red, del modelo TCP/IP. Utiliza la NIC para comunicación en la misma red.|

Los modelos en capas nos ayudan a ver como se integran los diferentes protocolos para posibilitar las comunicaciones en red. Este modelo describe el funcionamiento de los protocolos que se producen en cada capa, y como es la interación con las capas que están encima y por debajo de ellas. 
### Beneficios del modelo en capas. 

- Ayudan en el diseño de protocolos, ya que estos protocolos tienen información definida para la comunicación de la interfaz con las capas superiores e inferiores. 
- Fomentan la competencia ya que los productos de diversos proveedores se comunican sin problema utilizan los mismos protocolos. 
- Se pueden implementar cambios en una capa sin afectar las otras. 
- Proporciona un lenguaje común para describir las funciones y capacidades del networking. 

| Capa del modelo TCP/IP | Descripción |
| :--- | :--- |
| Aplicación | Representa datos para el usuario más el control de codificación y de diálogo.|
| Transporte | Permite la comunicación entre distintos dispositivos a través de la red | 
| Internet | Determina el mejor camino a través de la red |
| Acceso a la red | Controla los dispositivos de hardward y los medios de acceso a la red. |

## Modelo de referencia OSI 
Para que las comunicaciones en red se presenten de forma éxitosa, deben existir dos tipos de modelos básicos. El **Modelo de protocolo** y el **Modelo de referencia** 

- **Modelo de protocolo** Este modelo coincide con la estructura de un conjunto de protocolos en particular. Es un modelo rigido. Una Suite de protocolos incluye el conjunto de protocolos para las comunicaciones. El modelo TCP/IP es un modelo de protocolos que describe todas las funciones para que se puedan dar las comunicaciones en Internet. 

- **Modelo de referencia** Este modelo describe las funciones que se deben completar en una capa en particular. Pero no especifica como se deben llevar la función a cabo, por eso se llama modelo de referencia. El modelo de referencia no pretente dar dellates de todo, pretente ser una guía. 


| **Capa del Modelo OSI** | **Descripción** |
| :--- | :--- |
| 7 Aplicación | La capa de aplicación contiene los protocolos utilizados para las comunicaciones proceso a proceso |
| 6 Presentación | Proporciona una representación de los datos transferidos entre los servicios de la capa de aplicación. | 
| 5 Sesión | Proporciona servicios a la capa de presentación con el fin de organizar su diálogo y administrar el intercambio de datos| 
| 4 Trasnporte | Define los servicios para segmentar, transferir y reensamblar los datos para las comunicaciones individuales entre las terminales | 
| 3 Red | Proporciona los servicios para el intercambio de datos inviduales entre terminales identificadas. |
| 2 Enlace de Datos | Describen los medios comunes para el intercambio de tramas de datos entre dispositivos de un medio común. | 
| 1 Física | Describen los medios mécanicos, eléctricos, funcionales y de procidimiento para activar, desactivar y mantener conexiones físicas para la transmisión de bits hacía y desde un dispositivo de red. 

