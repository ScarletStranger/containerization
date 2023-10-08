# Контейнеризация (семинары)


## Урок 3. Введение в Docker

### **Домашнее задание**

Задание:
1) Установить Docker
2) Протестировать Docker
3) Хранение данных в контейнерах Docker


**История команд**

sudo apt update
Установите пакеты, которые позволят использовать репозиторий по HTTPS:

sudo apt install apt-transport-https ca-certificates curl software-properties-common
Добавьте официальный GPG-ключ Docker:

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
Для других дистрибутивов, замените URL на соответствующий.

Добавьте репозиторий Docker к списку источников пакетов:

echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
Обновите список пакетов, чтобы включить информацию о пакетах Docker из добавленного репозитория:

sudo apt update
Установите Docker:

sudo apt install docker-ce
Добавьте вашего пользователя в группу docker, чтобы избежать использования sudo для запуска Docker команд:

sudo usermod -aG docker $USER
Перезагрузите систему или запустите следующую команду, чтобы применить изменения в текущем сеансе:

newgrp docker
Теперь вы должны быть готовы использовать Docker через терминал. Вы можете проверить его работу, выполнив команду:

docker --version


2 -тестируем.

Запустите контейнер с использованием образа "cowsay". Команда будет выглядеть так:

docker run docker/whalesay cowsay Hello, Docker!
В данном примере используется образ "docker/whalesay", который содержит утилиту "cowsay". Он будет выводить на экран сообщение "Hello, Docker!" с помощью рисунка коровы.

вот несколько интересных вариаций запуска контейнеров с разными животными с использованием утилиты cowsay:

Запустить контейнер с рисунком слона:

docker run docker/whalesay cowsay -f elephant "Hello, Docker!"
Запустить контейнер с рисунком пингвина:

docker run docker/whalesay cowsay -f tux "Hello, Docker!"
Запустить контейнер с рисунком дракона:

docker run docker/whalesay cowsay -f dragon "Hello, Docker!"
Запустить контейнер с рисунком кенгуру:

docker run docker/whalesay cowsay -f kangaroo "Hello, Docker!"
Запустить контейнер с рисунком утки:

docker run docker/whalesay cowsay -f duck "Hello, Docker!"
Запустить контейнер с рисунком панды:

docker run docker/whalesay cowsay -f panda "Hello, Docker!"
Запустить контейнер с рисунком совы:

docker run docker/whalesay cowsay -f owl "Hello, Docker!"
Запустить контейнер с рисунком кота:

docker run docker/whalesay cowsay -f kitty "Hello, Docker!"
Эти команды запустят контейнеры с различными рисунками животных с использованием cowsay. Вы можете заменить текст "Hello, Docker!" на любой другой текст, который вы хотите, чтобы животное "сказало". Таким образом, вы сможете не только визуально проверить работу Docker, но и весело провести время!

3 - тестируем команды.

Создание и запуск контейнеров:

docker run: Запускает контейнер из образа.
docker start: Запускает остановленный контейнер.
docker stop: Останавливает работающий контейнер.
docker restart: Перезапускает контейнер.
docker exec: Выполняет команду внутри запущенного контейнера.
Управление контейнерами:
docker rm $(docker ps -aq): удалит все остановленные контейнеры


docker ps: Просмотр списка запущенных контейнеров.
docker ps -a: Просмотр списка всех контейнеров (включая остановленные).
docker rm: Удаляет контейнер.
docker logs: Просмотр логов контейнера.
Работа с образами:

docker images: Просмотр списка образов.
docker pull: Загрузка образа с Docker Hub.
docker build: Сборка образа из Dockerfile.
docker rmi: Удаляет образ.


4- Хранение данных в контейнерах Docker: Руководство с пояснениями

В данной методичке мы рассмотрим примеры хранения файлов в контейнерах Docker. Параллельно с теоретическими пояснениями, студенты также будут выполнять практические задания для лучшего понимания материала.

Введение:
Мы уже ознакомились с основами работы с Docker, умеем запускать контейнеры и управлять параметрами. Сейчас давайте разберемся с тем, как можно хранить данные в контейнерах. Это критически важно для инженеров, работающих с Docker, так как хранение данных - ключевой аспект работы.

Задачи:

Для начала давайте запустим контейнер из образа Ubuntu и войдем в него:

docker run -it -h GB --name gb-test ubuntu:22.10
Посмотрим содержимое корневой директории:

ls -l /
Создадим новую директорию в корне:

mkdir /example
Создадим файл "passwords.txt" и добавим в него какие-либо данные (представим, что это данные сайта или базы данных). Но что делать, если у нас нет редактора? Продолжим.

touch /example/passwords.txt
echo "123test" >> /example/passwords.txt
Объяснение:
Мы создали директорию и файл внутри контейнера Ubuntu.

Задача:
Давайте попробуем остановить контейнер и затем запустить его снова. Сохранятся ли наши данные?

docker stop gb-test
docker start gb-test
docker exec -it gb-test bash
cat /example/passwords.txt


**Дальше пройти не получилось, так как использую для работы с линуксом облачный сервер, а он, судя по ошибке, сбрасывает соединение, когда я пытаюсь взаимодействовать с контейнером**

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
