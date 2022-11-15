# MySQL installation

[https://www.actualidadgadget.com/az/mysql-i-windows-a-nec%C9%99-qura%C5%9Fd%C4%B1rmaq-olar/](https://www.actualidadgadget.com/az/mysql-i-windows-a-nec%C9%99-qura%C5%9Fd%C4%B1rmaq-olar/)

```

CREATE TABLE channels (

	id INT AUTO_INCREMENT PRIMARY KEY,
	type ENUM('Mobile','Web')
);

CREATE TABLE customers (

	id INT AUTO_INCREMENT PRIMARY KEY,
	first_name VARCHAR(30),
	last_name VARCHAR(30),
	phone_number VARCHAR(11)
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
