# RDS (Relational Database Service)

Hay diferentes bases de datos, como por ejemplo el *Amazon DocumentDB*, que es compatible con *MongoDB*, es como una réplica.

Después tenemos a *DynamoDB* (Propiedad de Amazon), tambien muy similar a *MongoDB* (pero no compatible), con clave-valor. Puede tener un coste mas elevado que las demás.

Esta el *Amazon MemoryDB for Redis*, es un servicio compatible con *Redis*.

Finalmente tendriamos la de *RDS*, entre las cuales se encuentas las base de datos relacionales, como MySQL, MariaDB, etc. Y tambien algunas de propiedad de *Amazon* compatible con MySQL.

Para saber, podemos tener replicas de nuestra Base de datos en la misma región.

*Es muy importante seleccion siempre la capa gratuita para evitar los costes del servicio, los cuales pueden ser muy elevados si solo los vamos a utilizar para modo desarrollo.*

Podemos negar *Acceso Público* de la base de datos si solo queremos una conexion directa con la maquina que creamos. Pero se puede dejar para conectarce desde una terminal. Es muy recomendable utilizar las base de datos dentro de los servicios de AWS.

