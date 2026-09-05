# Galaxy Flow — Презентационная платформа финансовой аналитики

Современный и адаптивный сайт-витрина для B2B SaaS-продукта, разработанный на **Vue 3** и собранный с помощью **Vite**. 
Проект служит фронтенд-оболочкой для презентации возможностей продукта и включает прямую интеграцию с интерактивной enterprise-аналитикой.

**🌐 Живое демо:** [galaxyflow.ru](https://galaxyflow.ru)

## 🚀 Ключевые особенности и технические решения
- **Интеграция с Microsoft Power BI:** Реализовано встраивание внешнего электронного отчета через `<iframe>`. Добавлена нативная ленивая загрузка (`loading="lazy"`) для снижения нагрузки на стартовый бандл и настроена безопасность через песочницу HTML5 (`sandbox="allow-scripts allow-same-origin allow-popups allow-forms"`).
- **Интерфейсная логика (Вкладки и Спойлеры):** Переключение табов и интерактивное раскрытие блока отчета до высоты `100%` реализованы с помощью прямого управления инлайн-стилями через связку Vue `$refs` и нативных CSS-переходов (`transition`).
- **Компонентный подход:** Интерфейс разделен на изолированные Vue-компоненты для удобной поддержки разметки (секции фич, требований и структуры табов).
- **Адаптивная верстка:** 100% адаптивный дизайн под любые типы экранов с использованием CSS Grid, Flexbox и препроцессора SASS (индентированный синтаксис).

## 🛠️ Команды проекта
```bash
# Клонирование и установка зависимостей
git clone https://github.com
cd galaxy-flow-app
npm install

# Запуск в режиме разработки
npm run dev

# Сборка для продакшна
npm run build
```

---

<details>
<summary><b>EU Click to open the English Version (Нажмите, чтобы открыть версию на английском)</b></summary>
<br>

# Galaxy Flow — Financial Analytics Showcase Platform

The platform serves as a production-ready presentation layer for financial products, featuring direct integration with live enterprise business intelligence reports.

**🌐 Live Demo:** [galaxyflow.ru](https://galaxyflow.ru)

## 🚀 Key Features & Tech Specs
- **Microsoft Power BI Integration:** Embedded a heavy external analytical dashboard via `<iframe>`. Optimized performance using native deferred rendering (`loading="lazy"`) and secured the context via strict HTML5 sandboxing (`sandbox="allow-scripts allow-same-origin allow-popups allow-forms"`).
- **UI Logic (Tabs & Disclosures):** Tab switching and smooth accordion expansion up to `100%` height are managed directly via inline style manipulation using Vue `$refs` paired with native CSS transitions.
- **Component Architecture:** UI is structured into modular Vue components separating presentation tabs, feature lists, and requirements grids.
- **Responsive Layout:** 100% pixel-perfect responsive design tailored for all modern viewport sizes using CSS Grid, Flexbox, and preprocessed SASS.

## 🛠️ Quick Start
```bash
# Clone the repository and install dependencies
git clone https://github.com/Qyaers/galaxy-flow-app
cd galaxy-flow-app
npm install

# Run the development server
npm run dev

# Build for production
npm run build
```

</details>
