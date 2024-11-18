#Zadania lab 4
##Zadanie 1
##a)
```sql
delete from postac where id_postaci = 4;
delete from postac where id_postaci = 5;
```
##b)
```sql
alter table przetwory drop foreign key przetwory_ibfk_2;
alter table walizka drop foreign key walizka_ibfk_1;
alter table postac modify id_postaci int;
alter table postac drop primary key;
```
##zadanie 2
```sql
Insert into postac values(default, 'Erak', 'wiking', '0340-01-22', '40');
Insert into postac values(default, 'Ragnarok', 'wiking', '0330-01-22', '50');
Insert into postac values(default, 'Hal', 'wiking', '0350-01-22', '30');
Insert into postac values(default, 'Stig', 'wiking', '0345-04-17', '35');
Insert into postac values(default, 'Berg', 'wiking', '0355-11-23', '25');
create table statek(nazwa_statku varchar(30) primary key, rodzaj_statku enum('karli', 'sneki', 'skeidy', 'drakary'), data_wodowania varchar(20), max_ladownosc int unsigned);
insert into statek values('Czapla', 'karli', '0345-08-23', '35');
insert into statek values('Delfin', 'drakar', '0355-05-09', '35');
alter table postac add column funkcja varchar(30);
Insert into postac(funkcja) values('Kapitan');
alter table postac add column statek varchar(30);
update postac set funkcja = 'Kapitan' where nazwa = 'Bjorn';
delete from izba where nazwa_izby = 'spizarnia';
drop table izba;
alter table postac add check(wiek<='1000');
insert into postac values(00000000011, 9, 'Loko', 'wąż', '1000-12-12', 255, null, null);
alter table postac modify column rodzaj enum('wiking', 'ptak', 'kobieta', 'syrena', 'wąż');
update statek max_ladownosc set max_ladownosc = max_ladownosc*0.7 where data_wodowania = '19__%';
SET SQL_SAFE_UPDATES = 0;
update postac set statek = null;
delete from postac where nazwa = 'Berg';
delete from statek;
drop table statek;
create table zwierzaki(id int primary key auto_increment, nazwa varchar(20), wiek int);
INSERT INTO zwierzaki (nazwa, wiek) SELECT nazwa, wiek FROM postac WHERE rodzaj = 'ptak' OR rodzaj = 'waz';
