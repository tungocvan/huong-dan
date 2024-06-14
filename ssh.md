sudo apt install openssh-server
service sshd status
service sshd start

nano  /etc/ssh/sshd_config
ListenAddress 0.0.0.0
PermitRootLogin yes
PubkeyAuthentication yes
PasswordAuthentication yes

sau khi cau hinh xong:
service sshd restart
service sshd status

Tao SSH Key và cấu hình xác thực bằng SSH Key:
https://xuanthulab.net/tao-ssh-key-va-xac-thuc-ket-noi-ssh-bang-public-private-key.html

file luu public key: 
neu la root -> /root/.ssh/authorized_keys
hoac user -> /user/.ssh/authorized_keys

// cach tao 1 cap key dang nhap ko can password
tao thu muc keys: mkdri keys
cd keys
ssh-keygen -t rsa
chon: id_rsa
enter 2 lan -> server tao ra 2 files: id_rsa (client)  id_rsa.pub (server)

sau do copy id_rsa.pub vao /root/.ssh/  va doi ten thanh tap tin authorized_keys 
mkdir -p  /root/.ssh
cp id_rsa.pub /root/.ssh/authorized_keys
chmod 600 /root/.ssh/authorized_keys
chmod 700 /root/.ssh

- phia client luu private key file id_rsa ve client:
cd C:\Users\Administrator\.ssh // Administrator là user trên windows
chuyen den thu muc .ssh cua window: xoa het tat ca file co trong .ssh vd: known_hosts
scp -r root@ip-server:/root/.ssh/id_rsa ./

test lai:
ssh root@ip-server -> chon yes
