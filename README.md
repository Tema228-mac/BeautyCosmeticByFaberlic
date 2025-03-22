<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BeautyCosmetic By Faberlic</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <h1>BeautyCosmetic By Faberlic</h1>
    </header>
    <nav>
        <ul>
            <li><a href="#">Новинки</a></li>
            <li><a href="#">Косметика</a></li>
            <li><a href="#">Макияж</a></li>
            <li><a href="#">Парфюмерия</a></li>
            <li><a href="#">Одежда</a></li>
            <li><a href="#">Здоровье</a></li>
            <li><a href="#">Дом</a></li>
        </ul>
    </nav>
    <main>
        <h2>Добро пожаловать в BeautyCosmetic!</h2>
        <p>Выбирайте лучшие товары для красоты и ухода.</p>
    </main>
    <script src="script.js"></script>
</body>
</html>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    background: linear-gradient(135deg, #0033cc, #66ccff);
    color: white;
    text-align: center;
}

header {
    padding: 20px;
    font-size: 1.5em;
}

nav {
    background: rgba(0, 0, 0, 0.2);
    padding: 10px;
}

nav ul {
    list-style: none;
    padding: 0;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

nav ul li {
    margin: 10px;
}

nav ul li a {
    text-decoration: none;
    color: white;
    font-weight: bold;
    padding: 8px 12px;
    border-radius: 5px;
    transition: 0.3s;
}

nav ul li a:hover {
    background: rgba(255, 255, 255, 0.3);
}

main {
    padding: 20px;
}
window.onload = function () {
    if (window.Telegram.WebApp) {
        Telegram.WebApp.expand(); // Разворачивает приложение на весь экран
    }
};
