# Funkcje SQL

Funkcje SQL pozwalają wykonywać obliczenia, przetwarzać tekst, pracować z datami oraz analizować dane. Funkcje mogą działać na pojedynczych wartościach albo na grupach rekordów.

## Funkcje agregujące

Funkcje agregujące zwracają jeden wynik dla grupy rekordów.

| Funkcja | Zastosowanie |
| --- | --- |
| `COUNT()` | liczy rekordy |
| `SUM()` | sumuje wartości |
| `AVG()` | oblicza średnią |
| `MIN()` | zwraca najmniejszą wartość |
| `MAX()` | zwraca największą wartość |

Przykłady:

```sql
SELECT COUNT(*) AS LiczbaPracownikow
FROM Pracownicy;
```

```sql
SELECT AVG(Pensja) AS SredniaPensja
FROM Pracownicy;
```

```sql
SELECT DzialID, MAX(Pensja) AS NajwyzszaPensja
FROM Pracownicy
GROUP BY DzialID;
```

## Funkcje tekstowe

Funkcje tekstowe służą do pracy z danymi znakowymi.

```sql
SELECT UPPER(Imie) AS ImieWielkimiLiterami
FROM Pracownicy;
```

```sql
SELECT CONCAT(Imie, ' ', Nazwisko) AS Pracownik
FROM Pracownicy;
```

```sql
SELECT LEN(Nazwisko) AS DlugoscNazwiska
FROM Pracownicy;
```

## Funkcje daty i czasu

SQL Server ma funkcje do obsługi dat.

```sql
SELECT GETDATE() AS AktualnaData;
```

```sql
SELECT YEAR(GETDATE()) AS AktualnyRok;
```

```sql
SELECT DATEADD(day, 7, GETDATE()) AS DataZaTydzien;
```

## Funkcje warunkowe

Instrukcja `CASE` pozwala zwrócić różne wartości zależnie od warunku.

```sql
SELECT Imie, Nazwisko, Pensja,
    CASE
        WHEN Pensja >= 7000 THEN 'wysoka'
        WHEN Pensja >= 5000 THEN 'srednia'
        ELSE 'niska'
    END AS KategoriaPensji
FROM Pracownicy;
```

Takie zapytanie może być użyte na przykład do przygotowania prostego raportu.
