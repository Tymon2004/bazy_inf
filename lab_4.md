#Zadania lab 4

##Zadanie 3
```sql
#1
CREATE TABLE `izba` (
  `adres_budynku` varchar(40) NOT NULL,
  `nazwa_izby` varchar(40) NOT NULL,
  `metraz` smallint unsigned,
  `kolor` varchar(30),
  `wlasciciel` int,
  PRIMARY KEY (`adres_budynku`,`nazwa_izby`),
  KEY `wlasciciel` (`wlasciciel`),)

#2
alter table izba add column kolor varchar(30) after metraz;
#3
insert into izba values('przetworowa 45', 'spizarnia', '50', 'brazowy', '2');
```
##Zadanie 4
```sql
#1
create table przetwory(id_przetworu int not null auto_increment,
rok_produkcji smallint unsigned,
id_wykonawcy int,
zawartosc varchar(40),
dodatek varchar(40) default 'papryczka chilli',
id_konsumenta int, primary key(id_przetworu),
foreign key(id_wykonawcy) references postac(id_postaci),
foreign key(id_konsumenta) references postac(id_postaci));

#2
insert into przetwory values(default, default, '2', 'bigos', default, '2');
```

##Zadanie 5
```sql
#1
Insert into postac values(default, 'Erak', 'wiking', '0340-01-22', '40');
Insert into postac values(default, 'Ragnarok', 'wiking', '0330-01-22', '50');
Insert into postac values(default, 'Hal', 'wiking', '0350-01-22', '30');
Insert into postac values(default, 'Stig', 'wiking', '0345-04-17', '35');
Insert into postac values(default, 'Berg', 'wiking', '0355-11-23', '25');
#2
create table statek(nazwa_statku varchar(30) primary key, rodzaj_statku enum('karli', 'sneki', 'skeidy', 'drakary'), data_wodowania varchar(20), max_ladownosc int unsigned);
#3
insert into statek values('Czapla', 'karli', '0345-08-23', '35');
insert into statek values('Delfin', 'drakar', '0355-05-09', '35');
#4
alter table postac add column funkcja varchar(30);
#5
update postac set funkcja = 'Kapitan' where nazwa = 'Bjorn';
#6
alter table postac add column statek varchar(30);
#7
delete from izba where nazwa_izby = 'spizarnia';
#8
drop table izba
