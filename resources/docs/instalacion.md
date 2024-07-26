## <b>01.2</b> Instalación

Ahora si ¡A darle caña al código, mis escuderos! 🛡️

> **Nota:**</br>
> Necesitarás una [versión de soportada de PHP](https://www.php.net/supported-versions.php) antes de continuar.
> Puedes probarlo con el comando `php -v`.
> Necesitarás una [versión de actualizada de Composer](https://www.php.net/supported-versions.php) antes de continuar.
> Puedes probarlo con el comando `composer -v`.

### Instalación de Laravel

¡Es hora de traer al escenario al framework más cool del reino! ✨

```bash
composer create-project laravel/laravel blog
```

¡Acción! Entra a la carpeta de tu proyecto y enciende el servidor de desarrollo: 🎬

```bash
cd blog
php artisan serve
```

¡Abre tu navegador y visita `http://127.0.0.1:8000` para ver la magia de Laravel en acción! 🎉

### Instalación de Laravel Jetstream

```shell
composer require laravel/jetstream
php artisan jetstream:install livewire --dark
php artisan migrate
```

¡Listo! Ya tienes instalado el sistema de auteticación y adminitrador de perfiles listo para ayudarte a crear aplicaciones web increíbles y seguras. 💪

### Instalación de Herramientas de seguridad

¡A blindar nuestro castillo, mis guardianes! ⚔️

#### 1. Roave/Security-Advisories, el sabio consejero

Este paquete nos mantendrá informados sobre vulnerabilidades conocidas en nuestras dependencias. ¡Como tener un oráculo que nos advierte de los peligros! 🧙‍♂️

```bash
composer require roave/security-advisories:dev-latest
```

#### 2. Enlightn/Security-Checker, el detective

Este paquete escaneará nuestro proyecto en busca de vulnerabilidades conocidas en las dependencias que usamos. ¡Un Sherlock Holmes para nuestro código! 🕵️‍♂️

```bash
composer require enlightn/security-checker:dev-latest
```

#### 3. Larastan, el arquitecto

Este paquete analizará nuestro código PHP en busca de errores y posibles vulnerabilidades. 🔎

```shell
composer require larastan/larastan:dev-latest
```

#### 4. Phan, el ingeniero

Este paquete analizará nuestro código PHP en busca de problemas que Larastan no detecta. 🔎🔍

```bash
composer require phan/phan:dev-latest
```

#### 5. PHPUnit, el framework de pruebas por excelencia

Este paquete nos permite escribir pruebas automatizadas para asegurarnos de que nuestro código funciona correctamente y no tiene vulnerabilidades. ✅

```bash
composer require phpunit/phpunit:dev-latest
```

#### 6. Laravel Pint, el mayordomo meticuloso

Este paquete limpiará y ordenará todo a su paso. 🧹

```bash
composer require laravel/pint:dev-latest
```

#### 7. Laravel Telescope, el ojo que todo lo ve

Este paquete te permite ver todo lo que sucede dentro de tu proyecto Laravel, desde las solicitudes que llegan hasta las consultas a la base de datos. 👁️

```bash
composer require laravel/telescope:dev-latest
```

¡Listo! Con estas herramientas de desarrollo, nuestra aplicación Laravel estará más segura que un búnker. 💪🔒

Siguiente paso: [01.3 Configuración](./configuracion)
