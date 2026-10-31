# Direccionamiento dinámico con DHCP
El objetivo es aprender a configurar un servidor HDCP. 

| Título del Tema | Objetivo del Tema |
|:---   |:---|
|Direccionamiento Estático y Dinámico | Comparar el direccionamiento IPv4 estático y dinámico. | 
| Configuración de DHCPv4 | Configure un servidor HDCPv4 para asinar dinámicamente las direcciones IPv4|

Si hacemos una configuración estática, cómo mínimo debo configuar lo siguiente. 

- **Dirección IP** - identifica al host en la red. 
- **Máscara de subred** - Se utiliza para identificar la red ala que está conectado el host. 
- **Puerta de enlace predeterminada** - Identifica el dispostivo de red que utiliza el host para acceder a Internet o a otra red remota. 

Las direcciones ip estáticas tiene algunas ventas. Son útiles para impresoras, servidores o otros dispositivos de red que deben estar accesibles para los clientes de red. 

La asignación estática de la información de direccionamiento puede proporcionar un mayor control de los recursos de red, pero introducir la información manual puede ser lento e incluso llevar a errores. 


### Asignación Dinámica de Direcciones IPv4

La configuración dinámica se logra mediante el protocolo de configuración dinámica de Host (HDCP). 

HDCP asigna automáticamente información de direccionamiento, como la dirección IPv4, la máscara de subred, puerta de enlace predeterminada y otra información de configuración. 

Esto es preferido para las grandes redes, y pequeñas, elimina la carga del administrador de red y también los errores. 

Las direcciones se arrendan a un dispositivo durante un periodo, luego regresa al pool para estar disponibles de nuevo, esto es útil, no se depende de una dirección fija. 

### Servidores HDCP
Varios tipos de dispositivos pueden actuar como servidores HDCP, siempre y cuando ejecuten software de servicios HDCP. En la mayoría de las redes grandes o medianas, el servidor HDCP es generalemtne un servidor local dedicado, basado en una PC. 

En caso de las redes domésticas, el servidor HDCP puede estar  ubicado en el ISP y un host de la red doméstica recibe su configuración IPv4 directamente del ISP. 

# Configuración HDCPv4
Básicamente un dispositivo en la red envía un paquete de descubrimiento HDCP. Para que cualquier servidor que esté escuchando y configurado, le brinde  una ip Ipv4. 
Puede ser también un servidor Web, un servidor Linux configurado para la Web. 

- Entonces, el dispositivo hace una difusión solicitando una IP. 
- Responde el servidor con una IP 192.168.1.15 y con la puerta de enlace predeterminada. 
- El cliente acepta la respuesta. 
- El router envía el reconocimiento que fue registrada la MAC en la tabla de direcciones. 

- ### HDCPDISCOVER el cliente envía el descubrimiento

- ### HDCPOFFER (oferta) cuando el servidor hace oferta. 

- ### HDCPREQUEST El cliente recibe y envía un mensaje indicando que aceptó la oferta. 

- ### DHCPACK REconocimiento. el servidor envía un mensaje final indicando que reconoció. 

