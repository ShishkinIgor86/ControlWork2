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

<image src="https://github.com/ShishkinIgor86/ControlWork2/blob/main/UML.jpg" alt="UML">

## 7. В подключенном MySQL репозитории создать базу данных “Друзья человека”
```
 CREATE DATABASE Human_friends;
```
## 8. Создать таблицы с иерархией из диаграммы в БД
```
USE Human_friends;
CREATE TABLE animal
(
	id INT AUTO_INCREMENT PRIMARY KEY, 
	type_of_animal VARCHAR(20)
);

INSERT INTO animal (type_of_animal)
VALUES ('pets'),
('pack_animal');  
   
CREATE TABLE pets
(
	id INT AUTO_INCREMENT PRIMARY KEY,
    type_name VARCHAR (20),
    type_id INT,
    FOREIGN KEY (type_id) REFERENCES animal (id) ON DELETE CASCADE ON UPDATE CASCADE
);

INSERT INTO pets (type_name, type_id)
VALUES ('cat', 1),
('dog', 1),  
('hamster', 1); 

CREATE TABLE pack_animal
(
	id INT AUTO_INCREMENT PRIMARY KEY,
    type_name VARCHAR (20),
    type_id INT,
    FOREIGN KEY (type_id) REFERENCES animal (id) ON DELETE CASCADE ON UPDATE CASCADE
);

INSERT INTO pack_animal (type_name, type_id)
VALUES ('horse', 2),
('donkey', 2),  
('camel', 2);

```
## 9. Заполнить низкоуровневые таблицы именами(животных), командами которые они выполняют и датами рождения
```
CREATE TABLE cat 
(       
    Id INT AUTO_INCREMENT PRIMARY KEY, 
    nickname VARCHAR(20), 
    date_of_birth DATE,
    commands VARCHAR(50),
    type_id int,
    Foreign KEY (type_id) REFERENCES pets (id) ON DELETE CASCADE ON UPDATE CASCADE
);

INSERT INTO cat (nickname, date_of_birth, commands, type_id)
VALUES ('Whiskers', '2019-05-15', 'Sit, Pounce', 1),
('Smudge', '2020-02-20', 'Sit, Pounce, Scratch', 1),  
('Oliver', '2020-06-30', 'Meow, Scratch, Jump', 1); 

CREATE TABLE dog 
(       
    id INT AUTO_INCREMENT PRIMARY KEY, 
    nickname VARCHAR(20), 
    date_of_birth DATE,
    commands VARCHAR(50),
    type_id int,
    Foreign KEY (type_id) REFERENCES pets (id) ON DELETE CASCADE ON UPDATE CASCADE
);
INSERT INTO dog (nickname, date_of_birth, commands, type_id)
VALUES ('Fido', '2020-01-01', 'Sit, Stay, Fetch', 2),
('Buddy', '2018-12-10', 'Sit, Paw, Bark', 2),  
('Bella', '2019-11-11', 'Sit, Stay, Roll', 2);

CREATE TABLE hamster
(       
    id INT AUTO_INCREMENT PRIMARY KEY, 
    nickname VARCHAR(20), 
    date_of_birth DATE,
    commands VARCHAR(50),
    type_id int,
    Foreign KEY (type_id) REFERENCES pets (id) ON DELETE CASCADE ON UPDATE CASCADE
);
INSERT INTO hamster (nickname, date_of_birth, commands, type_id)
VALUES ('Hammy', '2021-03-10', 'Roll, Hide', 3),
('Peanut', '2021-08-01', 'Roll, Spin', 3);

CREATE TABLE horse 
(       
    id INT AUTO_INCREMENT PRIMARY KEY, 
    nickname VARCHAR(20), 
    date_of_birth DATE,
    commands VARCHAR(50),
    type_id int,
    Foreign KEY (type_id) REFERENCES pack_animal (id) ON DELETE CASCADE ON UPDATE CASCADE
);
INSERT INTO horse (nickname, date_of_birth, commands, type_id)
VALUES ('Thunder', '2015-07-21', 'Trot, Canter, Gallop', 1),
('Storm', '2014-05-05', 'Trot, Canter', 1),  
('Blaze', '2016-02-29', 'Trot, Jump, Gallop', 1);

CREATE TABLE donkey
(       
    id INT AUTO_INCREMENT PRIMARY KEY, 
    nickname VARCHAR(20), 
    date_of_birth DATE,
    commands VARCHAR(50),
    type_id int,
    Foreign KEY (type_id) REFERENCES pack_animal (id) ON DELETE CASCADE ON UPDATE CASCADE
);
INSERT INTO donkey (nickname, date_of_birth, commands, type_id)
VALUES ('Eeyore', '2017-09-18', 'Walk, Carry Load, Bray', 2),
('Burro', '2019-01-23', 'Walk, Bray, Kick', 2);

CREATE TABLE camel 
(       
    id INT AUTO_INCREMENT PRIMARY KEY, 
    nickname VARCHAR(20), 
    date_of_birth DATE,
    commands VARCHAR(50),
    type_id int,
    Foreign KEY (type_id) REFERENCES pack_animal (id) ON DELETE CASCADE ON UPDATE CASCADE
);
INSERT INTO camel (nickname, date_of_birth, commands, type_id)
VALUES ('Sandy', '2016-11-03', 'Walk, Carry Load', 3),
('Dune', '2018-12-12', 'Walk, Sit', 3),  
('Sahara', '2015-08-14', 'Walk, Run', 3);

```
## 10. Удалив из таблицы верблюдов, т.к. верблюдов решили перевезти в другой питомник на зимовку. Объединить таблицы лошади, и ослы в одну таблицу.

```
SET SQL_SAFE_UPDATES = 0;
DELETE FROM camel;

SELECT nickname, date_of_birth, commands FROM horse
UNION SELECT  nickname, date_of_birth, commands FROM donkey;

```
## 11.Создать новую таблицу “молодые животные” в которую попадут все животные старше 1 года, но младше 3 лет и в отдельном столбце с точностью до месяца подсчитать возраст животных в новой таблице
```

CREATE TEMPORARY TABLE animals AS 
SELECT *, 'horse' as genus FROM horse
UNION SELECT *, 'donkey' AS genus FROM donkey
UNION SELECT *, 'dog' AS genus FROM dog
UNION SELECT *, 'cat' AS genus FROM cat
UNION SELECT *, 'hamster' AS genus FROM hamster;

CREATE TABLE younganimals (id INT NOT NULL AUTO_INCREMENT PRIMARY KEY)
SELECT nickname, date_of_birth, commands,
        Round((year(current_date()) - year(date_of_birth)) + (month(current_date() - month(date_of_birth)))/10, 2) as age
FROM animals
WHERE Round((year(current_date()) - year(date_of_birth)) + (month(current_date() - month(date_of_birth)))/10, 2) > 1 
	     AND Round((year(current_date()) - year(date_of_birth)) + (month(current_date() - month(date_of_birth)))/10, 2) < 3;
SELECT * FROM younganimals;

```

## 12. Объединить все таблицы в одну, при этом сохраняя поля, указывающие на прошлую принадлежность к старым таблицам.
```
CREATE TABLE newhumanFriend (id INT NOT NULL AUTO_INCREMENT PRIMARY KEY)
SELECT  nickname, date_of_birth, commands, 
        'cat' AS oldTable
FROM cat UNION 
SELECT nickname, date_of_birth, commands,
        'dog' AS oldTable
FROM dog UNION
SELECT  nickname, date_of_birth, commands,
        'hamster' AS oldTable
FROM hamster UNION 
SELECT  nickname, date_of_birth, commands,
        'horse' AS oldTable
FROM horse UNION 
SELECT  nickname, date_of_birth, commands,
        'donkey' AS oldTable
FROM donkey;

SELECT * FROM newhumanFriend;

```
## 13.Создать класс с Инкапсуляцией методов и наследованием по диаграмме.

<src/main/java/org/example/model>
