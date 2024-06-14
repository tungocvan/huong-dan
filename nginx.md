cd /etc/nginx/sites-available/
ls
cp tungocvan.tk ten-domain-cau-hinh
nano ten-domain-cau-hinh
chinh sua: server_name , root
nginx -t // kiem tra cau hinh -> oki->
ln -s  /etc/nginx/sites-available/ten-domain-cau-hinh /etc/nginx/sites-enabled/
nginx -s reload