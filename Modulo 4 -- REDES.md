# Objetivos de aprendizaje
- En este módulo, aprenderá a hacer lo siguiente:
- Describir los conceptos básicos de las redes.
- Describir la diferencia entre los recursos de redes públicas y privadas. 
- Explicar una puerta de enlace privada virtual con una situación de la vida real. 
- Explicar una red privada virtual (VPN) mediante un escenario de la vida real.
- Describir los beneficios de AWS Direct Connect. 
- Describir los beneficios de las implementaciones híbridas. 
- Describir los niveles de seguridad que se utilizan en una estrategia de TI.
- Describir los servicios que utilizan los clientes para interactuar con la red global de AWS.
# Conceptos Claves
VCP se puede subnetear (publica y privada)
Subred --> fragmento de una red mas grande, en este caso la VPC

DirectConnect --> linea dedicada del centro de datos a AWS

# Acronimos 
VPC --> Amazon Virtual Private Cloud 


# Contenido
## Conectividad con AWS
## Amazon Virtual Private Cloud (Amazon VPC)
Imagine los millones de clientes que utilizan los servicios de AWS. Además, imagine los millones de recursos que han creado estos clientes, como las instancias de Amazon EC2. Sin límites en torno a todos estos recursos, el tráfico de red podría fluir entre ellos sin restricciones. 
Un servicio de red que puede utilizar para establecer límites en torno a sus recursos de AWS es [Amazon Virtual Private Cloud (Amazon VPC)](https://aws.amazon.com/vpc/)
Amazon VPC le permite aprovisionar una sección aislada de AWS Cloud. En esta sección aislada, puede lanzar recursos en una red virtual que defina. Dentro de una Virtual Private Cloud (VPC), puede organizar los recursos en subredes. Una subred es una sección de una VPC que puede contener recursos, como instancias de Amazon EC2.

## Puerta de enlace de internet
Trafico Publico
![99622a54785e1936b68604effe5ba2a8.png](/images/99622a54785e1936b68604effe5ba2a8.png)
Trafico Privado
![435e7d2ebb888188bc6abb42ea00164e.png](/images/435e7d2ebb888188bc6abb42ea00164e.png)

Para permitir que el tráfico público de internet acceda a su VPC, adjunte una puerta de enlace de internet a la VPC.
![844723933f0e8a644aaab21e4ab6cb13.png](/images/844723933f0e8a644aaab21e4ab6cb13.png)

Una puerta de enlace de Internet es una conexión entre una VPC e Internet. Puede considerar que una puerta de enlace de Internet es similar a una puerta que los clientes utilizan para entrar en la cafetería. Sin una puerta de enlace de Internet, nadie puede acceder a los recursos de la VPC.

## ¿Qué pasa si tiene una VPC que solo incluye recursos privados?
## Puerta de enlace privada virtual
Para acceder a los recursos privados en una VPC, puede utilizar una puerta de enlace privada virtual. 
A continuación, se muestra un ejemplo de cómo funciona una puerta de enlace privada virtual. Puede considerar a la Internet como el camino entre su hogar y la cafetería. Supongamos que viaja por esta carretera con un guardaespaldas para que le proteja. Sigue utilizando el mismo camino que otros clientes, pero con una capa extra de protección. 
El guardaespaldas es como una conexión de red privada virtual (VPN) que cifra (o protege) el tráfico de internet de todas las demás solicitudes a su alrededor. 
La puerta de enlace privada virtual es el componente que permite que el tráfico de internet protegido entre en la VPC. Aunque su conexión a la cafetería tiene protección adicional, es posible que se produzcan congestiones vehiculares porque está usando la misma carretera que otros clientes.
![1fcbd0c287e68187d906e2a4ee511486.png](/images/1fcbd0c287e68187d906e2a4ee511486.png)
Una puerta de enlace privada virtual le permite establecer una conexión de red privada virtual (VPN) entre la VPC y una red privada, como un centro de datos en las instalaciones o una red corporativa interna. Una puerta de enlace privada virtual permite el tráfico hacia la VPC solo si procede de una red aprobada.

###  AWS Direct Connect
![7cd9c6bb384d8817f1af13522c74768f.png](/images/7cd9c6bb384d8817f1af13522c74768f.png)

[AWS Direct Connect](https://aws.amazon.com/directconnect/) es un servicio que le permite establecer una conexión privada dedicada entre su centro de datos y una VPC.  
Imagine que hay un edificio de departamentos con un pasillo que conecta directamente el edificio a la cafetería. Solo los residentes del edificio de apartamentos pueden moverse por este pasillo. 
Este pasillo privado proporciona el mismo tipo de conexión dedicada que AWS Direct Connect. Los residentes pueden entrar en la cafetería sin necesidad de utilizar la vía pública compartida con otros clientes.
![12afdbd9a1913d15269ca0bfa8f22cda.png](/images/12afdbd9a1913d15269ca0bfa8f22cda.png)
La conexión privada que proporciona AWS Direct Connect le ayuda a reducir los costos de red y a aumentar la cantidad de ancho de banda que puede viajar a través de la red.

# Listas de control de acceso a redes y subredes
AWS tiene soluciones que incluyen:
- Proteccion de las redes
- Seguridad de aplicaciones
- Identidad de usuario
- Autenticacion y autorizacion
- Prevencion de denegacion de servicio distribuida (DDOS)
- Integridad de datos
- Cifrado

La VPC ofrece solo una proteccion perimetral

Proteccion de Red
![370fc3aadadea0acb65f5a951ea1cea9.png](/images/370fc3aadadea0acb65f5a951ea1cea9.png)
ASD
![4085f83bd98579b0a8da6f0fa5aa79fb.png](/images/4085f83bd98579b0a8da6f0fa5aa79fb.png)
Las ACL controlan tanto el trafico entrante como saliente.
Por lo que puede entrar pero no salir (si fuera el caso)
OJO esto aplica a la subred, no a las instancias 


Grupos de seguridad 
![6941d69dd005a19bddbfdca89b961822.png](/images/6941d69dd005a19bddbfdca89b961822.png)
Controlan que paquetes y en que puertos pueden alcanzar las instancias.


# ACL VS Grupos de seguridad
![5811526fc486a84f6a89111800153bc1.png](/images/5811526fc486a84f6a89111800153bc1.png)
Las ACLS no tienen memoria (sin estado) Siempre revisan la lista de entrada y/o salida 
Los groupos de seguridad si tienen estado, memoria (recuerdan que paquetes salieron y permiten el retorno de esas peticiones) 
Los grupos de seguridad permiten explicitamente todo el trafico saliente. Verifican quien entra pero no quien sale.


Para obtener más información sobre el rol de las subredes dentro de una VPC, consulte el siguiente ejemplo de la cafetería.
Primero, los clientes entregan sus pedidos al cajero. El cajero le pasa las órdenes al barista. Este proceso permite que la fila siga funcionando sin problemas a medida que llegan más clientes. 
Imagine que algunos clientes intentan saltarse la fila del cajero y solicitan los pedidos directamente al barista. Esto interrumpe el flujo de tráfico y hace que los clientes accedan a una parte de la cafetería con acceso restringido a ellos.
![eadc6e370851cc7871ab4403ee193aa9.png](/images/eadc6e370851cc7871ab4403ee193aa9.png)
Para solucionarlo, los propietarios de la cafetería dividen el área del mostrador y colocan al cajero y al barista en estaciones de trabajo separadas. La estación de trabajo del cajero está orientada al público y está diseñada para recibir clientes. La zona del barista es privada. El barista puede seguir recibiendo pedidos del cajero pero no directamente de los clientes.
![3f7407a141bd7ab89268a7015e15c7dd.png](/images/3f7407a141bd7ab89268a7015e15c7dd.png)
Esto es similar a cómo puede utilizar los servicios de red de AWS para aislar recursos y determinar exactamente cómo fluye el tráfico de red.
Puede considerar el área del mostrador de la cafetería como una VPC. El área del mostrador se divide en dos áreas separadas para el puesto de trabajo del cajero y el puesto de trabajo del barista. En una VPC, las subredes son áreas independientes que se utilizan para agrupar recursos.
## Subredes
Una subred es una sección de una VPC en la que se pueden agrupar recursos en función de las necesidades operativas o de seguridad. Las subredes pueden ser públicas o privadas.
![3420374c5b906de859f193268bc5b60b.png](/images/3420374c5b906de859f193268bc5b60b.png)
Las subredes públicas contienen recursos a los que el público debe tener acceso, como el sitio web de una tienda en línea.
Las subredes privadas contienen recursos a los que solo se debe tener acceso a través de la red privada, como una base de datos que contiene la información personal de los clientes y los historiales de pedidos. 
En una VPC, las subredes se pueden comunicar entre sí. Por ejemplo, podría tener una aplicación que incluya instancias de Amazon EC2 de una subred pública que se comuniquen con bases de datos ubicadas en una subred privada.

## Tráfico de red en una VPC
Cuando un cliente solicita datos de una aplicación alojada en la nube de AWS, la solicitud se envía como un paquete. Un paquete es una unidad de datos enviada a través de internet o de una red. 
Entra en una VPC a través de una puerta de enlace de internet. Antes de que un paquete pueda entrar o salir de una subred, comprueba los permisos. Estos permisos indican quién envió el paquete y cómo intenta comunicarse con los recursos de una subred.
El componente de VPC que comprueba los permisos de paquetes para las subredes es una [lista de control de acceso (ACL) a la red](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-network-acls.html)



## ACL de red
Una ACL de red es un firewall virtual que controla el tráfico entrante y saliente a nivel de la subred.
Por ejemplo, salga de la cafetería e imagine que está en un aeropuerto. En el aeropuerto, los pasajeros intentan entrar a otro país. Puede considerar a los viajeros como paquetes y al oficial de control de pasaportes como una ACL de red. El oficial de control de pasaportes comprueba las credenciales de los pasajeros cuando entran y salen del país. Si un pasajero está en una lista aprobada, puede pasar. Sin embargo, si no está en la lista aprobada o está en una lista de pasajeros excluidos, no puede pasar.
![0af03a56ab253cdeaa8b802196fe8b7a.png](/images/0af03a56ab253cdeaa8b802196fe8b7a.png)
Cada cuenta de AWS incluye una ACL de red predeterminada. Al configurar la VPC, puede usar la ACL de red predeterminada de su cuenta o crear ACL de red personalizadas. 
De forma predeterminada, la ACL de red predeterminada de su cuenta permite todo el tráfico entrante y saliente, pero usted puede modificarla y agregar sus propias reglas. En el caso de las ACL de red personalizadas, se deniega todo el tráfico entrante y saliente hasta que agregue reglas para especificar qué tráfico permitir. Además, todas las ACL de red tienen una regla de denegación explícita. Esta regla garantiza que si un paquete no coincide con ninguna de las demás reglas de la lista, el paquete se deniega.


## Filtrado de paquetes sin estado
Las ACL de red realizan el filtrado de paquetes sin estado. No recuerdan nada y comprueban los paquetes que cruzan el borde de la subred en cada sentido: entrante y saliente. 
Recuerde el ejemplo anterior de un viajero que quiere ingresar a un país diferente. Es similar a enviar una solicitud desde una instancia de Amazon EC2 a internet.
Cuando una respuesta de paquete para esa solicitud vuelve a la subred, la ACL de red no recuerda la solicitud anterior. La ACL de red comprueba la respuesta del paquete con la lista de reglas para determinar si se permite o se deniega.
![a912831bc2dd14131126b2e26b1004bd.png](/images/a912831bc2dd14131126b2e26b1004bd.png)


Una vez que un paquete entró en una subred, se deben evaluar sus permisos para los recursos de la subred, como las instancias de Amazon EC2. 
El componente de VPC que corrobora los permisos de los paquetes para una instancia de Amazon EC2 es un [grupo de seguridad](https://docs.aws.amazon.com/vpc/latest/userguide/VPC_SecurityGroups.html)


## Grupos de seguridad
Un grupo de seguridad es un firewall virtual que controla el tráfico entrante y saliente de una instancia de Amazon EC2.
![e1fc3814e55872cef8364d2f6861e59b.png](/images/e1fc3814e55872cef8364d2f6861e59b.png)
De forma predeterminada, un grupo de seguridad deniega todo el tráfico entrante y permite todo el tráfico saliente. Puede añadir reglas personalizadas para configurar qué tráfico debe permitirse; cualquier otro tipo de tráfico será denegado
Para este ejemplo, imagine que se encuentra en un edificio de departamentos con un portero que recibe a los huéspedes en el vestíbulo. Puede considerar a los invitados como paquetes y al portero como un grupo de seguridad. A medida que llegan los invitados, el portero revisa una lista para asegurarse de que pueden entrar en el edificio. Sin embargo, el portero no vuelve a comprobar la lista cuando los invitados salen del edificio
Si tiene varias instancias de Amazon EC2 en la misma VPC, puede asociarlas al mismo grupo de seguridad o utilizar grupos de seguridad distintos para cada instancia.



## Filtrado de paquetes con estado
Los grupos de seguridad realizan el filtrado de paquetes con estado. Recuerdan las decisiones anteriores que se tomaron para los paquetes entrantes.
Considere el mismo ejemplo de envío de una solicitud desde una instancia de Amazon EC2 a internet. 
Cuando una respuesta de paquete para esa solicitud vuelve a la instancia, el grupo de seguridad recuerda la solicitud anterior. El grupo de seguridad permite que la respuesta continúe, independientemente de las reglas del grupo de seguridad de entrada.
![93de587cec805da3df0bece6417e7180.png](/images/93de587cec805da3df0bece6417e7180.png)
Tanto con las ACL de red como con los grupos de seguridad, puede configurar reglas personalizadas para el tráfico de la VPC. A medida que siga aprendiendo más sobre la seguridad y las redes de AWS, asegúrese de comprender las diferencias entre las ACL de red y los grupos de seguridad.
![f0ff57a87a08e1498af640c7040ecf4c.png](/images/f0ff57a87a08e1498af640c7040ecf4c.png)
Recuerde los componentes de la VPC

Recuerde el objetivo de los siguientes cuatro componentes de la VPC. Compare su respuesta y elija todas las tarjetas de los componentes de la VPC.

Para recordar los componentes de la VPC, seleccione cada una de las siguientes tarjetas.
![71524b50be636cdcb35d3901412530ed.png](/images/71524b50be636cdcb35d3901412530ed.png)


![13ef475384100581ec27d94d7d9f70d0.png](/images/13ef475384100581ec27d94d7d9f70d0.png)
## Redes globales
### Sistema de nombres de dominio (DNS) Route53
Supongamos que AnyCompany tiene un sitio web alojado en la nube de AWS. Los clientes introducen la dirección web en su navegador y acceden al sitio web. Esto ocurre debido a la resolución del sistema de nombres de dominio (DNS). La resolución de DNS implica un solucionador de DNS del cliente que se comunica con un servidor DNS de la empresa.
Puede considerar el DNS como la guía telefónica de internet. La resolución de DNS es el proceso de traducir el nombre de dominio a una dirección IP.
### Politicas de enrutamiento
- Enrutamiento basado en latencia
- DNS de geolocalizacion 
- Enrutamiento de geoproximidad
- Weighted Round Robin
Amazon CloudFront (ubincacion perimetral)
Entrega contenido perimetral a los usuarios en funcion de su ubicacion geografica
![53859c96a378b53b4619f7ac59c4ec65.png](/images/53859c96a378b53b4619f7ac59c4ec65.png)


Por ejemplo, supongamos que quiere visitar el sitio web de AnyCompany. 
- Cuando ingresa el nombre del dominio en el navegador, esta solicitud se envía a un solucionador de DNS del cliente. 
- El solucionador de DNS del cliente pide al servidor de DNS de la empresa la dirección IP que corresponde al sitio web de AnyCompany.
- El servidor DNS de la empresa responde y proporciona la dirección IP del sitio web de AnyCompany: 192.0.2.0.



## Amazon Route 53
[Amazon Route 53](https://aws.amazon.com/route53) es un servicio web de DNS. Ofrece a los desarrolladores y a las empresas una forma fiable de dirigir a los usuarios finales a aplicaciones de Internet alojadas en AWS. 
Amazon Route 53 conecta las solicitudes de los usuarios a la infraestructura que funciona en AWS (como las instancias de Amazon EC2 y los equilibradores de carga). Puede dirigir a los usuarios a una infraestructura fuera de AWS.
Otra característica de Route 53 es la capacidad de administrar los registros de DNS de los nombres de dominio. Puede registrar nuevos nombres de dominio directamente en Route 53. También puede transferir registros de DNS de nombres de dominio existentes administrados por otros registradores de dominios. Esto le permite administrar todos los nombres de dominio en una única ubicación.
En el módulo anterior, aprendió sobre Amazon CloudFront, un servicio de entrega de contenido. En el siguiente ejemplo se describe cómo Route 53 y Amazon CloudFront trabajan conjuntamente para entregar contenido a los clientes.

## Ejemplo: cómo Amazon Route 53 y Amazon CloudFront entregan contenido.
![deb725c50c2b1e8a32ee1da940f75789.png](/images/deb725c50c2b1e8a32ee1da940f75789.png)


Supongamos que la aplicación de AnyCompany funciona en varias instancias de Amazon EC2. Estas instancias se encuentran en un grupo de Auto Scaling que se adjunta a un equilibrador de carga de aplicaciones. 
- Un cliente solicita datos de la aplicación si accede al sitio web de AnyCompany. 
- Amazon Route 53 utiliza la resolución de DNS para identificar la dirección IP correspondiente de AnyCompany.com, 192.0.2.0. Esta información se devuelve al cliente. 
- La solicitud del cliente se envía a la ubicación perimetral más cercana a través de Amazon CloudFront. 
- Amazon CloudFront se conecta al Application Load Balancer, que envía el paquete entrante a una instancia de Amazon EC2.
