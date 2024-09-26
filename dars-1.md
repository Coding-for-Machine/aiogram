## Aiogram 1-dars

```bash
python3 -m venv myenv
source myenv/bin/activate
```
```bash
pip install aiogram
```
```bash
pip list
or
pip freeze
```
```bash
pip freeze > requirements.txt
```

### 1-missol
```python
import asyncio
from aiogram import Bot, Dispatcher

bot = Bot(token="") # <-- tokenni qavuslar orasiga qo'ying
dp = Dispatcher()

async def main():
    await dp.start_polling(bot)
    
asyncio.run(main())
```
### 2-misol
Dekoratorlar Python-da juda kuchli va foydali vositadir, chunki u dasturchilarga funksiya yoki sinfning xatti-harakatlarini o'zgartirishga imkon beradi. Dekoratorlar bizga o'ralgan funksiyaning harakatini doimiy ravishda o'zgartirmasdan kengaytirish uchun boshqa funktsiyani o'rashga imkon beradi. Ammo dekorativlarga chuqur sho'ng'ishdan oldin, dekorativlarni o'rganishda foydali bo'ladigan ba'zi tushunchalarni tushunib olaylik.
<br>

```python
import asyncio
from aiogram import Bot, Dispatcher, types
from aiogram.filters import CommandStart

bot = Bot(token="") # <-- tokenni qavuslar orasiga qo'ying
dp = Dispatcher()

@dp.message(CommandStart()) # <-- Dispatcher Decorators vazifani bajaradi
async def cmd_start(m: types.Message):
    await m.answer("Bu Start Cmd")
    
async def main():
    await dp.start_polling(bot)
    
asyncio.run(main())
```

### 3-Misol
```python
import logging
import asyncio
from aiogram import Bot, Dispatcher, types
from aiogram.filters import CommandStart

bot = Bot(token="7670506830:AAFXJsvNNew85PS8dJdlWf8geSLtav3SDeI") # <  tokenni qavuslar orasiga qo'ying
dp = Dispatcher()

@dp.message(CommandStart()) # <  Dispatcher Decorators vazifani bajaradi
async def cmd_start(m: types.Message):
    await m.answer("Bu Start Cmd")
    
async def main():
    await dp.start_polling(bot)

start_text = """"
          [ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ]
          [ ][ ][0][0][ ][ ][ ][0][0][0][ ][ ][0][ ][ ][ ][ ][0][ ]
          [ ][0][ ][ ][0][ ][ ][0][ ][ ][ ][ ][0][0][ ][ ][0][0][ ]
          [ ][0][ ][ ][ ][ ][ ][0][ ][ ][ ][ ][0][ ][0][0][ ][0][ ]
          [ ][0][ ][ ][ ][ ][ ][0][0][0][ ][ ][0][ ][  0 ][ ][0][ ]
          [ ][0][ ][ ][ ][ ][ ][0][ ][ ][ ][ ][0][ ][ ][ ][ ][0][ ]
          [ ][0][ ][ ][ ][ ][ ][0][ ][ ][ ][ ][0][ ][ ][ ][ ][0][ ]
          [ ][0][ ][ ][0][ ][ ][0][ ][ ][ ][ ][0][ ][ ][ ][ ][0][ ]
          [ ][ ][0][0][ ][ ][ ][0][ ][ ][ ][ ][0][ ][ ][ ][ ][0][ ]
          [ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ][ ]
          """
if __name__ == '__main__':
    try:
        print("exit", start_text)
        logging.basicConfig(level=logging.INFO) # 3   misolda qo'shildi. loyihamiz ishlayotganligi va ko'plam malumotlarni consolga chiqaradi 
        asyncio.run(main())
    except KeyboardInterrupt:
        print("[ ][ ][ ][ ][ ][ ][ ][ ][------ EXIT -----][ ][ ][ ][ ][ ][ ][ ][ ][ ]")
```

