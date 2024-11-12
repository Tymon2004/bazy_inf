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
select * from postac where rodzaj like 'wiking' order by data_ur asc;
delete from postac where id_postaci = 4;
delete from postac where id_postaci = 5;
alter table postac drop primary key;
alter table postac modify id_postaci int;
alter table przetwory drop foreign key przetwory_ibfk_2;
alter table walizka drop foreign key walizka_ibfk_1;
alter table postac drop primary key;
alter table postac add pesel int(11) first;
alter table postac modify pesel char(11) primary key;
update postac set pesel = "12345678912" where nazwa = "Bjorn";
update postac set pesel = "13579135790" where nazwa = "Teściowa";
update postac set pesel = "24682468000" where nazwa = "Drozd";
update postac set pesel = "09876543210" where nazwa = "Hal";
update postac set pesel = "19283746500" where nazwa = "Stig";
update postac set pesel = "93858948894" where nazwa = "Berg";
alter table postac add column rodzaj enum('wiking', 'ptak', 'kobieta', 'syrena') after nazwa;
Alter table postac drop rodzaj;
insert into postac values('19197417949', '9', 'Gertruda Nieszczera', 'syrena', '0360-04-01', '20', ' ', ' ');
show create table postac;
update postac set statek = "Czapla" where nazwa like '%a%' and rodzaj = "wiking";
create table marynarz like postac;
```
