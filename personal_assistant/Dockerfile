# Вказати базовий образ
FROM python:3.12.3

# Встановити робочу директорію в контейнері
WORKDIR /app

# Копіювати файли проекту в контейнер
COPY pyproject.toml poetry.lock* /app/

# Встановлення Poetry
RUN pip install poetry

# Встановити залежності проекту
RUN poetry config virtualenvs.create false \
    && poetry install --no-dev

# Копіювати весь код в контейнер
COPY . /app/

# Вказати команду для запуску застосунку
CMD ["python", "bot.py"]