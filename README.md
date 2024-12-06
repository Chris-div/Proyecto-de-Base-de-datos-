# 📚 Sistema Gestión de Biblioteca 📚

## 📄 Documentación del Proyecto 📄

### Enlace al prototipo en Figma

Puedes acceder al prototipo del sistema en Figma a través del siguiente enlace:  
[🔗 Accede al proyecto en Figma aquí](https://www.figma.com/design/qEbw0wGUj4szuVZkRE92yI/Untitled?node-id=0-1&t=9pNCrB56HUAFdb2S-1)

### Tabla de Contenidos

1. [📄 Introducción 📄](#📄-introducción-📄)

2. [🎯 Objetivo del Proyecto 🎯](#🎯-objetivo-del-proyecto-🎯)

3. [📌 Funcionalidades Principales 📌](#📌-funcionalidades-principales-📌)

4. [📂 Módulos del Sistema 📂](#📂-módulos-del-sistema-📂)

5. [🗂️ Estructura de la Base de Datos 🗂️](#🗂️-estructura-de-la-base-de-datos-🗂️)

6. [🔗 Relaciones Principales 🔗](#🔗-relaciones-principales-🔗)

7. [🛠️ Tecnologías Utilizadas 🛠️](#🛠️-tecnologías-utilizadas-🛠️)

8. [📚 Conclusiones y Próximos Pasos 📚](#📚-conclusiones-y-próximos-pasos-📚)


---

## 📄 Introducción 📄

La biblioteca es un recurso clave para la comunidad académica, proporcionando acceso a libros, revistas, tesis, tablets, computadoras y espacios de trabajo colaborativo. Sin embargo, la gestión manual de préstamos, devoluciones y reservas puede resultar ineficiente y propensa a errores.  

Este proyecto busca implementar un **sistema de gestión integral de biblioteca** que optimice y automatice estos procesos. La solución se centra en cubrir las necesidades específicas de los  usuarios.

## 🎯 Objetivo del Proyecto 🎯

El objetivo principal de este proyecto es **diseñar e implementar un sistema de gestión integral para la biblioteca** que permita optimizar los procesos de registro, préstamo, devolución y reserva de recursos, garantizando un uso eficiente y transparente de los mismos.  

### Objetivos Específicos:  
1. **Automatizar la gestión de préstamos y devoluciones:**  
   Reducir el tiempo y los errores asociados a los registros manuales mediante la implementación de procedimientos almacenados y controles automáticos en la base de datos.  

2. **Facilitar la administración de reservas:**  
   Proporcionar un módulo de reservas de cubículos que asegure la disponibilidad y evite conflictos de horarios entre los usuarios.  

3. **Mejorar la experiencia de los usuarios:**  
   Ofrecer una solución clara y organizada que permita a estudiantes acceder fácilmente a los recursos de la biblioteca.  

4. **Centralizar y estructurar la información:**  
   Diseñar una base de datos relacional que consolide los datos de usuarios, recursos y reservas, facilitando la trazabilidad y la gestión.  

5. **Proveer herramientas de análisis:**  
   Implementar reportes dinámicos y visualizaciones con Power BI para identificar patrones de uso, recursos más demandados y necesidades futuras.  

6. **Fomentar la sostenibilidad del sistema:**  
   Asegurar que el diseño y la estructura del sistema permitan futuras ampliaciones o integraciones con otros sistemas del instituto.  

Este proyecto busca no solo cubrir las necesidades actuales de la biblioteca, sino también ofrecer una base sólida para el crecimiento y la mejora continua.  


El sistema incluye módulos para:  
- Registrar y mantener la información de los usuarios y recursos.  
- Administrar el ciclo completo de préstamos y devoluciones.  
- Gestionar reservas de cubículos para trabajo en equipo con horarios claros.  
- Generar reportes detallados para facilitar la toma de decisiones informadas.  

Además, se ha diseñado una base de datos relacional robusta con más de 15 tablas interconectadas, procedimientos almacenados para automatizar tareas repetitivas, permitiendo identificar tendencias y optimizar la asignación de recursos.  

Este sistema no solo mejora la eficiencia operativa de la biblioteca, sino que también proporciona a la comunidad académica una experiencia de usuario más fluida y satisfactoria.  



---

## 📌 Funcionalidades Principales 📌

1. **Gestión de Usuarios:**
   - Registro y actualización de información de estudiantes, docentes y personal administrativo.
   - Relación de usuarios con departamentos y carreras.

2. **Gestión de Recursos:**
   - Control de préstamos de libros, revistas y tesis
   - Reglas específicas según el tipo de usuario y recurso.

3. **Reservas:**
   - Reserva de cubículos para trabajo en equipo.
   - Control de horarios y disponibilidad.

4. **Procedimientos Automatizados:**
   - Procedimientos almacenados para agilizar la gestión de préstamos y devoluciones.
   - Generación de reportes de uso y disponibilidad de recursos.

5. **Análisis y Reportes:**
   - Reportes dinámicos sobre el uso de recursos y comportamiento de los usuarios.
   - Visualización de datos a través de Power BI.
---

## 📂 Módulos del Sistema 📂

| **Módulo**           | **Descripción**                                                              |
| -------------------- | ---------------------------------------------------------------------------- |
| **Administrador**    | Registro, consulta y gestión de la información personal.                     |
| **Alumno**           | Permite realizar préstamos a través de la plataforma.                        |
| **Préstamo**         | Gestión de programación y asignación de material bibliográfico.              |
| **Reserva**          | Gestión de programación y asignación de cubículos de trabajo en equipo.      |
| **Reporte**          | Almacenamiento de diagnósticos, tratamientos y resultados de consultas.      |

---


## 🗂️ Estructura de la Base de Datos 🗂️

### 📊 Esquema General
Este es un resumen completo de las tablas y relaciones de la base de datos del sistema de gestión biblioteca.

https://www.figma.com/design/qEbw0wGUj4szuVZkRE92yI/Untitled?node-id=0-1&node-type=canvas

>**Usuario**

- ID_Usuario INT ***PRIMARY KEY***,
- Nombre VARCHAR2(45) ***NOT NULL***,
- Correo VARCHAR2(45) ***NOT NULL UNIQUE***,
- ape_paterno VARCHAR2(45) ***NOT NULL***,
- ape_materno VARCHAR2(45) **NOT NULL**,
- Contraseña VARCHAR2(100) ***NOT NULL***,
- Telefono INT ***NOT NULL***,
- rol VARCHAR2(45) ***NOT NULL***,
- sexo VARCAHR2(45)***NOT NULL***,
- Fecha_nacimiento DATETIME ***DEFAULT CURRENT_TIMESTAMP***,


> **Sedes**

- IdSedes INT ***PRIMARY KEY***,
- Nombre VARCHAR2(50) ***NOT NULL***


> **Reservas**

- ID_Reserva INT ***PRIMARY KEY***,
- ID_Usuarios INT ***NOT NULL***,
- Fecha_inicio DATETIME ***DEFAULT CURRENT_TIMESTAMP***,
- Fecha_fin DATETIME ***DEFAULT CURRENT_TIMESTAMP***,
- ***FOREIGN KEY*** (Usuario_id) ***REFERENCES*** Usuarios(IdUsuarios),


> **Prestamos**

- IdPrestamo INT ***PRIMARY KEY***,
- Fecha_prestamo DATETIME ***DEFAULT CURRENT_TIMESTAMP***,
- Fecha_devolucion DATETIME,
- Fecha_devolucion_real DATETIME,
- estado VARCHAR2(45) ***NOT NULL***,
- ***FOREIGN KEY*** (Usuarios_id) ***REFERENCES*** Usuario(IdUsuarios),
- ***FOREIGN KEY*** (Recursos_id) ***REFERENCES*** Recurso(IdRecurso),
- ***FOREGIN KEY*** (Ejemplares_idEjemplares) ***REFERENCIA*** Ejemplares(IdEjemplares)

> **Recurso**

- IdRecurso INT ***PRIMARY KEY***,
- Nombre VARCHAR2(45) ***NOT NULL***,
- modelo VARCHAR2(45) ***NOT NULL***,
- estado VARCHAR2(45) ***NOT NULL***,
-Fecha_adquisión DATETIME ***NOT NULL***
 
> **Libros**

- IdLibros INT ***PRIMARY KEY***,
- IdRecurso INT ***UNIQUE NOT NULL***,
- Titulo VARCHAR2(255) ***NOT NULL***,
- IdAutor INT ***NOT NULL***,
- IdEditorial INT ***NOT NULL***,
- año_publicacion ***DATETIME***,
- Genero VARCHAR2(45) ***NOT NULL***,
- ***FOREIGN KEY*** (IdRecurso) ***REFERENCES*** Recurso(IdRecurso),
- ***FOREIGN KEY*** (IdAutor) ***REFERENCES*** Autores(IdAutores),
- ***FOREIGN KEY*** (IdEditoriales) ***REFERENCES*** Editoriales(IdEditorial)

> **Autores**

- IdAutores INT ***PRIMARY KEY***,
- Nombre VARCHAR2(45) ***NOT NULL***,
- ape_paterno VARCHAR2(45) ***NOT NULL***,
- ape_materno VARCHAR2(45) ***NOT NULL***,
- país VARCHAR2(45) ***NOT NULL***,
- Fecha_nacimineto ***DATETIME***

> **Editoriales**

- IdEditorial INT ***PRIMARY KEY***,
- Nombre VARCHAR2(45) ***NOT NULL***
- dirección VARCHAR2(45) ***NOT NULL***,
- telefono VARCHAR (45)  ***NOT NULL***,
- Correo   VARCHAR (45)  ***NOT NULL**,

> **Departamento**

- ID_Departamento INT ***PRIMARY KEY***,
- Nombre_Departamento VARCHAR(2100) ***NOT NUL***

---

>**Ebook**
- Idebook INT ***PRIMARY KEY***,
- titulo VARCHAR(45) ***NOT NULL***,
- año_publicacion ***DATETIME***,
- descripcion VARCHAR(45) ***NOT NULL***,
- idioma VARCHAR(45) ***NOT NULL***,
- eISBN VARCHAR(45)  ***NOT NULL***,
- num_paginas VARCHAR(45) ***NOT NULL***,
- descriptores VARCHAR(45) ***NOT NULL***,
- url VARCHAR(45) ***NOT NULL***,
- Editoriales_id INT ***NOT NULL***,
- Autores_id INT ***NOT NULL***,
- ***FOREIGN KEY*** (Editoriales_id) ***REFERENCES*** Editoriales(IdEditorial),
- ***FOREIGN KEY*** (Autores_id) ***REFERENCES*** Autores(IdAutores)

>**Penalizaciones**
- Id INT  PRIMARY KEY,
- tipo VARCHAR(45) ***NOT NULL***,
- estado VARCHAR(45) ***NOT NULL***,
- observacion VARCHAR(45) ***NOT NULL***,
- fecha_inicio DATETIME ***NOT NULL***,
- fecha_fin DATETIME ***NOT NULL***,
- Usuarios_id INT ***NOT NULL***,
- ***FOREIGN KEY*** (Usuarios_id) ***REFERENCES*** Usuarios(idUsuarios)

- **Espacio** 
- idEspacio INT PRIMARY KEY ***NOT NULL***,
- tipo VARCHAR(45) ***NOT NULL***,
- capacidad INT ***NOT NULL***,
- nombre VARCHAR(45) ***NOT NULL***,
- estado VARCHAR(45) ***NOT NULL***,
- caracteristicas VARCHAR(120) ***NOT NULLL***,
- ***FOREIGN KEY*** (Sedes_id) ***REFRENCIA*** Sedes(IdSedes)

## 🔗 Relaciones Principales 🔗

1.**Usuarios** se relaciona con:

 -**Reservas**,**Préstamos**,**Comentarios**


2.**Sedes** se relaciona a:

   -**Espacio**


3.**Recursos** se conecta a:

   -**Ejemplares**,**Préstamos**


4.**Reservas** tiene una relación con:
   
   -**Espacio**,**Usuarios**


5.**Prestamos** está relacionado con:
   
   -**Usuarios**,**Recursos**


6.**Libros** se relaciona con:
   
   -**Editoriales**,**Departamentos**,**Autores (mediante Libros_has_Autores)**


7.**Ebooks** tiene una relación con:
   
   -**Editoriales**,**Autores**

---

## 🛠️ Tecnologías Utilizadas 🛠️ 

| **Tecnología** | **Uso**                                              |
| -------------- | ---------------------------------------------------- | 
| **Oracle**     | Gestión de la base de datos relacional.              |
| **Figma**      | Para poder hacer el vosquejo de como se veria mi wed |     

---


## 📚 Conclusiones y Próximos Pasos 📚

> **Conclusiones:** Este diagrama muestra la estructura de una base de datos relacional con tablas que gestionan tanto los aspectos personales como administrativos de la biblioteca, permitiendo llevar un control de los usuarios/alumnos, préstamos, reservas y reportes.


> **Próximos pasos:** A medida que este sistema crezca, se podría considerar agregar funcionalidades como la integración con sistemas de penalización, control del material bibliográfico, y una interfaz de usuario más robusta.

---
