# Lenguaje SQL

## ¿Qué es el lenguaje SQL? {#que-es-el-lenguaje-sql}
El lenguaje SQL (Structured Query Language) es un lenguaje de programación utilizado para interactuar con bases de datos relacionales. SQL se utiliza para crear, modificar y administrar bases de datos, así como para realizar consultas y manipulaciones de datos en ellas. SQL es un lenguaje declarativo, lo que significa que se describe el resultado que se desea obtener y el sistema de gestión de bases de datos se encarga de determinar cómo obtener ese resultado.

El lenguaje SQL consta de una serie de comandos y cláusulas que se utilizan para interactuar con las bases de datos. Algunos de los comandos más comunes incluyen:

- **SELECT**: se utiliza para seleccionar datos de una o varias tablas
- **INSERT**: se utiliza para insertar nuevos datos en una tabla
- **UPDATE**: se utiliza para actualizar datos existentes en una tabla
- **DELETE**: se utiliza para eliminar datos de una tabla
- **CREATE**: se utiliza para crear una nueva base de datos, tabla o vista
- **ALTER**: se utiliza para modificar la estructura de una base de datos, tabla o vista existente
- **DROP**: se utiliza para eliminar una base de datos, tabla o vista existente
- **JOIN**: se utiliza para combinar datos de dos o más tablas basándose en una condición de unión

Además, SQL también incluye cláusulas que se utilizan para filtrar y ordenar datos, como *WHERE*, *ORDER BY* y *GROUP BY*. También se pueden utilizar funciones de agregación, como *AVG*, *SUM*, *COUNT*, *MAX* y *MIN*, para realizar cálculos en los datos seleccionados.

SQL es un lenguaje estándar y se utiliza en una amplia variedad de sistemas de gestión de bases de datos, como Oracle, Microsoft SQL Server, MySQL, PostgreSQL, entre otros. Es un lenguaje fácil de aprender y se utiliza tanto por usuarios no técnicos como por programadores experimentados.

## Comandos básicos: SELECT, INSERT, UPDATE, DELETE {#comandos-basicos-select-insert-update-delete}

1. SELECT
El comando `SELECT` se utiliza para seleccionar datos de una o varias tablas en una base de datos. Con este comando se pueden especificar las columnas que se desean seleccionar, así como también se pueden utilizar cláusulas para filtrar y ordenar los datos seleccionados.
La sintaxis básica del comando SELECT es la siguiente:
```sql
SELECT column1, column2, ...
FROM tabla;
WHERE condicion;
ORDER BY column1, column2, ... ASC|DESC;
```

En esta sintaxis, `"columna1"` y `"columna2"` son las columnas que se desean seleccionar, `"tabla"` es la tabla de la que se seleccionarán los datos y `"condicion"` es una condición opcional que se utiliza para filtrar los datos seleccionados. La cláusula `"ORDER BY"` es opcional y se utiliza para ordenar los datos seleccionados por una o más columnas.

Por ejemplo, para seleccionar todas las columnas de una tabla llamada `"clientes"`, se puede utilizar el siguiente comando:

```sql
SELECT *
FROM clientes;
```

2. INSERT

El comando `INSERT` se utiliza para insertar nuevos datos en una tabla. Con este comando se pueden especificar las columnas en las que se insertarán los datos, así como también se pueden utilizar cláusulas para especificar los valores que se insertarán en cada columna.

La sintaxis básica del comando INSERT es la siguiente:

```sql
INSERT INTO tabla (columna1, columna2, ..., columnaN)
VALUES (valor1, valor2, ..., valorN);
```

En esta sintaxis, `"tabla"` es la tabla en la que se insertarán los datos, `"columna1"`, `"columna2"`, ..., `"columnaN"` son las columnas en las que se insertarán los datos y `"valor1"`, `"valor2"`, ..., `"valorN"` son los valores que se insertarán en cada columna.

Por ejemplo, para insertar un nuevo registro en una tabla llamada "clientes" con los valores "Juan Pérez" para la columna "nombre" y "México" para la columna "país", se puede utilizar el siguiente comando:
    
```sql
INSERT INTO clientes (nombre, pais)
VALUES ("Juan Pérez", "México");
```

3. UPDATE

El comando `UPDATE` se utiliza para actualizar datos existentes en una tabla. Con este comando se pueden especificar las columnas que se desean actualizar, así como también se pueden utilizar cláusulas para especificar los nuevos valores que se insertarán en cada columna. Además, se puede utilizar una cláusula `WHERE` para filtrar los registros que se actualizarán.

La sintaxis básica del comando UPDATE es la siguiente:

```sql
UPDATE tabla
SET columna1 = valor1, columna2 = valor2, ..., columnaN = valorN
WHERE condicion;
```

En esta sintaxis, `"tabla"` es la tabla en la que se actualizarán los datos, `"columna1"`, `"columna2"`, ..., `"columnaN"` son las columnas que se actualizarán y `"valor1"`, `"valor2"`, ..., `"valorN"` son los nuevos valores que se insertarán en cada columna. La cláusula `"WHERE"` es opcional y se utiliza para filtrar los registros que se actualizarán.

Por ejemplo, para actualizar el valor de la columna "país" a "Argentina" para todos los registros de una tabla llamada "clientes" que tengan un valor de "México" en la columna "país", se puede utilizar el siguiente comando:

```sql
UPDATE clientes
SET pais = "Argentina"
WHERE pais = "México";
```

4. DELETE
El comando `DELETE` se utiliza para eliminar datos de una tabla. Se especifica la condición que deben cumplir los registros que se desean eliminar. 
> **CUIDADO:** Si no se especifica ninguna condición, se eliminarán todos los registros de la tabla.

La sintaxis básica del comando DELETE es la siguiente:

```sql
DELETE FROM tabla
WHERE condicion;
```

En esta sintaxis, `"tabla"` es la tabla de la que se eliminarán los datos y `"condicion"` es una condición opcional que se utiliza para filtrar los registros que se eliminarán.

Por ejemplo, para eliminar todos los registros de una tabla llamada "clientes" que tengan un valor de "Argentina" en la columna "país", se puede utilizar el siguiente comando:

```sql
DELETE FROM clientes
WHERE pais = "Argentina";
```

Por ejemplo, para eliminar todos los registros de una tabla llamada "clientes", se puede utilizar el siguiente comando:

```sql
DELETE FROM clientes;
```

Es importante tener en cuenta que el comando DELETE elimina los registros de forma permanente y no se pueden recuperar una vez que se han eliminado. Por lo tanto, es recomendable tener precaución al utilizar este comando y asegurarse de que se estén eliminando los registros correctos.

## Cláusulas WHERE, ORDER BY y GROUP BY {#clausulas-where-order-by-y-group-by}

1. WHERE
La cláusula `WHERE` se utiliza para filtrar los registros que se seleccionan, actualizan o eliminan. Esta cláusula se puede utilizar con los comandos `SELECT`, `UPDATE` y `DELETE`. La sintaxis básica de la cláusula `WHERE` es la siguiente:

```sql
SELECT columna1, columna2, ...
FROM tabla
WHERE condicion;
```

En esta sintaxis, `"columna1"` y `"columna2"` son las columnas que se desean seleccionar, `"tabla"` es la tabla de la que se seleccionarán los datos y `"condicion"` es una condición que se utiliza para filtrar los registros que se seleccionarán, actualizarán o eliminarán.

Por ejemplo, para seleccionar todos los registros de una tabla llamada "clientes" que tengan un valor de "Mexico" en la columna "país", se puede utilizar el siguiente comando:

```sql
SELECT *
FROM clientes
WHERE pais = "Mexico";
```

2. ORDER BY

La cláusula `ORDER BY` se utiliza para ordenar los registros que se seleccionan. Esta cláusula se puede utilizar con el comando `SELECT`. La sintaxis básica de la cláusula `ORDER BY` es la siguiente:

```sql
SELECT columna1, columna2, ...
FROM tabla
WHERE condicion
ORDER BY columna1, columna2, ... ASC|DESC;
```

En esta sintaxis, `"columna1"` y `"columna2"` son las columnas que se desean seleccionar, `"tabla"` es la tabla de la que se seleccionarán los datos, `"condicion"` es una condición opcional que se utiliza para filtrar los registros que se seleccionarán y `"ASC"` o `"DESC"` es un parámetro opcional que se utiliza para especificar si los registros se ordenarán de forma ascendente o descendente.

Por ejemplo, para seleccionar todos los registros de una tabla llamada "clientes" y ordenarlos por el valor de la columna "nombre" en orden ascendente, se puede utilizar el siguiente comando:

```sql
SELECT *
FROM clientes
ORDER BY nombre ASC;
```

3. GROUP BY

La cláusula `GROUP BY` se utiliza para agrupar los registros que se seleccionan. Esta cláusula se puede utilizar con el comando `SELECT`. La sintaxis básica de la cláusula `GROUP BY` es la siguiente:

```sql
SELECT columna1, columna2, ..., func_agregacion(columnaX)
FROM tabla
GROUP BY columnaY;
```

En esta sintaxis, `"columna1"`, `"columna2"`, ..., `"columnaN"` son las columnas que se desean seleccionar, `"tabla"` es la tabla de la que se seleccionarán los datos, `"func_agregacion"` es una función de agregación que se utiliza para calcular un valor a partir de los valores de una columna y `"columnaY"` es la columna que se utilizará para agrupar los registros.

4. HAVING

La cláusula `HAVING` se utiliza para filtrar los grupos de registros que se seleccionan. Esta cláusula se puede utilizar con el comando `SELECT`. La sintaxis básica de la cláusula `HAVING` es la siguiente:

```sql
SELECT columna1, columna2, ..., func_agregacion(columnaX)
FROM tabla
GROUP BY columnaY
HAVING condicion;
```

En esta sintaxis, `"columna1"`, `"columna2"`, ..., `"columnaN"` son las columnas que se desean seleccionar, `"tabla"` es la tabla de la que se seleccionarán los datos, `"func_agregacion"` es una función de agregación que se utiliza para calcular un valor a partir de los valores de una columna, `"columnaY"` es la columna que se utilizará para agrupar los registros y `"condicion"` es una condición que se utiliza para filtrar los grupos de registros que se seleccionarán.

Por ejemplo, para seleccionar el número de clientes por país de una tabla llamada "clientes" y filtrar solo los países con más de 10 clientes, se puede utilizar el siguiente comando:

```sql
SELECT pais, COUNT(*)
FROM clientes
GROUP BY pais
HAVING COUNT(*) > 10;
```

En resumen, las cláusulas WHERE, ORDER BY, GROUP BY y HAVING son herramientas muy útiles para filtrar, ordenar y agrupar los resultados de una consulta SQL en función de las necesidades específicas de un usuario.

## Joins: INNER, LEFT, RIGHT, FULL {#joins-inner-left-right-full}

Los `"joins"` en SQL se utilizan para combinar datos de dos o más tablas en una sola consulta. Cuando se tiene información relacionada en varias tablas, es necesario unir las tablas para poder consultar la información de manera efectiva.

Existen varios tipos de "joins" en SQL, pero los más comunes son los siguientes:

1. **INNER JOIN:** Este tipo de "join" devuelve solo las filas que tienen coincidencias en ambas tablas que se están uniendo. Por ejemplo, si se tiene una tabla de clientes y una tabla de pedidos, se puede unir las dos tablas usando INNER JOIN para obtener una lista de todos los clientes que han realizado pedidos. La sintaxis básica de un INNER JOIN es la siguiente:

```sql
SELECT *
FROM clientes
INNER JOIN pedidos ON clientes.id = pedidos.id_cliente;
```

2. **LEFT JOIN:** Este tipo de "join" devuelve todas las filas de la tabla izquierda y las filas correspondientes de la tabla derecha. Si no hay una coincidencia en la tabla derecha, se rellenan los campos con valores NULL. Por ejemplo, si se tiene una tabla de clientes y una tabla de pedidos, se puede usar LEFT JOIN para obtener una lista de todos los clientes y sus pedidos correspondientes (si los tienen). La sintaxis básica de un LEFT JOIN es la siguiente:

```sql
SELECT *
FROM clientes
LEFT JOIN pedidos ON clientes.id = pedidos.id_cliente;
```

3. **RIGHT JOIN:** Este tipo de "join" devuelve todas las filas de la tabla derecha y las filas correspondientes de la tabla izquierda. Si no hay una coincidencia en la tabla izquierda, se rellenan los campos con valores NULL. Por ejemplo, si se tiene una tabla de clientes y una tabla de pedidos, se puede usar RIGHT JOIN para obtener una lista de todos los pedidos y sus clientes correspondientes (si los tienen). La sintaxis básica de un RIGHT JOIN es la siguiente:

```sql
SELECT *
FROM clientes
LEFT JOIN pedidos ON clientes.id = pedidos.id_cliente;
```

4. **FULL JOIN:** Este tipo de "join" devuelve todas las filas de ambas tablas, rellenando los campos con valores NULL cuando no hay coincidencias. Por ejemplo, si se tiene una tabla de clientes y una tabla de pedidos, se puede usar FULL JOIN para obtener una lista de todos los clientes y sus pedidos correspondientes (si los tienen). La sintaxis básica de un FULL JOIN es la siguiente:

```sql
SELECT *
FROM clientes
FULL OUTER JOIN pedidos ON clientes.id = pedidos.id_cliente;
```

Es importante tener en cuenta que las cláusulas de "join" deben especificar las columnas que se utilizan para unir las tablas (es decir, las claves primarias y foráneas), de lo contrario, no se obtendrán los resultados esperados. Además, es recomendable utilizar alias de tabla para que la consulta sea más legible y fácil de entender.

## Funciones de agregación: AVG, SUM, COUNT, MAX, MIN {#funciones-de-agregacion-avg-sum-count-max-min}

Las funciones de agregación se utilizan para calcular un valor a partir de los valores de una columna. Las funciones de agregación más comunes son:

1. COUNT: La función COUNT se utiliza para contar el número de filas en una tabla. Por ejemplo, si quisieras contar el número de empleados en una tabla, podrías utilizar la función COUNT.

```sql
SELECT COUNT(*)
FROM empleados;
```

2. SUM: La función SUM se utiliza para sumar los valores de una columna. Por ejemplo, si quisieras calcular el salario total de los empleados en una tabla, podrías utilizar la función SUM.

```sql
SELECT SUM(salario)
FROM empleados;
```

3. AVG: La función AVG se utiliza para calcular el promedio de los valores de una columna. Por ejemplo, si quisieras calcular el salario promedio de los empleados en una tabla, podrías utilizar la función AVG.

```sql
SELECT AVG(salario)
FROM empleados;
```

4. MIN: La función MIN se utiliza para obtener el valor mínimo de una columna. Por ejemplo, si quisieras obtener el salario mínimo de los empleados en una tabla, podrías utilizar la función MIN.

```sql
SELECT MIN(salario)
FROM empleados;
```

5. MAX: La función MAX se utiliza para obtener el valor máximo de una columna. Por ejemplo, si quisieras obtener el salario máximo de los empleados en una tabla, podrías utilizar la función MAX.

```sql
SELECT MAX(salario)
FROM empleados;
```

Todas estas funciones pueden ser utilizadas en combinación con la cláusula GROUP BY, que se utiliza para agrupar los datos en la tabla según una columna específica. De esta manera, puedes calcular las funciones de agregación para cada grupo de datos en la tabla, lo que puede ser útil para realizar análisis y cálculos resumidos en conjuntos de datos más grandes.

Es importante tener en cuenta que estas funciones agregadas pueden ser sensibles a los valores nulos en la tabla. Si una fila en la tabla tiene un valor nulo en la columna correspondiente, la función AVG, SUM, COUNT, MAX o MIN puede devolver resultados imprecisos o incorrectos. Por lo tanto, es importante comprender cómo manejar los valores nulos en las consultas SQL para garantizar resultados precisos.

## Subconsultas {#subconsultas}

Las subconsultas en SQL son consultas que se utilizan dentro de otras consultas. Es decir, una subconsulta es una consulta que se realiza dentro de otra consulta, que se denomina consulta principal. La subconsulta se ejecuta primero, y luego se utiliza su resultado en la consulta principal.

Las subconsultas se pueden utilizar en las cláusulas SELECT, FROM, WHERE y HAVING. Las subconsultas pueden ser útiles cuando se necesita utilizar información de una tabla para filtrar los resultados de otra tabla, o cuando se necesita realizar una operación compleja en una subconjunto de los datos.

Las subconsultas se pueden clasificar en dos tipos principales: *subconsultas correlacionadas* y *subconsultas no correlacionadas*.

Las *subconsultas no correlacionadas* son subconsultas que se pueden ejecutar de forma independiente de la consulta principal. La subconsulta no tiene ninguna relación con las filas de la tabla de la consulta principal. En otras palabras, la subconsulta se ejecuta solo una vez y su resultado se utiliza en la consulta principal. Por ejemplo, si se tiene una tabla de clientes y una tabla de pedidos, se puede utilizar una subconsulta no correlacionada para obtener una lista de todos los clientes que han realizado pedidos. La sintaxis básica de una subconsulta no correlacionada es la siguiente:

```sql
SELECT *
FROM clientes
WHERE id IN (SELECT id_cliente FROM pedidos);
```

En este ejemplo, la subconsulta se ejecuta primero y devuelve una lista de todos los clientes que han realizado pedidos. Luego, la consulta principal utiliza esta lista para filtrar los clientes que no han realizado pedidos.

Las *subconsultas correlacionadas*, por otro lado, están estrechamente relacionadas con la consulta principal. En este caso, la subconsulta se ejecuta una vez para cada fila de la tabla de la consulta principal, y utiliza valores de esa fila para filtrar los resultados de la subconsulta. Por ejemplo, si se tiene una tabla de clientes y una tabla de pedidos, se puede utilizar una subconsulta correlacionada para obtener una lista de todos los clientes que han realizado pedidos por un monto mayor a 1000. La sintaxis básica de una subconsulta correlacionada es la siguiente:

```sql
SELECT *
FROM clientes
WHERE id IN (SELECT id_cliente FROM pedidos WHERE monto > 1000);
```

En este ejemplo, la subconsulta se ejecuta una vez para cada fila de la tabla de clientes, y utiliza el valor de la columna id de la fila actual para filtrar los resultados de la subconsulta. Por lo tanto, la subconsulta devuelve una lista de todos los clientes que han realizado pedidos por un monto mayor a 1000. Luego, la consulta principal utiliza esta lista para filtrar los clientes que no han realizado pedidos por un monto mayor a 1000.

En resumen, las subconsultas son una herramienta poderosa en SQL que permiten realizar operaciones complejas en subconjuntos de datos. Es importante conocer los diferentes tipos de subconsultas y cómo utilizarlos para escribir consultas SQL eficaces y eficientes.

> **Nota:** En algunos casos, una subconsulta se puede reemplazar por una expresión de tabla derivada o por un join. Es importante tener en cuenta que esto puede tener un impacto en el rendimiento de la consulta, por lo que es importante evaluar diferentes opciones antes de tomar una decisión.

## Vistas {#vistas}

Una vista es una tabla virtual que se crea a partir de una consulta. En lugar de almacenar los datos físicamente, la vista se define como una consulta que recupera datos de una o varias tablas. Cuando se accede a una vista, se ejecuta la consulta subyacente y se devuelve el resultado como si fuera una tabla.

Las vistas tienen varias ventajas:

1. **Simplifican la consulta de datos:** en lugar de escribir una consulta compleja cada vez que se necesita acceder a ciertos datos, se puede crear una vista que contenga la consulta y luego acceder a los datos a través de la vista.

2. **Proporcionan seguridad:** en lugar de permitir el acceso directo a las tablas subyacentes, se pueden crear vistas que muestren solo los datos necesarios y restringir el acceso a las vistas.

3. **Simplifican la administración de los datos:** en lugar de tener que actualizar varias tablas cada vez que se realizan cambios en los datos, se pueden actualizar los datos en una vista y los cambios se propagarán automáticamente a las tablas subyacentes.

Para crear una vista en SQL, se utiliza la sintaxis `CREATE VIEW`. Por ejemplo, para crear una vista que muestre el nombre y el salario de los empleados de una tabla llamada `"employees"`, se puede escribir la siguiente consulta:

```sql
CREATE VIEW employee_names_salaries AS
SELECT name, salary
FROM employees;
```

Una vez creada la vista, se puede acceder a ella utilizando la sintaxis SELECT como si fuera una tabla. Por ejemplo, para mostrar los nombres y salarios de los empleados, se puede escribir la siguiente consulta:

```sql
SELECT * FROM employee_names_salaries;
```

Es importante tener en cuenta que las vistas se actualizan automáticamente cuando se modifican los datos subyacentes, por lo que cualquier cambio realizado en la tabla se reflejará en la vista. Sin embargo, las vistas no pueden ser utilizadas para modificar directamente los datos subyacentes. En cambio, se deben modificar los datos en las tablas subyacentes utilizando consultas de actualización regulares.

## Transacciones {#transacciones}

Una transacción es un conjunto de operaciones que se realizan como una unidad lógica de trabajo. Una transacción puede consistir en una o varias operaciones de lectura y/o escritura en una o varias tablas de la base de datos.

La transacción se utiliza para garantizar la integridad de los datos y para asegurar que las operaciones se realicen de manera consistente. Si una transacción falla, todas las operaciones realizadas en la transacción se deshacen (es decir, se revierten) para restaurar la base de datos al estado anterior a la transacción.

Las transacciones se componen de cuatro operaciones principales, comúnmente conocidas como ACID:

1. **Atomicidad:** garantiza que una transacción se realiza como una unidad indivisible de trabajo, lo que significa que todas las operaciones en la transacción se realizan con éxito o se deshacen si una de ellas falla.

2. **Consistencia:** garantiza que una transacción lleva a la base de datos desde un estado válido a otro estado válido, es decir, que la base de datos mantiene la integridad de los datos en todo momento.

3. **Aislamiento:** garantiza que las transacciones se ejecutan de manera aislada, lo que significa que una transacción no puede ver los cambios que realiza otra transacción hasta que se hayan confirmado.

4. **Durabilidad:** garantiza que los cambios realizados por una transacción se mantienen permanentemente en la base de datos, incluso en caso de un fallo del sistema o un apagón.

Se utiliza la sintaxis `BEGIN TRANSACTION` para iniciar una transacción, y se utiliza la sintaxis `COMMIT` para confirmar la transacción. Si una transacción falla o debe ser deshecha por alguna razón, se utiliza la sintaxis `ROLLBACK` para revertir la transacción.

Por ejemplo, para iniciar una transacción que actualiza el salario de un empleado y su posición en una tabla llamada `"employees"`, se puede escribir lo siguiente:

```sql
BEGIN TRANSACTION;

UPDATE employees SET salary = 50000, position = 'Manager' WHERE id = 1;

COMMIT;
```

Si la transacción se realiza con éxito, la base de datos se actualizará con los cambios realizados. Si la transacción falla por alguna razón, los cambios se revertirán automáticamente y la base de datos volverá al estado anterior a la transacción.

## Cursores {#cursores}

Un cursor es un objeto que permite procesar filas de una tabla o conjunto de resultados de una consulta una a la vez. Los cursores se utilizan principalmente para procesar conjuntos de resultados en un orden específico o para realizar operaciones complejas que requieren el acceso a datos de forma iterativa.

Para usar un cursor en SQL, primero se debe declarar el cursor, especificando la consulta que devuelve los datos que se van a procesar. Luego, se debe abrir el cursor y se deben recuperar los datos fila por fila. Después de procesar todas las filas, se debe cerrar el cursor para liberar los recursos.

La sintaxis para declarar y utilizar un cursor en SQL es la siguiente:

```sql
DECLARE cursor_name CURSOR FOR select_statement;
OPEN cursor_name;
FETCH NEXT FROM cursor_name INTO variable_list;
WHILE @@FETCH_STATUS = 0
BEGIN
    -- procesar la fila actual
    ...
    FETCH NEXT FROM cursor_name INTO variable_list;
END
CLOSE cursor_name;
```

En la declaración de un cursor, se especifica la consulta que se utilizará para recuperar los datos. Luego, se utiliza la cláusula `OPEN` para abrir el cursor y la cláusula `FETCH` para recuperar la primera fila de datos.

Dentro de un bucle `WHILE`, se procesa cada fila de datos con las operaciones necesarias. Luego, se utiliza `FETCH` para recuperar la siguiente fila y se repite el bucle hasta que se hayan procesado todas las filas.

Finalmente, se utiliza la cláusula `CLOSE` para cerrar el cursor y liberar los recursos.

Es importante tener en cuenta que los cursores pueden ser una herramienta poderosa, pero también pueden ser ineficientes y consumir muchos recursos. Por lo tanto, se deben utilizar con cuidado y solo cuando sea necesario. En muchos casos, se pueden utilizar consultas SQL más simples para lograr el mismo resultado sin necesidad de utilizar cursores.