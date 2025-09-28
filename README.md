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

## Flujo de instalación y comandos utilizados

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

## Introducción — Arquitectura MVC en Laravel
Laravel trabaja bajo el patrón de arquitectura Modelo–Vista–Controlador (MVC), el cual organiza el desarrollo de aplicaciones de forma estructurada. Los Modelos representan y gestionan las tablas de la base de datos, permitiendo la interacción con la información. Los Controladores contienen la lógica que conecta las rutas con los modelos y las vistas, procesando las peticiones y devolviendo respuestas. Las Vistas, por su parte, son plantillas Blade que generan el contenido visual de la aplicación y se muestran al usuario. Finalmente, las Rutas definen la relación entre una URL y la acción que debe ejecutar la aplicación. En este laboratorio, además, se utilizaron las migraciones, una herramienta que permite versionar y crear las tablas necesarias en la base de datos de forma controlada, garantizando la reproducibilidad del entorno de trabajo.

## Evidencias del laboratorio

Resultado visible del login, registro y dashboard:

(Login.png)<img width="1438" height="828" alt="Screen Shot 2025-09-14 at 1 35 49 PM" src="https://github.com/user-attachments/assets/66f2753f-7213-46b4-8049-b5537e01ba9c" />

(Register.png)<img width="1434" height="840" alt="Screen Shot 2025-09-14 at 1 35 23 PM" src="https://github.com/user-attachments/assets/ab02d8f3-a53e-4926-8f52-a6ce41230be9" />

(Dashboard.png)<img width="1437" height="838" alt="Screen Shot 2025-09-14 at 1 36 05 PM" src="https://github.com/user-attachments/assets/fcd4fcb0-41a1-41d8-9312-a77930e51e3a" />


## Base de Datos

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

## Dificultades y Soluciones

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

## Referencias

Laravel. (s. f.). Laravel - The PHP Framework for Web Artisans. Recuperado el 28 de septiembre de 2025, de https://laravel.com/docs

Laravel. (s. f.). Starter Kits: Breeze. Recuperado el 28 de septiembre de 2025, de https://laravel.com/docs/starter-kits#breeze

Composer. (s. f.). Dependency Manager for PHP. Recuperado el 28 de septiembre de 2025, de https://getcomposer.org

## Footer

Este laboratorio fue desarrollado como parte del curso Ingeniería Web de la Universidad Tecnológica de Panamá.

Estudiante: Diego Jaén
Correo: diego.jaen2@utp.ac.pa
Curso: Ingeniería Web
Instructor: Ing. Irina Fong
Fecha de ejecución: Septiembre 2025
