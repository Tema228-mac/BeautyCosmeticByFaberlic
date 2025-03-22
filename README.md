<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Магазин</title>
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <style>
        body { text-align: center; font-family: Arial, sans-serif; }
        button { padding: 10px 20px; font-size: 18px; margin-top: 20px; }
    </style>
</head>
<body>
    <h1>Добро пожаловать в магазин!</h1>
    <p>Вы можете заказать косметику прямо здесь.</p>
    <button id="buyButton">Купить</button>
    
    <script>
        let tg = window.Telegram.WebApp;
        tg.expand(); // Развернуть на весь экран

        document.getElementById("buyButton").addEventListener("click", function() {
            tg.sendData("Пользователь хочет купить товар!"); // Отправка данных в бота
            tg.close(); // Закрытие Mini App
        });
    </script>
</body>
</html>
