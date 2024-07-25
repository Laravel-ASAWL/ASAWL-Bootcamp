## <b>01.3</b> Configuración

¡Afinando las defensas de nuestro castillo Laravel! 🏰⚙️

Una vez que hemos equipado nuestro castillo con las mejores herramientas de seguridad (SCA, SAST, pruebas, Pint y Telescope), es hora de configurarlas para que funcionen a la perfección. ¡Es como que nuestro castillo sea inexpugnable! 🛡️

```shell
code phpstan.neon
```

```neon filename=phpstan.neon
includes:
    - vendor/larastan/larastan/extension.neon

parameters:
    paths:
        - app/
    level: 9
    excludePaths:
        - vendor/
```

```bash
code .phan/config.php
```

```php filename=.phan/config.php
<?php

return [
    'target_php_version' => 8.1,

    'directory_list' => [
        'app/',
        'database/',
        'resources/',
        'routes/',
        'tests/',
    ],

    'exclude_file_regex' => '@^vendor/.*/(tests?|Tests?)/@',

    'exclude_analysis_directory_list' => [
        'vendor/',
    ],

    'suppress_issue_types' => [
        'PhanRedundantArrayValuesCall',
        'PhanSuspiciousWeakTypeComparison',
        'PhanTypeMismatchPropertyDefault',
        'PhanUndeclaredClassInstanceof',
        'PhanUndeclaredClassMethod',
        'PhanUndeclaredClassReference',
        'PhanUndeclaredExtendedClass',
        'PhanUndeclaredFunction',
        'PhanUndeclaredInterface',
        'PhanUndeclaredMethod',
        'PhanUndeclaredProperty',
        'PhanUndeclaredStaticMethod',
        'PhanUndeclaredThis',
        'PhanUndeclaredTrait',
        'PhanUndeclaredTypeParameter',
        'PhanUndeclaredTypeReturnType',
    ],
];
```

```bash
code phpunit.xml
```

```xml filename=phpunit.xml
<?xml version="1.0" encoding="UTF-8"?>
<phpunit xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:noNamespaceSchemaLocation="vendor/phpunit/phpunit/phpunit.xsd"
         bootstrap="vendor/autoload.php"
         colors="true"
>
    <testsuites>
        <testsuite name="Feature">
            <directory>tests/Feature</directory>
        </testsuite>
        <testsuite name="Unit">
            <directory>tests/Feature/Database</directory>
        </testsuite>
    </testsuites>
    <source>
        <include>
            <directory>app</directory>
        </include>
    </source>
    <php>
        <env name="APP_ENV" value="testing"/>
        <env name="APP_MAINTENANCE_DRIVER" value="file"/>
        <env name="BCRYPT_ROUNDS" value="4"/>
        <env name="CACHE_STORE" value="array"/>
        <env name="DB_CONNECTION" value="sqlite"/>
        <env name="DB_DATABASE" value=":memory:"/>
        <env name="MAIL_MAILER" value="array"/>
        <env name="PULSE_ENABLED" value="false"/>
        <env name="QUEUE_CONNECTION" value="sync"/>
        <env name="SESSION_DRIVER" value="array"/>
        <env name="TELESCOPE_ENABLED" value="false"/>
    </php>
</phpunit>
```

```shell
code pint.json
```

```json filename=pint.json
{
    "preset": "laravel",
    "rules": {
        "control_structure_braces": false,
        "simplified_null_return": true,
        "braces": false,
        "new_with_braces": {
            "anonymous_class": false,
            "named_class": false
        }
    }
}
```

```shell
code composer.json
```

```json filename=composer.json
{
    ...
    "scripts": {
        "check": [
            "composer update",
            "composer sca",
            "composer sast",
            "composer test"
        ],
        "sca": [
            "composer diagnose",
            "composer audit",
            "vendor/bin/security-checker security:check"
        ],
        "sast": [
            "vendor/bin/phpstan analyse",
            "vendor/bin/phan --allow-polyfill-parser"
        ],
        "test": [
            "pint",
            "@php artisan test"
        ]
    },
    ...
}
```

¡Con una buena configuración, nuestras herramientas de seguridad trabajarán juntas como un equipo bien coordinado, protegiendo tu castillo de cualquier dragón que ose acercarse! 🏰🛡️

### ¡A analizar!

Cuando escuchemos que los dragones se acercan a tu castillo, mientras contruimos nuestro Blog ejecutamos el único comando para que haga su trabajo:

```bash
composer check
```

Posterior si encuentra alguna vulnerabilidad, nos avisará con un informe detallado. ¡Vamos a corregir esos errores y a dormir tranquilos! 😴

¡Listo! Con estas herramientas, nuestra aplicación Laravel estará más segura que un búnker. 💪🔒

Siguiente paso: [02. Construcción del Blog](./introduccion)
