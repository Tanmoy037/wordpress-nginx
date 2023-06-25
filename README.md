# wordpress-nginx
For building wordpress image -
``` docker build -t wordpress-image -f Dockerfile-wordpress . ```

For building nginx image -
``` docker build -t nginx-image -f Dockerfile-nginx . ```

For creating mysql image -
``` docker build -t mysql-image -f Dockerfile-mysql . ```


For running mysql container -
``` docker container run -d --name mysqldb -p 3306:3306 --restart=always -e MYSQL_ROOT_PASSWORD=root -e MYSQL_DATABASE=wordpress -e MYSQL_USER=wordpressuser -e MYSQL_PASSWORD=wordpress -v mysql_data:/var/lib/mysql mysql-image ```

For running the WordPress container - 
``` docker container run -d --name wordpress --link mysqldb -p 8080:80 -e WORDPRESS_DB_HOST=mysqldb:3306 -e WORDPRESS_DB_NAME=wordpress -e WORDPRESS_DB_USER=wordpressuser -e WORDPRESS_DB_PASSWORD=wordpress  -v wordpress_data:/var/www/html wordpress-image ```

For running the Nginx Container - 
``` docker run --name nginx -p 80:80 --link wordpress nginx-image ```

![Screenshot (349)](https://github.com/Tanmoy037/wordpress-nginx/assets/108757431/d0a57a64-b01e-49fa-872b-cb847029c536)


![Screenshot (350)](https://github.com/Tanmoy037/wordpress-nginx/assets/108757431/0a7976a2-16de-4467-a8ed-a62f00fd33c0)


