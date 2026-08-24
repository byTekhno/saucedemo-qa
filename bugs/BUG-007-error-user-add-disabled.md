# BUG-007 Add to cart не активна у части товаров (error_user)

**Статус:** New  
**Серьёзность:** Major  
**Приоритет:** High  
**Окружение:** Windows 11, Chrome 139, https://www.saucedemo.com/inventory.html  
**Пользователь:** `error_user` / `secret_sauce`  
**Дата:** 2026-08-24

## Шаги

1. Открыть https://www.saucedemo.com
2. Войти как `error_user` / `secret_sauce`
3. В каталоге нажать Add to cart у:
   - Sauce Labs Fleece Jacket
   - Sauce Labs Bolt T-Shirt
   - Test.allTheThings() T-Shirt (Red)
4. Проверить бейдж корзины и состав `/cart.html`

## Фактический результат

Кнопка Add to cart у этих трёх товаров не активна: клик не добавляет товар в корзину. На `/cart.html` эти позиции отсутствуют (корзина без изменений), бейдж не меняется, кнопка не становится Remove. Купить эти позиции под `error_user` нельзя.

## Ожидаемый результат

Add to cart добавляет товар, бейдж увеличивается, кнопка меняется на Remove.

## Дополнительно

- Воспроизводится всегда
- На `standard_user` Add to cart у этих товаров работает
- Связанный дефект: BUG-006 — у Backpack, Bike Light и Onesie Add срабатывает, но Remove не кликабельна
- Скрин: `bugs/screenshots/BUG-007-inventory.png` — каталог, неактивный Add to cart у трёх товаров
- Скрин: `bugs/screenshots/BUG-007-cart.png` — `/cart.html` без добавленных позиций после попытки Add

## Примечание

Дефект демо-роли `error_user`. Major: три SKU из шести нельзя добавить в корзину. Не Critical для всего магазина — часть товаров ещё кладётся (см. BUG-006).
