## Práctica 1.

1. Introducción a base de datos

Objetivo: Identificar el nivel de comprensión de los conceptos de base de datos,
mediante preguntas abiertas.
 
Preguntas:

1. ¿Cuáles son las cinco funciones principales del administrador de bases de datos?
(valor 1.5)

Asegurar el buen funcionamiento de las BD
Retención de información de las BD
Evitar pérdida de datos
Solucionar incidencias y pérdidas de datos
Asegurar la seguridad de los datos


2. Indíque cinco responsabilidades del sistema gestor de bases de datos (valor 1.5)

Instalar, configurar y gestionar bases de datos.
Dar soporte al equipo de desarrollo, seguridad informática y redes.
Definir el esquema del diccionario de datos.
Especificar restricciones de integridad para asegurar los datos.
Garantizar la alta disponibilidad de la base de datos.

3. En una BD al usuario del sistema se le brindarán recursos para realizar diversas
operaciones sobre estos archivos, tales como: (valor 1.5)

Agregar archivos nuevos en la BD, insertar, eliminar, actualizar y obtener datos de archivos existentes de la BD

4. ¿Qué es un Sistema de Información? (valor 1.5)

Conjunto de elementos orientados al tratamiento y administración de datos e información, organizados y listos para su posterior uso, generados para cubrir necesidad.

## Práctica 2.

2. Diseño de un modelo relacional

Objetivo: Representar desde un modelo entidad relación un problema


Ejercicio:

Tenemos que diseñar una base de datos sobre proveedores y disponemos de la siguiente
información:

Realiza el modelo entidad relación. (valor 6)

Tenemos esta información sobre una cadena editorial:

● La editorial tiene varias sucursales, con su domicilio, teléfono y un código de
sucursal.

● Cada sucursal tiene varios empleados, de los cuales tendremos su nombre,
apellidos, NIF y teléfono. Un empleado trabaja en una única sucursal.

● En cada sucursal se publican varias revistas, de las que almacenaremos su título,
número de registro, periodicidad y tipo.

● Una revista puede ser publicada por varias sucursales.

● La editorial tiene periodistas (que no trabajan en las sucursales) que pueden
escribir artículos para varias revistas. Almacenaremos los mismos datos que para
los empleados, añadiendo su especialidad.

● También es necesario guardar las secciones fijas que tiene cada revista, que
constan de un título y una extensión.

● Para cada revista, almacenaremos información de cada ejemplar, que incluirá la
fecha, número de páginas y el número de ejemplares vendidos.

  ![DBevaluciojuancarloscampos](https://user-images.githubusercontent.com/101900664/169730516-c6b45ca1-c942-4daf-9163-b31db3ba0ae9.png)

                  CREATE DATABASE Editorial;
             USE Editorial;
             --creamos tablas que no tengan dependencia
             create table sucursal(
              codigo_de_suc INT UNSIGNED PRIMARY KEY,
               domicilio VARCHAR(100) NOT NULL,
               telefono BIGINT UNSIGNED not null
            );
            INSERT INTO sucursal VALUES (01,'Tenayuca 15, Colonia Porvenir',5573485948);
            INSERT INTO sucursal VALUES (02,'Ahuehuetes 24, Colona Reynosa',3395847649);
            INSERT INTO sucursal VALUES (03,'San Juan 12, Colonia Electricistas',7293840947);

            INSERT INTO sucursal VALUES (04,'Manuel Buendía 948, Colonia Reforma',8293459375);
            INSERT INTO sucursal VALUES (05,'Petroleos 12, Cpolonia Alabama',7394850983);
            INSERT INTO sucursal VALUES (06,'Petén 1209, Roma Norte',5587394785);
            INSERT INTO sucursal VALUES (07,'Tlahuac 10, Colonia Reyes',4593849058);
            INSERT INTO sucursal VALUES (08,'Anaxagoras 15, Polanco',3384909859);
            INSERT INTO sucursal VALUES (09,'Miguel Hidalgo 98, Colonia Angustura',3338930403);
            INSERT INTO sucursal VALUES (10,'Cervantes 56, Colonia Juárez',2288473845);


            create table revista(
              Numero_de_registro INT UNSIGNED PRIMARY KEY,
               periodicidad VARCHAR(100) NOT NULL,
               tipo VARCHAR(100) not null,
              titulo varchar(100) not null
            );

            INSERT INTO revista VALUES (098,'SEMANAL','POLITICA','POLITICA HOY');
            INSERT INTO revista VALUES (099,'QUINCENAL','DEPORTIVA','EMOCION DEPORTIVA');
            INSERT INTO revista VALUES (100,'SEMANAL','ESPECTACULOS','MUNDO ROSA');
            INSERT INTO revista VALUES (101,'MENSUAL','VIDEOJUEGOS','VIDEOGAMER');
            INSERT INTO revista VALUES (102,'SEMANAL','CINE','CINE HOY');
            INSERT INTO revista VALUES (103,'MENSUAL','CULTURAL','TODO EN CULTURA');


            create table periodista(
              NIF_perio INT UNSIGNED primary key,
              nombre varchar (100) not null,
              apellido varchar(100) not null,
              apellido_mat varchar(100) not null,
              telefono BIGINT UNSIGNED not null,
              especialidad varchar(100) not null

             );

             INSERT INTO periodista VALUE (01,'KARLA','JUAREZ','PEREZ',5534563748,'DEPORTES');
             INSERT INTO periodista VALUE (02,'BEATRIZ','LOPEZ','ANGELES',7289467349,'POLITICA');
             INSERT INTO periodista VALUE (03,'TITO','MARQUEZ','GALINDO',8203978465,'ESPECTACULOS');
             INSERT INTO periodista VALUE (04,'ISABEL','SUAREZ','JIMENEZ',8263748987,'VIDEOJUEGOS');
             INSERT INTO periodista VALUE (05,'PABLO','FERNANDEZ','DUARTE',5523784938,'CINE');
             INSERT INTO periodista VALUE (06,'SERGIO','INFANTE','MORALES',7238946574,'CINE');
             INSERT INTO periodista VALUE (07,'CARLOS','GUIZAR','CISNEROS',3398475840,'CULTURA');
             INSERT INTO periodista VALUE (08,'JUAN','SALAS','MACIAS',5682394848,'DEPORTES');
             INSERT INTO periodista VALUE (09,'PEDRO','RICO','GARAY',5548738495,'POLITICA');
             INSERT INTO periodista VALUE (10,'ANGEL','HERAS','FUENTES',8236475894,'VIDEOJUEGOS');
             INSERT INTO periodista VALUE (11,'CESAR','SAN PEDRO','RODRIGUEZ',4585968495,'CINE');
             INSERT INTO periodista VALUE (12,'MAGDA','LIRA','SANCHEZ',7683749504,'POLITICA');


             --cramos tablas con depencencia
             create table empleados(
             NIF_emple INT UNSIGNED not null,
               nombre varchar(100) not null,
               apellido varchar(100) not null,
               apellido_mat varchar(100) not null,
               telefono BIGINT UNSIGNED ,
               codigo_de_suc1 INT UNSIGNED,
               FOREIGN KEY (codigo_de_suc1) REFERENCES sucursal(codigo_de_suc)
               );

              INSERT INTO empleados VALUES (01,'ANGELICA','BLANCAS','MIRANDA',null,01);
            INSERT INTO empleados VALUES (02,'DAVID','ASPEITIA','ESCOBEDO',null,02);
            INSERT INTO empleados VALUES (03,'ANGEL','GALINDO','HERAS',null,03);
            INSERT INTO empleados VALUES (04,'ISMAEL','FERNANDEZ','HERNADEZ',null,04);
            INSERT INTO empleados VALUES (05,'MAURICIO','ANDA','JUAREZ',null,05);
            INSERT INTO empleados VALUES (06,'ALONSO','BLANCO','ANGELES',null,06);
            INSERT INTO empleados VALUES (07,'ALMA','SALAZAR','HUERTA',null,07);
            INSERT INTO empleados VALUES (08,'BLANCA','SANTOS','SANTIAGO',null,08);
            INSERT INTO empleados VALUES (09,'IGNACIO','HERNANDEZ','HERNNDEZ',null,09);
            INSERT INTO empleados VALUES (10,'MAURICIO','MARQUEZ','CHAVEZ',null,10);


              create table sección(
              ID_sec INT UNSIGNED primary key,
                extención Varchar(100) not null,
                titulo varchar(100)not null,
                Numero_de_registro3 INT UNSIGNED,
                FOREIGN KEY(Numero_de_registro3) REFERENCES revista(Numero_de_registro)
              );

              INSERT INTO sección VALUE (1,'esp','espectaculos',098);
              INSERT INTO sección VALUE (2,'dep','deportes',098);
              INSERT INTO sección VALUE (3,'pol','politica',099);
              INSERT INTO sección VALUE (4,'cin','cine',103);
              INSERT INTO sección VALUE (5,'hog','hogar',102);
              INSERT INTO sección VALUE (6,'cul','cultura',101);
              INSERT INTO sección VALUE (7,'vid','videojuegos',100);


              create table ejemplar(
                ID_EJEM INT UNSIGNED primary key,
                Ejemp_vend INT UNSIGNED not null,
                Numero_de_paginas INT UNSIGNED not null,
                fecha DATE not null,
                Numero_de_registro4 INT UNSIGNED,
                FOREIGN KEY(Numero_de_registro4) REFERENCES revista(Numero_de_registro)
              );

               INSERT INTO ejemplar VALUE (01,4855,56,'2021-09-23',098);
              INSERT INTO ejemplar VALUE (02,1234,89,'2021-09-30',099);
              INSERT INTO ejemplar VALUE (03,5343,78,'2021-10-09',100);
              INSERT INTO ejemplar VALUE (04,5654,90,'2022-04-06',101);
              INSERT INTO ejemplar VALUE (05,3434,100,'2022-03-15',102);
              INSERT INTO ejemplar VALUE (06,6546,100,'2021-06-01',103);
              INSERT INTO ejemplar VALUE (07,4534,56,'2022-05-15',098);


              --creamos tablas intermedias
              create table suc_rev (
              codigo_de_suc2 INT UNSIGNED  not null,
                Numero_de_registro1 INT UNSIGNED not null,
                 FOREIGN KEY ( Numero_de_registro1) REFERENCES revista(Numero_de_registro),
               FOREIGN KEY (codigo_de_suc2) REFERENCES sucursal(codigo_de_suc)
              );
              create table rev_perio(
              Numero_de_registro2 INT UNSIGNED not null,
                NIF_perio1 INT UNSIGNED not null,
                 FOREIGN KEY ( Numero_de_registro2) REFERENCES revista(Numero_de_registro),
              FOREIGN KEY (NIF_perio1) REFERENCES periodista( NIF_perio)  
              );
