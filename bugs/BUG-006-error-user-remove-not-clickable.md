# BUG-006 Кнопка Remove не кликабельна у части товаров (error_user)

**Статус:** New  
**Серьёзность:** Major  
**Приоритет:** High  
**Окружение:** Windows 11, Chrome 139, https://www.saucedemo.com  
**Пользователь:** `error_user` / `secret_sauce`  
**Дата:** 2026-08-24

## Шаги

1. Открыть https://www.saucedemo.com
2. Войти как `error_user` / `secret_sauce`
3. Нажать Add to cart у Sauce Labs Backpack, Sauce Labs Bike Light и Sauce Labs Onesie
4. Попытаться нажать Remove на этих карточках в каталоге
5. Открыть корзину `/cart.html` и попытаться нажать Remove у тех же товаров
6. Открыть меню → Reset App State

## Фактический результат

После добавления Backpack, Bike Light и Onesie бейдж обновляется, кнопка меняется на `Remove`, но клик не удаляет товар. Из корзины эти позиции тоже нельзя убрать обычной кнопкой. Единственный рабочий способ очистить корзину — Reset App State.

## Ожидаемый результат

`Remove` в каталоге и в корзине удаляет товар, бейдж уменьшается, кнопка снова становится `Add to cart`.

## Дополнительно

- Воспроизводится всегда
- На `standard_user` Remove работает
- Связанный дефект: BUG-007 — у Fleece Jacket, Bolt T-Shirt и Test.allTheThings() T-Shirt (Red) Add to cart вообще не активна
- Скрин: `bugs/screenshots/BUG-006-inventory.png` — каталог, Remove не срабатывает
- Скрин: `bugs/screenshots/BUG-006-cart.png` — корзина, Remove не срабатывает

## Примечание

Дефект демо-роли `error_user`. Не Critical: товар добавить можно, обход через Reset. Major — штатное удаление сломано.
