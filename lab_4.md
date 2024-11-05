#Zadania lab 3

##Zadanie 3
```sql
CREATE TABLE `izba` (
  `adres_budynku` varchar(40) NOT NULL,
  `nazwa_izby` varchar(40) NOT NULL,
  `metraz` smallint unsigned,
  `kolor` varchar(30),
  `wlasciciel` int,
  PRIMARY KEY (`adres_budynku`,`nazwa_izby`),
  KEY `wlasciciel` (`wlasciciel`),)

#1
alter table izba add column kolor varchar(30) after metraz;
#2
insert into izba values('przetworowa 45', 'spizarnia', '50', 'brazowy', '2');
```
