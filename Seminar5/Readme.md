# Контейнеризация (семинары)


## Урок 5. Docker Compose и Docker Swarm

### **Домашнее задание**

Задание:
1 создать сервис, состоящий из 2 различных контейнеров: 1 - веб, 2 - БД

**История команд**

    1  apt update
    2  sudo apt install apt-transport-https ca-certificates curl software-properties-common
    3  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
    4  sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
    5  apt update
    6  apt-cache policy docker-ce
    7  sudo apt install docker-ce
    8  sudo systemctl status docker
    9  docker run hello-world
   10  docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=test -d mysql:8.0.31
   11  docker run --name myphp -d --link some-mysql:db -p 8081:80 phpmyadmin/phpmyadmin
   12  docker ps -a
   13  ip a
   14  docker ps -a
   15  docker systemctl
   16  mkdir testfolder/
   17  ll
   18  cd testfolder
   19  vim docker-compose.yml
   20  docker compose up -d
   21  vim docker-compose.yml
   22  docker container ls
   23  docker stop 6dfbab24dad0
   24  docker compose up -d
   25  docker ps -a
   26  vim docker-compose.yml
   27  docker stop ecec26c833b7
   28  docker stop b75b0ede16ce
   29  docker ps -a
   30  history


**Выполнение**

![LXC setup](https://github.com/ScarletStranger/containerization/blob/main/Seminar3/Pics/1.png)

![LXC setup](https://github.com/ScarletStranger/containerization/blob/main/Seminar3/Pics/2.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar3/Pics/3.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar3/Pics/4.png)

![LXC setup](https://github.com/ScarletStranger/containerization/blob/main/Seminar3/Pics/5.png)

![LXC setup](https://github.com/ScarletStranger/containerization/blob/main/Seminar3/Pics/6.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar3/Pics/7.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar3/Pics/8.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar3/Pics/9.png)

*Подготовил студент Geek Brains* [**`Леденев Максим`**](https://github.com/ScarletStranger), containerization
