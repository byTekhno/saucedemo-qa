# BUG-002 Поле Last Name на чекауте не даёт ввести фамилию (problem_user)

**Статус:** Confirmed  
**Серьёзность:** Critical  
**Приоритет:** High  
**Окружение:** Windows 11, Chrome 139, [https://www.saucedemo.com/checkout-step-one.html](https://www.saucedemo.com/checkout-step-one.html)  
**Пользователь:** `problem_user` / `secret_sauce`  
**Дата обнаружения:** 2026-08-20  
**Дата подтверждения:** 2026-08-22

## Шаги

1. Войти как `problem_user` / `secret_sauce`
2. Добавить в корзину товар, который удаётся добавить (если часть кнопок Add to cart не работает — взять рабочую)
3. Открыть корзину → Checkout
4. Ввести First Name `Ivan`
5. Кликнуть в Last Name и попытаться ввести `Ivanov`
6. Заполнить Postal Code `100100` и нажать Continue

## Фактический результат

Поле Last Name не принимает фамилию (остаётся пустым). После Continue показывается ошибка `Error: Last Name is required`. Обзор заказа не открывается — завершить покупку нельзя.

## Ожидаемый результат

Фамилия вводится, Continue открывает `/checkout-step-two.html`.

## Дополнительно

- Воспроизводится всегда на `problem_user`
- На `standard_user` форма работает (см. прогон TC-CHK-*)
- Это заложенный дефект демо-роли, но для роли пользователя  — Critical: нельзя оформить заказ
- Скрин: `bugs/screenshots/BUG-002-problem_user-checkout-step-one.png` — ошибка `Last Name is required`, заказ заблокирован

