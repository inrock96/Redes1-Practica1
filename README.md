
### Redes de Computadoras 1
### Practica 1 
### Inti Andrés Samayoa
### 201504002
# Manual de configuración

## Topología
En la siguiente topología se muestran 4 hosts que está conectada con 2 switches distintos y estos se conectan entre si con un router que será el centro principal de la comunicación.

A continuación se muestra una tabla con los hosts y los ip configurados:
| Host | Conectado a  | Dirección IP |
| ----------- | ----------- |----------- | 
| linux-1 | Switch1 | 192.168.12.30 |
| PC2 | Switch1 | 192.168.12.15 |
| PC3 | Switch2 | 192.168.10.15 |
| PC4 | Switch2 | 192.168.10.30 |

Las interfaces del router poseen las siguientes ips:
| Interfaz | Dirección de Red  | Dirección IP |
| ----------- | ----------- |----------- | 
| interfaz f0/0 | 192.168.12.0/24 | 192.168.12.254 |
| interfaz f0/1 | 192.168.10.0/24 | 192.168.10.254 |
![fa0config](/images/topologia.jpg)
## Configuración
### Configuración de router

A continuación se muestra la configuración para la interfaz f0/0 del router R1.  
1. Se utilizó el comando **duplex** para especificar que será full duplex
2. el comando **ip address** para asignar la dirección ip y el gateway (192.168.12.0/24)
3. Comando no shutdown para levantar la interfaz

![fa0config](/images/fe00.jpg)
Ahora se muestra la configuración para la interfaz f0/1 del router R1.  
1. Se utilizó el comando **duplex** para especificar que será full duplex
2. el comando **ip address** para asignar la dirección ip y el gateway (192.168.10.0/24)
3. Comando no shutdown para levantar la interfaz
![fa0config](/images/fe01.jpg)
### Configuración de máquina virtual (tinycore linux)
Para la configuración de ip de la máquina virtual
1. Se va al panel de control
2. Clic en network
3. Configurar la dirección ip con el asistente
![fa0config](/images/linux_config.jpg)
### Configuración de VPCS
Para la configuración de las VPCS desde el terminal de putty:
1. Utilizar comando **ip**
2. Ingresar dirección ip
3. Ingresar máscara subred
4. ingresar gateway
![fa0config](/images/pc2_config.jpg)
![fa0config](/images/pc3_config.jpg)
![fa0config](/images/pc4_config.jpg)
## Glosario
| Término | Descripción |
| ----------|------------ |
| VPCS | Es un ordenador virtual que funciona como el punto de inicio y final de las transferencias de datos. |
| VLAN | Una VLAN es un acrónimo de virtual LAN o red de area local virtual. Es un método para crear redes lógicas independientes que se encuentran dentro de una misma red física. |
| Topología | Es el mapa físico o lógico de una red para intercambiar datos |
| Máquina virtual | Es un software que simula un sistema de computación y puede ejecutar programas como si fuese una computadora real. |
| Dirección ip | Es un conjunto de números que identifica, de manera lógica y jerárquica, a una Interfaz en la red de un dispositivo (computadora, laptop, teléfono inteligente) que utilice el protocolo o, que corresponde al nivel de red del modelo TCP/IP. |
| FastEthernet | Es el nombre de una serie de estándares de IEEE de redes Ethernet de 100 Mbps |
| Ethernet | Es un estándar de redes de área local para computadores |
| Router | Es un dispositivo que permite interconectar computadoras que funcionan en el marco de una red. |
| Switch | Es el dispositivo digital lógico de interconexión de equipos que opera en la capa de enlace de datos del modelo OSI. |
| Máscara de red | Es una combinación de bits que sirve para delimitar el ámbito de una red de ordenadores.​ Su función es indicar a los dispositivos qué parte de la dirección IP es el número de la red, incluyendo la subred, y qué parte es la correspondiente al host. |
| Gateway | Es el dispositivo que actúa de interfaz de conexión entre aparatos o dispositivos, y también posibilita compartir recursos entre dos o más ordenadores.|
