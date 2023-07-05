## 1. DDL

### A. Crear una nueva base de datos de nombre "carreras"

Para crear una nueva base de datos llamada "carreras", puedes utilizar el siguiente código SQL:

```sql
CREATE DATABASE carreras;
```

### B. Crear una nueva tabla: Corredor

Para crear la tabla "Corredor" con las especificaciones dadas, utiliza el siguiente código SQL:

```sql
CREATE TABLE Corredor (
    Numero INT PRIMARY KEY,
    Nombre VARCHAR(255),
    Altura DECIMAL(3, 2),
    Peso DECIMAL(5, 2),
    T100mts TIME,
    FNac DATE,
    IdPais INT
);
```

### C. Agregar el atributo T400mts a la tabla Corredor

Para agregar el atributo "T400mts" a la tabla "Corredor", utiliza el siguiente código SQL:

```sql
ALTER TABLE Corredor
ADD T400mts TIME;
```

### D. Eliminar el atributo Peso de la tabla Corredor

Para eliminar el atributo "Peso" de la tabla "Corredor", utiliza el siguiente código SQL:

```sql
ALTER TABLE Corredor
DROP COLUMN Peso;
```

### E. Eliminar la base de datos "carreras"

Para eliminar la base de datos "carreras", utiliza el siguiente código SQL:

```sql
DROP DATABASE carreras;
```

## 2. Normalización

### A. Segunda Forma Normal (2FN)

La Segunda Forma Normal (2FN) se cumple cuando una tabla está en Primera Forma Normal (1FN) y todos sus atributos no clave dependen completamente de la clave primaria. En otras palabras, no debe haber dependencias parciales en la tabla.

**Ejemplo de aplicación:**

Supongamos que tenemos la siguiente tabla "Estudiantes_Cursos":

| EstudianteID | Nombre   | CursoID | CursoNombre |
|--------------|----------|---------|-------------|
| 1            | Juan     | 101     | Matemáticas |
| 1            | Juan     | 102     | Física      |
| 2            | Maria    | 101     | Matemáticas |
| 3            | Pedro    | 103     | Química     |

Para aplicar la 2FN, separamos la tabla en dos tablas:

1. Estudiantes:

| EstudianteID | Nombre |
|--------------|--------|
| 1            | Juan   |
| 2            | Maria  |
| 3            | Pedro  |

2. Cursos:

| CursoID | CursoNombre |
|---------|-------------|
| 101     | Matemáticas |
| 102     | Física      |
| 103     | Química     |

### B. Tercera Forma Normal (3FN)

La Tercera Forma Normal (3FN) se cumple cuando una tabla está en Segunda Forma Normal (2FN) y todos sus atributos no clave dependen solo de la clave primaria y no de otros atributos no clave. En otras palabras, no debe haber dependencias transitivas en la tabla.

**Ejemplo de aplicación:**

Supongamos que tenemos la siguiente tabla "Empleados":

| EmpleadoID | Nombre   | DepartamentoID | DepartamentoNombre | Ubicacion |
|------------|----------|----------------|--------------------|-----------|
| 1          | Juan     | 101            | IT                 | Edificio A|
| 2          | Maria    | 102            | RRHH               | Edificio B|
| 3          | Pedro    | 101            | IT                 | Edificio A|

Para aplicar la 3FN, separamos la tabla en dos tablas:

1. Empleados:

| EmpleadoID | Nombre   | DepartamentoID |
|------------|----------|----------------|
| 1          | Juan     | 101            |
| 2          | Maria    | 102            |
| 3          | Pedro    | 101            |

2. Departamentos:

| DepartamentoID | DepartamentoNombre | Ubicacion  |
|----------------|--------------------|------------|
| 101            | IT                 | Edificio A |
| 102            | RRHH               | Edificio B |