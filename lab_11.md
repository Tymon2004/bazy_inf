```sql
create table student(
id_studenta int primary key auto_increment, 
imie varchar(100) not null, 
nazwisko varchar(100) not null, 
rok_studiów int unsigned, 
data_urodzenia date);

create table kierunek(
id_kierunku int unsigned auto_increment primary key, 
nazwa_kierunku varchar(200) not null);

create table student_na_kierunku(
student int, 
kierunek int unsigned, 
foreign key(student) References student(id_studenta), 
foreign key(kierunek) References kierunek(id_kierunku),
constraint id_student_na_kierunku primary key(student, kierunek));

create table przedmiot(
id_przedmiotu int primary key auto_increment, 
nazwa_przedmiotu varchar(200) not null, 
opis text);

create table kierunek_has_przedmioty(
kierunek int unsigned not null, 
przedmiot int not null, 
obowiazkowy bool default 1,
foreign key (kierunek) references kierunek(id_kierunku),
foreign key (przedmiot) references przedmiot(id_przedmiotu),
constraint id_kierunek_has_przedmioty primary key(kierunek, przedmiot));
```
