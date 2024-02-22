# Introducción al módulo 2
En este módulo, aprenderá a hacer lo siguiente:

-    Identificar los distintos tipos de instancias de Amazon EC2.
-    Diferenciar entre las distintas opciones de facturación de Amazon EC2.
-    Resumir los beneficios de Amazon EC2 Auto Scaling.
-    Resumir los beneficios de Elastic Load Balancing.
-    Dar un ejemplo de los usos de Elastic Load Balancing.
-    Resumir las diferencias entre Amazon Simple Notification Service (Amazon SNS) y Amazon Simple Queue Service (Amazon SQS).
-    Resumir las opciones de cómputo adicionales de AWS.

ELB = Elastic Load Balancing 
SQS =  Amazon simple Queue Service
SNS = Amazon Simple Notification Service

	Tenencia multiple: Uso compartido del hardware subyacente entre maquinas virtuales
	Equilibrado de carga = Balanceo de carga
	Arquitectura Desacoplada
	Arquitectura estrechamente acoplada= Si 1 componente falla o cambia, todo el proceso se vera afectado
    Arquitectura de acoplamiento debil = Si un componente falla no provocara una caida en cascada

Ofrece flexibilidad y control 
![cdb6b081c1e1a63f9726d3b74ef157b0.png](/images/cdb6b081c1e1a63f9726d3b74ef157b0.png)

Proveer mas memoria y CPU



- Esperar a que le entreguen los servidores.
- Instalar los servidores en su centro de datos físico.
- Realizar todas las configuraciones necesarias.

- Puede aprovisionar y lanzar una instancia de Amazon EC2 en cuestión de minutos.
- Puede dejar de usarla cuando haya terminado de ejecutar una carga de trabajo.
- Solo paga por el tiempo de cómputo que utiliza cuando una instancia se está ejecutando, no cuando está detenida o finalizada.
- Puede ahorrar costos si solo paga por la capacidad del servidor que necesite o desee.

![3ad1cc709d297b31605f9b7afc376809.png](/images/3ad1cc709d297b31605f9b7afc376809.png)
![9fa76a0f77f545a8461f4146e431ae2b.png](/images/9fa76a0f77f545a8461f4146e431ae2b.png)
![5c90e30cb170493de3a2629fcae9f793.png](/images/5c90e30cb170493de3a2629fcae9f793.png)


Ofrecen flexibilidad a la hora de desplegar una solucion 
[Los tipos de instancias de Amazon EC2](https://aws.amazon.com/ec2/instance-types/) están optimizados para distintas tareas. Al seleccionar un tipo de instancia, tenga en cuenta las necesidades específicas de sus cargas de trabajo y aplicaciones. Es posible que incluya requisitos para las capacidades de cómputo, memoria o almacenamiento.

Las instancias de propósito general brindan un equilibrio entre recursos de cómputo, de memoria y de redes. Puede utilizarlos para diversas cargas de trabajo, tales como:
- servidores de aplicaciones
- servidores de juegos
- servidores backend para aplicaciones empresariales
- bases de datos pequeñas y medianas
Imagine que tiene una aplicación en la que las necesidades de recursos de cómputo, memoria y redes son aproximadamente equivalentes. Puede considerar ejecutarla en una instancia de uso general porque la aplicación no requiere optimización en ninguna área de recursos única.

Las instancias de cómputo optimizado son ideales para aplicaciones vinculadas a cómputo que se benefician de los procesadores de alto rendimiento. Al igual que las instancias de propósito general, puede usar instancias de cómputo optimizado para cargas de trabajo como servidores web, de aplicaciones y de juegos.
Sin embargo, la diferencia es que las aplicaciones de cómputo optimizado son ideales para servidores web de alto rendimiento, servidores de aplicaciones con uso intensivo de cómputo y servidores de juegos dedicados. También puede usar instancias optimizadas para informática para cargas de trabajo de procesamiento por lotes que requieren procesar muchas transacciones en un solo grupo.

Las instancias optimizadas de memoria están diseñadas para ofrecer un rendimiento rápido para las cargas de trabajo que procesan grandes conjuntos de datos en la memoria. En cómputo, la memoria es un área de almacenamiento temporal. Contiene todos los datos e instrucciones que necesita una unidad central de procesamiento (CPU) para poder completar acciones. Antes de que se pueda ejecutar un programa o una aplicación de computadora, se carga desde el almacenamiento en la memoria. Este proceso de carga previa le proporciona a la CPU acceso directo al programa de computadora.
Imagine que tiene una carga de trabajo que requiere que se carguen previamente grandes cantidades de datos antes de ejecutar una aplicación. Este escenario puede ser una base de datos de alto rendimiento o una carga de trabajo que implique procesar en tiempo real una gran cantidad de datos no estructurados. En este tipo de casos de uso, considere usar una instancia optimizada para memoria. Las instancias optimizadas para memoria le permiten ejecutar cargas de trabajo con altas necesidades de memoria y obtener un excelente rendimiento.

Las instancias de cómputo acelerado utilizan aceleradores de hardware, o coprocesadores, para realizar algunas funciones de manera más eficiente de lo que es posible en el software que se ejecuta en las CPU. Ejemplos de estas funciones incluyen cálculos numéricos de punto flotante, procesamiento de grafos y coincidencia de patrones de datos.
En cómputo, un acelerador de hardware es un componente que puede acelerar el procesamiento de datos. Las instancias de cómputo acelerado son ideales para cargas de trabajo como aplicaciones gráficas, streaming de juegos y streaming de aplicaciones.

Las instancias optimizadas de almacenamiento están diseñadas para las cargas de trabajo que necesitan realizar con gran frecuencia accesos secuenciales de lectura y escritura a conjuntos de datos grandes en el almacenamiento local. Algunos ejemplos de cargas de trabajo adecuadas para instancias optimizadas de almacenamiento incluyen sistemas de archivos distribuidos, aplicaciones de almacén de datos y sistemas de procesamiento de transacciones en línea (OLTP) de alta frecuencia.
En cómputo, el término operaciones de entrada/salida por segundo (IOPS) es una métrica que mide el rendimiento de un dispositivo de almacenamiento. Indica cuántas operaciones de entrada o salida diferentes puede realizar un dispositivo en un segundo. Las instancias optimizadas para almacenamiento están diseñadas para ofrecer decenas de miles de IOPS aleatorias y de baja latencia a las aplicaciones. 
Puede considerar las operaciones de entrada como datos introducidos en un sistema, como registros ingresados en una base de datos. Una operación de salida son datos generados por un servidor. Un ejemplo de salida podría ser el análisis realizado en los registros de una base de datos. Si tiene una aplicación que requiere un alto nivel de IOPS, una instancia optimizada para almacenamiento puede proporcionar un mejor rendimiento en comparación con otros tipos de instancias no optimizadas para este tipo de casos de uso.

Con Amazon EC2, solo paga por el tiempo de cómputo que utiliza. Amazon EC2 ofrece diversas opciones de precios para distintos casos de uso. Por ejemplo, si su caso práctico puede soportar interrupciones, puede ahorrar con las instancias de spot. También puede ahorrar si se compromete de forma anticipada y reserva un nivel mínimo de uso con las instancias reservadas.

Las instancias bajo demanda son ideales para cargas de trabajo irregulares a corto plazo que no se pueden interrumpir. No se aplican costos iniciales ni contratos mínimos. Las instancias se ejecutan de forma continua hasta que las detiene y solo paga por el tiempo de cómputo que utiliza.
Los casos prácticos de muestra de instancias bajo demanda incluyen el desarrollo y la prueba de aplicaciones y la ejecución de aplicaciones que tienen patrones de uso impredecibles. Las instancias bajo demanda no se recomiendan para cargas de trabajo que duran un año o más porque dichas cargas pueden experimentar un mayor ahorro de costos mediante instancias reservadas.

Las instancias reservadas son un descuento de facturación que se aplica al uso de instancias bajo demanda en su cuenta. Hay dos tipos de instancias reservadas disponibles:

-   las instancias reservadas convertibles



- descripción de la plataforma (sistema operativo): por ejemplo, Windows Server de Microsoft o Red Hat Enterprise Linux
- tenencia: tenencia predeterminada o tenencia dedicada

Instancia reservada convertible: si debe ejecutar las instancias de EC2 en una zona de disponibilidad diferente o tipos de instancias diferentes, es posible que las instancias reservadas convertibles sean las indicadas para usted. Nota: Consigue un mejor descuento cuando necesita flexibilidad para ejecutar las instancias de EC2.


-   Adquiera una nueva instancia reservada que coincida con los atributos de la instancia (familia y tamaño, región, plataforma y tenencia de la instancia).

AWS ofrece Savings Plans para algunos servicios de cómputo, incluido Amazon EC2. Los Savings Plans de las instancias de EC2 reducen los costos de las instancias de EC2 cuando se compromete a realizar gastos por hora a una familia de instancias y a una región por un periodo de 1 año o de 3 años. Este compromiso del periodo genera ahorros de hasta el 72 % comparado a las tarifas bajo demanda. Cualquier uso hasta el compromiso se cobra según la tarifa de Savings Plans con descuento (por ejemplo, 10 USD por hora). Cualquier uso más allá del compromiso se cobra en base a las tarifas bajo demanda regulares.
Los Savings Plans de las instancias de EC2 son una buena opción si necesita flexibilidad en su uso de Amazon EC2 sobre la duración del periodo de compromiso. Tiene el beneficio de ahorrar en la ejecución de cualquier instancia de EC2 dentro de una familia de instancias de EC2 en una región elegida (por ejemplo, el uso de M5 en Virgina del Norte) sin importar la zona de disponibilidad, el tamaño, el sistema operativo o la tenencia de la instancia. Los ahorros con los Savings Plans de las instancias de EC2 son similares a los ahorros suministrados por las instancias reservadas Standard.
Sin embargo, al contrario de las instancias reservadas, no debe especificar de antemano el tipo y el tamaño de la instancia de EC2 (por ejemplo m5.xlarge), el sistema operativo ni la tenencia para obtener un descuento. Además, no debe comprometerse a un número determinado de instancias de EC2 durante un periodo de 1 año o de 3 años. Asimismo, los Savings Plans de las instancias de EC2 no incluyen una opción de reserva de capacidad de EC2.
Más adelante en este curso, analizará el explorador de costos de AWS, que puede utilizar para visualizar, entender y administrar los costos y el uso de AWS a través del tiempo. Si está considerando las opciones de Savings Plans, puede utilizar el explorador de costos de AWS para analizar el uso de Amazon EC2 durante los últimos 7, 30 o 60 días. El explorador de costos de AWS también proporciona recomendaciones personalizadas para los Savings Plans. Estas recomendaciones calculan cuánto podría ahorrar en los costos mensuales de Amazon EC2, en función del uso anterior de Amazon EC2 y del importe del compromiso por hora de un Savings Plan de 1 o 3 años.

Las instancias de spot son ideales para las cargas de trabajo con tiempos de inicio y finalización flexibles, o que pueden resistir interrupciones. Las instancias de spot utilizan capacidad de cómputo de Amazon EC2 no utilizada y ofrecen ahorros con un descuento de hasta el 90 % de los precios bajo demanda.
Imagine que tiene un trabajo de procesamiento en segundo plano que puede iniciarse y detenerse según sea necesario (como el trabajo de procesamiento de datos de una encuesta de clientes). La intención es iniciar y detener el trabajo de procesamiento sin afectar a las operaciones generales de su empresa. Si realiza una solicitud de spot y la capacidad de Amazon EC2 está disponible, se lanza la instancia tipo spot. Sin embargo, si realiza una solicitud de spot y la capacidad de Amazon EC2 no está disponible, la solicitud no se realizará correctamente hasta que la capacidad esté disponible. La capacidad no disponible puede retrasar el inicio del trabajo de procesamiento en segundo plano.
Después de lanzar una instancia de spot, si la capacidad ya no está disponible o aumenta la demanda de instancias de spot, es posible que la instancia se interrumpa. Es posible que esto no suponga ningún problema para el trabajo de procesamiento en segundo plano. Sin embargo, en el ejemplo anterior de desarrollo y prueba de aplicaciones, lo más probable es que desee evitar interrupciones inesperadas. Por lo tanto, elija un tipo de instancia de EC2 diferente que sea ideal para esas tareas.

Los servidores dedicados son servidores físicos con capacidad de instancias de Amazon EC2 totalmente dedicados a su uso. 
Puede utilizar las licencias de software por zócalo, por núcleo o por máquina virtual (VM) existentes para ayudar a mantener el cumplimiento de las licencias. Puede comprar reservas de hosts dedicados y hosts dedicados bajo demanda. De todas las opciones de Amazon EC2 cubiertas, los hosts dedicados son los de mayor costo.

- Escalabilidad 
- Eslasticidad
Definen como las instancias pueden crecer y decrecer dinamicamente
![0c614f0beb716687fb17b0af4d090f63.png](/images/0c614f0beb716687fb17b0af4d090f63.png)

![4f6f2f50a4759095f3737b72160cf847.png](/images/4f6f2f50a4759095f3737b72160cf847.png)
![a6994354d31eaf47c00f67e6eccd1ccd.png](/images/a6994354d31eaf47c00f67e6eccd1ccd.png)
# Escalabilidad

Si quisiera que el proceso de escalado se realizara automáticamente, ¿qué servicio de AWS utilizaría? El servicio de AWS que proporciona esta funcionalidad para las instancias de Amazon EC2 es Amazon EC2 Auto Scaling.

Si ha intentado acceder a un sitio web que no se cargaba y que con frecuencia se agotaba el tiempo de espera, es posible que el sitio haya recibido más solicitudes de las que pudo gestionar. Esta situación es similar a esperar en una larga fila en una cafetería, cuando solo hay un barista presente para recibir pedidos de los clientes.
![be54ea3ad191bf11673010f893b2d76c.png](/images/be54ea3ad191bf11673010f893b2d76c.png)
Amazon EC2 Auto Scaling le permite añadir o eliminar automáticamente instancias de Amazon EC2 en respuesta a la demanda cambiante de las aplicaciones. Al escalar y reducir horizontalmente de forma automática sus instancias según sea necesario, podrá mantener una mayor sensación de disponibilidad de las aplicaciones.
En Amazon EC2 Auto Scaling, puede utilizar dos enfoques: escalado dinámico y escalado predictivo.
- El escalado dinámico responde a la demanda cambiante. 
- El escalado predictivo programa automáticamente el número correcto de instancias de Amazon EC2 en función de la demanda prevista.
Ejemplo: Amazon EC2 Auto Scaling



En la nube, la potencia de cómputo es un recurso programático, por lo que puede adoptar un enfoque más flexible en el tema del escalado. Al añadir Amazon EC2 Auto Scaling a una aplicación, puede añadir nuevas instancias a la aplicación cuando sea necesario y cancelarlas cuando ya no las necesite.
Imagine que se está preparando para iniciar una aplicación en instancias de Amazon EC2. Al configurar el tamaño del grupo de Auto Scaling, puede establecer el número mínimo de instancias de Amazon EC2 en una. Esto significa que, en todo momento, debe haber al menos una instancia de Amazon EC2 funcionando.
![f7aa2dd3f208de67df260ad9faf6dafc.png](/images/f7aa2dd3f208de67df260ad9faf6dafc.png)
Al crear un grupo de Auto Scaling, puede establecer el número mínimo de instancias de Amazon EC2. La capacidad mínima es el número de instancias de Amazon EC2 que se lanzan inmediatamente después de crear el grupo de Auto Scaling. En este ejemplo, el grupo de Auto Scaling tiene una capacidad mínima de una instancia de Amazon EC2.
A continuación, puede establecer la capacidad deseada en dos instancias de Amazon EC2, aunque su aplicación necesite un mínimo de una sola instancia de Amazon EC2 para funcionar.
La tercera configuración que puede establecer en un grupo de Auto Scaling es la capacidad máxima. Por ejemplo, puede configurar el grupo de Auto Scaling para que escale horizontalmente en respuesta al aumento de la demanda, pero solo hasta un máximo de cuatro instancias de Amazon EC2.
Dado que Amazon EC2 Auto Scaling utiliza instancias de Amazon EC2, solo paga por las instancias que utiliza, cuando las utiliza. Ahora cuenta con una arquitectura rentable que proporciona la mejor experiencia al cliente y reduce los gastos.

## Elastic Load Balancing
Elastic Load Balancing es el servicio de AWS que distribuye automáticamente el tráfico de aplicaciones entrantes entre varios recursos, como las instancias de Amazon EC2. 
Un equilibrador de carga actúa como un único punto de contacto para todo el tráfico web que entra en el grupo de Auto Scaling. Esto significa que, al agregar o quitar instancias de Amazon EC2 en respuesta a la cantidad de tráfico entrante, estas solicitudes se dirigen primero al equilibrador de carga. A continuación, las solicitudes se distribuyen en varios recursos que se encargarán de gestionarlas. Por ejemplo, si tiene varias instancias de Amazon EC2, Elastic Load Balancing distribuye la carga de trabajo entre las distintas instancias para que ninguna instancia tenga que cargar la mayor parte. 
Aunque Elastic Load Balancing y Amazon EC2 Auto Scaling son servicios independientes, trabajan juntos para ayudar a garantizar que las aplicaciones que se ejecutan en Amazon EC2 puedan proporcionar alto rendimiento y disponibilidad. 

![186e135fac24c6da7aafed3b5fea31ae.png](/images/186e135fac24c6da7aafed3b5fea31ae.png)
Periodo de baja demanda
Este es un ejemplo de cómo funciona Elastic Load Balancing. Supongamos que algunos clientes han venido a la cafetería y están listos para ordenar. 
Si solo hay unas pocas cajas registradoras abiertas, esto coincide con la demanda de los clientes que necesitan servicio. Es menos probable que la cafetería tenga cajas registradoras abiertas sin clientes. En este ejemplo, puede considerar las cajas registradoras como instancias de Amazon EC2.


Este es un ejemplo de cómo funciona Elastic Load Balancing. Supongamos que algunos clientes han venido a la cafetería y están listos para ordenar. 
Si solo hay unas pocas cajas registradoras abiertas, esto coincide con la demanda de los clientes que necesitan servicio. Es menos probable que la cafetería tenga cajas registradoras abiertas sin clientes. En este ejemplo, puede considerar las cajas registradoras como instancias de Amazon EC2.

## Aplicaciones monolíticas y microservicios
Las aplicaciones se componen de varios componentes. Los componentes se comunican entre sí para transmitir datos, atender solicitudes y mantener la aplicación en funcionamiento. 
Imagine que tiene una aplicación con componentes acoplados estrechamente. Estos componentes pueden incluir bases de datos, servidores, la interfaz de usuario, lógica empresarial y otros. Este tipo de arquitectura se puede considerar una aplicación monolítica. 
En este enfoque de la arquitectura de aplicaciones, si ocurre un error en un solo componente, sucede lo mismo en otros componentes y quizás falle toda la aplicación.
![1f8ef6da18b07606e22c8c0762ea0dac.png](/images/1f8ef6da18b07606e22c8c0762ea0dac.png)
Para ayudar a mantener la disponibilidad de las aplicaciones cuando ocurre un error en un solo componente, puede diseñar la aplicación mediante un enfoque de microservicios.
![015320ec8a51794925114d7f0bd92109.png](/images/015320ec8a51794925114d7f0bd92109.png)
En un enfoque de microservicios, los componentes de las aplicaciones tienen un acoplamiento débil. En este caso, si un solo componente falla, los demás componentes siguen funcionando porque se comunican entre sí. El acoplamiento débil evita que toda la aplicación falle. 
Al diseñar aplicaciones en AWS, puede adoptar un enfoque de microservicios con servicios y componentes que cumplen distintas funciones. Dos servicios facilitan la integración de aplicaciones: Amazon Simple Notification Service (Amazon SNS) y Amazon Simple Queue Service (Amazon SQS).


En Amazon SNS, los suscriptores pueden ser servidores web, direcciones de correo electrónico, funciones de AWS Lambda u otras opciones. 
![8d7305738ad24d1a07efe682d2e1d096.png](/images/8d7305738ad24d1a07efe682d2e1d096.png)
![e43eca58a739ca1e04f0dae3335c1228.png](/images/e43eca58a739ca1e04f0dae3335c1228.png)

Amazon Simple Queue Service (Amazon SQS) es un servicio de cola de mensajes. 
Con Amazon SQS, puede enviar, almacenar y recibir mensajes entre componentes de software, sin perder mensajes ni requerir la disponibilidad de otros servicios. En Amazon SQS, una aplicación envía mensajes a una cola. Un usuario o servicio toma un mensaje de la cola, lo procesa y luego, lo elimina de la cola.
Para analizar dos ejemplos de cómo utilizar Amazon SQS, seleccione los botones de flechas para mostrar cada uno.

![987b34c270e0a3f1ee78319357ab7f15.png](/images/987b34c270e0a3f1ee78319357ab7f15.png)
# Cómputo sin servidor q
Anteriormente en este módulo, aprendió sobre Amazon EC2, un servicio que le permite ejecutar servidores virtuales en la nube. Si tiene aplicaciones que desea ejecutar en Amazon EC2, debe hacer lo siguiente:
- Aprovisionar instancias (servidores virtuales).
- Subir su código.
- Seguir administrando las instancias mientras se ejecuta la aplicación.

![2675196bb0492b18499c84bb2143870d.png](/images/2675196bb0492b18499c84bb2143870d.png)
El término “sin servidor” significa que el código se ejecuta en servidores, pero no es necesario aprovisionar ni administrar estos servidores. Con el cómputo sin servidor, puede concentrarse más en innovar nuevos productos y funciones en lugar de mantener los servidores.
Otro beneficio del cómputo sin servidor es la flexibilidad de escalar aplicaciones sin servidor automáticamente. El cómputo sin servidor puede ajustar la capacidad de las aplicaciones modificando las unidades de consumo, como el rendimiento y la memoria. 
Un servicio de AWS para cómputo sin servidor es AWS Lambda.

# AWS Lambda
[AWS Lambda](https://aws.amazon.com/lambda) es un servicio que permite ejecutar código sin tener que aprovisionar ni administrar servidores. 

Cuando utiliza AWS Lambda, solo paga por el tiempo de cómputo que consume. Los cargos se aplican solo cuando el código se está ejecutando. También puede ejecutar código para prácticamente cualquier tipo de aplicación o servicio backend, todo sin ninguna administración.

Por ejemplo, una función de Lambda sencilla podría implicar cambiar automáticamente el tamaño de las imágenes cargadas en la nube de AWS. En este caso, la función se activa cuando se carga una nueva imagen.

## Funcionamiento de AWS Lambda
![f84bbdf1086668ac9afec0f7e6c90c10.png](/images/f84bbdf1086668ac9afec0f7e6c90c10.png)
- Suba el código a Lambda. 
- Establezca el código para que se active desde una fuente de eventos, como servicios de AWS, aplicaciones móviles o puntos de enlace HTTP.
- Lambda ejecuta su código solo cuando se activa.
- Solo paga por el tiempo de cómputo que utiliza. En el ejemplo anterior de cambio de tamaño de imágenes, pagaría solo por el tiempo de cómputo que utiliza cuando se cargan nuevas imágenes. Al cargar las imágenes, Lambda ejecuta el código para la función de cambio de tamaño de imagen.

## En AWS, también puede crear y ejecutar aplicaciones en contenedores.
## Contenedores
Los contenedores le proporcionan un modo estándar de empaquetar el código y las dependencias de la aplicación en un único objeto. También puede utilizar contenedores para procesos y flujos de trabajo en los que existen requisitos esenciales de seguridad, fiabilidad y escalabilidad.
Para analizar un ejemplo sobre cómo funcionan los contenedores, seleccione los botones de flechas.
![d2632efceaeaad491b6c7def7f5cd473.png](/images/d2632efceaeaad491b6c7def7f5cd473.png)
![8433d566dc65426020564f8872833ea6.png](/images/8433d566dc65426020564f8872833ea6.png)

##  Amazon Elastic Container Service (Amazon ECS)
[Amazon Elastic Container Service (Amazon ECS)](https://aws.amazon.com/ecs/) es un sistema de administración de contenedores altamente escalable y de alto rendimiento que le permite ejecutar y escalar aplicaciones en contenedores en AWS. 
Amazon ECS admite los contenedores de Docker. Docker(opens in a new tab) es una plataforma de software que le permite crear, probar e implementar aplicaciones rápidamente. AWS es compatible con el uso de Docker Community Edition de código abierto y Docker Enterprise Edition de suscripción. Con Amazon ECS, puede utilizar las llamadas API para iniciar y detener aplicaciones habilitadas para Docker.

## Amazon Elastic Kubernetes Service (Amazon EKS)
[Amazon Elastic Kubernetes Service (Amazon EKS)](https://aws.amazon.com/eks/) es un servicio completamente administrado que puede utilizar para ejecutar Kubernetes en AWS. 
[Kubernetes](https://kubernetes.io/) es un software de código abierto que le permite implementar y administrar aplicaciones en contenedores a escala. Una gran comunidad de voluntarios mantiene Kubernetes y AWS colabora activamente con la comunidad de Kubernetes. A medida que se publiquen nuevas características y funcionalidades para las aplicaciones de Kubernetes, podrá aplicar fácilmente estas actualizaciones a sus aplicaciones administradas por Amazon EKS.


## AWS Fargate
[AWS Fargate](https://aws.amazon.com/fargate/) es un motor de cómputo sin servidor para contenedores. Funciona tanto con Amazon ECS como con Amazon EKS. 
Cuando utiliza AWS Fargate, no tiene que aprovisionar ni administrar servidores. AWS Fargate administra la infraestructura de servidores por usted. Puede centrarse más en innovar y desarrollar aplicaciones y pagar solo por los recursos necesarios para ejecutar sus contenedores.
