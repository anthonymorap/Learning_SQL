
# Learning SQL

de Alan Beaulieu

## Capitulo 1: Una pequeña introducción

Este es un capitulo introductorio donde los puntos a tocar consisten en:

- Un poco de historia de sistemas de bases de datos
- El modelo de base de datos relacional
- Vocabulario relevante en el mundo de SQL
- Información estándar del mundo de SQL

### Introducción

Una base de datos presenta información que se encuentra relacionada por que pertenece a un tema en común. Un ejemplo sería los directorios telefónicos que presentan información sobre personas y negocios, sus direcciones y teléfonos.

Estas formas de bases de datos presentan problemas ya sea por la forma en que almacenan la información, la poca practicidad al momento de querer solicitar información y lo lentas que pueden ser las actualizaciones.

Aquí es donde entran los sistemas de bases de datos, estos buscan resolver los problemas tradicionales con ayuda de las nuevas tecnologías informáticas. Con esto pasamos de tener bases de datos en papel a utilizar computadoras y mecanismos de recuperación de información más sofisticados, agilizando considerablemente la forma en que obtenemos información de una base de datos.

### El modelo relacional de bases de datos

Este fue propuesto por el doctor E. F. Codd en 1970, un investigador de IBM que publicó el paper 'A Relational
Model of Data for Large Shared Data Banks'. Con esto propone que los datos sean representados en tablas.

La idea es que utilizamos la información redundante o que se repite entre tablas para conectar la información de la base de datos.

La información en una tabla se encuentra identificada como única en una fila, por lo que en una tabla no puedemos tener observaciones que se repitan. A esta identificación le conocemos como primary key.

Pudieramos utilizar una combinación de campos de la tabla para utilizar como primary key, a esto le conocemos como compound key. Si utilizamos un primary key obtenido por la información que de forma natural estaría en la tabla le llamamos natural key, de otra forma, si el sistema o nosotros creamos un campo para usar como primary key, pues le llamamos surrogate key.

Como mencionabamos antes para conectar las tablas utilizamos la información redundante entre las tablas, un campo que se repita entre las tablas. El primary key es nativo de una sola tabla, en esa es que se genera, mientras que en otras tablas tendremos un foreign key, que representa una copia del primary key y no puede representar una observación que no exista, es decir que para existir un foreign key primero tiene que haber un primary key.

Estos campos tienen una relación clara, y es que son únicos entre toda la base de datos, por lo que podemos relacionar las tablas utilizando esta información que se repite en la base de datos.

De esto podemos pasar al concepto de joins, que no es más que unir tablas en base a la relaciones que existen en la base de datos.

Otro concepto importante es el de normalización, básicamente buscamos refinar el diseño de la base de datos para asegurarnos que cada pieza independiente de información se encuentra en un solo lugar, exceptuando las foreign keys.

| Termino             | Definición                                                                                              |
|---------------------|---------------------------------------------------------------------------------------------------------|
| Entidad             | Algo de interés para los usuarios de la base de datos. Ejemplos son clientes, partes, productos, países |
| Columna o campo     | Una pieza indicidual en una tabla                                                                       |
| Fila u observación  | Es un conjunto de columnas que describen a una entidad                                                  |
| Tabla               | Un conjunto de filas                                                                                    |
| Conjunto resultante | Es otro nombre para una tabla, usualmente resultado de un query en SQL                                  |
| Primary key         | Una o más columnas que puede utilizarse como identificador único para cada fila en una tabla            |
| Foreign key         | Una o más columnas que puede utilizarse para identificar una fila en otra tabla                         |


### SQL

El lenguaje SQL como tal está dividido en partes:

- Schema statements, utilizados para definir estructuras de datos en la base de datos
- Data statements, utilizados para manipular las estructuras de datos anteriormente creadas
- Transaction statements

Un ejemplo de un schema statement es el siguiente, con el cual creamos una tabla `corporation`.

```SQL
CREATE TABLE corporation
    (corp_id SMALLINT,
    name VARCHAR(30),
    CONSTRAINT pk_corporation PRIMARY KEY (corp_id)
    );
```

Un ejemplo de un data statement para insertar información en la tabla sería el siguiente.

```SQL
INSERT INTO corporation (corp_id, name)
VALUES (27, 'Acme Paper Corporation');
```

Los elementos creados via SQL schema statements se guardan en tablas especiales llamadas data dictionary o comúnmente metadata.

Hay que tener en cuenta que SQL es un lenguaje de programación nonprocedural, por lo que los statements que utilizamos definen los inputs y outputs pero la forma en que se ejecuta todo se lo dejamos al optimizador de la base de datos. Este simplemente busca la forma más eficiente de ejecutar la solicitud que hagamos.

## Capítulo 2: Creando y llenando una base de datos

Se tratan temas sobre creación de una base de datos, tipos de datos y como se almacenan en SQL.

El proceso completo de crear una tabla, tomando en cuenta conceptos de diseño y los schema statements.

Insertar, agregar y eliminar datos de las tablas.

Character data

- Utilizamos estas variables para almacenar texto
- Nuestra principal cuestión es si la cantidad caractéres es fija o variable

Numeric data

Temporal data - fechas

## Table Creation

