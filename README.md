# Документирование приложения для продажи билетов на концерт музыкальной группы

## 1. Структура функциональных возможностей (Mind Map)

# Система продажи билетов на концерты

Этот проект описывает архитектуру и функциональность системы продажи билетов на концерты музыкальных групп. В рамках работы были разработаны диаграммы с использованием **Mermaid** для визуализации структуры и процессов системы.

---

## Диаграмма функциональных возможностей

```mermaid
mindmap
  root((Система продажи билетов))
    Пользователи
      Покупатели
      Организаторы
    Концерты
      Каталог концертов
      Управление событиями
      Услуги (VIP, стандарт)
    Билеты
      Покупка
      Бронирование
      Электронные билеты
    Платежи
      Онлайн оплата
      История транзакций
    Безопасность
      Аутентификация
      Защита данных
    Интеграции
      Платежные системы
      Платформы мероприятий
```

### Описание:
Пользователи: покупатели и организаторы.
Концерты: управление событиями и их категориями.
Билеты: покупка, бронирование, электронные билеты.
Платежи: онлайн оплата и история транзакций.
Безопасность: аутентификация и защита данных.

## 2. Диаграмма путешествия пользователя (User Journey Diagram)

```mermaid
journey
  title Путь пользователя: Покупка билета
  section Вход в систему
    Авторизация: 5: Пользователь
    Просмотр личного кабинета: 4: Пользователь
  section Просмотр концертов
    Поиск концертов: 5: Пользователь
    Выбор мероприятия: 4: Пользователь
    Чтение описания концерта: 3: Пользователь
  section Покупка билета
    Выбор билета: 5: Пользователь
    Оплата: 4: Пользователь
    Подтверждение заказа: 3: Система
  section После покупки
    Получение электронного билета: 5: Пользователь
    Уведомление о статусе заказа: 4: Система

```

### Описание:

Пользователь выполняет авторизацию и переходит в личный кабинет.
Выбирает концерт, читает информацию, оформляет билет.
Получает электронный билет и уведомление о заказе.

## 3. Квадрант-граф (Prioritization Quadrant)

```mermaid
quadrantChart
  title Приоритеты разработки
  x-axis Easy --> Hard
  y-axis Low Priority --> High Priority

  "Регистрация": [0.2, 0.75]
  "Концерты": [0.38, 0.85]
  "Покупка": [0.65, 0.95]
  "Транзакции": [0.72, 0.65]
  "Интеграции": [0.78, 0.8]
  "Э-билеты": [0.25, 0.9]
  "Управление": [0.5, 0.5]
  "Аутентификация": [0.15, 0.8]
  "Данные": [0.9, 0.95]
```

### Описание:

Высокий приоритет: покупка билетов, электронные билеты, защита данных.
Средний приоритет: интеграции, транзакции, управление концертами.

## 4. Гит граф (Gitgraph)

```mermaid
gitGraph
  commit id: "v0.1.0: Инициализация проекта"
  commit id: "v0.2.0: Базовый интерфейс пользователей"
  commit id: "v0.3.0: Каталог концертов"

  branch feature-auth
  checkout feature-auth
  commit id: "Добавление аутентификации"
  commit id: "Роли пользователей"

  checkout main
  merge feature-auth id: "Слияние с основным"

  branch feature-payments
  checkout feature-payments
  commit id: "Интеграция с платёжными системами"
  commit id: "История транзакций"

  checkout main
  merge feature-payments id: "Слияние платёжных функций"

  branch feature-tickets
  checkout feature-tickets
  commit id: "Создание системы билетов"
  commit id: "Электронные билеты"

  checkout main
  merge feature-tickets id: "Слияние системы билетов"
  commit id: "v1.0.0: Первый стабильный релиз"
```

### Описание:

Основные ветки: аутентификация, платежи, билеты.
Итоговый релиз: v1.0.0.
