docker images
docker ps | docker ps -l } docker ps -a

- docker run
docker run -p 80:80 -p 443:443 -p 33060:3306 --name tnv_php_mysql -v /d/docker/tnv-php-mysql:/var/www/tnv-php-mysql --network tnv-network -it tnv_php_mysql_v1:latest
docker run -p 33060:3306 --name mysql --network tnv-network --hostname mysql  -v /d/docker/mysql:/home -it tungocvan/tnv-mysql-8-wordpress:v1.0
docker run -p 80:80 --name wordpress653 --network tnv-network --hostname wordpress653  -it tungocvan/tnv-php82-1:1.0

- docker exec -it contianer-id bash / sh
- docker stop|start|rm contianer-id

- tao network docker:
docker network create tnv-network
docker network ls
docker network rm tnv

- build docker container -> images
docker stop  contianer-id
docker commit  contianer-id ten-image:phien-ban

- day image len docker hub
docker tag images-name:phien-ban tungocvan/images-name:phien-ban
docker push tungocvan/images-name:phien-ban

- stop container hoac xoa container hang loat: co name bat dau la: laradock

docker ps -a --filter "name=laradock"
docker rm $(docker ps -a --filter "name=laradock" -q)

- xoa images thi docker rmi images-id

- download image ve local:
docker pull image-name:phienban

- doi voi file yml hoac yaml dung docker compose
 docker-compose up -d ten_service 
 docker-compose up -d  // khoi tao cac container co trong file