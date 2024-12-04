# Документирование приложения для дистанционного изучения английского языка

## 1. Структура функциональных возможностей (Mind Map)

```mermaid
mindmap
  root((Приложение для изучения английского языка))
    Пользователи
      Регистрация
      Профиль
      Роли (Преподаватель, Студент)
    Курсы
      Каталог курсов
      Уроки
      Задания
    Прогресс
      Отслеживание результатов
      Отчёты для преподавателей
      Уведомления о достижениях
    Коммуникации
      Чат между студентом и преподавателем
      Уведомления
      Обратная связь по заданиям
    Оплата
      Платежи за курсы
      История транзакций
    Безопасность
      Аутентификация
      Защита данных
      Модерация контента
    Интеграции
      Видео-платформа
      Сторонние платежные системы
```

### Описание:

Эта диаграмма иллюстрирует структуру функциональных возможностей приложения для дистанционного изучения английского языка.

### Основные узлы и их значение:

* <u>Пользователи:</u> функционал, связанный с управлением учетными записями, профилями и рейтингами.

* <u>Защита данных:</u> безопасность приложения.

* <u>Прогресс:</u> описывает процессы, связанные с успеваемость студента, включая оценки и т.д.

* <u>Коммуникации:</u> система взаимодействия между пользователями (чаты, уведомления).

* <u>Курсы:</u> основная сущность приложения, объединяющая основные темы, задания, учебные материалы.

## 2. Диаграмма путешествия пользователя (User Journey Diagram)

```mermaid
journey

  title Путь пользователя: Первое завершение урока

  section Регистрация

    Переход на сайт: 5: Новый пользователь

    Заполнение формы: 4: Новый пользователь

    Подтверждение email: 3: Система

  section Личный кабинет

    Указание уровня языка: 4: Студент

    Формирование расписания: 3: Студент

    Просмотр доступных курсов: 2: Студент

  section Выбор курса

    Поиск курса в каталоге: 5: Студент

    Чтение описания курса: 4: Студент

    Регистрация на курс: 3: Студент

  section Прохождение урока

    Изучение материалов: 5: Студент

    Выполнение упражнений: 4: Студент

    Проверка ответов: 3: Система

  section Завершение урока

    Получение результатов: 5: Студент

    Оценка урока: 4: Преподаватель

    Обратная связь от преподавателя: 3: Преподаватель
```

### Описание:

Диаграмма описывает ключевые этапы взаимодействия пользователя с системой:

* Регистрация: пользователь создает учетную запись и настраивает свой профиль.

* Личный кабинет: пользователь управляет своим профилем.

* Выбор курса: пользователь просматривает доступные курсы, используя различные фильтры и иные инструменты поиска.

* Прохождение урока: студент проходит новый урок.

* Завершение урока: пользователь-студент завершает урок, получает обратную связь от преподавателя в виде оценки, отзыва на его работу.

## 3. Квадрант-граф (Prioritization Quadrant)

```mermaid
quadrantChart

    title Priorities of Functionality Development

    x-axis Easy --> Hard

    y-axis Low Priority --> High Priority

  

    "Registration": [0.28, 0.9]

    "Course Catalog": [0.3, 0.8]

    "Lesson Content": [0.4, 0.95]

    "Student Progress Tracking": [0.6, 0.8]

    "Student-Teacher Chat": [0.5, 0.7]

    "Course Payments": [0.7, 0.9]

    "Notifications": [0.6, 0.5]

    "Achievement Badges": [0.3, 0.3]

    "Video Integration": [0.87, 0.8]

    "Authentication": [0.1, 0.9]

    "Data Protection": [0.9, 0.9]

    "Content Moderation": [0.55, 0.55]
```

### Описание:

Квадрант-граф помогает приоритизировать разработку функций системы. Каждая точка соответствует функционалу:

* Ось X: сложность реализации (от простого к сложному).

* Ось Y: приоритет для пользователей (от низкого к высокому).

## 4. Гит граф (Gitgraph)

```mermaid
gitGraph
    commit id: "v0.1.0: Project initialization"
    commit id: "v0.2.0: Basic user interface"
    commit id: "v0.3.0: Course catalog integration"
    
    branch feature-auth
    checkout feature-auth
    commit id: "Add user authentication"
    commit id: "Implement user roles"
    checkout main
    merge feature-auth id: "Merge auth features into main"
    commit id: "v0.4.0: Authentication and roles feature"
    
    branch feature-courses
    checkout feature-courses
    commit id: "Add course catalog"
    commit id: "Implement course registration"
    commit id: "Add lesson content display"
    checkout main
    merge feature-courses id: "Merge course features into main"
    commit id: "v0.5.0: Course management features"
    
    branch feature-progress
    checkout feature-progress
    commit id: "Add progress tracking"
    commit id: "Add performance reports"
    checkout main
    merge feature-progress id: "Merge progress features into main"
    commit id: "v0.6.0: Progress tracking release"
    
    branch feature-chat
    checkout feature-chat
    commit id: "Add chat functionality"
    commit id: "Implement notifications"
    checkout main
    merge feature-chat id: "Merge chat features into main"
    commit id: "v0.7.0: Chat and notifications release"
    
    branch feature-security
    checkout feature-security
    commit id: "Improve data protection"
    commit id: "Implement content moderation"
    commit id: "Advanced logging and security updates"
    checkout main
    merge feature-security id: "Merge security features into main"
    commit id: "v0.8.0: Security enhancements"
    
    commit id: "v1.0.0: First stable release"

```

### Описание:

 Гит-граф показывает процесс разработки системы через версии:

1. Основная ветка (main): стабильные версии системы.

2. Функциональные ветки: каждая ветка посвящена отдельной функциональности (пользователи, курсы, прогресс и т.д.).

3. Слияния: после завершения работы над веткой, изменения интегрируются в main.
