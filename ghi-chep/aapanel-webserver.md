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

### Lỗi không update được bài

Publishing failed. You are probably offline

Cài Really Simple SSL plugin và thêm vào file .htaccess code sau:

```
# Really Simple SSL
Header always set Strict-Transport-Security: "max-age=31536000" env=HTTPS
Header always set Content-Security-Policy "upgrade-insecure-requests"
Header always set X-Content-Type-Options "nosniff"
Header always set X-XSS-Protection "1; mode=block"
Header always set Expect-CT "max-age=7776000, enforce"
Header always set Referrer-Policy: "no-referrer-when-downgrade"
# End Really Simple SSL
```
