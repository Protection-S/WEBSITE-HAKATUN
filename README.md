# СЛАВЯНСКИЙ БАСТИОН

## Описание проекта

Это ASP.NET Core веб-приложение, разработанное для учета проектов студентов. Приложение предоставляет возможность авторизации, регистрации пользователей, а также управления проектами и профилем пользователя. Существуют три основных контроллера: `HomeController`, `ProjectController`, `ProfileController`.

## Содержание

1. [Установка](#установка)
2. [Настройка](#настройка)
   1. [Настройка базы данных PostgreSQL](#настройка-базы-данных-postgresql)
   2. [Установка необходимых пакетов](#установка-необходимых-пакетов)
3. [Использование](#использование)
4. [Структура проекта](#структура-проекта)


## Установка

1. Склонируйте репозиторий:

   ```bash
   git clone https://github.com/ваш-юзернейм/ваш-репозиторий.git
2. Перейдите в директорию проекта:

cd ваш-репозиторий

3. Запустите приложение:
   
dotnet run

№ Настройка
1. Настройка базы данных PostgreSQL
Убедитесь, что у вас установлен сервер PostgreSQL. Если нет, скачайте и установите его с официального сайта PostgreSQL.

Откройте командную строку PostgreSQL и создайте базу данных для вашего приложения:

psql -U ваш_пользователь -c "CREATE DATABASE Название_БД;"

2. В файле appsettings.json укажите строку подключения к вашей базе данных:

{
  "ConnectionStrings": {
    "DefaultConnection": "Host=localhost;Port=5432;Database=Название_БД;Username=ваш_пользователь;Password=ваш_пароль;"
  },
  // Другие настройки...
}

# Установка необходимых пакетов

1. Откройте консоль диспетчера пакетов NuGet:
   dotnet restore
2. Установите пакеты Entity Framework:

dotnet add package Microsoft.EntityFrameworkCore
dotnet add package Npgsql.EntityFrameworkCore.PostgreSQL

3. Примените миграции для создания таблиц в базе данных:

dotnet ef migrations add ИмяВАШЕЙМИГРАЦИИ
dotnet ef database update

4.Убедитесь, что вы в корневой папке проекта, где находится файл Startup.cs.

Примечание: Если команды dotnet ef не распознаются, установите инструменты Entity Framework:

dotnet tool install --global dotnet-ef

# Использование

1. Запустите приложение.
2. Перейдите по адресу http://localhost:5000 в вашем веб-браузере.
3. Авторизуйтесь или зарегистрируйтесь.
4. Используйте кнопки "Проекты" и "Профиль" для управления проектами и профилем соответственно.

# Структура проекта

Controllers/: Контроллеры приложения.
HomeController.cs: Контроллер для домашней страницы.
ProjectController.cs: Контроллер для управления проектами.
ProfileController.cs: Контроллер для управления профилем пользователя.
Views/: Представления для контроллеров.
Models/: Модели данных приложения.
wwwroot/: Статические ресурсы, такие как CSS, JavaScript и изображения.
appsettings.json: Конфигурационные настройки приложения.


