# Firefox Better Nova

Classic-style tabs and tamer corners for Firefox's **Nova** UI (Firefox 157+).

Firefox 157 redesigned the tab strip: inactive tabs became solid "buttons",
the active tab got a rainbow gradient border, menu highlights and dropdown
panels gained huge rounded corners. This `userChrome.css` brings back a
classic, calmer look:

- **Inactive tabs** are transparent (plain labels), not solid buttons.
- **Active tab** is a real tab shape — rounded top corners, bottom corners
  that flare *outward* (folder-tab style), sitting flush against the toolbar.
- **Active tab color** matches the address-bar toolbar exactly, and the strip
  behind the tabs is slightly darkened for contrast.
- **Top bar gradient** keeps the base purple but drops the peach/orange end.
- **Menu-item highlights** and **dropdown panels** use small, sane corner radii.

> Tested on Firefox 158 (macOS). Works in both light and dark themes
> (colors use `light-dark()`). Tuned for **horizontal** tabs.

---

## Screenshot

<!-- Add a screenshot here, e.g. docs/preview.png -->
_Add your own screenshot._

---

## Requirements

- Firefox **157 or newer** with the new **Nova** UI enabled
  (`browser.nova.enabled` = `true`, which is the default on these versions).

## Installation

1. Open `about:support`, find **Profile Folder** (Папка профиля) and click
   **Open Folder** / **Показать в Finder**.
2. In the profile folder, create a folder named `chrome` (if it doesn't exist).
3. Copy [`chrome/userChrome.css`](chrome/userChrome.css) into that `chrome` folder,
   so the final path is `…/<profile>/chrome/userChrome.css`.
4. Open `about:config`, search for
   `toolkit.legacyUserProfileCustomizations.stylesheets` and set it to `true`.
5. **Fully restart** Firefox (quit and reopen — chrome CSS is only read at startup).

## Customization

All knobs live at the top of `userChrome.css` as CSS variables:

| Variable | Default | What it controls |
|---|---|---|
| `--tab-border-radius` | `6px` | Rounding of the active tab's top corners |
| `--tab-curve` | `8px` | Size of the outward flare on the bottom corners |
| `--tabstrip-darken` | `rgba(0,0,0,.07)` / `.18` | How much darker the strip behind the tabs is |
| `--panel-menuitem-border-radius` | `4px` | Rounding of menu-item hover highlights |
| `--popup-border-radius` | `8px` | Rounding of dropdown panels / address-bar results |

Edit a value, save, and restart Firefox.

## How it works

Firefox 157+ ships a token-based "Nova" theme. This stylesheet overrides a
handful of those design tokens (`--tab-background-color`,
`--toolbar-background-color`, `--toolbox-background-color-gradient-trailing`,
`--panel-menuitem-border-radius`, `--popup-border-radius`, …) and reshapes the
selected tab's `.tab-background` — including two masked pseudo-elements that
draw the outward-curving bottom corners. See the comments in the file for
details.

## Uninstall

Delete `chrome/userChrome.css` (or the whole `chrome` folder) and restart
Firefox. Optionally set
`toolkit.legacyUserProfileCustomizations.stylesheets` back to `false`.

## License

[MIT](LICENSE)

---

# Firefox Better Nova (Русский)

Классический вид вкладок и адекватные скругления для интерфейса **Nova**
в Firefox (версии 157+).

В Firefox 157 переделали панель вкладок: неактивные вкладки стали сплошными
«кнопками», у активной появилась радужная рамка-градиент, а у подсветки меню и
выпадающих панелей — огромные скругления. Этот `userChrome.css` возвращает
спокойный классический вид:

- **Неактивные вкладки** прозрачные (просто текст), а не кнопки.
- **Активная вкладка** — настоящий «язычок»: верхние углы скруглены, нижние
  загибаются *наружу*, вкладка прижата к тулбару.
- **Цвет активной вкладки** точно совпадает с панелью адресной строки, а
  подложка под вкладками чуть затемнена для контраста.
- **Градиент верхней панели** — оставлен базовый фиолетовый, персиковый убран.
- **Подсветка пунктов меню** и **выпадающие панели** — умеренные скругления.

> Проверено на Firefox 158 (macOS). Работает в светлой и тёмной теме.
> Настроено под **горизонтальные** вкладки.

## Требования

- Firefox **157 или новее** с включённым интерфейсом **Nova**
  (`browser.nova.enabled` = `true`, по умолчанию включён на этих версиях).

## Установка

1. Открой `about:support`, найди **Папку профиля** и нажми **Показать в Finder**.
2. В папке профиля создай папку `chrome` (если её нет).
3. Скопируй [`chrome/userChrome.css`](chrome/userChrome.css) в папку `chrome`,
   чтобы путь был `…/<профиль>/chrome/userChrome.css`.
4. Открой `about:config`, найди
   `toolkit.legacyUserProfileCustomizations.stylesheets` и поставь `true`.
5. **Полностью перезапусти** Firefox (CSS хрома читается только при старте).

## Настройка

Все параметры — это CSS-переменные в начале файла: `--tab-border-radius`,
`--tab-curve`, `--tabstrip-darken`, `--panel-menuitem-border-radius`,
`--popup-border-radius`. Измени значение, сохрани, перезапусти Firefox.

## Удаление

Удали `chrome/userChrome.css` (или папку `chrome`) и перезапусти Firefox.

## Лицензия

[MIT](LICENSE)
