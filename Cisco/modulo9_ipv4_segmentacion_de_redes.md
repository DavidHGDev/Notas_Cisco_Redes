# IPv4 y segmentación de redes
Su objetivo es explicar como se utilizan las direcciones IPv4 en la comunicación y segmentación. 

| Título del Tema | Objetivo del Tema |
| :--- | :--- |
| Unidifusión, difusión y multidifusión de IPv4 | Entender y comparar las características de unidifusión, difusión y multidifusión del IPv4 |
| Tipos de direcciones IPv4 | Entender las direcciones Publicas, Privadas y Reservadas |
| Segmentación de la red | Entender como la división en subredes segmenta una red para permitir una mejor comunicación. |

## Unidifusión, difusión y multidifusión de IPv4

**Unidifusión** es cuando un dispositivo realiza comunicación con otro dispositivo uno a uno. Esto afecta a IPv4. 

Un paquete de Unidifusión tiene una dirección IP de destino que es una dirección de unidifusión que va a un único destinatario. 
Una dirección ip de origen solo puede ser de unidifusión, ya que el paquete solo puede originarse de un único origen. Esto es indepediente si la dirección destino es unidifusión, difusión o multidifusión. 

### Difusión 
Una difusión significa que todos los paquetes de la red van a recibir ese paquete. El switch lo va a reenviar excepto por el puerto de entrada. 

**Trasmisión de trasmisión** hace referencia a un dispositivo que hace una comunicación a todos los dispositivos en una red unipersonales. Los paquetes de difusión tienen una dirección de destino que solo tiene 1. y la IPv4 destino es 255.255.255.255

- **Nota:** IPv4 utiliza paquetes de difusión. Sin embargo, IPv6 no hay paquetes de difusión. 

Todos los dispositivos del mismo dominio de difusión deben procesar un paquete de difusión. 

Un dominio de difusión identifica a todos los hots del mismo segmento de red. 

Una trasmisión puede ser dirigida o limitada. Una difusión dirigida se envía a todos los hots de una red específica. 

Por ejemplo, un host de la red 172.16.4.0/24 envía un paquete a la dirección 172.16.4.255. Se envia una difusión limitada a la dirección 255.255.255.255. de manera predeterminada los enrutadores no reenvían difusiones. 

Los paquetes de difusión usan recursos de la red y hacen que cada host receptor en la red procese el paquete. Por lo tanto, se debe limitar el tráfico de una difusión para que no afecte negativamene el rendimiento de la red o de los dispositivos. Esto debido a qué los **enrutadores** separan los dominios de difusión, la **subdivisión** de redes puede mejorar rendimiento de la red al eliminar el exceso de tráfico de una difusión. 

### Multidifusión 
La transmisión multidifusión reduce el tráfico al permitir que un único host envíe un paquete de multidifusión a un grupo de hosts que esté suscripto a un grupo de difusión. 

Un paquete de multififusión tiene una dirección IP destino de multidifusión. IPv4 reservó las direcciones de 224.0.0.0 a 239.255.255.255 como rango para multidifusión. 

Los hosts que reciben paquetes de multidifusión se denominan clientes de multidifusión. Estos utilizan servicios solicitados y qué previamente se debieron de suscribir a un servicio de multidifusión. 

Cada grupo de multidifusión está representado por una sola dirección IPv4 de destino multidifusión. Quiere decir que cuando un hots se suscribe, procesa los paquetes enviados a esa dirección de multidifusión y los paquetes dirigidos a esa dirección de unidifusión asignada exclusivamente. 

Los protocolos de enrutamiento como OSPF utilizan transmisiones de multidifusión. Por ejemplo, los routers habilitados por OSPF se comunican entre sí mediante una dirección de multidifusión OSPF reservada 224.0.0.5. Solo los dispositivos habilitados con OSPF procesarán los paquetes, los demás ignoran esos paquetes. 


# Direcciones IPv4 Públicas y Privadas 
Hay direcciones IPv4 que no se puede usar para salir a internet y en cambio, hay otras que se autoasignan para salir a internet. 

Las direcciones IPv4 públicas son direcciones que se enrutan globalmente entre routers de proveedores ISP. Sin embargo, no todas las direcciones IPv4 se pueden usar en internet. Existen bloques de direcciones que se denominan privadas, que la mayoría de organizaciones utiliza para comunicaciones internas. 

Las direcciones privadas no son exclusivas y cualquier red privada interna puede usarlas. 

|Dirección de red y prefijo | Rango de direcciones privadas de RFC 1918| 
| :--- | :--- |
| 10.0.0.0/8 | 10.0.0.0 a 10.255.255.255 |
| 172.16.0.0/12 | 172.16.0.0 a  172.31.255.255 |
| 192.168.0.0/16 | 192.168.0.0 a 192.168.255.255 |

## Enrutamiento a Internet 
### Traducción de direcciones de red (NAT), para utilizarlas como IP privadas. 

Las direcciones privadas no son enrutables globalmente. La mayoría de las empresas y hasta host en hogares utilizan direcciones ip privadas para dirigirse a todos los dispositivos internos (Intranet), incluidos host y enrutadores. 

Antes de enviar un paquete por el Internet, fuera de la red privada, se deben traducir a una ip pública, de lo contrario, se deben descartar dichos paquetes. 

**Traducción de direcciones de red (NAT)** se utiliza para traducir un paquete que tiene una dirección ip privada a una dirección ip pública, esto generalmente lo realiza un router del IPS, para que pueda salir la información. 


## Direcciones IPv4 de uso especial 
Hay direcciones que se pueden asignar a los host, pero con restricciones en la forma cómo se pueden comunicar por la red. 

### Direcciones de loopback 
Direcciones de bucle invertido (loopback) (127.0.0.0 /8 o 127.0.0.1 a 127.255.255.254) se identifican más comúnmente cómo 127.0.0.1. Estas direcciones se utilizan normalmente par dirigir el tráfico hacía el mismo host. 
el ping se utiliza para probar conexiones con otros host, pero también se puede utilizar con el mismo host 127.0.0.1. 

- **Direcciones de enlace local** Direcciones link-local o direcciones ip privadas automáticas (APIPA) 169.254.0.0/16 o 169.254.255.254 Los utiliza el cliente de windows y sirven para comunicación punto a punto. Generalemnte no se utiliza para eso, y las utiliza cuando el equipo no puede obtener una IP a traves de otros métodos. 

## Direccionamiento con clase heredado
A los clientes se les asignaba los números de acuerdo a 3 clases. A, B, C. 
- **Clase A (0.0.0.0/8 a 127.0.0.0/8)**: Diseñada para admitir redes extremadamente grandes, con más de 16 millones de host. La clae A, utiliza un prefijo de /8 con el primer octeto para indicar la red y los tres octetos restante para indicar las direcciones de hosts. Con más de 16 millones de host por red. 

- **Clase B (128.0.0.0/16 a 191.255.0.0/16)**: Fue diseñada para satisfacer la necesidad de redes moderadas o grandes, con capacidad de hasta 65.000 direcciones de host. La clase B, utiliza un prefijo 16, los dos primeros octetos para la red y los otros dos octetos para la dirección de los host. 

- **Clase C (192.0.0.0/24 a 223.255.255.0/24)** Fue diseñada para admitir redes pequeñas, con una capacidad máxima de 254 hosts. Utiliza un prefijo /24 para indicar los primeros 3 octetos para la red y el octeto restante para las direcciones de host. 

**Nota:** también hay un bloque de multidifusión de **Clase D**  que consta de 224.0.0.0 a 239.0.0.0 y un bloque de direcciones experimental **Clase E** que consta de 240.0.0.0 a 255.0.0.0

Las redes de clase A, representan un 50% e hizo que la gran mayoría no se utilizara. También, al inicio con un número limitado de host, funcionaba de maravilla. 

En total de redes 
- Clase A. con un total de 128 redes en total. Para un total de hosts por red de 16 777 214
- Clase B. En total 16,384 para un total de host por red de 65,534
- Clase C. En total 2,097,152, y total de hosts por red de 254. 

En los años 1990 cuando nació el WWW World Wide Web. El direccionamiento con clase fue ineficiente y fue necesario reemplazarlo por las direcciones IP sin clase, la que se utiliza hoy en día. 

El direccionamiento sin clase ignora las reglas de las clases (A, B, C). 

Las direcciones de IPv4 públicas (Direcciones de red y máscaras de subred) se asignan en función del número de direcciones que se puede justificar. 

## Asignación de direcciones IP 

Las direcciones iPv4 públicas, son direcciones en las que se utiliza el routing globalmente entre Routers ISP. Las direcciones públicas deben ser únicas. 

Tanto las direcciones Ipv4 y IPv6 son administradas por la autoridad de números asignados a Internet (Internet Assined Numbers Authority, IANA). (La IANA administra y asigna bloques de direcciones IP a los Registros Regionales de Internet RIR). 

Los (RIR) proporcionan bloques de direcciones IP a los proveedores ISP. Quienes a su vez proporcionan bloques de direcciones IP a organizaciones o proveedores ISP más pequeños. 

> **Adaptación: Chuleta de Identificación Rápida de IPs**
> Si veo una IP, escaneo el PRIMER OCTETO. Así sé qué es de inmediato:
> 
> - **Empieza por `10.x.x.x`** ➡️ PRIVADA (Clase A). Muy usada en redes corporativas grandes (Ej. La intranet de Tigo o redes de servidores).
> - **Empieza por `172.16` hasta `172.31`** ➡️ PRIVADA (Clase B). Usada en redes medianas o contenedores (Docker suele asignar IPs 172.17.x.x por defecto).
> - **Empieza por `192.168.x.x`** ➡️ PRIVADA (Clase C). La típica IP de mi casa o de redes Wi-Fi pequeñas (SOHO).
> - **Empieza por `127.x.x.x`** ➡️ LOOPBACK (Localhost). Soy yo mismo hablando conmigo mismo. Si hago ping a 127.0.0.1 y falla, mi tarjeta de red física o sus drivers están muertos.
> - **Empieza por `169.254.x.x`** ➡️ APIPA. Significa ¡ERROR DE DHCP! Mi PC no encontró a quién le diera una IP, así que se asignó esta de emergencia. No puedo navegar.
> 
> **¿Y las Públicas?** ➡️ Si la IP *NO* cae en ninguna de las reglas anteriores (por ejemplo, `8.8.8.8` o `200.15.4.1`), entonces es PÚBLICA y navega directamente en internet sin NAT.

### Tabla de Subnetting: Los únicos números válidos para la Máscara (Último Octeto)

| Máscara (Decimal) | CIDR | Bits Cero | Fórmula | Hosts Útiles | Uso Típico |
| :--- | :--- | :--- | :--- | :--- | :--- |
| 255.255.255.**128** | /25 | 7 | (2^7) - 2 | **126** | Partir la red plana a la mitad exacta. |
| 255.255.255.**192** | /26 | 6 | (2^6) - 2 | **62** | Redes medianas. |
| 255.255.255.**224** | /27 | 5 | (2^5) - 2 | **30** | Departamentos u oficinas pequeñas. |
| 255.255.255.**240** | /28 | 4 | (2^4) - 2 | **14** | Enlaces restringidos de alta seguridad. |
| 255.255.255.**248** | /29 | 3 | (2^3) - 2 | **6** | Redes mínimas para servidores. |
| 255.255.255.**252** | /30 | 2 | (2^2) - 2 | **2** | Enlace estricto Punto a Punto (Router a Router). |


# Segmentación de la red
ARP - Un router puede propagar el paquete a otras ip para identificar si alguna responde dentro de la red. 

## Dominios de difusión y segmentación. 
En una LAN ethernet los dispositivos utilizan difusión y el protocolo de resolución de direcciones (Address Resolution Protocol - ARP) para localizar otros dispositivos en la red. ARP envía transmisiones de capa 2 a una dirección IPv4 conocida en la red local para descubrir la dirección MAC asociada. Los dispositivos de LAN Ethernet también localizan otros dispositivos. 

Por lo general, un host adquiere la dirección IPv4  utilizando el protocolo de configuración dinámica DHCP qué envía trasmisiones a la red local para localizar un servidor DHCP. 

Los Switches propagan las difusiones por toda la red, excepto por aquella dónde recibieron la difusión. 

Los **Routers** no propagan difusiones. Cuando un router recibe una difusión no la propaga a otras interfaces. 
Por lo tanto, cada interfaz de router se conecta  a un dominio de transmisión y las trasmisiones solo se propagan dentro de ese dominio de trasmisión específico. 

## Problemas con los dominios de difusión grandes
### Un dominio de difusión amplio 
Un dominio de difusión grande conecta muchísimos hosts. Y esto puede generar problemas, debido a qué si tiene muchos host conectados, cada host debe procesar la información y esto genera una red lenta. Un dispositivo debe aceptar y procesar cada paquete de la difusión. 

## Comunicación entre redes
La solución para reducir el tamaño de la red para crear dominios de difusión más pequeños, se denomina subredes. Estos espacios de redes más pequeños se demonina subredes. 

Ejemplo, dividir la red 172.16.0.0/16 en dos redes máscara 24. 172.16.0.0/24 y 172.16.1.0/24. 

Cómo podemos ver en el ejemplo anterior, la longitud del prefijo ha cambiado de una sola red /16 a dos redes con máscara /24. Esta es la base de la división en subredes. El uso de bits de host para crear subredes adicionales. 

**Nota** Los términos de subred y red suelen usar indistintamente. La mayoría de las redes son una subred de otra red más grande. 

## Razones para la segmentación de redes

La división en subredes disminuye el tráfico de la red general y mejora el rendimiento de la red. Y permite al administrador implementar políticas de seguridad para proteger la red, o liminar las difusiones por configuraciones mal realizadas o mal intencionadas. Separando departamentos o lotes de red. 

Se puede realizar separación o división por pisos, por ubicación. por ejemplo 
- LAN 1 (10.0.1.0/24) Primer piso. 
- LAN 2 (10.0.2.0/24) Segundo Piso. 

Se pueden crear por grupo o difusión, y separar de las interfaces que salen del router GO/0. puerto GigabitEthernet 1. 

y por tipo de dispositivo, separar las impresoras, los servidores y las computadoras normales. 



