# Activity Diagram — UC-02: Навігація по базовому меню («Навчання», «Гуртожиток»)

```mermaid
flowchart TD
    Start([Початок: Команда /start]) --> LoadMain[Завантаження базових категорій Category]
    LoadMain --> ShowMain[Відображення головного меню:<br/>Навчання, Гуртожиток, Пошук контактів, Задати питання]
    ShowMain --> Input[Очікування дії студента]

    Input --> CheckInput{Натиснуто кнопку<br/>базового меню?}
    CheckInput -->|Ні: довільний текст| InvalidMsg[Повідомлення: команду не розпізнано]
    InvalidMsg --> ShowMain

    CheckInput -->|Так: Навчання або Гуртожиток| FetchSub[Запит підрозділів категорії з Supabase]
    FetchSub --> CheckDB{Дані успішно<br/>завантажено?}

    CheckDB -->|Ні: помилка БД / порожньо| ErrMsg[Повідомлення про тимчасову недоступність<br/>та пропозиція Задати питання]
    ErrMsg --> ShowMain

    CheckDB -->|Так| ShowSub[Відображення меню підрозділів обраної категорії<br/>+ кнопка Назад до меню]
    ShowSub --> SubAction{Вибір студента}

    SubAction -->|Назад до меню| ShowMain
    SubAction -->|Вибір підрозділу| OpenInfo[Перехід до перегляду інформації UC-01]
    OpenInfo --> End([Кінець])