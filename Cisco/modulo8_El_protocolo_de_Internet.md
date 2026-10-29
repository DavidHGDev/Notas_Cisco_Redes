# EL PROTOCOLO DE INTERNET

**Objetivo del módulo** Explicas las características de la dirección IP.

| **Título del Tema** | **Objetivo del Tema** |
| :--- | :--- |
| Própositivo de Una dirección IPv4 | Explicar el próposito de una dirección IPv4 |
| Estructura de la dirección IPv4 | Explicar y entender como las direcciones IPv3 y las subredes funcionan juntas | 

## Próposito de una dirección IPv4
Un host necesita una dirección IPv4 para participar en internet y prácticamente toda LAN tiene una dirección IPv4. Bien sea para comunicación local o para comunicación global. Debe estar bien configurada con una dirección única, si es global para faciliar la comunicación remota. 

### Octetos y notación decimal con puntos

La dirección IPv4 tiene 32 bits. Ejemplo: 11010001101001011100100000000001. Lo cual resulta muy difícil de leer. 

Por esta razón, se agrupan en conjunto de 4 bytes, y cada uno tiene 8 bits, por ello se llaman octetos.  **11010001.10100101.11001000.00000001** 

Entonces, lo que se hace es convertir estos binarios a decimal separado por puntos, y la representación sería **209.165.200.1**

## La Estructura de la Dirección IPv4
La dirección IPv4, tiene un identificador para el segmento de red, y otro para el host. 

las 3 primeras partes son para la red, y la última para el host. 

La **Mascara de subred** se utiliza para identificar la red a la que está conectado el host. 

Se comoce como direccionamiento jerarquico, por ejemplo, Los 3 primeros octetos corresponden al segmento de red, y el último octeto al host. 

La porción de red indica la red en la que cada dirección de host única está ubicada. Los enrutadores solo necesitan saber como llegar a cada red, en vez de saber la dirección única de cada host. 

Con el direccionamiento IPv4 pueden existir varias redes lógicas en una red física, si la porción de red de las direcciones del host correspondiente a la red es diferente. Por ejemplo, tres host en una única red local física tienen la misma porción de red en su IPv4 (192.168.18) y otros 3 tienen porciones de red diferentes IPv4 (192.168.5). Los host que tiene la misma porción de red pueden comunicarse entre sí, sin utilizar el **routing**. 

y esto va determinado por la máscara de red. Si por ejemplo tenemos 255.255.0.0 la porción de red cae sobre el segundo octeto y la porción del host, tercero y cuardo octeto. 

## 📍 Direccionamiento: Lógico vs Físico (Capas OSI)

En las redes, los equipos utilizan dos tipos de identidades para comunicarse, cada una operando en una capa distinta del modelo OSI:

- **Dirección Física (MAC):** Opera en la **Capa 2 (Enlace de Datos)**. 
  - Es inmutable y viene grabada en el hardware de la tarjeta de interfaz de red (NIC).
  - Gobierna la entrega de las tramas (frames) de nodo a nodo dentro de una misma red local (LAN).
  
- **Dirección Lógica (IP):** Opera en la **Capa 3 (Red)**.
  - Es jerárquica y administrada por software (asignada manualmente o vía DHCP). 
  - Cambia dependiendo de la red lógica a la que el equipo se conecte.
  - Gobierna la entrega de paquetes de extremo a extremo, permitiendo que el router determine la mejor ruta para salir hacia redes externas o Internet.

> **Adaptación (Analogía táctica):** 
> La MAC es como mi número de cédula: nunca cambia, garantiza mi identidad física y la uso para moverme internamente. La IP es como la nomenclatura de mi casa en El Poblado: es un esquema lógico, agrupa a los equipos por zonas y cambia si me mudo a otra red. El switch trabaja leyendo cédulas en la red local (Capa 2); el router lee las direcciones de las calles para enviar paquetes lejos (Capa 3).