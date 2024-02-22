# Objetivos de aprendizaje
En este módulo, aprenderá a hacer lo siguiente:

- Resumir los beneficios de la infraestructura global de AWS.
- Describir el concepto básico de las zonas de disponibilidad.
- Describir los beneficios de Amazon CloudFront y las ubicaciones perimetrales.
- Comparar los distintos métodos de aprovisionamiento de los servicios de AWS.

# Conceptos Claves
Automatizacion
Alta disponibilidad y tolerancia a fallos
Saturacion de rutas
Los datos de las regiones no sales de ellas, exepto con el permiso del propietario de los datos

# Acrónimos
Amazon CloudFront>> CDN Content Delivery Networks -->Redes de entrega de contenido
Ubicaciones de borde o perimetrales 
Amazon Route53 --> Servicio de DNS
AWS Outpost--> region operativa dentro del centro de datos del cliente
Zona de disponibilidad AZ 
API --> Application Program Interface 


# Contenido
## Regiones 
- Areas ailadas geograficas
- Las regiones se componen de zonas de disponibilidad 
- Ubicaciones de borde o perimetrales ejecutan AWS CloudFront


Para seleccionar una region se debe tomar en cuenta:
1. Cumplimiento --> leyes o requisitos locales al negocio
2. Proximidad--> estar cerca a los clientes
3. Disponibilidad de servicios --> Todos los servicios requiridos estan disponibles en esa region?
4. Precios --> puede que los precios varien entre regiones
### Cumplimiento con los requisitos legales y de gobernanza de datos
Dependiendo de su empresa y de la ubicación, es posible que tenga que ejecutar los datos desde áreas específicas. Por ejemplo, si la empresa requiere que todos los datos residan dentro de los límites del Reino Unido, elegiría la región de Londres. 
No todas las empresas tienen regulaciones de datos en función de la ubicación, por lo que es posible que deba centrarse más en los otros tres factores.
### Proximidad a sus clientes
Seleccionar una región cercana a sus clientes le ayudará a enviarles contenido más rápido. Por ejemplo, quizá su empresa tiene sede en Washington DC y muchos de sus clientes viven en Singapur. Puede considerar la posibilidad de ejecutar la infraestructura en la región de Virginia del Norte para estar cerca de la sede de la empresa y ejecutar las aplicaciones desde la región de Singapur.
### Servicios disponibles dentro de una region
A veces, es posible que la región más cercana no tenga todas las características que desea ofrecer a los clientes. AWS innova con frecuencia mediante la creación de nuevos servicios y la ampliación de las características de los servicios existentes. Sin embargo, para que los nuevos servicios estén disponibles en todo el mundo, a veces es necesario que AWS desarrolle hardware físico de una región a la vez. 
Imagine que sus desarrolladores quieren crear una aplicación que utiliza Amazon Braket (la plataforma de computación cuántica de AWS). A la fecha de creación de este curso, Amazon Braket aún no está disponible en todas las regiones de AWS del mundo, por lo que los desarrolladores tendrían que ejecutarlo en una de las regiones que ya lo ofrecen.
### Precios
Imagine que está considerando ejecutar aplicaciones tanto en Estados Unidos como en Brasil. Debido a la estructura tributaria de Brasil, podría costar un 50 % más ejecutar la misma carga de trabajo en la región de São Paulo en comparación con la región de Oregón. Aprenderá con más detalle que hay varios factores que determinan los precios, pero por ahora debe saber que el costo de los servicios puede variar de una región a otra.

## Ubicaciones Perimetrales 
Para clientes que no estan necesariamente cercanos a las regiones
Una ubicación perimetral es un sitio que Amazon CloudFront utiliza para almacenar copias almacenadas en caché del contenido más cerca de los clientes para una entrega más rápida.
Seleccione cada marcador enumerado para más información.
![3ea511e08121565975777973756fe18f.png](/images/3ea511e08121565975777973756fe18f.png)

![6d4594ef75233dd0fbe2b71052b3a0c3.png](/images/6d4594ef75233dd0fbe2b71052b3a0c3.png)
![beaab0949fdce15d824f02c49e87ab51.png](/images/beaab0949fdce15d824f02c49e87ab51.png)


## Cómo aprovisionar recursos de AWS
### Formas de interactuar con los servicios de AWS
- List itemConsola de navegador de AWS
- AWS Command  Interface CLI (basado en scripts)
- SDK de AWS (Kits de desarrollo).
![394d8c91b4d43b285c18911f61d9fae5.png](/images/394d8c91b4d43b285c18911f61d9fae5.png)


![0d991cec7b8ea7911122ffa87b28a745.png](/images/0d991cec7b8ea7911122ffa87b28a745.png)
![11085c6189b6380298526b5ea6eb6915.png](/images/11085c6189b6380298526b5ea6eb6915.png)

Herramientas Administradas para aprovisionamiento
## AWS Elastic Beanstalk

Con AWS Elastic Beanstalk, usted suministra opciones de código y configuración, y Elastic Beanstalk implementa los recursos necesarios para realizar las siguientes tareas:
- Ajuste de capacidad
- Balanceo de carga
- Escalado automático
- Supervisión del estado de las aplicaciones

## AWS CloudFormation
Con AWS CloudFormation, puede tratar su infraestructura como código. Esto significa que puede crear un entorno y escribir líneas de código en lugar de utilizar la consola de administración de AWS para aprovisionar recursos individualmente.
AWS CloudFormation proporciona recursos de forma segura y repetible, lo que le permite crear con frecuencia la infraestructura y aplicaciones sin tener que realizar acciones manuales. Determina las operaciones correctas que se deben realizar al momento de administrar la pila y revierte los cambios automáticamente si detecta errores.
Una plantilla de CloudFormation utiliza .yml o .json
Soporta entre otros servicios:
- Almacenamiento
- Analitica
- Bases de datos
- Machine Learning
Permite desplegar o utilizart la misma plantilla en diferentes regiones o incluso cuentas
