# SQL for creating the electron\_banking database

```sql

CREATE TABLE channels (

	id INT AUTO_INCREMENT PRIMARY KEY,
	type ENUM('Mobile','Web')
);

CREATE TABLE customers (

	id INT AUTO_INCREMENT PRIMARY KEY,
	first_name VARCHAR(30),
	last_name VARCHAR(30),
	phone_number VARCHAR(13)
);

CREATE TABLE transactions (

	id INT AUTO_INCREMENT PRIMARY KEY,
	channel_id INT,
	customer_id INT,
	date DATETIME,
	FOREIGN KEY (channel_id) REFERENCES channels(id),
	FOREIGN KEY (customer_id) REFERENCES customers(id)
);

```
