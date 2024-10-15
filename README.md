## Деплой

### Nginx
1. Установить пакеты
`sudo apt update`
`sudo apt install nginx certbot python3-certbot-nginx`

2. Скопировать nginx.conf в директорию `/etc/nginx/sites-available` и назвать по примеру `example.com.conf`, переименовать пути к папкам внутри файла, проверить правильность файла `sudo nginx -t`
3. Перезагрузить nginx
`sudo systemctl reload nginx`
4. Настроить брандмауэр
`sudo ufw allow 'Nginx Full'`
`sudo ufw delete allow 'Nginx HTTP'`
1. Настройка SSL сертификата
`sudo certbot --nginx -d example.com`

1. Склонировать репозиторий backend в папку /backend
2. Настроить `.env-prod` файл
3. Заменить путь в `docker-compose.yaml` в разделе `volumes`
4. Склонировать репозиторий admin-frontend в папку /admin
5. Склонировать репозиторий public-frontend в папку /public
6.  Выполнить команду `docker compose build`
7.  Выполнить команду `docker compose up`

P.S. Meilisync вроде как не настроен вообще в коде