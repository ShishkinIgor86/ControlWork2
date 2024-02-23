# Задание
## 1. Используя команду cat в терминале операционной системы Linux, создать два файла Домашние животные (заполнив файл собаками, кошками,хомяками) и Вьючные животными заполнив файл Лошадьми, верблюдами и ослы), а затем объединить их. Просмотреть содержимое созданного файла. Переименовать файл, дав ему новое имя (Друзья человека).
```
igor86@igor86:~$ cat >Pets\
igor86@igor86:~$ cat >PackAnimals\
igor86@igor86:~$ cat Pets\
igor86@igor86:~$ cat PackAnimals\
igor86@igor86:~$ cat Pets PackAnimals > Human_friend\
igor86@igor86:~$ cat Human_friend\
igor86@igor86:~$ cat -b Human_friend\
igor86@igor86:~$ mv Human_friend "Друзья человека"\
igor86@igor86:~$ cat "Друзья человека"\
igor86@igor86:~$ ls
```
P.S. В файле igor86@igor86 ~Animals.txt весь вывод команд в терминале Ubuntu

## 2. Создать директорию, переместить файл туда.
```
igor86@igor86:~$ sudo mkdir Animals\
igor86@igor86:~$ ls\
igor86@igor86:~$ sudo mv 'Друзья человека' /home/igor86/Animals\
igor86@igor86:~$ cd Animals\
igor86@igor86:~/Animals$ ls\
igor86@igor86:~/Animals$ cat 'Друзья человека'\
igor86@igor86:~/Animals$
```
P.S. В файле igor86@igor86 ~Animals.txt весь вывод команд в терминале Ubuntu

## 3. Подключить дополнительный репозиторий MySQL. Установить любой пакет из этого репозитория.
```
igor86@igor86:~$ sudo wget https://dev.mysql.com/get/mysql-apt-config_0.8.23-1_all.deb\
igor86@igor86:~$ sudo dpkg -i mysql-apt-config_0.8.23-1_all.deb\
igor86@igor86:~$ sudo apt-get update\
igor86@igor86:~$ sudo apt-get install mysql-server\
igor86@igor86:~$ mysql --version
```
P.S. В файле igor86@igor86 ~ MySQL.txt весь вывод команд в терминале Ubuntu

## 4. Установить и удалить deb-пакет с помощью dpkg.
```
// Install memtest86+_4.20-1.1ubuntu8_amd64.deb 

igor86@igor86:~$ wget http://archive.ubuntu.com/ubuntu/pool/main/m/memtest86+/memtest86+_4.20-1.1ubuntu8_amd64.deb\
igor86@igor86:~$ sudo dpkg -i memtest86+_4.20-1.1ubuntu8_amd64.deb

//Uninstall memtest86+

igor86@igor86:~$ sudo dpkg -r memtest86+
```
P.S. В файле igor86@igor86 ~memtest86.txt весь вывод команд в терминале Ubuntu

## 5. Выложить историю команд в терминале ubuntu

<image src="https://github.com/ShishkinIgor86/ControlWork2/blob/main/history.jpg" alt="History">

## 6. Нарисовать диаграмму, в которой есть класс родительский класс, домашние животные и вьючные животные, в составы которых в случае домашних животных войдут классы: собаки, кошки, хомяки, а в класс вьючные животные войдут: Лошади, верблюды и ослы).
