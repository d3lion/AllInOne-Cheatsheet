# MySQL Application

<img src="https://media.licdn.com/dms/image/v2/C5112AQEhwbQ9yal_JQ/article-cover_image-shrink_720_1280/article-cover_image-shrink_720_1280/0/1520187069366?e=2147483647&v=beta&t=MfgynU-tW-dyo0y04z5fUvhGINcELcgTk6uDxME5Y6g" width="600"/>

## Descripción
MySQL Application es una aplicación diseñada para gestionar bases de datos MySQL de manera eficiente y segura. Proporciona una interfaz intuitiva y una serie de herramientas avanzadas para facilitar la administración de bases de datos.

## Características
- Gestión de usuarios y permisos.
- Creación, modificación y eliminación de bases de datos y tablas.
- Ejecución de consultas SQL.
- Importación y exportación de datos.
- Monitorización del rendimiento de la base de datos.

## Hoja de Trucos
# MySQL Cheat Sheet

## 1. Conexión y Manejo de Bases de Datos
```sql
-- Conectar a MySQL
mysql -u usuario -p

-- Mostrar bases de datos
SHOW DATABASES;

-- Usar una base de datos
USE nombre_base_datos;

-- Crear una base de datos
CREATE DATABASE nombre_base_datos;

-- Eliminar una base de datos
DROP DATABASE nombre_base_datos;
```

## 2. Tablas
```sql
-- Mostrar tablas
SHOW TABLES;

-- Crear una tabla
CREATE TABLE nombre_tabla (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nombre VARCHAR(100) NOT NULL,
    edad INT,
    fecha_registro TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Mostrar estructura de una tabla
DESCRIBE nombre_tabla;

-- Eliminar una tabla
DROP TABLE nombre_tabla;

-- Modificar una tabla
ALTER TABLE nombre_tabla ADD columna_nueva VARCHAR(50);
ALTER TABLE nombre_tabla DROP COLUMN columna_nueva;
ALTER TABLE nombre_tabla MODIFY COLUMN edad SMALLINT;
```

## 3. CRUD (Create, Read, Update, Delete)
```sql
-- Insertar datos
INSERT INTO nombre_tabla (nombre, edad) VALUES ('Juan', 30);

-- Leer datos
SELECT * FROM nombre_tabla;
SELECT nombre, edad FROM nombre_tabla WHERE edad > 25;

-- Actualizar datos
UPDATE nombre_tabla SET edad = 35 WHERE nombre = 'Juan';

-- Eliminar datos
DELETE FROM nombre_tabla WHERE nombre = 'Juan';
```

## 4. Consultas Avanzadas
### 4.1 Consultas Simples y con Múltiples Filtros
```sql
-- Ordenar resultados
SELECT * FROM nombre_tabla ORDER BY edad DESC;

-- Filtrar resultados
SELECT * FROM nombre_tabla WHERE nombre LIKE 'J%';

-- Filtrar con múltiples condiciones
SELECT * FROM nombre_tabla WHERE edad > 25 AND nombre LIKE 'J%';

-- Agrupar resultados
SELECT edad, COUNT(*) FROM nombre_tabla GROUP BY edad;

-- Limitar resultados
SELECT * FROM nombre_tabla LIMIT 10;
```

### 4.2 Consultas con JOIN
```sql
-- INNER JOIN
SELECT a.nombre, b.descripcion 
FROM nombre_tabla a
INNER JOIN otra_tabla b ON a.id = b.id_nombre_tabla;

-- LEFT JOIN
SELECT a.nombre, b.descripcion 
FROM nombre_tabla a
LEFT JOIN otra_tabla b ON a.id = b.id_nombre_tabla;

-- RIGHT JOIN
SELECT a.nombre, b.descripcion 
FROM nombre_tabla a
RIGHT JOIN otra_tabla b ON a.id = b.id_nombre_tabla;
```

### 4.3 Consultas con Subconsultas
```sql
-- Subconsulta en WHERE
SELECT nombre FROM nombre_tabla 
WHERE id IN (SELECT id_nombre_tabla FROM otra_tabla WHERE descripcion = 'Ejemplo');

-- Subconsulta en FROM
SELECT avg(edad) FROM (SELECT edad FROM nombre_tabla WHERE edad > 20) AS subconsulta;

-- Subconsulta en SELECT
SELECT nombre, (SELECT COUNT(*) FROM otra_tabla WHERE otra_tabla.id_nombre_tabla = nombre_tabla.id) AS total_relaciones
FROM nombre_tabla;
```

## 5. Claves y Relaciones
```sql
-- Crear clave primaria
ALTER TABLE nombre_tabla ADD PRIMARY KEY (id);

-- Crear clave foránea
ALTER TABLE otra_tabla ADD FOREIGN KEY (id_nombre_tabla) REFERENCES nombre_tabla(id);
```

## 6. Índices y Optimización
```sql
-- Crear un índice
CREATE INDEX idx_nombre ON nombre_tabla(nombre);

-- Eliminar un índice
DROP INDEX idx_nombre ON nombre_tabla;
```

## 7. Usuarios y Privilegios
```sql
-- Crear un usuario
CREATE USER 'usuario'@'localhost' IDENTIFIED BY 'contraseña';

-- Otorgar privilegios
GRANT ALL PRIVILEGES ON nombre_base_datos.* TO 'usuario'@'localhost';

-- Revocar privilegios
REVOKE ALL PRIVILEGES ON nombre_base_datos.* FROM 'usuario'@'localhost';

-- Mostrar usuarios
SELECT User, Host FROM mysql.user;
```

## 8. Creación de Vistas
```sql
-- Crear una vista
CREATE VIEW vista_nombre AS
SELECT nombre, edad FROM nombre_tabla WHERE edad > 25;

-- Consultar una vista
SELECT * FROM vista_nombre;

-- Actualizar una vista
CREATE OR REPLACE VIEW vista_nombre AS
SELECT nombre, edad FROM nombre_tabla WHERE edad > 30;

-- Eliminar una vista
DROP VIEW vista_nombre;
```

## 9. Copias de Seguridad y Restauración
```sh
-- Exportar base de datos
mysqldump -u usuario -p nombre_base_datos > backup.sql

-- Importar base de datos
mysql -u usuario -p nombre_base_datos < backup.sql
```

## Uso
Una vez instalada, puede acceder a la aplicación desde su navegador web en `http://localhost:3000`. Inicie sesión con sus credenciales de MySQL y comience a gestionar sus bases de datos.

## Contribución
Si desea contribuir a MySQL Application, por favor siga estos pasos:

1. Haga un fork del repositorio.
2. Cree una nueva rama (`git checkout -b feature/nueva-caracteristica`).
3. Realice sus cambios y haga commit (`git commit -am 'Añadir nueva característica'`).
4. Haga push a la rama (`git push origin feature/nueva-caracteristica`).
5. Cree un nuevo Pull Request.

## Licencia
Este proyecto está licenciado bajo la Licencia MIT. Consulte el archivo [LICENSE](LICENSE) para obtener más detalles.

## Contacto
Para preguntas o soporte, por favor abra un issue en el repositorio o contacte con el autor a través de [correo electrónico](mailto:autor@example.com).
