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

sql no es key sensitive

linux si lo es

todas las vistas Terminan en plurar

una vista guarda solo el select +
para no crear duplicados 

Count(*)

es un if para cambiar 
select Country_name, decode(Region_ID, 
'1' , 'Europa', 
'2' , 'America', 
'3' , 'Asia', 
'4' , 'Africa') Region
from countries;

select first_name || ' ' || last_name, hire_date, TRUNC((sysdate - hire_date)/365) from employees;

select first_name || ' ' || last_name nombre,
hire_date,
TRUNC((sysdate - hire_date)/365) AÑOS_servicios,
CASE 
WHEN TRUNC((sysdate - hire_date)/365) BETWEEN 0 and 15 then '%5'
WHEN TRUNC((sysdate - hire_date)/365) BETWEEN 16 and 20 then '%10'
else '%20'
end aumento
from employees;



SELECT
    -- Concatenamos el primer y último nombre para mostrar el nombre completo.
    first_name || ' ' || last_name AS nombre,
    hire_date fecha, -- Fecha de contratación del empleado.
    
    -- Calculamos los años de servicio dividiendo la diferencia entre la fecha actual y la de contratación por 365.
    TRUNC((SYSDATE - hire_date) / 365) AS años_servicios,
    salary AS salario_anterior, -- Salario anterior del empleado.
    -- Calculamos el salario aumentado aplicando el porcentaje de aumento.
    ROUND(salary * (1 + 
        CASE
            WHEN TRUNC((SYSDATE - hire_date) / 365) BETWEEN 0 AND 15 THEN 0.05
            WHEN TRUNC((SYSDATE - hire_date) / 365) BETWEEN 16 AND 20 THEN 0.10
            ELSE 0.20
        END
    ), 2) AS salario_aumentado,
    
    -- Definimos otro CASE para mostrar el porcentaje de aumento como texto.
    CASE
        WHEN TRUNC((SYSDATE - hire_date) / 365) BETWEEN 0 AND 15 THEN '5%'
        WHEN TRUNC((SYSDATE - hire_date) / 365) BETWEEN 16 AND 20 THEN '10%'
        ELSE '20%'
    END AS aumento_efectuado
FROM employees;
