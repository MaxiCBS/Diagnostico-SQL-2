# Escribir el enunciado de cada punto

## a)
  Se crea la tabla marcas. Con tres campos, ninguno puede ser nulo y el PRIMARY KEY es IdMarca, el cual es un entero pequeño predeterminado en 1. Los otros dos campos son NombreMarca y NombreCiudad los cuales son cadenas de caracteres.

```
  CREATE TABLE MARCAS (
    IdMarca SMALLINT NOT NULL DEFAULT 1,
    NombreMarca CHAR(10) NOT NULL,
    NombreCiudad CHAR(60) NOT NULL,
    PRIMARY KEY (idMarca));
```

## b)
  Se crea la tabla coches, es similar a la tabla marcas, con la diferencia de que su PRIMARY KEY, que en este caso se llama 'codcoche', no tiene el valor predeterminado en 1. Luego tiene el campo nombre y modelo que son cadenas de caracteres.

```
  CREATE TABLE COCHES (
    codcoche SMALLINT NOT NULL,
    nombre CHAR(15) NOT NULL,
    modelo CHAR(10),
    PRIMARY KEY (codcoche));
```

## c)
  Se crea la tabla marco, en la cual se declara IdMarca y codcoche de la misma forma que en sus respectivas tablas. Se crea la clave primaria combinando IdMarca y codcoche. Es una tabla con solo dos campos, que hacen referencia al contenido de marcas y coches
  
```
  CREATE TABLE MARCO (
    IdMarca SMALLINT NOT NULL,
    codcoche SMALLINT NOT NULL,
    PRIMARY KEY (IdMarca, codcoche),
    FOREIGN KEY (IdMarca) REFERENCES MARCAS(IdMarca),
    FOREIGN KEY (codcoche) REFERENCES COCHES(codcoche)
  );
```

## d)
  Se insertan valores a la tabla marcas, completando los campos IdMarca, NombreMarca y NombreCiudad

```
  INSERT INTO MARCAS VALUES (1,'vw','Mar del Plata');
  INSERT INTO MARCAS VALUES (2,'renault','Rosario');
  INSERT INTO MARCAS VALUES (3,'fiat','Cordoba');
  INSERT INTO MARCAS VALUES (4,'ford','Neuquen');
```

## e)
  Se solicita que se muestre la totalidad de contenido de la tabla Marcas
  
```
  SELECT * FROM MARCAS;
```

## f)
  Se solicita que se muestre los campos NombreMarca y NombreCiudad de la tabla Marcas
```
  SELECT NombreMarca, NombreCiudad FROM MARCAS;
```

## g)
  Se solicita que se muestre los campos NombreMarca y NombreCiudad correspondientes al IdMarca con valor 2 en la tabla marcas
  
```
  select NombreMarca,NombreCiudad from MARCAS where IdMarca = 2;
```

## h)
  Se solicita que se muestren los campos NombreMarca y NombreCiudad de la tabla marcas, donde NombreCiudad sea igual a 'Neuquen'
  
```
  select NombreMarca, NombreCiudad from marcas where NombreCiudad = 'Neuquen';
```

## i)
  Se solicita que se muestre los campos NombreMarca y NombreCiudad de la tabla marcas, donde NombreCiudad comience con S

```
  select NombreMarca,NombreCiudad from marcas where NombreCiudad LIKE 'S%';
```

## j)
  
  Se solicita realizar cambios en la tabla marcas. El cual consiste en cambiar en el campo 'ciudad', todos los campos que digan 'Jujuy' por 'Neuquen'
```
  update marcas set ciudad = 'Nuequen' where ciudad = 'Jujuy';
```
