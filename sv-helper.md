# Алгоритм реализации вёрстки страницы "Stardew Valley Helper"

## Цель
Реализовать HTML-разметку страницы по готовым CSS-стилям. В этом файле — подсказки по структуре, тегам и классам для каждой части страницы.  
Необходимо строго соблюдать классы и семантику для правильного отображения.

---

## Общие рекомендации

- Используй семантические теги: `<header>`, `<nav>`, `<main>`, `<section>`, `<footer>`.
- Для контейнеров и элементов добавляй нужные классы из иерархии.
- Заголовки — от `<h1>` до `<h3>` по уровню вложенности.
- Для списков используй `<ul>` или `<ol>` в зависимости от задачи.
- Ссылки для навигации — `<a>` с `href="#id_секции"`.
- Обрати внимание на вложенность элементов.

---

## Подсказки по структуре и классам

### 1. Шапка (`header.header`)

- Тег: `<header>`
- Внутри: контейнер `<div>` с классом `.container` и `.header__inner`
- Заголовок сайта: `<div class="title">`
- Навигация: `<nav>` с `<ul class="nav__list">`
- Элементы меню: `<li>` с `<a class="nav__link" href="#id_секции">`

---

### 2. Баннер (`section.hero`)

- Тег: `<section>` с классом `.hero`
- Заголовок: `<h1 class="hero__title">`
- Текст: `<p class="hero__text">`
- Кнопка: `<a class="hero__btn" href="#id_секции">`

---

### 3. Основные секции — внутри `<main class="container">`

Каждая секция — `<section class="section <название>" id="<id>">`  
Общие элементы:  
- Заголовок: `<h2 class="section-title">`

#### 3.1 Быстрый доход (`.money`)

- Контейнер карточек: `<div class="grid-cards">`
- Карточка: `<div class="tip-card">`
- Заголовок карточки: `<h3 class="tip-card__title">`
- Описание: `<p>`

---

#### 3.2 Скрытые механики (`.hidden-mechanics`)

- Структура и классы аналогичны `.money`
- Тег `<section id="hidden" class="section hidden-mechanics">`

---

#### 3.3 Лучшие маршруты дня (`.routes`)

- Контейнер: `<div class="timeline">`
- Элемент маршрута: `<div class="timeline__block">`
- Время: `<div class="timeline__time">`
- Описание маршрута: `<div class="timeline__desc">`

---

#### 3.4 Прокачка навыков (`.skills`)

- Контейнер: `<div class="ranking-cards">`
- Карточка навыка: `<div class="rank-card">`
- Уровень навыка: `<span class="rank-card__level">`
- Обёртка для заголовка и текста: `<div>`
- Заголовок навыка: `<h3 class="rank-card__title">`
- Описание: `<p>`

---

#### 3.5 Избегай ошибок (`.mistakes`)

- Аналогично структуре `.money` и `.hidden-mechanics`
- Контейнер карточек: `<div class="grid-cards">`
- Карточка: `<div class="tip-card">`
- Заголовок: `<h3 class="tip-card__title">`
- Текст: `<p>`

---

### 4. Футер (`footer.footer`)

- Тег: `<footer>`
- Текст: `<p class="footer__text">`

---

## Иерархия классов (для быстрой навигации и проверки)

```
body
├── header.header
│   └── div.container.header__inner
│       ├── div.title
│       └── nav
│           └── ul.nav__list
│               ├── li > a.nav__link
├── section.hero
│   ├── h1.hero__title
│   ├── p.hero__text
│   └── a.hero__btn
├── main.container
│   ├── section.section.money#money
│   │   ├── h2.section-title
│   │   └── div.grid-cards
│   │       └── div.tip-card
│   │           ├── h3.tip-card__title
│   │           └── p
│   ├── section.section.hidden-mechanics#hidden
│   │   └── (как .money)
│   ├── section.section.routes#routes
│   │   ├── h2.section-title
│   │   └── div.timeline
│   │       └── div.timeline__block
│   │           ├── div.timeline__time
│   │           └── div.timeline__desc
│   ├── section.section.skills#skills
│   │   ├── h2.section-title
│   │   └── div.ranking-cards
│   │       └── div.rank-card
│   │           ├── span.rank-card__level
│   │           └── div
│   │               ├── h3.rank-card__title
│   │               └── p
│   └── section.section.mistakes#mistakes
│       └── div.grid-cards
│           └── div.tip-card
│               ├── h3.tip-card__title
│               └── p
└── footer.footer
└── p.footer__text

```

---

## Дополнительные советы

- Используй `id` для каждой секции, чтобы навигация работала корректно.
- Для карточек и блоков — строго соблюдай классы, иначе стили не применятся.
- Тексты и иконки (эмодзи) используй по образцу из CSS.
- Проверяй валидность HTML и структуру, чтобы не было ошибок вложения.
- Следи за отступами и читаемостью кода.
