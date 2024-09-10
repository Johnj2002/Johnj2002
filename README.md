from telegram import Update
from telegram.ext import Updater, CommandHandler, MessageHandler, Filters, CallbackContext

TOKEN = '7500623654:AAEeKoCh1yW1OhuhGanB_jtg85r5Im4Qcyg'

def start(update: Update, context: CallbackContext) -> None:
    update.message.reply_text('Bonjour ! Je suis votre bot.')

def echo(update: Update, context: CallbackContext) -> None:
    update.message.reply_text(update.message.text)

def main():
    updater = Updater(7500623654:AAEeKoCh1yW1OhuhGanB_jtg85r5Im4Qcyg)

    dispatcher = updater.dispatcher

    dispatcher.add_handler(CommandHandler("start", start))
    dispatcher.add_handler(MessageHandler(Filters.text & ~Filters.command, echo))

    updater.start_polling()
    updater.idle()

if __name__ == '__main__':
    main()
  
