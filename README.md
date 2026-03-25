# IoT Vega Server

Сервер для работы с устройствами IoT Vega. Поддерживает подключение по WebSocket с шифрованием SSL/TLS.

---

## 📦 Содержание
- [Системные требования](#-системные-требования)
- [Установка IoT Vega Server](#-установка-iot-vega-server)
- [Запуск сервера](#-запуск-сервера)
- [Подключение через Admin Tool](#-подключение-через-admin-tool)

---

## 💻 Системные требования

- **ОС:** Windows 7/8/10/11 или Linux
- **Место:** 200 МБ свободного места
- **Порты:** 
  - `8001/UDP` - для подключения шлюзов
  - `8002/TCP` - для WebSocket/WSS

---

## 📥 Установка IoT Vega Server

### 1. Скачай сервер [Download](https://github.com/JohON0/Lorawan-manual/raw/refs/heads/main/iot-vega-server-1.9.0rc19.7.zip)

### 2. Распакуй архив
Распакуй содержимое архива в папку с сертификатами по пути:
```
C:\iot-vega-server\
Если нету папки, то ее нужно создать
```

После распаковки в папке должны лежать:
- `Файлы сервера`
- `iot-vega-server.exe`
- `settings.conf`

---

## ⚙️ Настройка конфигурации

Открой файл `C:\iot-vega-server\settings.conf` любым текстовым редактором.

### Было (SSL выключен):
```ini
[host]
ip=127.0.0.1
udpPort=8001
tcpPort=8002
webSocketPath=/
useSSL=0
certFileName=cert.crt
keyFileName=key.key

[root]
root=root
password=123
```

### Стало (SSL включён):
```ini
[host]
ip=0.0.0.0              # Слушаем все интерфейсы
udpPort=8001
tcpPort=8002
webSocketPath=/
useSSL=0                 # Выключаем SSL
certFileName=cert.crt    # Файл сертификата
keyFileName=key.key      # Файл ключа

[root]
root=root
password=123             # !!!!!!Нужно изменить на свой пароль!!!!!!!
```

---

## 🚀 Запуск сервера

### Способ 1: Через проводник
Просто дважды кликни по файлу `iot-vega-server.exe`

### Способ 2: Через командную строку
```cmd
cd C:\iot-vega-server
iot-vega-server.exe
```
---

## 🌐 Подключение через Admin Tool

### 1. Скачай Admin Tool
```
https://iotvega.com/content/ru/soft/server/IoT%20Vega%20AdminTool%20v1.1.8.zip
```

### 2. Распакуй архив
```
C:\iot-vega-admin\
```

### 3. Подключись к серверу

1. Открой файл `C:\iot-vega-admin\index.html` в браузере
2. Введи логин и пароль (по умолчанию: `root` / `123`)
3. Нажми на шестеренку ⚙️ в правом верхнем углу
4. В настройках подключения укажи:
   - **Адрес:** IP твоего компьютера (например, `192.168.1.100`)
   - **Порт:** `8002` (оставляем)
   - **Протокол:** `ws://` (подставится автоматически)
5. Нажми **"Sign in"**

### 4. Готово!
Ты подключился к серверу по защищённому каналу (WS).

---

## 🔒 Безопасность

### Обязательно сделай:
1. **Смени пароль** `123` в `settings.conf` на свой
2. **Открой только нужные порты** в фаерволе (8001/UDP, 8002/TCP)
3. **Не храни ключи** в публичном доступе

### Для продакшена:
- Используй сертификаты от доверенного центра
- Настрой файрвол
- Регулярно обновляй сервер

---

## 🔗 Полезные ссылки

- [Официальный сайт IoT Vega](https://iotvega.com)
- [Скачать сервер](https://iotvega.com/content/ru/soft/server/iot-vega-server-1.9.0rc19.7.zip)
- [Скачать Admin Tool](https://iotvega.com/content/ru/soft/server/IoT%20Vega%20AdminTool%20v1.1.8.zip)
- [Документация](https://iotvega.com/content/ru/documentation)

---

## 📞 Поддержка

- 📧 Email: support@iotvega.com
- 🌐 Сайт: https://iotvega.com

---

## 📄 Лицензия

Проприетарное ПО. Все права принадлежат IoT Vega.

---

*Инструкция составлена для версии сервера 1.9.0rc19.7 и Admin Tool v1.1.8*
```
