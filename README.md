# Домашнее задание к занятию «Защита хоста»
## Задание 1
Установите eCryptfs.
Добавьте пользователя cryptouser.
Зашифруйте домашний каталог пользователя с помощью eCryptfs.
## Ответ
Был установлен пакет acryptfs-utils
![alt text](img/1.JPG)
Добавлен пользователь cryptouser и прописан в файле sudoers, а также созданы файлы в директории users
![alt text](img/2.JPG)
помощью команды sudo ecryptfs-migrate-home -u cryptouser зашифровала каталог пользователя
![alt text](img/3.JPG)
Результат и информация для восстановления
![alt text](img/4.JPG)

## Задание 2
- Установите поддержку LUKS.
- Создайте небольшой раздел, например, 100 Мб.
- Зашифруйте созданный раздел с помощью LUKS.
В качестве ответа пришлите снимки экрана с поэтапным выполнением задания.
## Ответ
Была установлена поддержка LUKS — пакет cryptsetup
#### sudo apt-get install cryptsetup
![alt text](img/5.JPG)

Дополнительно  подготовила диск. Так в у меня существовал только один раздел в Linux, который не подлежит изменению, я в VirtualBox через менеджер виртуальных носителей добавила дисковое пространство и потом уже через программу gparted сформировала нужный мне раздел
##### sudo apt install gparted

![alt text](img/6.JPG)

![alt text](img/7.JPG)

Зашифровала раздел sda3

sudo cryptsetup -y -v --type luks2 luksFormas /dev/sda3 — сама шифровка

![alt text](img/6.1.JPG)

Провела монтирование раздела и выврл смонтированного диска
![alt text](img/8.JPG)
![alt text](img/9.JPG)


sudo cryptsetup luksDump /dev/sda3 — для проверки шифрования
![alt text](img/10.JPG)

