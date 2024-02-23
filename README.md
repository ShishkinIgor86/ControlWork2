Задание
1. Используя команду cat в терминале операционной системы Linux, создать
два файла Домашние животные (заполнив файл собаками, кошками,
хомяками) и Вьючные животными заполнив файл Лошадьми, верблюдами и
ослы), а затем объединить их. Просмотреть содержимое созданного файла.
Переименовать файл, дав ему новое имя (Друзья человека).

igor86@igor86:~$ cat >Pets

Fido Dog 2020-01-01 Sit, Stay, Fetch
Whiskers Cat 2019-05-15 Sit, Pounce
Hammy Hamster 2021-03-10 Roll, Hide
Buddy Dog 2018-12-10 Sit, Paw, Bark
Smudge Cat 2020-02-20 Sit, Pounce, Scratch
Peanut Hamster 2021-08-01 Roll, Spin
Bella Dog 2019-11-11 Sit, Stay, Roll
Oliver Cat 2020-06-30 Meow, Scratch, Jump

igor86@igor86:~$ cat >PackAnimals

Thunder Horse 2015-07-21 Trot, Canter, Gallop
Sandy Camel 2016-11-03 Walk, Carry Load
Eeyore Donkey 2017-09-18 Walk, Carry Load, Bray
Storm Horse 2014-05-05 Trot, Canter
Dune Camel 2018-12-12 Walk, Sit
Burro Donkey 2019-01-23 Walk, Bray, Kick
Blaze Horse 2016-02-29 Trot, Jump, Gallop
Sahara Camel 2015-08-14 Walk, Run

igor86@igor86:~$ cat Pets

Fido Dog 2020-01-01 Sit, Stay, Fetch
Whiskers Cat 2019-05-15 Sit, Pounce
Hammy Hamster 2021-03-10 Roll, Hide
Buddy Dog 2018-12-10 Sit, Paw, Bark
Smudge Cat 2020-02-20 Sit, Pounce, Scratch
Peanut Hamster 2021-08-01 Roll, Spin
Bella Dog 2019-11-11 Sit, Stay, Roll
Oliver Cat 2020-06-30 Meow, Scratch, Jump

igor86@igor86:~$ cat PackAnimals

Thunder Horse 2015-07-21 Trot, Canter, Gallop
Sandy Camel 2016-11-03 Walk, Carry Load
Eeyore Donkey 2017-09-18 Walk, Carry Load, Bray
Storm Horse 2014-05-05 Trot, Canter
Dune Camel 2018-12-12 Walk, Sit
Burro Donkey 2019-01-23 Walk, Bray, Kick
Blaze Horse 2016-02-29 Trot, Jump, Gallop
Sahara Camel 2015-08-14 Walk, Run

igor86@igor86:~$ cat Pets PackAnimals > Human_friend

igor86@igor86:~$ cat Human_friend

Fido Dog 2020-01-01 Sit, Stay, Fetch
Whiskers Cat 2019-05-15 Sit, Pounce
Hammy Hamster 2021-03-10 Roll, Hide
Buddy Dog 2018-12-10 Sit, Paw, Bark
Smudge Cat 2020-02-20 Sit, Pounce, Scratch
Peanut Hamster 2021-08-01 Roll, Spin
Bella Dog 2019-11-11 Sit, Stay, Roll
Oliver Cat 2020-06-30 Meow, Scratch, Jump
Thunder Horse 2015-07-21 Trot, Canter, Gallop
Sandy Camel 2016-11-03 Walk, Carry Load
Eeyore Donkey 2017-09-18 Walk, Carry Load, Bray
Storm Horse 2014-05-05 Trot, Canter
Dune Camel 2018-12-12 Walk, Sit
Burro Donkey 2019-01-23 Walk, Bray, Kick
Blaze Horse 2016-02-29 Trot, Jump, Gallop
Sahara Camel 2015-08-14 Walk, Run

igor86@igor86:~$ cat -b Human_friend

     1  Fido Dog 2020-01-01 Sit, Stay, Fetch
     2  Whiskers Cat 2019-05-15 Sit, Pounce
     3  Hammy Hamster 2021-03-10 Roll, Hide
     4  Buddy Dog 2018-12-10 Sit, Paw, Bark
     5  Smudge Cat 2020-02-20 Sit, Pounce, Scratch
     6  Peanut Hamster 2021-08-01 Roll, Spin
     7  Bella Dog 2019-11-11 Sit, Stay, Roll
     8  Oliver Cat 2020-06-30 Meow, Scratch, Jump
     9  Thunder Horse 2015-07-21 Trot, Canter, Gallop
    10  Sandy Camel 2016-11-03 Walk, Carry Load
    11  Eeyore Donkey 2017-09-18 Walk, Carry Load, Bray
    12  Storm Horse 2014-05-05 Trot, Canter
    13  Dune Camel 2018-12-12 Walk, Sit
    14  Burro Donkey 2019-01-23 Walk, Bray, Kick
    15  Blaze Horse 2016-02-29 Trot, Jump, Gallop
    16  Sahara Camel 2015-08-14 Walk, Run
    
igor86@igor86:~$ mv Human_friend Друзья человека
mv: target 'человека': No such file or directory

igor86@igor86:~$ mv Human_friend "Друзья человека"

igor86@igor86:~$ cat "Друзья человека"

Fido Dog 2020-01-01 Sit, Stay, Fetch
Whiskers Cat 2019-05-15 Sit, Pounce
Hammy Hamster 2021-03-10 Roll, Hide
Buddy Dog 2018-12-10 Sit, Paw, Bark
Smudge Cat 2020-02-20 Sit, Pounce, Scratch
Peanut Hamster 2021-08-01 Roll, Spin
Bella Dog 2019-11-11 Sit, Stay, Roll
Oliver Cat 2020-06-30 Meow, Scratch, Jump
Thunder Horse 2015-07-21 Trot, Canter, Gallop
Sandy Camel 2016-11-03 Walk, Carry Load
Eeyore Donkey 2017-09-18 Walk, Carry Load, Bray
Storm Horse 2014-05-05 Trot, Canter
Dune Camel 2018-12-12 Walk, Sit
Burro Donkey 2019-01-23 Walk, Bray, Kick
Blaze Horse 2016-02-29 Trot, Jump, Gallop
Sahara Camel 2015-08-14 Walk, Run

igor86@igor86:~$ ls

 compose   PackAnimals   Pets  'Друзья человека'


2. Создать директорию, переместить файл туда.

igor86@igor86:~$ sudo mkdir Animals
[sudo] password for igor86:

igor86@igor86:~$ ls

 Animals   compose   PackAnimals   Pets  'Друзья человека'
 
igor86@igor86:~$ sudo mv 'Друзья человека' /home/igor86/Animals

igor86@igor86:~$ cd Animals

igor86@igor86:~/Animals$ ls

'Друзья человека'

igor86@igor86:~/Animals$ cat 'Друзья человека'

Fido Dog 2020-01-01 Sit, Stay, Fetch
Whiskers Cat 2019-05-15 Sit, Pounce
Hammy Hamster 2021-03-10 Roll, Hide
Buddy Dog 2018-12-10 Sit, Paw, Bark
Smudge Cat 2020-02-20 Sit, Pounce, Scratch
Peanut Hamster 2021-08-01 Roll, Spin
Bella Dog 2019-11-11 Sit, Stay, Roll
Oliver Cat 2020-06-30 Meow, Scratch, Jump
Thunder Horse 2015-07-21 Trot, Canter, Gallop
Sandy Camel 2016-11-03 Walk, Carry Load
Eeyore Donkey 2017-09-18 Walk, Carry Load, Bray
Storm Horse 2014-05-05 Trot, Canter
Dune Camel 2018-12-12 Walk, Sit
Burro Donkey 2019-01-23 Walk, Bray, Kick
Blaze Horse 2016-02-29 Trot, Jump, Gallop
Sahara Camel 2015-08-14 Walk, Run

igor86@igor86:~/Animals$
