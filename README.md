## contenido
the relational model conssts of the following
collection of objects or relations
tables, view, indexes, and sequences
set of operators to act on the relations
operadores basicos
data integrity for accuracy and consistency
llave primaria, llave foreana, valor unica etc...

each row of data in a table is uniquely identified by a primary key.

you can logically relate data from multiple tables using foreing keys.

Admin23r2 administrador de la maquina del laboratorio

para cambiar el nombre de usuario se necesita alter user system identified by @nombredeseado

para conectr la base de datos ingrese connect system

para entrar a la configuracion entre connect sys as sysdba y ingrese Admin23r2 o 1234

DESC para describir la tabla con sus elementos

hr 1234
tncd name donde se guarda la hora y el nombre de lo usuario


'' para poner un espacio en codigo anci 39

|| para concatenar en codigo anci 124

alter user @usuario identified by @contra;

alter user @usuario account unlock;

initcap(@cosaque se deja buscar), que es 

select COUNT (DISTINCT department_id) empleados, department_id from employees
GROUP BY department_id;
