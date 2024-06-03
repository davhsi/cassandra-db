```
CREATE KEYSPACE IF NOT EXISTS ecommerce 
WITH replication = {'class': 'SimpleStrategy', 'replication_factor': 1};

USE ecommerce;

CREATE TABLE IF NOT EXISTS products (
    product_id UUID PRIMARY KEY,
    name TEXT,
    price DECIMAL
);

CREATE TABLE IF NOT EXISTS orders (
    order_id UUID PRIMARY KEY,
    product_id UUID,
    quantity INT,
    total_price DECIMAL
);

INSERT INTO products (product_id, name, price) VALUES (uuid(), 'Product A', 19.99);

SELECT * FROM products;

UPDATE products SET price = 313.69 WHERE product_id = <existing_product_id>;

DELETE FROM products WHERE product_id = <existing_product_id>;
```
