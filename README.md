# Laboratorio 2: Login y Registro en Laravel

Alumno: Diego Jaén
Curso: Ingeniería Web
Instructor: Ing. Irina Fong
Fecha: 29 de Septiembre 2025

## Prerrequisitos del laboratorio:

- PHP 8.2

- Laravel 11

- Composer 2.1

- MAMP (servidor local)

- MySQL 8 (incluido en MAMP)

- Apache (incluido en MAMP)

- macOS 12

- Visual Studio Code

- npm (se utilizó para Breeze)

🚀 Flujo de instalación y comandos utilizados

Crear el proyecto Laravel:

composer create-project laravel/laravel:^11.0 myapp
cd myapp


Instalar paquete de autenticación Breeze:

composer require laravel/breeze --dev
php artisan breeze:install blade


Instalar dependencias frontend:

npm install
npm run dev


Configuración de entorno:

cp .env.example .env
php artisan key:generate


Migraciones para crear las tablas:

php artisan migrate


Levantar servidor de desarrollo:

php artisan serve

🏗️ Introducción — Arquitectura MVC en Laravel

Laravel trabaja bajo el patrón Modelo–Vista–Controlador (MVC):

Models (app/Models) → representan las tablas de la base de datos y su lógica.

Controllers (app/Http/Controllers) → reciben la petición, procesan la lógica y retornan respuestas.

Views (resources/views) → contienen las plantillas Blade que generan la interfaz visual.

Routes (routes/web.php) → definen las rutas de la aplicación y a qué controlador/vista apuntan.

Para este laboratorio también utilizamos migraciones, que permiten versionar y crear tablas en la base de datos:

php artisan migrate

📷 Evidencias del laboratorio

Resultado visible del login, registro y dashboard:

(Login.png)
(Register.png)
(Dashboard.png)

🗄️ Base de Datos

Configuración en el archivo .env (usando MySQL de MAMP en el puerto 8889):

DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=8889
DB_DATABASE=myapp_db
DB_USERNAME=root
DB_PASSWORD=root


Migraciones ejecutadas con:

php artisan migrate


Backup de la base de datos generado con:

/Applications/MAMP/Library/bin/mysqldump -u root -p -P 8889 myapp_db > database/backups/backup_myapp.sql

Dificultades y Soluciones

Error: “Vite manifest not found at public/build/manifest.json”
Causa: no se habían compilado los assets de Vite.
Solución: ejecutar npm install && npm run dev o npm run build.

Error: “Could not open input file: artisan”
Causa: estaba fuera de la carpeta del proyecto.
Solución: entrar con cd ~/myapp antes de ejecutar comandos.

Error: Problemas instalando Composer con Homebrew (macOS 12.7 no soportado).
Solución: instalar Composer usando el PHP de MAMP en /usr/local/bin.

Confusión: En lugar de “Login/Register” aparecía “Dashboard”.
Explicación: eso ocurre porque ya había un usuario logueado; al cerrar sesión reaparecen las opciones de login/registro.

📚 Referencias

Documentación oficial de Laravel: https://laravel.com/docs

Documentación de Laravel Breeze: https://laravel.com/docs/starter-kits#breeze

Composer: https://getcomposer.org

✍️ Footer

Este laboratorio fue desarrollado como parte del curso Ingeniería Web de la Universidad Tecnológica de Panamá.

Estudiante: Diego Jaén
Correo: tu_correo@utp.ac.pa

Instructor: Ing. Irina Fong
Fecha de ejecución: Septiembre 2025
