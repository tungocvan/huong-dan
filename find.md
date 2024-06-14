find / -name "php.ini" 2>/dev/null
find / -type f -name "*.txt" 2>/dev/null
find duong-dan-thu-muc-can-tim -type f -name "*.txt" 2>/dev/null


find / -type f -name "*.txt" -exec cp {} /path/to/destination \; 2>/dev/null
find duong-dan-thu-muc-can-tim -type f -name "*.txt" -exec cp {} /home/user/destination \; 2>/dev/null

find / -type f -name "*.txt" -exec rm {} \; 2>/dev/null
find duong-dan-thu-muc-can-tim -type f -name "*.txt" -exec rm {} \; 2>/dev/null

find . -type d -exec chmod 755 {} \;
find . -type f -exec chmod 644 {} \;

// hàm tìm kiếm duong dan file thực thi
which php
which php-fpm7.4


