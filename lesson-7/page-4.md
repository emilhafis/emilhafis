# Page 4

## SQL for creating the electron\_banking database

​CREATE TABLE channels (​id INT AUTO\_INCREMENT PRIMARY KEY,type ENUM('Mobile','Web'));​CREATE TABLE customers (​id INT AUTO\_INCREMENT PRIMARY KEY,first\_name VARCHAR(30),last\_name VARCHAR(30),phone\_number VARCHAR(11));​CREATE TABLE transactions (​id INT AUTO\_INCREMENT PRIMARY KEY,channel\_id INT,customer\_id INT,date DATETIME,FOREIGN KEY (channel\_id) REFERENCES channels(id),FOREIGN KEY (customer\_id) REFERENCES customers(id));​
