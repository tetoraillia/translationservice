# ЗВІТ

## Практична робота №1

**Дисципліна:** Об'єктно-орієнтоване проєктування  
**Тема:** Об'єктно-орієнтований аналіз предметної області за допомогою ШІ-агентів з використанням UML-діаграм  
**Студент:** Тетьора Ілля Сергійович  
**Група:** КІ-26  
**Предметна область:** Служба перекладу документів  
**Репозиторій:** https://github.com/tetoraillia/translationservice

## 1. Варіант і сценарії

Варіант використовує ролі **Замовник, Перекладач, Редактор** та сценарії:

1. завантаження документа й вибір мовної пари;
2. переклад із термінологічним глосарієм;
3. редакторська вичитка та фіксація правок;
4. отримання засвідченого перекладу.

## 2. Артефакти в репозиторії

1. `docs/usecase.puml` — PlantUML-діаграма варіантів використання.
2. `docs/class.mmd` — Mermaid-діаграма класів.
3. `docs/sequence.mmd` — Mermaid-діаграма послідовності.
4. `docs/state.mmd` — Mermaid-діаграма станів.
5. `docs/crc.xlsx` — CRC-картки для всіх доменних класів.
6. `specs/001-translation-service/` — специфікація, план, завдання, модель даних, quickstart і research.
7. `.specify/memory/constitution.md` — конституція проєкту.

## 3. Перевірка вимог

- Use-case діаграма містить усіх трьох акторів і щонайменше три бізнес-операції.
- Class-діаграма містить абстрактний `DocumentActor`, інтерфейс `QualityControllable`, конкретні ролі та доменні класи.
- Показані наслідування, реалізація інтерфейсу, залежності, композиція й агрегація.
- У класах зафіксовані конструктори, final-метод `displayRole`, перевизначений `performTask` і перевантажений `addSegment`.
- Sequence-діаграма використовує ті самі класи, що й class-діаграма.
- State-діаграма містить початковий і кінцевий стани та переходи за бізнес-сценаріями.
- CRC-картки охоплюють `DocumentActor`, `Customer`, `Translator`, `Editor`, `TranslationProject`, `SourceDocument`, `LanguagePair`, `Glossary` і `TranslationSegment`.

## 4. Запити до ШІ та перевірка convergence

Для підготовки артефактів застосовано послідовність запитів:

1. `/speckit-constitution` — сформувати правила моделі та SOLID-обмеження.
2. `/speckit-specify` — описати службу перекладу, акторів, сценарії та критерії приймання.
3. `/speckit-plan` — спланувати UML, CRC-картки та структуру репозиторію.
4. `/speckit-tasks` — розкласти роботу на перевірювані завдання.
5. `/speckit-implement` — створити вихідні файли діаграм, специфікації та CRC-картки.
6. `/speckit-converge` — звірити узгодженість класів, послідовності, станів і вимог.

Фінальний знімок репозиторію після convergence-проходу: [converge-repo.png](converge-repo.png). Він показує опублікований репозиторій із фінальним набором артефактів. Додатково перевірено валідність `docs/crc.xlsx` командою `unzip -t` і виконано рендер усіх чотирьох діаграм.

## 5. Рендери та URL-и

Коди перевірені у PlantUML/Mermaid renderer. Публічні посилання на файли:

- [Use case source](https://github.com/tetoraillia/translationservice/blob/main/docs/usecase.puml) · [PNG](https://github.com/tetoraillia/translationservice/blob/main/report/usecase.png)
- [Class source](https://github.com/tetoraillia/translationservice/blob/main/docs/class.mmd) · [PNG](https://github.com/tetoraillia/translationservice/blob/main/report/class.png)
- [Sequence source](https://github.com/tetoraillia/translationservice/blob/main/docs/sequence.mmd) · [PNG](https://github.com/tetoraillia/translationservice/blob/main/report/sequence.png)
- [State source](https://github.com/tetoraillia/translationservice/blob/main/docs/state.mmd) · [PNG](https://github.com/tetoraillia/translationservice/blob/main/report/state.png)
- [CRC sheet XLSX](https://github.com/tetoraillia/translationservice/blob/main/docs/crc.xlsx)
- [Таблиця варіантів Google Sheets](https://docs.google.com/spreadsheets/d/1bkgXq1hIMnqPgN_rW6AIDhOjtwFBymAs/edit)
- [Методичні вказівки](https://docs.google.com/document/d/1qZac_8rFnl6p3fHYRvHrOFxLOG43KyVLwBKvs0jgALE/edit)
- [Mermaid Live](https://mermaid.live/) · [PlantUML server](https://www.plantuml.com/plantuml/)

У class-діаграмі `displayRole()` має сигнатуру `displayRole() final void`; `performTask()` перевизначається конкретними акторами, а `addSegment()` має дві форми.

## 6. Висновок

Побудовано узгоджену UML-модель служби перекладу документів із трьома ролями, чотирма бізнес-сценаріями, абстракцією ролей, інтерфейсом контролю якості, CRC-картками та моделлю життєвого циклу проєкту.
