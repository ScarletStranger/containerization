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
    9  sudo usermod -aG docker ${user}
   10  sudo usermod -aG docker ${root}
   11  docker run hello-world
   12  docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=test -d mysql:8.0.31
   13  docker run --name myphp -d --link some-mysql:db -p 8081:80 phpmyadmin/phpmyadmin
   14  docker ps -a
   15  ip a
   16  docker ps -a
   17  docker systemctl
   18  mkdir testfolder/
   19  ll
   20  cd testfolder
   21  vim docker-compose.yml
   22  docker compose up -d
   23  vim docker-compose.yml
   24  docker container ls
   25  docker stop 6dfbab24dad0
   26  docker compose up -d
   27  docker ps -a
   28  vim docker-compose.yml
   29  docker stop ecec26c833b7
   30  docker stop b75b0ede16ce
   31  docker ps -a
   32  history



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
