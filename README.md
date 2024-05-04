# Market_Basket_Analysis
Market basket analysis is a data mining technique used by retailers to increase sales by better understanding customer purchasing patterns. 
It involves analyzing large data sets, such as purchase history, to reveal product groupings, as well as products that are likely to be purchased together.

Dataset for this project was sourced from Google BigQuery's Library ("TheLook_Ecommerce Database).
Below is SQL code used to extract the needed attributes.

SELECT
o.user_id,
(oi.order_id),
product_id,
num_of_item AS quantity, 
name,
sale_price,
o.status,
o.created_at AS Date,
city
FROM bigquery-public-data.thelook_ecommerce.order_items AS oi
JOIN bigquery-public-data.thelook_ecommerce.orders AS o ON oi.user_id = o.user_id
JOIN bigquery-public-data.thelook_ecommerce.products AS p ON oi.id = p.id
JOIN bigquery-public-data.thelook_ecommerce.events AS e ON oi.id = e.id
