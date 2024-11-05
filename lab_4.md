#Zadania lab 3

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
