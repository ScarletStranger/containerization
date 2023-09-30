# Контейнеризация (семинары)


## Урок 1. Механизмы пространства имен


### **Домашнее задание**

Задание:
1) Изменение корневой папки
2) Добавление дополнительных файлов
3) Создание Пространства Имен для Сети
4) Изоляция по Процессам и Файловой Системе


**История команд**


mkdir ~/testfolder

mkdir ~/testfolder/bin

cp /bin/bash ~/testfolder/bin

mkdir ~/testfolder/lib ~/testfolder/lib64

cp /lib/x86_64-linux-gnu/libtinfo.so.6 ~/testfolder/lib

cp /lib/x86_64-linux-gnu/libc.so.6 ~/testfolder/lib

cp /lib64/ld-linux-x86-64.so.2 ~/testfolder/lib64/

sudo chroot ~/testfolder /bin/bash

ls

cp /bin/ls ~/testfolder/bin/

cp /lib/x86_64-linux-gnu/libselinux.so.1 ~/testfolder/lib/

cp /lib/x86_64-linux-gnu/libpcre2-8.so.0 ~/testfolder/lib/

ldd ~/testfolder/bin/ls

chroot ~/testfolder

ls /

ip netns add testns

ip netns exec testns bash

unshare --net --pid --fork --mount-proc /bin/bash

ps aux

unshare

ip a

ls

ls /

ps aux



**Выполнение**

![ChrootPreparation](https://github.com/ScarletStranger/containerization/blob/main/Seminar1/1.png)

![FileAddition](https://github.com/ScarletStranger/containerization/blob/main/Seminar1/2.png)

![Ipnets](https://github.com/ScarletStranger/containerization/blob/main/Seminar1/3.png)

![FileSystemIsolation](https://github.com/ScarletStranger/containerization/blob/main/Seminar1/4.png)


*Подготовил студент Geek Brains* [**`Леденев Максим`**](https://github.com/ScarletStranger), containerization
