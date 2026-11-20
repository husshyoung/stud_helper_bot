# Матриця простежуваності вимог (RTM) — v1.0

| Вимога (SRS) | Use Case / Специфікація | Критерій приймання (AC) | Проєктний артефакт |
| :--- | :--- | :--- | :--- |
| **FR-01** Отримання статичної інформації (розклад дзвінків, правила, реквізити та інструкції для оплати) | UC-01 Отримання статичної інформації | AC-01 | Use Case Diagram; `model/activity-uc-01.md`; Class Diagram (`Category`, `ReferenceInfo`) |
| **FR-02** Навігація по базовому меню («Навчання», «Гуртожиток») | UC-02 Навігація по базовому меню (включається через `«include»` у базові сценарії) | AC-02 | Use Case Diagram; `model/activity-uc-02.md`; Class Diagram (`Student`, `Category`) |
| **FR-03** Пошук контактів за ключовим словом | UC-03 Пошук контактів за ключовим словом | AC-03 | Use Case Diagram; `model/activity-uc-03.md`; Class Diagram (`Student.searchContact()`, `ReferenceInfo`) |
| **FR-04** Відправка запитання адміністратору (Куратору / Студраді) | Розширення (`«extend»`) основних сценаріїв: «Відправка запитання адміністратору» | AC-04 | Use Case Diagram; Class Diagram (`Student.submitQuestion()`, `Question.forwardToAdmin()`) |
| **NFR-01** Час відповіді бота $\le$ 2 с | UC-01, UC-02, UC-03 | AC-05 | `docs/implementation-plan.md` (перевірка у ЛР №4) |
| **NFR-02** Зрозумілість відповідей та обробка помилок/порожніх результатів | UC-01, UC-02, UC-03 | AC-06 | `docs/use-cases.md`; `model/activity-uc-01..03.md` |
