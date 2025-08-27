O código do 'coiso.dart' deve ser inserido no arquivo principal de um arquivo flutter.

Dentro do HeidiBD, criar o banco com os seguintes comandos SQL:

CREATE DATABASE client_order_system; 
USE client_order_system; 
CREATE TABLE clients ( 
client_id INT AUTO_INCREMENT PRIMARY KEY, 
name VARCHAR(100) NOT NULL, 
email VARCHAR(100) UNIQUE NOT NULL, 
address TEXT, 
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP 
); 

CREATE TABLE orders ( 
order_id INT AUTO_INCREMENT PRIMARY KEY, 
client_id INT NOT NULL, 
order_date DATE NOT NULL, 
total_amount DECIMAL(10,2) NOT NULL, 
status ENUM('pending', 'completed', 'cancelled') DEFAULT 'pending', 
created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP, 
FOREIGN KEY (client_id) REFERENCES clients(client_id) 
); 



