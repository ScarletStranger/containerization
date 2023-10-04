# Контейнеризация (семинары)


## Урок 2. Механизмы контрольных групп

### **Домашнее задание**

Задание:
1) запустить контейнер с ubuntu, используя механизм LXC
2) ограничить контейнер 256 Мб ОЗУ и проверить, что ограничение работает
3) добавить автозапуск контейнеру, перезагрузить ОС и убедиться, что контейнер действительно запустился самостоятельно
4) при создании указать файл, куда записывать логи
5) после перезагрузки проанализировать логи


**История команд**

Установка ЛКС
sudo apt update
apt-get install lxc debootstrap bridge-utils lxc-templates
apt-get install lxd-installer
lxd init(Здесь просто нажимаем на Enter что уствновились значения по умолчанию)
Проверяем
lxc storage list
lxc storage list
И создаем контейнер

Создаем
sudo apt update
lxc-create -n test123 -t ubuntu --создаем контейнер
lxc-start -n test123 -- запускаем
lxc-attach -n teat123 -- войдем в него
free -m —проверяем пямаять
exit -- выходим
lxc-stop -n test123 - -закрываем

nano /var/lib/lxc/test123/config-открываем
lxc.rootfs.path = dir:/var/lib/lxc/test1234/rootfs — путь
lxc.uts.name = test1234 -- имя

Network configuration — Конфегурация сети
.
.
.
lxc.cgroup2.memory.max = 256M -- ограничиваем(В режиме Вставка делаем запись)

lxc-start -n test123 -- запускаем
lxc-attach -n teat123 -- войдем в него
free -m -- проверяем пямаять
!!!Видим что наше ограничение работает!!!

**Дальше пройти не получилось, так как использую для работы с линуксом облачный сервер, а он, судя по ошибке, сбрасывает соединение, когда я пытаюсь взаимодействовать с контейнером**

**Выполнение**

![LXC setup](https://github.com/ScarletStranger/containerization/blob/main/Seminar2/1.png)

![LXC setup](https://github.com/ScarletStranger/containerization/blob/main/Seminar2/2.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar2/3.png)

![LXC launch](https://github.com/ScarletStranger/containerization/blob/main/Seminar2/4.png)

![MemoryLimit](https://github.com/ScarletStranger/containerization/blob/main/Seminar2/5.png)

![MemoryLimit](https://github.com/ScarletStranger/containerization/blob/main/Seminar2/6.png)

![MemoryLimit](https://github.com/ScarletStranger/containerization/blob/main/Seminar2/7.png)

![Final](https://github.com/ScarletStranger/containerization/blob/main/Seminar2/8.png)

*Подготовил студент Geek Brains* [**`Леденев Максим`**](https://github.com/ScarletStranger), containerization
