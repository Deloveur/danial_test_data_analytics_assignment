# Блок 3: SQL

В данном блоке представлены решения заданий по SQL.

---

## Задание 1: Абитуриенты

Требуется определить позицию абитуриента в общем рейтинге по количеству набранных баллов.

```sql
SELECT
    id,
    scores,
    RANK() OVER (ORDER BY scores DESC) AS position
FROM examination;

---

## Задание 2: FULL JOIN

```sql
SELECT *
FROM table1 t1
FULL JOIN table2 t2
    ON t1.id = t2.id;

---

Даны две таблицы: первая содержит 30 строк, вторая — 20 строк.
Выполняется операция FULL JOIN.

Минимальное количество строк в результате — 30 (если все ключи второй таблицы содержатся в первой).
Максимальное количество строк — 50 (если ключи полностью уникальны).

---

## Задание 3: Покупки

```sql
SELECT
    a.client_id
FROM account a
JOIN transaction t
    ON a.id = t.account_id
WHERE
    t.type = 'BUY'
    AND t.transaction_date >= CURRENT_DATE - INTERVAL '1 month'
GROUP BY
    a.client_id
HAVING
    SUM(t.amount) < 5000;

---
Запрос агрегирует суммы покупок клиентов за последний месяц по всем их счетам и отбирает клиентов с общей суммой покупок менее 5000 рублей.

---

##
