 cd /var/www/ham-mysql/
 chua các hàm thao tác đến mysql
 ./ten-ham-mysql.sh -> kiểm tra thông tin kết nối mysql

 cau hinh mysql:
 nano /etc/mysql/mysql.conf.d/mysqld.cnf
 bind-address            = 0.0.0.0
 mysqlx-bind-address     = 0.0.0.0
 service mysql status!start!stop!restart

 dang nhap mysql:
 mysql -u ten-user -p'matkhau';

 - câu lệnh import
 mysql -u ten-user -p'matkhau'  < ten-database.gz

 - câu lệnh export
 mysqldump  -u ten-user -p'matkhau'  > ten-database

 - câu lệnh truy cập từ xa
mysql -h [remote_host_ip] -u [username] -p'mat-khau'

- Tạo tài khoản người dùng mới:
// truy cap noi bo
CREATE USER 'tungocvan'@'localhost' IDENTIFIED BY 'password'; 
GRANT ALL PRIVILEGES ON *.* TO 'tungocvan'@'localhost';
FLUSH PRIVILEGES;

// user có the truy cap ra ben ngoai
CREATE USER 'tungocvan'@'%' IDENTIFIED BY 'Van@2024'; 
GRANT ALL PRIVILEGES ON *.* TO 'tungocvan'@'%';
FLUSH PRIVILEGES;
SELECT User,Host FROM mysql.user;

// các lệnh sau khi đăng nhập vào mysql có thể sử dụng:

CREATE DATABASE ten-database;
SHOW DATABASES;
use ten-database;
SHOW TABLES;
select * from users;
DELETE FROM users WHERE id=1;
TRUNCATE TABLE ten_bang;



// các lệnh khác
- Xem danh sách các tài khoản người dùng:
SELECT User,Host FROM mysql.user;
- Đổi mật khẩu cho tài khoản người dùng:
ALTER USER 'username'@'localhost' IDENTIFIED BY 'new_password';
- Xóa tài khoản người dùng:
DROP USER 'username'@'localhost';
- Thay đổi quyền của người dùng:
REVOKE permission ON database.table FROM 'username'@'localhost';
- Hiển thị tất cả các quyền của người dùng:
SHOW GRANTS FOR 'username'@'localhost';