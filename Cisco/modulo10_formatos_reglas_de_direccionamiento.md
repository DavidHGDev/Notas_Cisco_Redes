**Título del módulo** Formatos y reglas del direccionamiento IPv6. 

**Objetivo del móudlo** Explicar las características del direccionamiento IPv6. 

|**Título del Tema**| **Objetivo del Tema**|
|:---|:---|
|Problemas con IPv4|Entender por qué nació la necesidad de generar IPv6|
|Asignación de direcciones IPv6| Entender cómo se presentan las direcciones IPv6|

## Fechas de agotamiento de las direcciones IPv4 de RIR. 
IPv4 se está quedando sin direcciones, por eso es necesario aprender IPv6. 

La IPv6 tiene mayor capacidad con 132 bits de capacidad, lo que significa que puede tener direcciones más extensas y una capacidad de undecillones (es decir, 340 seguidos de 36 ceros) de posibles direcciones. 

También, el **IETF** cuando comenzó a desarrollar el sucesor de IPv4, aprovechó la oportunidad para agregar mejoras y una fue el protocolo de mensajes de control de Internet versión 6. (ICMP6) que incluye la resolución de direcciones y la configuración automática de direcciones que no se encuentra en ICMP para IPv4. 

IPv4 tiene un máximo teórico de 4300 millones de direcciones. Las direcciones privadas en combinación con la traducción de direcciones de red (NAT) fueron esenciales para demostrar la reducción del espacio de direcciones IPv4. Sin embargo, NAT es problemático para muchas aplicaciones, crea latencia y tiene limitaciones que impiden severamente las comunicaciones entre pares. 

En estados únidos los proveedores de telefonía móvil reportan que más del 90% de su tráfico es por IPv6. 

La mayoría de empresas grandes se pasan a IPv6. 

### Internet de las cosas IoT. 
Hoy en día, el interent es muchísimo más diferente a cómo era antes. Hoy tenemos muchísimos más dispositivos como autós inteligentes e incluso sistemas de vigilancia, lo que genera un aumento significativo en la crediente demanda de IPs. 

## Coexistencia de IPv4 e IPv6

No hay una fecha específica para el cambio de IPv6. Por ahora y por una cuantas décadas más, seguiran funcionando tanto IPv4 cómo IPv6. El IETF creó diversos protocolos y herramients para ayudar a los administradores de redes a migrar las redes a IPv6. Las técnicas de migración se pueden dividir en tres categorías. 

+ **Doble pila** pérmite que tanto IPv4 como IPv6 coexistan en el mismo segmento de red. Los dispositivos **dual-stack** ejecutan pilas de protocolos IPv4 e IPv6 de manera simultánea. Es conocido como IPv6 nativo, esto significa que la red del cliente tiene una conexión a IPv6 a su ISP y puede acceder al contenido que se encuentra en internet a través de IPv6. 

- **Tunerización** Es el método para transportar un paquete IPv6 a través de una red IPv4. El paquete IPv6 se encapsula dentro de un paquete IPv4, de manera similar a lo que sucede con otros tipos de datos. 

- **Traducción** La traducción de direcciones de Redes 64 (NAT64) permité que los dispositivos con IPv6 habilitado se comuniquen con dispositivos IPv4 habilitado mediante una técnica de traducción similiar a la NAT para IPv4. Un paquete IPv6 se traduce a un paquete Ipv4, y un paquete IPv4 se traduce a un paquete IPv6. 

**Nota** Siempre que sea posible se debe utilizar IPv6 nativo, solo se debe utilizar la **Tunerización o la Traducción** para la transición a IPv6 nativo. 


# Sistema de números hexadecimales 

Los sistemas IPv6 se representa mediante dígitos hexadecimales. Este sistema base de 16 números utiliza los dígitos del 0 al 9, y las letras de la A a la F: 

En las direcciones IPv6, estos 16 dígitos se representan como **hextetos** para que sea muchísimo más legible. 

## Formatos de direcciones IPv6
### Segmentos o hextetos de 16 bits

Lo primero es entender como se escribe y se formatea una dirección IPv6. 

Las direcciones IPv6 tiene una longitud de 128 bits y se escriben como una cadena de valores hexadecimales. Cada cuatro bits está representado por un solo dígito hexadecimal; para un total de 32 valores hexadecimales,. 

Las direcciones IPv6 no distinguen entre mayúsculas o minúsculas. 

+ **4 dígitos hexadecimales = 16 dígitos binarios** 

|0000|0000|0000|0000|
|:---|:---|:---|:---|
|a|a|a|a|
|1111|1111|1111|1111|


y son separadas por :

### Formato preferido. 

El formato para escribir una dirección IPv6 x: x: x: x: x: x:, dónde cada "x" consta de cuatro valores hexadecimales. El término octeto hace referencia a los ochos bits de una dirección IPv4. En IPv6, un "hexteto" es el término no oficial que se utiliza para referirse a un segmento de 16 bits o cuadro valores hexadecimales. Cada "x" es un único hexteto que tiene 16 bits o cuadro dígitos hexadecimales. 

El formato preferido significa que dirección IPv6 se escribe utiliznado los 32 dígitos hexadecimales. No significa necesariamente que sea un método ideal para representar la dirección IPv6. 

Dos reglas que ayudan a educir la cantidad de dígitos necesarios para represenar una dirección IPv6. Ejemplo en formáto preferido. 

| N° | Dirección IPv6 Completa (Sin Comprimir) | Dirección Comprimida (Regla 1 y 2) | Tipo de Dirección |
| :---: | :--- | :--- | :--- |
| **1** | `2001:0db8:0000:1111:0000:0000:0000:0200` | `2001:db8:0:1111::200` | Global Unicast (Documentación RFC 3849) |
| **2** | `2001:0db8:0000:00a3:abcd:0000:0000:1234` | `2001:db8:0:a3:abcd::1234` | Global Unicast (Documentación RFC 3849) |
| **3** | `2001:0db8:000a:0001:c012:9aff:fe9a:19ac` | `2001:db8:a:1:c012:9aff:fe9a:19ac` | Global Unicast (Documentación RFC 3849) |
| **4** | `2001:0db8:aaaa:0001:0000:0000:0000:0000` | `2001:db8:aaaa:1::` | Global Unicast (Documentación RFC 3849) |
| **5** | `fe80:0000:0000:0000:0123:4567:89ab:cdef` | `fe80::123:4567:89ab:cdef` | Link-Local |
| **6** | `fe80:0000:0000:0000:0000:0000:0000:0001` | `fe80::1` | Link-Local |
| **7** | `fe80:0000:0000:0000:c012:9aff:fe9a:19ac` | `fe80::c012:9aff:fe9a:19ac` | Link-Local (Formato EUI-64) |
| **8** | `fe80:0000:0000:0000:0123:4567:89ab:cdef` | `fe80::123:4567:89ab:cdef` | Link-Local |
| **9** | `0000:0000:0000:0000:0000:0000:0000:0001` | `::1` | Loopback (Equivalente a 127.0.0.1) |
| **10** | `0000:0000:0000:0000:0000:0000:0000:0001` | `::1` | Loopback (Equivalente a 127.0.0.1) |

básicamente, cuando representamos una dirección en formáto preferido, es cuando la tenemos con sus 32 dígitos hexadecimales. 

+ dos reglas hexadecimales. 
1. **tódos los ceros que están a la izquierda del último dígito se eliminan para comprimir

2001 : 0db8 : acad : 0000 :
2001 :  db8 : acad :    0 :

2. Cualquier cadena continua de uno o más segmentos de 16 bits que consiste en solo ceros, se puede representar con un doble dos puntos. 

Esto solo se puede aplicar una vez, que se pone el :: para reemplezar la cadena o las cacenas de 0. 
Por ejemplo. 

2001:0db8:0000:0000:0000:1234:0000:5678

y se convierte la cadena más grande 
**2001:db8::1234:0:5678**

### Regla 1 - Omitir ceros iniciales. 

La primera regla nos ayuda a reducir la notación de las direcciones IPv6 es con omitir los ceros iniciales en cualquier hexteto. 

Esta regla solo es válida para ceros iniciales, y NO para ceros finales; de lo contrario, la dirección sería ambigua. 

### Regla 2 - Dos puntos dobles 
La segunda regla para reducir la notación IPv6 es con dos puntos dobles (::) puede reemplazar cualquier cadena única y continua de uno o más hextetos de 16 bits que consisten en todos los ceros. los (::) se utilizan en vez de los hextetos de tres (0:0:0). 

Los dos puntos dobles solo pueden utilizar una sola vez dentro de una dirección. 

Se recomienda utilizar los dos puntos dobles en la cadena más larga, si son iguales, en la primera. 


