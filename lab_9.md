```sql
create table adres_klienta select * from __firma_zti.adres_klienta;
create table dzial select * from __firma_zti.dzial;
create table jednostka_miary select * from __firma_zti.jednostka_miary;
create table kategoria select * from __firma_zti.kategoria;
create table klient select * from __firma_zti.klient;
create table pozycja_zamowienia select * from __firma_zti.pozycja_zamowienia;
create table pracownik select * from __firma_zti.pracownik;
create table stan_magazynowy select * from __firma_zti.stan_magazynowy;
create table status_zamowienia select * from __firma_zti.status_zamowienia;
create table towar select * from __firma_zti.towar;
create table typ_adresu select * from __firma_zti.typ_adresu;
create table zamowienie select * from __firma_zti.zamowienie;


#Zadanie 1.1
#1
select nazwisko from pracownik order by nazwisko asc;
#2
select imie, nazwisko, pensja from pracownik where data_urodzenia > '1979-12-31' order by data_urodzenia asc;
#3
select * from pracownik where pensja between 3500 and 5000;
#4
select towar.id_towaru, towar.nazwa_towaru, stan_magazynowy.ilosc from towar, stan_magazynowy where ilosc > 10 and towar.id_towaru = stan_magazynowy.towar order by ilosc desc;
#5
select id_towaru, nazwa_towaru from towar where nazwa_towaru like 'A%' or nazwa_towaru like 'B%' or nazwa_towaru like 'C%';
#6
select id_klienta, pelna_nazwa from klient where czy_firma = '0';
#7
select id_zamowienia, data_zamowienia from zamowienie order by data_zamowienia desc limit 10;
#8
select id_pracownika, imie, nazwisko, pensja from pracownik order by pensja asc limit 5;
#9
select id_towaru, nazwa_towaru, cena_zakupu from towar where nazwa_towaru not like '%a%' order by cena_zakupu desc limit 10;
#10
select towar.id_towaru, towar.nazwa_towaru, jednostka_miary.nazwa 
from towar, stan_magazynowy, jednostka_miary 
where towar.id_towaru=stan_magazynowy.towar 
and jednostka_miary.nazwa ='szt' 
order by towar.nazwa_towaru asc;

select towar.id_towaru, towar.nazwa_towaru, jednostka_miary.nazwa 
from towar, stan_magazynowy, jednostka_miary 
where towar.id_towaru=stan_magazynowy.towar 
and jednostka_miary.nazwa ='szt' 
order by towar.cena_zakupu desc;

#11
Create table towary_powyzej_100 select id_towaru, nazwa_towaru, cena_zakupu from towar where cena_zakupu >= 100;
#12
Create table pracownik_50_plus select * from pracownik where data_urodzenia;
select * from infs_piekarskit.pracownik;
```



