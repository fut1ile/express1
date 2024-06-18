# Описание приложения:
Данное Express-приложение определяет порт для прослушивания = 3000, реализует статическое обсулиживание файлов из директории 'public' (где находится файл index.html) и обрабатывает маршруты для '/about' и несуществующих страниц.

**index.html**

```html

<!DOCTYPE html>
<html>
  <head>
    <title>Простое приложение Express</title>
  </head>
  <body>
    <h1>Добро пожаловать в простое приложение Express!</h1>
  </body>
</html>
```
**app.js** 

```javascript
const express = require('express');
const app = express();
const port = 3000;

app.use(express.static('public'));

app.get('/about', (req, res) => {
res.send('Это простое приложение на Express.js');
});

app.use((req, res) => {
res.status(404).send('Страница не найдена');
});

app.listen(port, () => {
console.log(Сервер: http://localhost:${port});
});
```
**Инструкция по работе приложения**

Перед запуском проекта, необходимо убедиться в наличии Node.js и npm. Через npm можно установить необходимые зависимости (Express):

*npm install express*

Для запуска проекта необходимо ввести в терминале следующую команду: 

*node app.js* - данная команда запускает Express приложение на заданном порте (3000). В консоль выведется сообщение о запуске сервера и адрес. По нему можно перейти, чтобы проверить выполнение программы.

