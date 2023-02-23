	# Documenting Project-2

    `sudo apt update`
    `sudo apt install nginx`
    	![nginx installation](./Project-2/Images-2/apt%20install%20nginx%201.PNG)
    `sudo systemctl status nginx`
    	![nginx systemctl status](./Project-2/Images-2/nginx%20installation%20status.PNG)
    `curl http://localhost:80`
    	[nginx server response from internet](https://35.173.135.206:80)
    `sudo apt install mysql-server`
    `sudo mysql -p`
    `sudo apt install php-fpm php-mysql`
    	![php-fpm php-mysql installation output1](./Project-2/Images-2/php-fpm%20php-mysql%20installation%20output%201.PNG)
        ![php-fpm php-mysql installation output2](./Project-2/Images-2/php-fpm%20php-mysql%20installation%20output%202.PNG)
    `sudo mkdir /var/www/projectLEMP`
    `sudo chown -R $USER:$USER /var/www/projectLEMP`
    `sudo vim /etc/nginx/sites-available/projectLEMP`
    `sudo ln -s /etc/nginx/sites-available/projectLEMP /etc/nginx/sites-enabled/`
    `sudo nginx -t`
    ![nginx syntax output](./Project-2/Images-2/nginx%20syntax%20ok.PNG)
    `sudo unlink /etc/nginx/sites-enabled/default`
    `sudo systemctl reload nginx`
    `sudo echo 'Hello LEMP from hostname' $(curl -s http://169.254.169.254/latest/meta-data/public-hostname) 'with public IP' $(curl -s http://169.254.169.254/latest/meta-data/public-ipv4) > /var/www/projectLEMP/index.html`
    [opening url in browser](https://35.173.135.206:80)
    ![browser output](./Project-2/Images-2/IP%20Address%20in%20browser%20output-nginx%20php.PNG)
    `sudo nano /var/www/projectLEMP/info.php`
    - <?php
- phpinfo();
[opening page in browser](https://35.173.135.206/info.php
![browser output](./Project-2/Images-2/IP%20Address%20in%20browser%20output-nginx%20info.php)
`sudo mysql -p`
`mysql> CREATE DATABASE `example_database`;`
`mysql>  CREATE USER 'example_user'@'%' IDENTIFIED WITH mysql_native_password BY 'password';`
`mysql> GRANT ALL ON example_database.* TO 'example_user'@'%';`
`mysql> exit`
`mysql -u example_user -p`
	![example_user login successful](./Project-2/Images-2/example_user%20successfully%20logs%20into%20mysql.PNG)
`mysql> SHOW DATABASES;`
![confirmation of user control of database](./Project-2/Images-2/confirmation%20of%20user%20control%20of%20database.PNG)
![my test_table output]()
`mysql> CREATE TABLE example_database.todo_list (item_id INT AUTO_INCREMENT,content VARCHAR(25), PRIMARY KEY(item_id))`
![creating table database](./Project-2/Images-2/Creating%20table.PNG)
`mysql> INSERT INTO example_database.todo_list (content) VALUES ("My first important item");`
`mysql> INSERT INTO example_database.todo_list (content) VALUES ("My second important item");`
`mysql> INSERT INTO example_database.todo_list (content) VALUES ("My third important item");`
![inserting rows of content](./Project-2/Images-2/Inserting%20rows%20of%20contents%20in%20test%20table.PNG)
`mysql>  SELECT * FROM example_database.todo_list;`
![my test_table output](./Project-2/Images-2/My%20test%20table%20output.PNG)
`mysql> exit`
`vim /var/www/projectLEMP/todo_list.php`
![todo_list script content](./Project-2/Images-2/todo_list.php%20script.PNG)
	[requesting for my todo_list table from browser](http://35.173.135.206/todo_list.php)
    	![todo_list table from browser](./Project-2/Images-2/Requesting%20for%20my%20test%20table%20from%20browser.PNG)
