# <b>02.</b> Instalando el trío dinámico: Laravel, Pint y Jetstream 😎

> **Note**
> Necesitarás una [versión de soportada de PHP](https://www.php.net/supported-versions.php) antes de continuar. Puedes probarlo con el comando `php -v`.
> Necesitarás una [versión de actualizada de Composer](https://www.php.net/supported-versions.php) antes de continuar. Puedes probarlo con el comando `php -v`.

1. **Laravel, el maestro de ceremonias:**

Empezamos invocando al mismísimo Laravel con este conjuro mágico en nuestra terminal:

```shell
composer require laravel/laravel blog
```

¡Pum! ✨ Un nuevo proyecto Laravel aparece de la nada, listo para ser moldeado a nuestro antojo.

2. **Pint, el estilista del código:**

Laravel dispone de un estilista de código mediante Pint, así que no hay que hacer mucho lío para instalarlo, solo con un simple:

```shell
composer require laravel/pint --dev
```

un simple archivo de configuración:

```json filename=pint.json
{
    "preset": "laravel",
    "rules": {
        "simplified_null_return": true,
        "braces": false,
        "new_with_braces": {
            "anonymous_class": false,
            "named_class": false
        }
    }
}
```

...y Pint estará listo para poner orden en nuestro código, dejándolo más bonito que un jardín zen. 💅

3. **Jetstream, el piloto automático:**

Ahora viene lo bueno: Jetstream, que nos ahorra un montón de trabajo con la autenticación y la interfaz de usuario. Lo invocamos con:

```shell
composer require laravel/jetstream
```

Luego, elegimos nuestro stack preferido Livewire(Blade) o Inertia(VueJS) y desatamos su poder:

```shell
php artisan jetstream:install livewire --dark
```

¡Y voilá! ✨ Jetstream despliega sus alas y nos proporciona un sistema de autenticación y una interfaz de usuario que quitan el hipo. 🚀

Con este trío dinámico instalado, estamos listos para crear aplicaciones Laravel que sean seguras, elegantes y funcionales. ¡A darle caña al código! 👨‍💻
