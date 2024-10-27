from aiogram import Bot, Dispatcher, executor, types
from aiogram.contrib.fsm_storage.memory import MemoryStorage
api = "*********************************************"
bot = Bot(token=api)
dp = Dispatcher(bot, storage=MemoryStorage())


@dp.message_handler(commands=['start'])
async def start_message (message):
    print('Привет! Я бот, помогающий твоему здоровью.')
    await message.answer ('Привет! Я бот, помогающий твоему здоровью.')

#обработка нетипичноего сообщения
@dp.message_handler()
async def all_message(message):
    #print(f"Иное сообщение, {message}")
    print('Введите команду /start, чтобы начать общение.')
    await message.answer ('Введите команду /start, чтобы начать общение.')



if __name__ == '__main__':
    print("Begin")
    executor.start_polling(dp, skip_updates = True)
