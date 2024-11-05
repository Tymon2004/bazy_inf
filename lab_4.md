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
```
