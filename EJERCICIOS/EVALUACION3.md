
## Práctica 4
### Data warehouse

Objetivo: Demostrar la identificación de los elementos que componen data warehouse y
su esquema

Ejercicio:

1. ¿Qué es un DataWarehouse?(valor 2)

Es un sistema para agregar y combinar datos de diferentes fuentes en un solo almacen de datos unico, con la finalidad de realizar analis de grandes volumenes de datos.



2. Realiza un diseño del modelo en estrella (valor 2)


![Untitled Diagram drawio (2)](https://user-images.githubusercontent.com/101900664/171707415-e40c3958-4013-4750-9eb6-a178a51a4bad.png)



3. Realiza un diseño del modelo copo de nieve (valor 2)


![Untitled Diagram drawio (3)](https://user-images.githubusercontent.com/101900664/171708539-cd88592d-8c7c-4268-8053-639b8f7b42f8.png)


## Práctica 7
### Funciones en SQL
Objetivo: Demostrar el uso y aplicación en una base de datos para mejorar la gestión

Ejercicio:

1. Calcula el número total de productos que hay en la tabla productos. (valor 4.5)

USE tienda;
SELECT COUNT(clave_prod) FROM producto;


2. Muestra el número total de productos que tiene cada uno de los fabricantes. El listado
también debe incluir los fabricantes que no tienen ningún producto. El resultado
mostrará dos columnas, una con el nombre del fabricante y otra con el número de
productos que tiene. Ordene el resultado descendentemente por el número de
productos. (valor 4.5)


USE tienda;
SELECT marca,COUNT(marca) FROM producto group by marca order by 2 asc ;


3. Muestra el precio máximo, precio mínimo y precio medio de los productos de cada
uno de los fabricantes. El resultado mostrará el nombre del fabricante junto con los
datos que se solicitan. (valor 4.5)

USE tienda;
SELECT marca, MAX(precio), MIN(precio), AVG(precio)
FROM producto  
GROUP BY marca;


4. Muestra el nombre de cada fabricante, junto con el precio máximo, precio mínimo,
precio medio y el número total de productos de los fabricantes que tienen un precio
medio superior a 200€. Es necesario mostrar el nombre del fabricante. (valor 4.5)

USE tienda;
SELECT marca, MAX(precio), 
MIN(precio), AVG(precio), 
COUNT(*) FROM producto 
GROUP BY marca 
HAVING AVG(precio) > 200;


## Práctica 8.
### Disparadores (Triggers)

Objetivo: Demostrar las operaciones que se realizan en una base de datos.

Ejercicio: Crea una base de datos llamada test que contenga una tabla llamada
alumnos con las siguientes columnas. (valor 18)

Evaluación:

Creación de la base de datos : 9 puntos.

Creación de los Disparadores(Triggers): 9 puntos.

Tabla alumnos:

● id (entero sin signo)

● nombre (cadena de caracteres)

● apellido1 (cadena de caracteres)

● apellido2 (cadena de caracteres)

● nota (número real)


DROP DATABASE test;
CREATE DATABASE test;
        USE test;

        CREATE TABLE alumnos(
          id INT UNSIGNED PRIMARY KEY,
         nombre VARCHAR(100) not null,
          apellido1 VARCHAR(100) not null,
          apellido2 VARCHAR(100) not null,
          nota FLOAT not null
        );

Una vez creada la tabla escriba dos triggers con las siguientes características:

● Trigger 1: trigger_check_nota_before_insert

  o Se ejecuta sobre la tabla alumnos.
  
  o Se ejecuta antes de una operación de inserción.
  
  o Si el nuevo valor de la nota que se quiere insertar es negativo, se guarda
  como 0.
  
  o Si el nuevo valor de la nota que se quiere insertar es mayor que 10, se
  guarda como 10.

● Trigger2 : trigger_check_nota_before_update
  o Se ejecuta sobre la tabla alumnos.
  
  o Se ejecuta antes de una operación de actualización.
  
  o Si el nuevo valor de la nota que se quiere actualizar es negativo, se guarda
  como 0.
  
  o Si el nuevo valor de la nota que se quiere actualizar es mayor que 10, se
  guarda como 10.
  
Una vez creados los triggers escribe varias sentencias de inserción y actualización
sobre la tabla alumnos y verifica que los triggers se están ejecutando
correctamente.
