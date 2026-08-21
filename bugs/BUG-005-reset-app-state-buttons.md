# BUG-005 Reset App State не сбрасывает кнопки Remove в каталоге

**Статус:** New  
**Серьёзность:** Major  
**Приоритет:** Medium  
**Окружение:** Windows 11, Chrome 139, [https://www.saucedemo.com](https://www.saucedemo.com)  
**Пользователь:** `standard_user` / `secret_sauce`  
**Дата:** 2026-08-22

## Шаги

1. Открыть [https://www.saucedemo.com](https://www.saucedemo.com)
2. Войти как `standard_user` / `secret_sauce`
3. Добавить в корзину 2 товара (например Backpack и Bike Light), бейдж = 2
4. Открыть меню → Reset App State
5. Посмотреть бейдж и кнопки на карточках товаров в каталоге
6. Открыть корзину `/cart.html`

## Фактический результат

Бейдж корзины исчезает. Список в корзине пустой. В каталоге у Backpack и Bike Light остаётся кнопка `Remove` вместо `Add to cart`. Состояние кнопок не сбрасывается вместе с корзиной.

## Ожидаемый результат

После Reset App State бейдж отсутствует, корзина пустая, на всех товарах в каталоге снова `Add to cart`.

## Дополнительно

- Воспроизводится всегда
- Воспроизводится на `standard_user`
- Связанный кейс: TC-NAV-004
- Скрин: `bugs/screenshots/BUG-005.png` - каталог с `Remove` при пустой корзине / без бейджа
- Скрин: `bugs/screenshots/BUG-005-cart.png` - пустая корзина, без бейджа

## Примечание

Это рассинхрон UI и состояния корзины после сброса. Не особенность демо-ролей `problem_user` / `visual_user`.