sudo apt update
sudo apt upgrade
apt install nano -y


// hàm tìm kiếm duong dan file thực thi
which php
which php-fpm7.4

// lay dia chi ip
hostname -I
ip a

// anh xa port ra ngoai
netsh interface portproxy add v4tov4 listenport=80 listenaddress=0.0.0.0 connectport=80 connectaddress=172.24.59.239
netsh interface portproxy delete v4tov4 listenport=80 listenaddress=0.0.0.0
netsh interface portproxy reset
netsh interface portproxy show all