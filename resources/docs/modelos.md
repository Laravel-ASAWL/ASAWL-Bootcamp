## <b>02.1</b> Modelos

¡Manos a la obra, esculpiendo los cimientos de nuestro blog! 🧱🔨

En Laravel, los modelos son como los pilares que sostienen toda la estructura de nuestra aplicación. Vamos a crear los tres pilares fundamentales de nuestro blog:

**1. User 👤:**

Este modelo representará a nuestros usuarios, los reyes y reinas de nuestro blog. 👑

```bash
code app/Models/User.php
```

Dentro de este modelo, definiremos los atributos que caracterizan a un usuario:

```php

```

**2. Post 📝:**

Aquí es donde la magia ocurre. Los posts serán el corazón de nuestro blog, el lugar donde nuestros usuarios compartirán sus ideas, historias y conocimientos. 🪄

```bash
php artisan make:model Post
```

Los atributos de un post podrían ser:

```php
// app/Models/Post.php
class Post extends Model
{
    protected $fillable = [
        'title',
        'content',
        'user_id', // Relación con el usuario que creó el post
    ];
}
```

**3. Comment 💬:**

Los comentarios son la chispa que enciende la conversación y el debate en nuestro blog. ¡Sin ellos, sería como un monólogo aburrido! 🔥

```bash
php artisan make:model Comment
```

Un comentario tendrá los siguientes atributos:

```php
// app/Models/Comment.php
class Comment extends Model
{
    protected $fillable = [
        'content',
        'user_id', // Relación con el usuario que escribió el comentario
        'post_id', // Relación con el post al que pertenece el comentario
    ];
}
```

¡Y eso es todo! Ya tenemos nuestros tres pilares listos para construir un blog increíble. Ahora, a seguir trabajando en las relaciones entre estos modelos, las migraciones para crear las tablas en la base de datos y mucho más. ¡Esto se pone cada vez más interesante! 🚀
