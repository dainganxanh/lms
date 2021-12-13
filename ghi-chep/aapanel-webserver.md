# 🔃 aaPanel Webserver

## Setup

```
wget -O install.sh http://www.aapanel.com/script/install-ubuntu_6.0_en.sh
bash install.sh
```

Mặc định panel chạy port 8888

Nên thay đổi port đồng thời mở port tương ứng trên router

Kiểm tra trạng thái các port: ufw status

Cài đặt Nginx, MySQL, FTP, PHP, phpMyadmin, Mail Server (LEMP)

## Wordpress

Bật URL Rewrite

```
location /
{
	 try_files $uri $uri/ /index.php?$args;
}
rewrite /wp-admin$ $scheme://$host$uri/ permanent;
```

### Lỗi không truy cập được wp-admin

Lỗi báo: too many redirects issue in wordpress

Cách xử lý: Thêm vào sau tag php đầu file **wp-config.php**&#x20;

```
if($_SERVER['PHP_SELF']=="/index.php")
{
define('WP_HOME','https://yourdomain.com');
define('WP_SITEURL','https://yourdomain.com');
}
else
{
define('WP_HOME','http://yourdomain.com');
define('WP_SITEURL','http://yourdomain.com');
}
```
