```sql
create table kreatura select * from wikingowie.kreatura;
create table zasob select * from wikingowie.zasob;
create table ekwipunek select * from wikingowie.ekwipunek;
select * from zasob;
select * from zasob where rodzaj like 'jedzenie';
select idKreatury, idZasobu, ilosc from kreatura, zasob where (kreatura.idKreatury = 1 or kreatura.idKreatury = 3 or kreatura.idKreatury = 5) and idKreatury = idZasobu;
select * from kreatura where udzwig < 50 and rodzaj not like 'wiedzma';
select * from zasob where waga between 2 and 5;
select * from kreatura where (nazwa like '%or%' and udzwig between 30 and 70);
select * from zasob where dataPozyskania like '%07%' or dataPozyskania like '%08%';
select * from zasob where rodzaj not like '' order by waga asc;
select * from kreatura where dataUr not like '' order by dataUr asc limit 5;
select distinct rodzaj from zasob;
select concat('Kreatura: ', nazwa,  ' to ', rodzaj) from kreatura where rodzaj like 'wi%';
select sum('ilosc' * 'waga') as 'Waga Calkowita' from zasob where dataPozyskania like '2007%';
select * from zasob where rodzaj is null;
```
