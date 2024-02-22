# Objetivos de aprendizaje
En este módulo, aprenderá a hacer lo siguiente:
- Resumir el concepto básico de almacenamiento y bases de datos.
- Describir los beneficios de Amazon Elastic Block Store (Amazon EBS).
- Describir los beneficios de Amazon Simple Storage Service (Amazon S3).
- Describir los beneficios de Amazon Elastic File System (Amazon EFS).
- Resumir varias soluciones de almacenamiento.
- Describir los beneficios de Amazon Relational Database Service (RDS).
- Describir los beneficios de Amazon DynamoDB.
- Resumir varios servicios de base de datos.
# Conceptos Claves
Almacenamiento en bloque
Los discos en una instacia EC2 son Efimeros o temporales y duraran tanto como la instacia
Volumentes EBS resuelven ese problema
# Acronimos 
EBS Amazon Elastic Block Store 
S3 Amazon Simple Storage Server
WORM escribir una vez, leer muchas veces
EFS Amazon Elastic File System 

# Contenido

## Almacenes de instancias y Amazon Elastic Block Store (Amazon EBS)
Almacenamiento en bloques
Los volumentes EBS requieren: 
Tamano
Tipo 
Configuraciones
EBS soporta realizar respaldo progresivos (instantaneas o snapshots)


Los volúmenes de almacenamiento a nivel de bloque se comportan como discos duros físicos.
Un [almacén de instancias](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html) proporciona almacenamiento temporal a nivel de bloques para una instancia de Amazon EC2. Un almacén de instancias es un almacenamiento en disco que está conectado físicamente a la computadora host para una instancia de EC2 y, por lo tanto, tiene la misma vida útil que la instancia. Cuando la instancia está terminada, pierde todos los datos que se encuentran en el almacén de instancias.
Para analizar un ejemplo de cómo funcionan los almacenes de instancias, seleccione los botones de flechas para mostrar cada paso.
![409caf28cd4c0bef665da5af9e73c09b.png](../../_resources/409caf28cd4c0bef665da5af9e73c09b.png)


![10360408c2c57470a55868045b2cb1c5.png](../../_resources/10360408c2c57470a55868045b2cb1c5.png)


![4d9f4cc767d678ccc83442c334224d6e.png](../../_resources/4d9f4cc767d678ccc83442c334224d6e.png)


![fd067caa568c74e28e074d433c002768.png](../../_resources/fd067caa568c74e28e074d433c002768.png)

![0a4a65062660dc0e752657ad0afd7002.png](../../_resources/0a4a65062660dc0e752657ad0afd7002.png)

[Amazon Elastic Block Store (Amazon EBS)](https://aws.amazon.com/ebs)  es un servicio que proporciona volúmenes de almacenamiento a nivel de bloques y que puede utilizarse con instancias de Amazon EC2. Si detiene o termina una instancia de Amazon EC2, todos los datos del volumen de EBS adjunto siguen estando disponibles.
Para crear un volumen de EBS, debe definir la configuración (como el tamaño y el tipo de volumen) y aprovisionarlo. Después de crear un volumen de EBS, se puede adjuntar a una instancia de Amazon EC2.
Dado que los volúmenes de EBS son para datos que deben persistir, es importante hacer una copia de seguridad de los datos. Puede realizar copias de respaldo progresivas de los volúmenes de EBS mediante la creación de instantáneas de Amazon EBS.


## Instantáneas de Amazon EBS
![2503b2a3c1b5c54b723679c6cf171fd7.png](../../_resources/2503b2a3c1b5c54b723679c6cf171fd7.png)
Una [instantánea de EBS](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/EBSSnapshots.html) es una copia de seguridad progresiva. Esto significa que la primera copia de seguridad realizada de un volumen copia todos los datos. Para las copias de seguridad posteriores, solo se guardan los bloques de datos que han cambiado desde la última instantánea. 
Las copias de respaldo progresivas son diferentes de las copias de respaldo completas, en las que se copian todos los datos de un volumen de almacenamiento cada vez que se realiza una copia de respaldo. La copia de seguridad completa incluye datos que no han cambiado desde la copia de seguridad más reciente.



# Amazon Simple Storage Service (Amazon S3)

Los datos se guardan como objetos (archivo)
Se almacenan en Buckets(directorio)
Se pueden crear versiones de objetos (rastro documental)
Soporta hasta 5TBs 
Niveles de acceso (se accesan frecuente vs a los que no)


## S3 Standard 
99.99999999999 11 nueves  soporta perdida de datos de hasta 2 instalaciones simultaneas
Los datos se guardan en 3 ubicaciones
Se puede usar para sitios web staticos

## S3 Standard-Infrecuente Access (S3 Standard-IA)
Respaldos 
Archivos de recuperacion de DR

## S3 Glacier Flexible Retrival
Retencion de datos durante un periodo de tiempo 

Politicas de ciclos de vida, mueve objetos entre los diferentes niveles de almacenamiento 

## S3 Deep Archive

## Almacenamiento de objetos
![407da0047af26f0e6201564a6d5a4223.png](../../_resources/407da0047af26f0e6201564a6d5a4223.png)
En el almacenamiento de objetos, cada objeto consta de datos, metadatos y una clave.
Los datos pueden ser una imagen, un video, un documento de texto o cualquier otro tipo de archivo. Los metadatos contienen información sobre qué son los datos, cómo se usan, el tamaño del objeto, etc. La clave de un objeto es su identificador único.

![0bda3f2bae60a81aa6cf7891a515ce8a.png](../../_resources/0bda3f2bae60a81aa6cf7891a515ce8a.png)

## Amazon Simple Storage Service (Amazon S3)
[Amazon Simple Storage Service (Amazon S3)](https://aws.amazon.com/s3/) es un servicio que proporciona almacenamiento a nivel de objeto. Amazon S3 almacena los datos como objetos en buckets.
Puede cargar cualquier tipo de archivo en Amazon S3, como imágenes, videos, archivos de texto, etc. Por ejemplo, puede utilizar Amazon S3 para almacenar archivos de copia de seguridad, archivos multimedia de un sitio web o documentos archivados. Amazon S3 ofrece espacio de almacenamiento ilimitado. El tamaño máximo de archivo de un objeto de Amazon S3 es de 5 TB.
Al cargar un archivo en Amazon S3, puede establecer permisos para controlar la visibilidad y el acceso a él. También puede utilizar la función de control de versiones de Amazon S3 para realizar un seguimiento de los cambios en los objetos a lo largo del tiempo.
## Clases de almacenamiento de Amazon S3
Con Amazon S3, solo paga por lo que utiliza. Puede elegir entre [varias clases de almacenamiento](https://aws.amazon.com/s3/storage-classes) para seleccionar una opción que se ajuste a las necesidades de negocio y costos. Al seleccionar una clase de almacenamiento de Amazon S3, tenga en cuenta estos dos factores:
- Con qué frecuencia piensa recuperar sus datos
- Qué tanta disponibilidad deben tener los datos
Para obtener más información sobre las clases de almacenamiento de Amazon S3, expanda cada una de las siguientes ocho categorías.
![a2eeefd89ced2fdc9e3347584df8e92f.png](../../_resources/a2eeefd89ced2fdc9e3347584df8e92f.png)
![22fe028edf6a9c071f44a65dc6a681a0.png](../../_resources/22fe028edf6a9c071f44a65dc6a681a0.png)
![d4d940b9610059b5e75d89cb9130390d.png](../../_resources/d4d940b9610059b5e75d89cb9130390d.png)
![c777943a2ae8caf0ec3ce9fc62740fa2.png](../../_resources/c777943a2ae8caf0ec3ce9fc62740fa2.png)

# Amazon Elastic File System (Amazon EFS)

