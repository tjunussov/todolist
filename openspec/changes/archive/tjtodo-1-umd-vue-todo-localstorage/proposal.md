# UMD Vue todo с localStorage

**Task:** TJTODO-1 — UMD Vue todo с localStorage (https://syrma.app/TJTODO-1)

## Why

Нужен простой todo-лист без шага сборки — один HTML-файл, Vue подключён через UMD `<script>` (CDN), без Vite/webpack/npm. Данные должны переживать перезагрузку страницы.

## What Changes

- Один файл `index.html`: Vue 3 (global build, UMD) через `<script src>`, Composition API (`<script setup>`-стиль недоступен в UMD без сборки, поэтому — `createApp` + `setup()` в обычном `<script>`), Quasar не используется (чистый Vue, без сборки под Quasar CLI).
- Список задач: добавить (ввод + Enter/кнопка), отметить выполненной (чекбокс), удалить (кнопка).
- Персист: весь список задач читается/пишется в `localStorage` под одним ключом, синхронно при каждом изменении (`watch` с `deep: true` либо запись в каждом действии).
- Без сервера, без API, без тестового фреймворка — статический файл, открывается напрямую в браузере.

## Impact

- Новый файл, не затрагивает существующий код (его нет — папка проекта пустая).
- Affected capability: `todo-app` (новая).
