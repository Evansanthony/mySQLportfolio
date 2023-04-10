SELECT 
  customers.customer_name, 
  orders.order_date, 
  order_items.product_name,
  order_items.quantity, 
  order_items.price_per_unit, 
  order_items.quantity * order_items.price_per_unit AS total_price
FROM 
  customers 
  JOIN orders ON customers.customer_id = orders.customer_id
  JOIN order_items ON orders.order_id = order_items.order_id
WHERE 
  orders.order_date BETWEEN '2022-01-01' AND '2022-12-31'
ORDER BY 
  customers.customer_name, 
  orders.order_date;

