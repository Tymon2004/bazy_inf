####Lab_7
```sql
create table wyprawa select * from wikingowie.wyprawa;
create table uczestnicy select * from wikingowie.uczestnicy;
create table etapy_wyprawy select * from wikingowie.etapy_wyprawy;
create table sektor select * from wikingowie.sektor;
select wyprawa.nazwa, count(kreatura.nazwa), group_concat(kreatura.nazwa separator '|') as liczba_uczestnikow from wyprawa inner join uczestnicy on wyprawa.id_wyprawy=uczestnicy.id_wyprawy inner join kreatura on kreatura.idKreatury=uczestnicy.id_uczestnika group by wyprawa.id_wyprawy;
select * from wyprawa;
select * from uczestnicy, wyprawa;
select * from kreatura;
select sektor.nazwa, ifnull(count(etapy_wyprawy.sektor), 'brak'), sektor.id_sektora from etapy_wyprawy
right join sektor on etapy_wyprawy.sektor=sektor.id_sektora group by sektor.id_sektora;
select sektor.nazwa, if(count(etapy_wyprawy.sektor=0), 'nie był odwiedzany', count(etapy_wyprawy.sektor)), sektor.id_sektora from etapy_wyprawy
right join sektor on etapy_wyprawy.sektor=sektor.id_sektora group by sektor.id_sektora;
 select nazwa, length(nazwa) from kreatura;
 ```
