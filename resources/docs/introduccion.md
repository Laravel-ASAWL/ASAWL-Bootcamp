# <b>02</b> Cronstucción del Blog

¡Manos a la obra, vamos a crear un blog con Laravel que sea la envidia del internet! 😎

## Introducción

A continuación vamos a explicar en que consiste nuestra aplicación web.

### Models

-   Los **modelos** son como las habitaciones de nuestro castillo.

    -   **User** El usuario 👤: El alma del blog, podrá registrarse, iniciar sesión, crear artículos y dejar comentarios.
    -   **Post** El artículo 📝: Donde la magia sucede, los artículos serán escritos por los usuarios escritores y tendrán el contenido que nuestros usuarios lectores amarán.
    -   **Comment** El comentario 💬: La interacción es clave, los comentarios permitirán a los usuarios expresar sus opiniones y generar debate.

### Relationships

-   Los **relaciones entre modelos** son como las conexiones entre las habitaciones de nuestro castillo.

    -   Un usuario puede crear muchos artículos. 👤 ➡️ 📝📝📝
    -   Un artículo puede tener muchos comentarios. 📝 ➡️ 💬💬💬
    -   Un comentario pertenece a un usuario y a un artículo. 💬 ➡️ 👤 & 📝

### Migrations

-   las **migraciones** son como las puertas, las ventanas, los closets, los baños, etc... de las habitaciones del castillo.

    -   Con las migraciones vamos a crear las tablas de nuestra base de datos que darán vida a nuestros modelos. 🏗️

### Factories y Seeders

-   Las **fabricas y semillas** son como magos que crean usuarios, articulos y comentarios para poblar nuestro castillo.

    -   En las fabricas se detalla el tipo de dato de cada una de las propiedades de nuestros modelos de pruebas. 
    -   En las semillas de datos se detallan el numero de registros que se crearán en nuestra base de datos. 🌱

### Policies

-   Las **políticas** son como los guardias de cada habitación de nuestro castillo. Ellos deciden quién puede entrar, quién puede hacer cambios y quién debe quedarse fuera. 💂‍♂️

    -   Las politicas ontrolan si un usuario puede crear, editar o eliminar un artículo o un comentario. 📝💬

### Services

-   Los **servicios** son como los consejeros del rey, tomando decisiones importantes y coordinando las acciones de los diferentes componentes. 🧠

    -   Los servicios se encargan de la lógica de negocio de nuestra aplicación web. 🧠

### Repositories

-   Los Repositorios(Repositorios) son como los bibliotecarios de nuestro castillo. Se encargan de organizar y gestionar el acceso a los libros (datos) de nuestra biblioteca (base de datos). 📚

### Requests

-   Los **peticiones** son como los requisitos mínimos para solicitar información en nuestro castillo. 📝💬

    -   Con las peticiones se asegura que los datos enviados en los formularios sean del tipo especifico. 📝💬

### Controllers

-   Los **controladores** son los directores de nuestro castillo. Se encargan de mantener en el orden a los visitantes. 🎬

    -   Los controladores se encargarán de manejar las peticiones de los visitantes, interactuan con las politicas y los servicios, ordenan a la vista mostrar la información requerida por el visitante. 👨‍💻


**Views**

-   Las Views(Vistas) son los escenarios en donde la magia visual sucede. Crearemos las plantillas Blade para mostrar los posts, los comentarios y los formularios para que los usuarios interactúen. 🎭

**Routes**

-   Las Routes(Rutas) son las caminos del castillo. rutas definirán las URLs de nuestro blog, como `/posts`, `/posts/{id}`, etc., para que los usuarios puedan navegar fácilmente. 🗺️

**10. Pruebas, los detectives:**

-   Escribiremos pruebas para asegurarnos de que todo funcione como debería y detectar errores antes de que los usuarios los encuentren. 🔎

Siguiente paso: [02.1 Modelos](./modelos)
