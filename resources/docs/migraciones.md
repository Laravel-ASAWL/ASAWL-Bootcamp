## <b>02.2</b> Migraciones

¡Manos a la obra, arquitectos de la base de datos! 👷‍♂️🏗️

Ahora que tenemos los planos de nuestro blog (los modelos `User`, `Post` y `Comment`), es hora de construir los cimientos: las tablas de la base de datos. Para eso, usaremos las migraciones de Laravel, una herramienta que nos permite definir la estructura de nuestras tablas de forma ordenada y segura.

**1. Migración para la tabla `users`:**

Esta migración viene por defecto en la instalación de Laravel y es modificada automáticamente en la isntalación de Laravel Jetstrea, por tanto no hay cambios que realizar.

```php filename=database/migrations/xxxx_xx_xx_xxxxxx_create_users_table.php
use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     */
    public function up(): void
    {
        Schema::create('users', function (Blueprint $table) {
            $table->id();
            $table->string('name');
            $table->string('email')->unique();
            $table->timestamp('email_verified_at')->nullable();
            $table->string('password');
            $table->rememberToken();
            $table->foreignId('current_team_id')->nullable();
            $table->string('profile_photo_path', 2048)->nullable();
            $table->timestamps();
        });

        Schema::create('password_reset_tokens', function (Blueprint $table) {
            $table->string('email')->primary();
            $table->string('token');
            $table->timestamp('created_at')->nullable();
        });

        Schema::create('sessions', function (Blueprint $table) {
            $table->string('id')->primary();
            $table->foreignId('user_id')->nullable()->index();
            $table->string('ip_address', 45)->nullable();
            $table->text('user_agent')->nullable();
            $table->longText('payload');
            $table->integer('last_activity')->index();
        });
    }

    /**
     * Reverse the migrations.
     */
    public function down(): void
    {
        Schema::dropIfExists('users');
        Schema::dropIfExists('password_reset_tokens');
        Schema::dropIfExists('sessions');
    }
};
```

**2. Migración para la tabla `posts`:**

```bash
php artisan make:migration create_posts_table
```

En esta migración, definiremos los campos de la tabla `posts`, incluyendo la relación con la tabla `users`:

```php filename=database/migrations/xxxx_xx_xx_xxxxxx_create_posts_table.php
use App\Models\User;
use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     */
    public function up(): void
    {
        Schema::create('posts', function (Blueprint $table) {
            $table->id();
            $table->foreignIdFor(User::class)->constrained()->restrictOnDelete();
            $table->string('title');
            $table->string('slug')->unique();
            $table->text('description');
            $table->longText('body');
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     */
    public function down(): void
    {
        Schema::dropIfExists('posts');
    }
};
```

**3. Migración para la tabla `comments`:**

```bash
php artisan make:migration create_comments_table
```

Aquí definiremos los campos de la tabla `comments`, incluyendo las relaciones con las tablas `users` y `posts`:

```php filename=database/migrations/xxxx_xx_xx_xxxxxx_create_comments_table.php
use App\Models\Post;
use App\Models\User;
use Illuminate\Database\Migrations\Migration;
use Illuminate\Database\Schema\Blueprint;
use Illuminate\Support\Facades\Schema;

return new class extends Migration
{
    /**
     * Run the migrations.
     */
    public function up(): void
    {
        Schema::create('comments', function (Blueprint $table) {
            $table->id();
            $table->foreignIdFor(User::class)->constrained()->restrictOnDelete();
            $table->foreignIdFor(Post::class)->constrained()->cascadeOnDelete();
            $table->text('body');
            $table->timestamps();
        });
    }

    /**
     * Reverse the migrations.
     */
    public function down(): void
    {
        Schema::dropIfExists('comments');
    }
};
```

**¡A construir!**

Una vez que tengamos nuestras migraciones listas, ejecutamos el siguiente comando para crear las tablas en nuestra base de datos:

```bash
php artisan migrate
```

¡Listo! Ya tenemos los cimientos de nuestro blog listos para empezar a construir sobre ellos. ¡Ahora viene la parte divertida de darle vida a nuestro blog con controladores, vistas y rutas! 🚀

Siguiente paso: [<b>02.3</b> Controladores](./controladores)