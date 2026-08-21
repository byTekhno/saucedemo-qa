# BUG-004 Можно оформить заказ с пустой корзиной

**Статус:** New  
**Серьёзность:** Major  
**Приоритет:** High  
**Окружение:** Windows 11, Chrome 139, [https://www.saucedemo.com](https://www.saucedemo.com)  
**Пользователь:** `standard_user` / `secret_sauce`  
**Дата:** 2026-08-20

## Шаги

1. Открыть [https://www.saucedemo.com](https://www.saucedemo.com)
2. Войти как `standard_user` / `secret_sauce`
3. Убедиться, что корзина пустая (бейджа нет), открыть корзину `/cart.html`
4. Нажать Checkout
5. Заполнить First Name `Anna`, Last Name `Ivanova`, Postal Code `101000`
6. Нажать Continue
7. Нажать Finish

## Фактический результат

`Checkout` из пустой корзины доступен. Форма на шаге 1 принимается без товаров. Обзор заказа открывается с пустым составом, `Item total: $0`, `Tax: $0.00`, `Total: $0.00.`  `Finish` переводит на `/checkout-complete.html` с текстом `Thank you for your order!`. Пустой заказ успешно завершается.

## Ожидаемый результат

Кнопка Checkout недоступна при пустой корзине **или** система показывает ошибку до Thank you и не даёт завершить заказ без товаров.

## Дополнительно

- Воспроизводится всегда
- Воспроизводится на `standard_user` (не только на демо-ролях)
- Скрин: `bugs/screenshots/BUG-004.png` — страница Thank you
- Скрин: `bugs/screenshots/BUG-004-overview.png` — обзор без товаров / `$0.00`
- Скрин: `bugs/screenshots/BUG-004-cart.png` — пустая корзина с активным `Checkout`

## Примечание

Это бизнес-логика магазина, а не особенность `problem_user` / `visual_user`.

Кандидат на Critical, если бизнес считает пустой заказ недопустимым.