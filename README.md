# 🐕 Мой Hugo блог

Личный сайт на Hugo с минималистичной темой. Порт темы [astro-theme-breeze](https://github.com/linftyz/astro-theme-breeze).

---

## 🚀 Быстрый старт

```bash
# Запуск сервера разработки
hugo server

# Сборка сайта
hugo

# Сборка + индексация поиска
hugo && npx pagefind --site public
```

---

## 📁 Структура проекта

```
├── assets/
│   ├── css/
│   │   ├── main.css        ← все стили темы
│   │   └── syntax.css      ← подсветка кода (catppuccin)
│   └── icons/              ← SVG иконки (Font Awesome)
│       ├── github.svg
│       ├── telegram.svg
│       └── email.svg
├── content/
│   ├── posts/              ← статьи блога
│   ├── projects/           ← проекты
│   ├── friends/            ← страница друзей
│   ├── tools/              ← страница инструментов
│   └── about.md            ← страница "Обо мне"
├── data/
│   ├── navigation.yaml     ← пункты меню
│   ├── tools.yaml          ← инструменты на странице /tools
│   ├── friends.json        ← список друзей
│   └── tagnames.yaml       ← красивые названия тегов и категорий
├── layouts/                ← шаблоны Hugo
├── static/
│   ├── logo.png            ← логотип (светлая тема)
│   └── logo1.png           ← логотип (тёмная тема)
└── hugo.toml               ← главный конфиг
```

---

## ✍️ Написание статей

Создай файл в `content/posts/название-статьи.md`:

```toml
+++
title = "Заголовок статьи"
description = "Краткое описание для SEO."
date = 2026-01-01T00:00:00
draft = false
categories = ["csharp-development"]
tags = ["csharp", "blazor-server", "mssql"]
+++

Текст статьи...
```

### Форматирование в тексте

| Что | Как писать |
|---|---|
| Жирный | `**текст**` |
| Курсив | `*текст*` |
| Инлайн-код | `` `код` `` |
| Путь к файлу | `` `/src/pages/index.ts` `` |
| Ссылка | `[текст](url)` |
| Картинка | `![alt](путь)` |

### Блоки кода

````
```cs
public class Hello { }
```
````

Поддерживаемые языки: `cs`, `xml`, `sql`, `js`, `ts`, `html`, `css`, `bash`, `json`, `yaml` и другие.

### Математические формулы

Инлайн: `$E = mc^2$`

Блок:
```
$$
\int_0^\infty e^{-x^2} dx = \frac{\sqrt{\pi}}{2}
$$
```

---

## 🏷️ Теги и категории

Теги и категории пишутся **slug-ом** (без спецсимволов), а красивое отображение настраивается в `data/tagnames.yaml`.

**Пример:**

В frontmatter поста:
```toml
categories = ["csharp-development"]
tags = ["csharp", "dotnet", "aspnet-core"]
```

В `data/tagnames.yaml`:
```yaml
tags:
  csharp: "C#"
  dotnet: ".NET"
  aspnet-core: "ASP.NET Core"

categories:
  csharp-development: "C# Development"
```

---

## ⚙️ Настройки (hugo.toml)

| Параметр | Описание |
|---|---|
| `title` | Название сайта |
| `params.hue` | Цвет темы (0–360) |
| `params.logo` | Логотип для светлой темы |
| `params.logoDark` | Логотип для тёмной темы |
| `params.recentPostsCount` | Количество постов на главной |
| `params.newPostDays` | Сколько дней показывать значок "New" |
| `params.mathRenderer` | Рендерер формул: `katex` или `mathjax` |
| `params.footer.enabled` | Показывать футер: `true` / `false` |
| `params.comments.enabled` | Включить комментарии: `true` / `false` |

### Цвета темы (hue)

| Число | Цвет |
|---|---|
| `165` | 🟢 Sage Green |
| `250` | 🔵 Ocean Blue |
| `280` | 🟣 Lavender Purple |
| `330` | 🩷 Rose Pink |
| `30` | 🟠 Warm Orange |
| `45` | 🟡 Golden Yellow |
| `200` | 🩵 Teal |

---

## 👥 Добавление друзей

Редактируй `data/friends.json`:

```json
[
  {
    "name": "Имя друга",
    "description": "Краткое описание",
    "link": "https://example.com",
    "avatar": "https://example.com/avatar.png"
  }
]
```

---

## 🛠️ Добавление инструментов

Редактируй `data/tools.yaml`:

```yaml
- name: development
  items:
    - name: VS Code
      link: https://code.visualstudio.com
      icon: mdi:microsoft-visual-studio-code
```

---

## 🔗 Добавление проекта

Создай файл `content/projects/название.md`:

```toml
+++
title = "Название проекта"
description = "Описание проекта."
tech = ["C#", "Blazor", "MSSQL"]
links.github = "https://github.com/..."
links.demo = "https://..."
status = "completed"
+++
```

---

## 🔍 Поиск

Поиск работает через [Pagefind](https://pagefind.app) — статический индекс.

- В режиме `hugo server` — поиск не работает
- После `hugo build` запусти: `npx pagefind --site public`
- Затем снова `hugo server` — поиск заработает

---

## 🌐 Деплой

Сайт — полностью статический. Подходит любой хостинг:

- **Cloudflare Pages** — бесплатно, быстро
- **GitHub Pages** — бесплатно
- **Netlify** — бесплатно
- **Vercel** — бесплатно

---

## 📝 Лицензия

MIT — делай что хочешь.