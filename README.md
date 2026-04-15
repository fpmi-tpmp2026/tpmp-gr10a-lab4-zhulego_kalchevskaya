# README.md

## Project Name

**Autopark Management System** - Система управления автопарком

## Description

Система управления автопарком предназначена для автоматизации учёта транспортных средств, водителей и выполненных заказов. Приложение позволяет просматривать, добавлять и удалять информацию об автомобилях, водителях и заказах. Реализована система аутентификации пользователей с разграничением ролей (admin, dispatcher, driver). Поддерживается формирование базовых отчётов по пробегу автомобилей и заработку водителей.

## Installation

### Требования
- Операционная система: Linux / macOS / Windows (с WSL или MinGW)
- Компилятор: GCC
- Библиотека: SQLite3

### Шаги установки

1. Клонирование репозитория:
```bash
git clone https://github.com/zhulegoalina/zhulego_kalchevskaya_code.git
cd zhulego_kalchevskaya_code
```

2. Установка SQLite3 (Ubuntu/Debian):
```bash
sudo apt-get install sqlite3 libsqlite3-dev
```

3. Установка SQLite3 (CentOS/RHEL):
```bash
sudo yum install sqlite sqlite-devel
```

4. Установка SQLite3 (macOS):
```bash
brew install sqlite3
```

5. Создание структуры каталогов:
```bash
mkdir -p data bin build include src tests
```

6. Компиляция проекта:
```bash
make
```

7. Инициализация базы данных:
```bash
sqlite3 data/autopark.db < database/schema.sql
```

## Usage

### Запуск приложения
```bash
./bin/autopark
```

### Авторизация
| Роль | Логин | Пароль |
|------|-------|--------|
| Admin | admin | admin123 |
| Dispatcher | dispatcher1 | pass123 |
| Driver | driver1 | pass123 |

### Меню приложения

#### Для всех пользователей:
- `1` - Просмотр списка автомобилей
- `2` - Просмотр списка водителей
- `3` - Просмотр списка заказов

#### Для диспетчера и администратора:
- `4` - Добавление автомобиля
- `5` - Добавление водителя
- `6` - Добавление заказа
- `7` - Обновление данных автомобиля
- `8` - Обновление данных водителя

#### Для администратора:
- `9` - Удаление автомобиля
- `10` - Удаление водителя
- `11` - Удаление заказа
- `12` - Отчёты

### Пример работы

```
=== Autopark Login ===
Username: admin
Password: admin123
Login successful!

=== Autopark Management ===
1. View cars
2. View drivers
3. View orders
4. Add car
5. Add driver
6. Add order
7. Update car
8. Update driver
9. Delete car
10. Delete driver
11. Delete order
12. Reports
0. Exit
Choose: 1

=== Cars ===
id = 1
car_number = A001AA
brand = Volvo
mileage = 120000
load_capacity = 5.5

id = 2
car_number = B002BB
brand = Scania
mileage = 85000
load_capacity = 8.0

id = 3
car_number = C003CC
brand = MAN
mileage = 45000
load_capacity = 6.0
```

### Пример добавления заказа (с проверкой грузоподъёмности)
```
Choose: 6
Enter date (YYYY-MM-DD): 2025-04-15
Enter driver ID: 1
Enter car ID: 1
Enter distance: 300
Enter cargo weight: 4.5
Enter cost: 600
Order added successfully! Driver earnings: 120.00
```

## Project Structure
```
zhulego_kalchevskaya_code/
├── bin/                    # Исполняемый файл
├── include/                # Заголовочные файлы
│   ├── auth.h
│   ├── cars.h
│   ├── database.h
│   ├── drivers.h
│   ├── orders.h
│   └── reports.h
├── src/                    # Исходный код
│   ├── main.c
│   ├── auth.c
│   ├── cars.c
│   ├── database.c
│   ├── drivers.c
│   ├── orders.c
│   └── reports.c
├── tests/                  # CUnit тесты
│   ├── test_auth_cunit.c
│   ├── test_cars_cunit.c
│   ├── test_database_cunit.c
│   ├── test_drivers_cunit.c
│   ├── test_orders_cunit.c
│   └── test_reports_cunit.c
├── data/                   # База данных
│   └── autopark.db
├── database/               # SQL скрипты
│   └── schema.sql
├── .github/workflows/      # CI/CD
│   └── ci.yml
├── Makefile
└── README.md
```

## Contributing

### Авторы проекта

| Автор | Роль | Реализованные задачи |
|-------|------|---------------------|
| Жулего Алина | Team Lead | Архитектура БД, аутентификация, интеграция SQLite |
| Кальчевская Полина Сергеевна | Backend Developer | CRUD операции для автомобилей и водителей |
| Кальчевская Полина Сергеевна | QA Engineer | Модульное тестирование, CI/CD |
| Жулего Алина | Backend Developer | CRUD операции для заказов, отчёты |

**Репозиторий с кодом и сборкой проекта:** [https://github.com/zhulegoalina/zhulego_kalchevskaya_code.git](https://github.com/zhulegoalina/zhulego_kalchevskaya_code.git)
