# Когортный анализ и RFM-сегментация пользователей маркетплейса

**Цель проекта:** сформулировать рекомендации маркетплейсу на основе анализа данных.

**Задачи проекта:** проанализировать совершенные покупки и ответить на следующие вопросы:

1. Сколько было пользователей, которые совершили покупку только один раз?
2. Сколько заказов в месяц в среднем не доставляется по разным причинам? Вывести детализацию по причинам.
3. По каждому товару определить в какой день недели товар чаще всего покупается.
4. Сколько у каждого из пользователей в среднем покупок в неделю (по месяцам)?
5. Выполнить когортный анализ пользователей. В период с января по декабрь выявить когорту с самым высоким retention на третий месяц.
6. Построить RFM-сегментацию пользователей для качественной оценки аудитории.

**Описание данных:**

**olist_customers_datase.csv** — таблица с уникальными идентификаторами пользователей

- customer_id — позаказный идентификатор пользователя
- customer_unique_id — уникальный идентификатор пользователя (аналог номера паспорта)
- customer_zip_code_prefix — почтовый индекс пользователя
- customer_city — город доставки пользователя
- customer_state — штат доставки пользователя

**olist_orders_dataset.csv** — таблица заказов

- order_id — уникальный идентификатор заказа (номер чека)
- customer_id — позаказный идентификатор пользователя
- order_status — статус заказа
- order_purchase_timestamp — время создания заказа
- order_approved_at — время подтверждения оплаты заказа
- order_delivered_carrier_date — время передачи заказа в логистическую службу
- order_delivered_customer_date — время доставки заказа
- order_estimated_delivery_date — обещанная дата доставки

**olist_order_items_dataset.csv** — товарные позиции, входящие в заказы

- order_id — уникальный идентификатор заказа (номер чека)
- order_item_id — идентификатор товара внутри одного заказа
- product_id — ид товара (аналог штрихкода)
- seller_id — ид производителя товара
- shipping_limit_date — максимальная дата доставки продавцом для передачи заказа партнеру по логистике
- price — цена за единицу товара
- freight_value — вес товара

**Уникальные статусы заказов в таблице olist_orders_dataset:**

- created — создан
- approved — подтверждён
- invoiced — выставлен счёт
- processing — в процессе сборки заказа
- shipped — отгружен со склада
- delivered — доставлен пользователю
- unavailable — недоступен
- canceled — отменён

**Используемые библиотеки:**

`pandas` `matplotlib` `seaborn` `requests` `urlencode` `datetime` `attrgetter` `warnings` `interactiveshell`
