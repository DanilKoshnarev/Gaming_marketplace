# Gaming Marketplace

Це проект на основі Django для онлайн-ринку, де користувачі можуть купувати та продавати відеоігри. Проект містить три основні додатки: Games, Payments та Users.

## Структура проекту

- **Games**: Обробляє списки ігор, включаючи деталі, такі як назва, ціна, розробник, жанр та рік.
- **Payments**: Керує платіжними транзакціями, фіксуючи ім'я користувача, суму грошей та додатковий коментар.
- **Users**: Керує обліковими записами користувачів, включаючи ім'я користувача, ім'я, прізвище, електронну адресу та пароль.

## Початок роботи

### Вимоги

- Python 3.x
- Django 3.x

### Встановлення

1. **Клонування репозиторію**:
    ```bash
    git clone <адреса_репозиторію>
    cd Gaming_marketplace
    ```

2. **Встановлення залежностей**:
    ```bash
    pip install -r requirements.txt
    ```

3. **Запуск проекту Django**:
    ```bash
    django-admin startproject Gaming_marketplace
    cd Gaming_marketplace
    ```

4. **Створення та запуск додатків**:
    ```bash
    python manage.py startapp Games
    python manage.py startapp Payments
    python manage.py startapp Users
    ```

5. **Створення початкових міграцій та виконання міграцій**:
    ```bash
    python manage.py makemigrations
    python manage.py migrate
    ```

### Використання

1. **Запуск сервера розробки**:
    ```bash
    python manage.py runserver
    ```

2. **Доступ до проекту** за адресою `http://127.0.0.1:8000/`.

## Моделі

### Games

```python
from django.db import models

class Game(models.Model):
    name = models.CharField(max_length=200)
    price = models.DecimalField(max_digits=5, decimal_places=2)
    creator = models.CharField(max_length=200)
    genre = models.CharField(max_length=200)
    year = models.IntegerField()
```

### Payments

```python
from django.db import models

class Payment(models.Model):
    username = models.CharField(max_length=200)
    amount_money = models.DecimalField(max_digits=5, decimal_places=2)
    comment = models.TextField(null=True, blank=True)
```

### Users

```python
from django.db import models

class User(models.Model):
    username = models.CharField(max_length=200)
    first_name = models.CharField(max_length=200)
    last_name = models.CharField(max_length=200)
    email = models.EmailField()
    password = models.CharField(max_length=200)
```

## Створення міграцій

Після внесення змін до моделей, виконайте наступні команди для створення та застосування міграцій:

```bash
python manage.py makemigrations
python manage.py migrate
```

Якщо потрібно, відкотити міграцію до певної версії:

```bash
python manage.py migrate Payments <номер_міграції>
```

## Ліцензія

Цей проект ліцензовано під ліцензією MIT. Дивіться файл LICENSE для деталей.
