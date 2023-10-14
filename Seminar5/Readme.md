# Контейнеризация (семинары)


## Урок 5. Docker Compose и Docker Swarm

### **Домашнее задание**

Задание:
1 создать сервис, состоящий из 2 различных контейнеров: 1 - веб, 2 - БД

**История команд**


apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
apt update
apt-cache policy docker-ce
sudo apt install docker-ce
sudo systemctl status docker
docker run hello-world
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=test -d mysql:8.0.31
docker run --name myphp -d --link some-mysql:db -p 8081:80 phpmyadmin/phpmyadmin
docker ps -a
ip a
docker ps -a
docker systemctl
mkdir testfolder/
ll
cd testfolder
vim docker-compose.yml
docker compose up -d
vim docker-compose.yml
docker container ls
docker stop 6dfbab24dad0
docker compose up -d
docker ps -a
vim docker-compose.yml
docker stop ecec26c833b7
docker stop b75b0ede16ce
docker ps -a
history


**Выполнение**

![LXC setup](https://github.com/ScarletStranger/containerization/blob/main/Seminar5/Pics/1.png)

![LXC setup](https://github.com/ScarletStranger/containerization/blob/main/Seminar5/Pics/2.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar5/Pics/3.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar5/Pics/4.png)

![LXC setup](https://github.com/ScarletStranger/containerization/blob/main/Seminar5/Pics/5.png)

![LXC setup](https://github.com/ScarletStranger/containerization/blob/main/Seminar5/Pics/6.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar5/Pics/7.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar5/Pics/8.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar5/Pics/9.png)

*Подготовил студент Geek Brains* [**`Леденев Максим`**](https://github.com/ScarletStranger), containerization
