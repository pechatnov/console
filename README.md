### SSH
###### Генерация ключа
`ssh-keygen -t rsa`
###### Просмотр ключа
`cat ~/.ssh/id_rsa.pub`
###### Вход
`ssh bitrix@dev.ru`
###### Админ
`sudo su`  
`sudo -s`
###### Архив
`zip -r bitrix.zip bitrix`  
`unzip bitrix.zip`  
`zip -r /home/bitrix/www/www.zip /home/bitrix/www`  
`unzip www.zip -d /home/bitrix/www`

### Mysql
###### Админ
`sudo mysql -u root`
###### Перезагрузка
`sudo service mysql restart`  
`systemctl stop mysql`  
`systemctl start mysql`
###### Создание бекапа
`mysqldump -u bxgrand1 -p asd > asd.sql`
###### Создание сюперюзера
`CREATE USER 'bxgrand1'@'localhost' IDENTIFIED BY 'password123';`  
`GRANT ALL PRIVILEGES ON * . * TO 'bxgrand1'@'localhost';`  
`FLUSH PRIVILEGES;`

### Apache
###### Перезагрузка
`service httpd restart`
###### Установка пакетов
`yum install mc`  
`yum install curl-devel`  
`yum install nano`  
`yum install nodejs`  
`yum install npm`  
`npm install -g @bitrix/cli`

### BitrixVM
###### Перейти в корень
`/root/menu.sh`
###### Симлинки
`/home/bitrix/ext_www`
###### Кеш
`/opt/webdir/tmp`
###### Конфиг для редиректов
`/etc/httpd/bx/custom/z_bx_custom.conf`
###### Конфиг сессии
`/etc/php.ini`

### Rights
###### Права на файлы
`/home/bitrix/www`  
`find . -type d -exec chmod 775 {} \;`  
`find . -type f -exec chmod 664 {} \;`  
`find . -type d -exec chown bitrix:bitrix {} \;`  
`find . -type f -exec chown bitrix:bitrix {} \;`

### Migrations
###### Список
`php /home/bitrix/www/bitrix/modules/sprint.migration/tools/migrate.php ls`
###### Запуск
`php /home/bitrix/www/bitrix/modules/sprint.migration/tools/migrate.php up`

## Vue
###### Запуск сборки
`cd /home/bitrix/www/local/js`  
`bitrix build`

### Sql
###### Обновление в таблице
`UPDATE b_uts_user SET UF_STATUS = 1 WHERE VALUE_ID = "111";`

### Git
###### Изменение url
`git remote set-url origin 'url'`
###### Создание ветки от master
`git checkout master`  
`git checkout -b release/1.0`  
`git pull origin release/1.0`  
`git log --graph`
###### Создание ветки от release
`git checkout -b release/1.0 origin/release/1.0`
###### Обновление ветки
`git pull origin release/1.0`
###### Сброс изменений
`cd /home/bitrix/www`  
`git reset --hard`  
`git clean -fd`