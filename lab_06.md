sql
```
select avg(waga) from kreatura;
select rodzaj, avg(waga), count(*) from kreatura group by rodzaj;
select year(now()) - (dataUr) as wiek from kreatura;
select rodzaj, sum(waga*ilosc) as sum_waga from zasob group by rodzaj;
select rodzaj, sum(waga*ilosc) as sum_waga from zasob group by rodzaj having sum_waga > 100;
select nazwa, avg(waga) from zasob where ilosc >=4 group by nazwa having sum(waga) > 10;
select count(distinct nazwa) from zasob group by rodzaj having rodzaj >=1;
select k.idKreatury, k.nazwa, e.idKreatury, e.idZasobu, e.ilosc from kreatura k, ekwipunek e, zasob z where e.idKreatury=k.idKreatury and z.idZasobu=e.idZasobu;
select k.idKreatury, k.nazwa, e.idKreatury from kreatura k, ekwipunek e inner join ekwipunek on k.idKreatury=e.idKreatury where e.idKreatury is null;
select * from kreatura natural join ekwipunek;
select k1.idKreatury, k1.idKreatury, k1.nazwa, k2.nazwa from kreatura k1 inner join kreatura k2 on k1.idKreatury=k2.idKreatury -5;
select avg(waga*ilosc) from kreatura, ekwipunek where (kreatura.rodzaj not like 'malpa' or kreatura.rodzaj not like 'waz') having sum(ilosc) < 30;
select * from zasob;
select * from ekwipunek;
select * from kreatura;
```
