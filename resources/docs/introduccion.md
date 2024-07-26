# <b>02</b> Cronstucción del Blog

¡Manos a la obra, vamos a crear un blog con Laravel que sea la envidia del internet! 😎

## Introducción

A continuación vamos a explicar nuestra aplicación en que consiste.

**Models**

-   Los Models(Modelos) son como las habitaciones de nuestro castillo.

    -   **User 👤:** (Usuario) El alma del blog, nuestros usuarios podrán registrarse, iniciar sesión y dejar comentarios.
    -   **Post 📝:** (Artículo) Aquí es donde la magia sucede, los posts tendrán el contenido que nuestros usuarios amarán.
    -   **Comment 💬:** (Comentario) La interacción es clave, los comentarios permitirán a los usuarios expresar sus opiniones y generar debate.

**Relationships**

-   Los Relationships(Relaciones entre modelos) son como los pasillos de nuestro castillo.

    -   Un usuario puede crear muchos posts. 👤 ➡️ 📝📝📝
    -   Un post puede tener muchos comentarios. 📝 ➡️ 💬💬💬
    -   Un comentario pertenece a un usuario y a un post. 💬 ➡️ 👤 & 📝

**Migrations**

-   las Migrations(Migraciones) son como las puertas, las ventanas, los closets, los baños, etc de las habitaciones del castillo.

    -   Con las migraciones vamos a crear las tablas de nuestra base de datos que darán vida a nuestros modelos. 🏗️

**Factories**

-   Los Factories(Fabricas) son como pequeñas fábricas que generan datos falsos para nuestros modelos. ¡Es como tener un equipo de escritores fantasmas que crean usuarios, articulos y comentarios para nosotros! 👻📝

**Seeders**

-   Los Seeders(Semillas) son como jardineros que plantan las semillas (datos) generadas por los factories en nuestra base de datos. 🌱

**Policies**

-   Los Policies(Politicas) son como los guardias de cada habitación de nuestro castillo. Ellos deciden quién puede entrar, quién puede hacer cambios y quién debe quedarse fuera. 💂‍♂️

**Requests**

-   Los Requests(Peticiones) son como los filtros de aire de nuestro castillo. Se aseguran de que solo entren datos limpios y seguros, evitando que los dragones (datos maliciosos) contaminen nuestro reino. 💨

**Repositories**

-   Los Repositorios(Repositorios) son como los bibliotecarios de nuestro castillo. Se encargan de organizar y gestionar el acceso a los libros (datos) de nuestra biblioteca (base de datos). 📚

**Services**

-   Los Services(Servicios) son como los consejeros del rey. Se encargan de la lógica de negocio de nuestra aplicación, tomando decisiones importantes y coordinando las acciones de los diferentes componentes. 🧠

**Controllers**

-   Los Controllers(Controladores) son los directores que se encargarán de manejar las peticiones de los usuarios, mostrar los posts, guardar los comentarios y mantener el orden en nuestro blog. 🎬

**Views**

-   Las Views(Vistas) son los escenarios en donde la magia visual sucede. Crearemos las plantillas Blade para mostrar los posts, los comentarios y los formularios para que los usuarios interactúen. 🎭

**Routes**

-   Las Routes(Rutas) son las caminos del castillo. rutas definirán las URLs de nuestro blog, como `/posts`, `/posts/{id}`, etc., para que los usuarios puedan navegar fácilmente. 🗺️

**10. Pruebas, los detectives:**

-   Escribiremos pruebas para asegurarnos de que todo funcione como debería y detectar errores antes de que los usuarios los encuentren. 🔎

Siguiente paso: [02.1 Modelos](./modelos)
