# mrub
The official mrub repository, unofficial and high-speed library for rubika...
# how to install library
Enter the following command to install the library in your terminal
```
pip install mrub
```
# Web Socket Example
```
from mrub.socket import Client
import asyncio

socket = Client('YOUR-AUTH')
seened : list = []


async def main():
	while 1:
		async for chats in socket.handler():
			try:
				for chat in chats:
					if chat['object_guid'].startswith('g'):
						if not chat['object_guid'] + chat['chat']['last_message']['message_id'] in seened:
							text : str = chat['chat']['last_message']['text']
							print(text)
							seened.append(chat['object_guid'] + chat['chat']['last_message']['message_id'])
			except :
					...
```

This source code receives and prints the latest messages using the Rubica web socket

# روبی
مخزن رسمی روبی، کتابخانه غیر رسمی و پرسرعت روبیکا...

# مثال وب سوکت
```
from mrub.socket import Client
import asyncio

socket = Client('YOUR-AUTH')
seened : list = []


async def main():
	while 1:
		async for chats in socket.handler():
			try:
				for chat in chats:
					if chat['object_guid'].startswith('g'):
						if not chat['object_guid'] + chat['chat']['last_message']['message_id'] in seened:
							text : str = chat['chat']['last_message']['text']
							print(text)
							seened.append(chat['object_guid'] + chat['chat']['last_message']['message_id'])
			except :
					...
```

این سورس کد با استفاده از وب سوکت روبیکا آخرین پیام ها را دریافت میکند و چاپ میکند


# چگونگی نصب کتابخانه
دستور زیر را در ترمینال خود برای نصب کتابخانه وارد کنید

```
pip install mrub
```
