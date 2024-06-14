chown -R www-data:www-data thu-muc-website

// phan quyen thu muc
chmod -R 775 ten-thu-muc
chmod -R 755 ten-thu-muc

// phan quyen bao mat wordpess
cd wordpress
find . -type d -exec chmod 755 {} \;
find . -type f -exec chmod 644 {} \;