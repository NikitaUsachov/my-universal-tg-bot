# Universal Telegram AI Bot

Форк Telegram-бота для работы с LLM. В данной сборке добавлена поддержка альтернативных провайдеров API (OpenRouter) и интегрирована быстрая система распознавания голосовых сообщений.

## Основные изменения и особенности

* **Поддержка OpenRouter:** Возможность использования любых текстовых моделей через единый API-ключ.
* **Распознавание голоса через Groq:** Стандартный OpenAI Whisper заменен на модель `whisper-large-v3` от Groq для ускорения обработки аудиосообщений.
* **Исправление ошибок форматирования:** Добавлена фильтрация спецсимволов в транскрибированном тексте для предотвращения падений бота с ошибкой `Can't parse entities`.
* **Поддержка Vision-моделей:** Отдельная переменная для моделей компьютерного зрения (анализ изображений).
* **Docker:** Готовая конфигурация для быстрого развертывания.

## Установка и запуск

1. Склонируйте репозиторий:
```bash
git clone [https://github.com/NikitaUsachov/my-universal-tg-bot.git](https://github.com/NikitaUsachov/my-universal-tg-bot.git)
cd my-universal-tg-bot
```

2. Создайте файл конфигурации из шаблона:
```bash
cp env.example .env
nano .env
```

3. Заполните обязательные переменные в файле `.env`:
* `TELEGRAM_BOT_TOKEN` — токен бота (получается у @BotFather).
* `OPENAI_API_KEY` — API-ключ от платформы OpenRouter.
* `GROQ_API_KEY` — API-ключ от консоли Groq.
* `OPENAI_MODEL` — основная текстовая модель (например, `openai/gpt-4o-mini`).
* `OPENAI_VISION_MODEL` — визуальная модель для фото (например, `google/gemini-2.5-flash`).

4. Запустите контейнер:
```bash
docker compose up -d --build
```
