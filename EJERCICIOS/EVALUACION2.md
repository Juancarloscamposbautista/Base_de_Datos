## Práctica 3.
### Introducción a SQL
Objetivo: Demostrar la correcta identificación de los conceptos del lenguaje SQL
Ejercicio:

1. Menciona los comandos DMl: (valor .85)

select,insert,update,delete.

2. Menciona 3 tipos de datos que existen: (valor .85)

char,varchar, int.

3. ¿Qué diferencia existe entre TRUNCATE y DELETE?(valor .85)

que truncate es ddl y delete es un comando dml

4. ¿Para qué se utiliza el atributo UNIQUE?(valor .85)

para que no se inserten valores duplicados.

5. ¿Qué diferencia hay entre los tipos de datos VARCHAR y CHAR? (valor .85)

varchar es de longitud variable y char es de longitud fija.

6. Defina brevemente el significado de las siglas SQL(valor .85)

lenguaje de consulta estructurada por sus siglas en ingles.

7. Defina brevemente qué es MySQL WorkBench (valor .85)


 es una herramienta visual de diseño de bases de datos que integra desarrollo de software, administración de bases de datos, diseño de bases de datos, gestión y mantenimiento para el sistema de base de datos 

## Práctica 5.
### Gestores de base de datos

Objetivo: Categorizar los distintos gestores de base de datos que existen y señalar las
ventajas y desventajas

Evaluación: Conoce los tipos de gestores de base de datos 3 puntos.

Domina sus diferencias de los gestores de base de datos mencionados 3 puntos

Ejercicio:

En un mapa conceptual presenta 3 gestores de bases de datos, sus características
principales, las ventajas y desventajas. (valor 6)

![image](https://user-images.githubusercontent.com/91554777/170415427-e2b7321b-a97f-43b0-ac24-6e506c307e6b.png)


![MAPAconseptual](https://user-images.githubusercontent.com/101900664/170423553-d5cc98e4-9e3c-4980-b78e-3a22ac6e90f3.png)


## Práctica 6.
### Herramienta en línea y ejercicio necesarios para realizar las prácticas

Creación de base de datos.

Objetivo: Demostrar mediante la creación de una base de datos el uso y la aplicación de
las funciones

Ejercicio: Creación de la base de datos (valor 18 puntos)

Tienda de informática

![image](https://user-images.githubusercontent.com/91554777/170415101-717bca19-3644-46a9-8a57-8d5940c5d283.png)




Modelo entidad/relación
  
  
             CREATE DATABASE Tienda_de_informática;
                           USE Tienda_de_informática;

                           create table Producto(
                            codigo VARCHAR(100) PRIMARY KEY,
                             Nombre_de_producto VARCHAR(100) NOT NULL,
                             precio BIGINT UNSIGNED not null,
                             Fabricante VARCHAR(100) not null
                          );
                          INSERT INTO Producto VALUES ('DD-23','Disco duro SATA3 1TB',86.99,'SEAGATE');
                          INSERT INTO Producto VALUES ('MM-34','Memoria RAM DDR4 8GB',120.6,'CRUCIAL');
                          INSERT INTO Producto VALUES ('DD-98','Disco SSD 1TB',150.99,'SAMNSUNG');
                          INSERT INTO Producto VALUES ('MM-98','Geforce GTX 1050Ti',185.7,'GIGABYTE');
                          INSERT INTO Producto VALUES ('MM-23','Geforce GTX 1080 Xtreme',755.6,'CRUCIAL');
                          INSERT INTO Producto VALUES ('MT-12','Monitor 24 LED Full HD',202.1,'ASUS');
                          INSERT INTO Producto VALUES ('MT-08','Monitor 27 LED Full HD',245.99,'ASUS');
                          INSERT INTO Producto VALUES ('LP-19','Portátil Yoga 520',559.2,'LENOVO');
                          INSERT INTO Producto VALUES ('LP-11','Portátil Ideapd 320',444.2,'LENOVO');
                          INSERT INTO Producto VALUES ('IM-56','Impresora HP Deskjet 3720',599.93,'HP');
                          INSERT INTO Producto VALUES ('IP-54','Impresora HP Laserjet Pro M26nw',180.3,'HP');
               



Base de datos para MySQL


![evalucion 2 juan carlos campos](https://user-images.githubusercontent.com/101900664/170512612-4c142539-d3c4-4f42-86cc-f8d054235193.png)



