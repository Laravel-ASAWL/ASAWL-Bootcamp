# <b>01.</b> Seguridad en Laravel

¡A blindar nuestro Laravel como un verdadero fuerte! 🏰🔒

## <b>01.1</b> Herramientas de Seguridad

Imagina que tu aplicación de Laravel es un castillo y los errores y vulnerabilidades son dragones que quieren robar tus tesoros (datos de usuarios, información confidencial, etc.). Las herramientas de seguridad web en Laravel es como construir murallas, fosos y torres de vigilancia para proteger tu castillo. 🛡️⚔️

Laravel ya viene con varias medidas de seguridad incorporadas, pero siempre podemos reforzarlas. ¡Vamos a equiparnos con las mejores herramientas para defender nuestro reino! 💪

### 1. Análisis de Composición de Software

**¡SCA al rescate! 🦸‍♂️🔍**

Imagina que tu castillo está construido con diferentes tipos de bloques (dependencias de terceros). Algunos de estos bloques pueden ser débiles o tener grietas por donde los dragones (vulnerabilidades) pueden colarse. 🐉🧱

- Roave/Security-Advisories: Nuestro consejero que nos avisa de vulnerabilidades conocidas en nuestras dependencias. 🧙‍♂️
- Enlightn/Security-Checker: El detective que escanea nuestro código en busca de problemas de seguridad. 🕵️‍♂️

El SCA como un inspector de edificios que revisa cada bloque de tu castillo y te avisa si encuentra alguno defectuoso. 🐉🧱🧙‍♂️🕵️‍♂️

### 2. Pruebas Estáticas de Análisis de Seguridad

**¡SAST, el arquitecto e ingeniero de la seguridad! 👷‍♂️🏰**

Imagina que en la construcción del castillo, no estás seguro de si los planos (código) son 100% seguros. Podrían haber errores de diseño que los dragones puedan aprovechar. 🐉🏰
 
- Larastan: Nuestro artiquecto que analiza nuestro código PHP en busca de errores y posibles vulnerabilidades. 🔎
- Phan: Nuestro ingeniero Otra herramienta de análisis estático que puede encontrar problemas que Larastan no detecta. 🔎🔍
 
El SAST como un arquitecto y un ingeniero experto que revisan tus planos con lupa, buscando posibles puntos débiles antes de que el castillo esté terminado. 🐉🏰🔎🔍

### 3. Pruebas de Código

**¡Testing, los caballeros guardianes de tu castillo! 🛡️⚔️**

Imagina que tu castillo ya está construido, pero quieres asegurarte de que resistirá cualquier ataque de los dragones. 🐉🏰

- PHPUnit: El framework de pruebas por excelencia para Laravel. Nos permite escribir pruebas automatizadas para asegurarnos de que nuestro código funciona correctamente y no tiene vulnerabilidades. ✅

Las pruebas de código son como un ejército de caballeros que simulan diferentes escenarios de batalla para poner a prueba las defensas de tu castillo. 🐉🏰✅

### 4. Otras herramientas

**¡PINT y Telescope, los guardianes del orden y la armonía en tu castillo! 🏰✨**

#### Laravel Pint, el mayordomo meticuloso 🧹🤵‍♂️

Imagina que tu castillo es un palacio gigante, lleno de habitaciones (archivos) y pasillos (código). Con el tiempo, el polvo (errores de formato) se acumula y el caos reina. ¡PINT al rescate!

PINT es como un mayordomo meticuloso que recorre cada rincón de tu castillo, limpiando y ordenando todo a su paso. 🧹✨
 
#### Laravel Telescope, el ojo que todo lo ve 🔭👁️

Telescope es como un ojo mágico que te permite ver todo lo que sucede dentro de tu castillo, desde las solicitudes que llegan hasta las consultas a la base de datos. 👁️✨ 

¡Con estas herramientas, nuestra aplicación Laravel será una fortaleza inexpugnable! 💪🏰

Siguiente paso: [01.2 Instalación](./instalacion)
