from telegram import Update, InlineKeyboardButton, InlineKeyboardMarkup
from telegram.ext import Updater, CommandHandler, CallbackQueryHandler, CallbackContext

# Список товаров
products = [
    {"name": "Помада", "price": "300 рублей"},
    {"name": "Тушь", "price": "500 рублей"},
    {"name": "Крем для лица", "price": "800 рублей"},
]

# Функция для обработки команды /start
def start(update: Update, context: CallbackContext):
    keyboard = [[InlineKeyboardButton("Показать товары", callback_data='show_products')]]
    reply_markup = InlineKeyboardMarkup(keyboard)
    update.message.reply_text('Добро пожаловать в магазин косметики! Выберите действие:', reply_markup=reply_markup)

# Функция для показа товаров
def show_products(update: Update, context: CallbackContext):
    keyboard = []
    for product in products:
        button_text = f"{product['name']} - {product['price']}"
        keyboard.append([InlineKeyboardButton(button_text, callback_data=product['name'])])
    
    reply_markup = InlineKeyboardMarkup(keyboard)
    update.callback_query.edit_message_text(text='Выберите товар:', reply_markup=reply_markup)

# Функция обработки выбора товара
def buy_product(update: Update, context: CallbackContext):
    product_name = update.callback_query.data
    product = next((p for p in products if p['name'] == product_name), None)
    
    if product:
        update.callback_query.edit_message_text(text=f"Вы выбрали: {product['name']}.\nЦена: {product['price']}. Для завершения покупки свяжитесь с нами.")
    else:
        update.callback_query.edit_message_text(text="Товар не найден.")

def main():
    # Вставьте ваш токен
    updater = Updater("YOUR_TOKEN", use_context=True)
    
    # Получение диспетчера для регистрации обработчиков
    dp = updater.dispatcher
    
    # Регистрация обработчиков команд
    dp.add_handler(CommandHandler("start", start))
    dp.add_handler(CallbackQueryHandler(show_products, pattern='show_products'))
    dp.add_handler(CallbackQueryHandler(buy_product))
    
    # Запуск бота
    updater.start_polling()
    updater.idle()

if __name__ == '__main__':
    main()
****
