## <b>02.1</b> Modelos

¡Manos a la obra, esculpiendo los cimientos de nuestro blog! 🧱🔨

En Laravel, los modelos son como los pilares que sostienen toda la estructura de nuestra aplicación. Vamos a crear los tres pilares fundamentales de nuestro blog:

**1. User 👤:**

Laravel por defecto ya incluye User, este modelo representará a nuestros usuarios, los reyes y reinas de nuestro blog. 👑

```bash
code app/Models/User.php
```

Dentro de este modelo, definiremos los atributos que caracterizan a un usuario:

```php filename=app/Models/User.php
namespace App\Models;

use Database\Factories\UserFactory;
use Illuminate\Contracts\Auth\MustVerifyEmail;
use Illuminate\Database\Eloquent\Factories\Factory;
use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Relations\HasMany;
use Illuminate\Foundation\Auth\User as Authenticatable;
use Illuminate\Notifications\Notifiable;
use Laravel\Fortify\TwoFactorAuthenticatable;
use Laravel\Jetstream\HasProfilePhoto;
use Laravel\Sanctum\HasApiTokens;

class User extends Authenticatable implements MustVerifyEmail
{
    use HasApiTokens;
    use HasFactory;
    use HasProfilePhoto;
    use Notifiable;
    use TwoFactorAuthenticatable;

    /**
     * Create a new factory instance for the model.
     */
    protected static function newFactory(): Factory
    {
        return UserFactory::new();
    }

    /**
     * Determine if the user can view the Telescope.
     */
    public function scopeHasTelescopeAccess(): bool
    {
        return in_array($this->email, [
            __('wasal@example.com'),
        ]);
    }

    /**
     * The attributes that are mass assignable.
     *
     * @var array<int, string>
     */
    protected $fillable = [
        'name',
        'email',
        'password',
    ];

    /**
     * The attributes that should be hidden for serialization.
     *
     * @var array<int, string>
     */
    protected $hidden = [
        'password',
        'remember_token',
        'two_factor_recovery_codes',
        'two_factor_secret',
    ];

    /**
     * The accessors to append to the model's array form.
     *
     * @var array<int, string>
     */
    protected $appends = [
        'profile_photo_url',
    ];

    /**
     * Get the attributes that should be cast.
     *
     * @return array<string, string>
     */
    protected function casts(): array
    {
        return [
            'email_verified_at' => 'datetime',
            'password' => 'hashed',
        ];
    }

    /**
     * Get the posts for the user.
     */
    public function posts(): HasMany
    {
        return $this->hasMany(Post::class);
    }

    /**
     * Get the comments for the user.
     */
    public function comments(): HasMany
    {
        return $this->hasMany(Comment::class);
    }
}
```

**2. Post 📝:**

Aquí es donde la magia ocurre. Los posts serán el corazón de nuestro blog, el lugar donde nuestros usuarios compartirán sus ideas, historias y conocimientos. 🪄

```bash
php artisan make:model Post
```

Los atributos de un post podrían ser:

```php filename=app/Models/Post.php
namespace App\Models;

use Database\Factories\PostFactory;
use Illuminate\Database\Eloquent\Factories\Factory;
use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;
use Illuminate\Database\Eloquent\Relations\BelongsTo;
use Illuminate\Database\Eloquent\Relations\HasMany;

class Post extends Model
{
    use HasFactory;

    /**
     * Create a new factory instance for the model.
     */
    protected static function newFactory(): Factory
    {
        return PostFactory::new();
    }

    /**
     * The attributes that are mass assignable.
     *
     * @var array<int, string>
     */
    protected $fillable = [
        'id',
        'user_id',
        'title',
        'slug',
        'description',
        'body',
    ];

    /**
     * Get the user that owns the post.
     */
    public function user(): BelongsTo
    {
        return $this->belongsTo(User::class);
    }

    /**
     * Get the comments for the post.
     */
    public function comments(): HasMany
    {
        return $this->hasMany(Comment::class);
    }
}
```

**3. Comment 💬:**

Los comentarios son la chispa que enciende la conversación y el debate en nuestro blog. ¡Sin ellos, sería como un monólogo aburrido! 🔥

```bash
php artisan make:model Comment
```

Un comentario tendrá los siguientes atributos:

```php filename=app/Models/Comment.php
namespace App\Models;

use Database\Factories\CommentFactory;
use Illuminate\Database\Eloquent\Factories\Factory;
use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;
use Illuminate\Database\Eloquent\Relations\BelongsTo;

class Comment extends Model
{
    use HasFactory;

    /**
     * Create a new factory instance for the model.
     */
    protected static function newFactory(): Factory
    {
        return CommentFactory::new();
    }

    /**
     * The attributes that are mass assignable.
     *
     * @var array<int, string>
     */
    protected $fillable = [
        'id',
        'user_id',
        'post_id',
        'body',
    ];

    /**
     * Get the user that owns the comment.
     */
    public function user(): BelongsTo
    {
        return $this->belongsTo(User::class);
    }

    /**
     * Get the post that owns the comment.
     */
    public function post(): BelongsTo
    {
        return $this->belongsTo(Post::class);
    }
}
```

¡Y eso es todo! Ya tenemos nuestros tres pilares listos para construir un blog increíble y las relaciones entre estos modelos, Ahora, a trabajar en las migraciones para crear las tablas en la base de datos y mucho más. ¡Esto se pone cada vez más interesante! 🚀

Siguiente paso: [<b>02.2</b> Migraciones](./migraciones)
