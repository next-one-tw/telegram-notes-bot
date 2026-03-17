# 📝 Telegram Notes Bot

[![Go](https://img.shields.io/badge/Go-1.21+-00ADD8?style=flat-square&logo=go)](https://golang.org/)
[![Telegram Bot](https://img.shields.io/badge/Telegram-Bot-2CA5E0?style=flat-square&logo=telegram)](https://core.telegram.org/bots)
[![MIT License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)
[![Go Report Card](https://goreportcard.com/badge/github.com/yourusername/telegram-notes-bot?style=flat-square)](https://goreportcard.com/report/github.com/yourusername/telegram-notes-bot)

Telegram бот для создания и управления личными заметками. Написан на Go с использованием конкурентной архитектуры и потокобезопасного хранения в памяти.

## ✨ Возможности

- ✅ **Создание заметок** — сохраняйте важную информацию командой `/save`
- 📋 **Просмотр списка** — все заметки одной командой `/list`
- 🔍 **Получение по заголовку** — быстрый доступ к нужной заметке через `/get`
- 🗑️ **Удаление заметок** — управляйте коллекцией командой `/delete`
- 🚀 **Конкурентная обработка** — каждый запрос в отдельной горутине
- 🔒 **Безопасно** — потокобезопасное хранилище с `sync.RWMutex`

## 🛠️ Технологии

- **Язык:** Go 1.21+
- **Библиотеки:**
  - [go-telegram-bot-api](https://github.com/go-telegram-bot-api/telegram-bot-api) — работа с Telegram API
  - [godotenv](https://github.com/joho/godotenv) — загрузка переменных окружения
- **Хранилище:** In-memory с конкурентным доступом (`sync.RWMutex`)
- **Архитектура:** Конкурентная обработка запросов в горутинах

## 📋 Команды бота

| Команда | Описание | Пример |
|---------|----------|--------|
| `/start` | Приветствие и список команд | `/start` |
| `/save` | Сохранить заметку | `/save Покупки; Купить молоко` |
| `/get` | Получить заметку по заголовку | `/get Покупки` |
| `/list` | Показать все заметки | `/list` |
| `/delete` | Удалить заметку | `/delete Покупки` |

## 🚀 Быстрый старт

### 1. Получите токен бота

1. Найдите в Telegram [@BotFather](https://t.me/botfather)
2. Отправьте команду `/newbot`
3. Следуйте инструкциям и сохраните полученный токен

### 2. Установка и запуск

```bash
# Клонируйте репозиторий
git clone https://github.com/yourusername/telegram-notes-bot.git
cd telegram-notes-bot

# Установите зависимости
go mod download

# Создайте файл с токеном (скопируйте из примера)
cp .env.example .env
# Отредактируйте .env, вставьте ваш токен

# Запустите бота
go run main.go
