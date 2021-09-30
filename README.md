# Kryton-Bot
# Hola amigxs  aqui les vengo a mostrar unas lineas de comando que le seran muy util y de gran ayuda para su primer BOT de Telegram ...
import telebot

bot = telebot.TeleBot("TOKEN")

@bot.message_handler(commands=["start"])
def send_welcome (message):
    print(message)
    chatid = message.chat.id
    nombreUsuario =  message.chat.username
    saludo = "Hola {nombre}, Bienvenido a nuestro BOT"
    bot.send_message(chatid, saludo.format(nombre=nombreUsuario))
    #bot.reply_to(message, "Hola, En que puedo ayudarte?")

@bot.message_handler(commands=["chao"])
def send_welcome(message):
    print(message)
    chatid = message.chat.id
    nombreUsuario = message.chat.username
    chao = "Chao {nombre} , Gracias por usar este BOT"
    bot.send_message(chatid, chao.format(nombre=nombreUsuario))

@bot.message_handler(commands=["help"])
def send_welcome(message):
    print(message)
    chatid = message.chat.id
    nombreUsuario = message.chat.username
    ayuda = "Dime {nombre} , en que te podemos ayudar"
    bot.send_message(chatid, ayuda.format(nombre=nombreUsuario))

@bot.message_handler(func=lambda m: True)
def echo_all(message):
    chatid = message.chat.id
    bot.send_message(chatid, "POR EL MOMENTO ESTE BOT SOLO ACEPTA EL COMANDO /start , /help y /chao ...")

print("EL B O T se esta ejecutando")

bot.polling()
