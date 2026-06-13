# Instrukcja JOIN

Instrukcja `JOIN` służy do łączenia danych z kilku tabel. W relacyjnych bazach danych informacje często są rozdzielone na wiele tabel, dlatego łączenie tabel jest jedną z podstawowych umiejętności w SQL.

## Przykładowe tabele

Tabela `Pracownicy`:

| ID | Imie | Nazwisko | DzialID |
| --- | --- | --- | --- |
| 1 | Jan | Kowalski | 1 |
| 2 | Anna | Nowak | 2 |
| 3 | Piotr | Zielinski | 1 |

Tabela `Dzialy`:

| ID | Nazwa |
| --- | --- |
| 1 | IT |
| 2 | Administracja |

## INNER JOIN

`INNER JOIN` zwraca tylko te rekordy, które mają pasujące dane w obu tabelach.

```sql
SELECT Pracownicy.Imie, Pracownicy.Nazwisko, Dzialy.Nazwa AS Dzial
FROM Pracownicy
INNER JOIN Dzialy
    ON Pracownicy.DzialID = Dzialy.ID;
```

## LEFT JOIN

`LEFT JOIN` zwraca wszystkie rekordy z lewej tabeli oraz pasujące rekordy z prawej tabeli. Jeśli nie ma dopasowania, w wyniku pojawi się wartość `NULL`.

```sql
SELECT Pracownicy.Imie, Pracownicy.Nazwisko, Dzialy.Nazwa AS Dzial
FROM Pracownicy
LEFT JOIN Dzialy
    ON Pracownicy.DzialID = Dzialy.ID;
```

## RIGHT JOIN

`RIGHT JOIN` działa podobnie do `LEFT JOIN`, ale zwraca wszystkie rekordy z prawej tabeli.

```sql
SELECT Pracownicy.Imie, Pracownicy.Nazwisko, Dzialy.Nazwa AS Dzial
FROM Pracownicy
RIGHT JOIN Dzialy
    ON Pracownicy.DzialID = Dzialy.ID;
```

## FULL JOIN

`FULL JOIN` zwraca wszystkie rekordy z obu tabel. Jeśli nie ma dopasowania, brakujące dane są oznaczone jako `NULL`.

```sql
SELECT Pracownicy.Imie, Pracownicy.Nazwisko, Dzialy.Nazwa AS Dzial
FROM Pracownicy
FULL JOIN Dzialy
    ON Pracownicy.DzialID = Dzialy.ID;
```

## Alias tabeli

Alias skraca zapis zapytania i poprawia czytelność.

```sql
SELECT p.Imie, p.Nazwisko, d.Nazwa AS Dzial
FROM Pracownicy AS p
INNER JOIN Dzialy AS d
    ON p.DzialID = d.ID;
```

Alias jest szczególnie przydatny w dłuższych zapytaniach, w których pojawia się kilka tabel.
