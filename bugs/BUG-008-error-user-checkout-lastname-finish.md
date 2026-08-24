# BUG-008 error_user: нельзя заполнить Last Name и нельзя нажать Finish на Overview

**Статус:** New  
**Серьёзность:** Critical  
**Приоритет:** High  
**Окружение:** Windows 11, Chrome 139, https://www.saucedemo.com  
**Пользователь:** `error_user` / `secret_sauce`  
**Дата:** 2026-08-24

## Шаги

1. Открыть https://www.saucedemo.com
2. Войти как `error_user` / `secret_sauce`
3. Убедиться, что корзина пустая (бейдж = 0/не отображается)
4. Открыть `/cart.html` → нажать `Checkout`
5. На `/checkout-step-one.html` ввести First Name `Ivan`
6. Попытаться заполнить `Last Name` (не удаётся/остается пустым)
7. Оставить `Last Name` пустым и нажать `Continue`
8. На `/checkout-step-two.html` попытаться нажать `Finish`

## Фактический результат

На шаге 1 `Last Name` не заполняется (или не отображается ввод), при этом `Continue` проходит и открывает `/checkout-step-two.html`.

На шаге 2 кнопка `Finish` не удаётся для завершения заказа (клик/нажатие не работает), поэтому заказ завершить нельзя.

## Ожидаемый результат

`Last Name` заполняется, `Continue` открывает обзор заказа, а `Finish` завершает заказ и ведёт на `/checkout-complete.html` (Thank you).

## Дополнительно

- Воспроизводится при `error_user`
- Похоже на проблему в валидации/кликах checkout у `error_user`
- Скрин: `bugs/screenshots/BUG-008-cart-checkout.png` — пустая корзина, `Checkout` доступен
- Скрин: `bugs/screenshots/BUG-008-info.png` — `Last Name` не заполняется, `Continue` доступен
- Скрин: `bugs/screenshots/BUG-008-overview.png` — `Finish` не удаётся нажать

## Примечание

Критично, потому что невозможно завершить заказ (не выполняется шаг `Finish`) для `error_user`.

