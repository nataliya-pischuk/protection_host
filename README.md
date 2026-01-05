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
помощью команды sudo ecryptfs-migrate-home -u cryptouser зашифрован каталог пользователя
![alt text](img/3.JPG)
Результат
![alt text](img/4.JPG)
