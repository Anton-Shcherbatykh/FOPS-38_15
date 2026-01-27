## Домашнее задание к занятию 5. «Практическое применение Docker» (FOPS-38, Щербатых А.Е.)

### Задача 1

1. Сделайте в своем GitHub пространстве fork [репозитория](https://github.com/netology-code/shvirtd-example-python).

2. Создайте файл Dockerfile.python на основе существующего Dockerfile:

- Используйте базовый образ python:3.12-slim
- Обязательно используйте конструкцию COPY . . в Dockerfile
- Создайте .dockerignore файл для исключения ненужных файлов
- Используйте CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "5000"] для запуска
- Протестируйте корректность сборки 2.1 (Необязательная часть, *) Используйте multistage сборку вместо single stage.

3. (Необязательная часть, *) Изучите инструкцию в проекте и запустите web-приложение без использования docker, с помощью venv. (Mysql БД можно запустить в docker run).

4. (Необязательная часть, *) Изучите код приложения и добавьте управление названием таблицы через ENV переменную.

### Ответ 1

[Ссылка на репозиторий](https://github.com/Anton-Shcherbatykh/FOPS-38_15-05)

Файл ```Dockerfile.python```

```bash
FROM python:3.12-slim
WORKDIR /app
COPY requirements.txt ./
RUN pip install -r requirements.txt
COPY main.py ./
CMD ["python", "main.py"]
```
