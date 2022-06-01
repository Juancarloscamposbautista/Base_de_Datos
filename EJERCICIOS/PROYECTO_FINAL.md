# Proyecto Final de base de datos.
### Indicaciones de lo que se debe realizar

● Diseña el modelo entidad-relación del siguiente problema.

● Crea el script para la base de datos.
Proveedores

Tenemos que diseñar una base de datos sobre proveedores y disponemos de
la siguiente información:

● De cada proveedor conocemos su nombre, dirección, ciudad, provincia y
un código de proveedor que será único para cada uno de ellos.

● Nos interesa llevar un control de las piezas que nos suministra cada
proveedor. Es importante conocer la cantidad de las diferentes piezas
que nos suministra y en qué fecha lo hace. Tenga en cuenta que un
mismo proveedor nos puede suministrar una pieza con el mismo código
en diferentes fechas. El diseño de la base de datos debe permitir
almacenar un histórico con todas las fechas y las cantidades que nos ha
proporcionado un proveedor.

● Una misma pieza puede ser suministrada por diferentes proveedores.

● De cada pieza conocemos un código que será único, nombre, color,
precio y categoría.

● Pueden existir varias categorías y para cada categoría hay un nombre y
un código de categoría único.

● Una pieza sólo puede pertenecer a una categoría.



![Untitled Diagram drawio (1)](https://user-images.githubusercontent.com/101900664/171442115-55f255fc-a5cc-48af-b019-7ea188223d32.png)



            CREATE DATABASE PROVEEDORES;
            USE PROVEEDORES;

            CREATE TABLE Proveedor(
              cod_prove INT UNSIGNED PRIMARY KEY,
             nombre_pro VARCHAR(100) not null,
              dirección VARCHAR(100) not null,
              ciudad VARCHAR(100) not null,
              privincia VARCHAR(100) not null
            );

            CREATE TABLE categoria( 
            cod_catego INT UNSIGNED PRIMARY KEY,
              nombre_cate VARCHAR (100) not null
            );

            CREATE TABLE Pieza(
            cod_piez INT UNSIGNED PRIMARY KEY,
            nombre_piez VARCHAR (100) not null,
              color VARCHAR(100) not null,
              precio INT UNSIGNED not null,
              cod_catego1 INT UNSIGNED not null,
              FOREIGN KEY (cod_catego1) REFERENCES categoria
              (cod_catego)
            );

            CREATE TABLE suministra(
            Fecha_d_suministro DATE not null,
              cantidad_suministrada VARCHAR(100) not null,
              cod_prove1 INT UNSIGNED not null,
              cod_piez1 INT UNSIGNED not null,
              FOREIGN KEY (cod_prove1) REFERENCES Proveedor(cod_prove),
              FOREIGN KEY (cod_piez1) REFERENCES Pieza(cod_piez)
            );
