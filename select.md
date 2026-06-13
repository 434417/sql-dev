# Instrukcja SELECT

Instrukcja `SELECT` służy do pobierania danych z tabeli. Jest jedną z najczęściej używanych instrukcji w języku SQL.

## Pobranie wszystkich danych

```sql
SELECT *
FROM Pracownicy;
```

Znak `*` oznacza pobranie wszystkich kolumn z tabeli.

## Pobranie wybranych kolumn

```sql
SELECT Imie, Nazwisko, Stanowisko
FROM Pracownicy;
```

W praktyce lepiej wskazywać konkretne kolumny, ponieważ wynik zapytania jest wtedy czytelniejszy.

## Filtrowanie danych

Do filtrowania rekordów używa się klauzuli `WHERE`.

```sql
SELECT Imie, Nazwisko, Pensja
FROM Pracownicy
WHERE Pensja > 5000;
```

Przykład z tekstem:

```sql
SELECT *
FROM Pracownicy
WHERE Stanowisko = 'Programista';
```

## Sortowanie wyników

Do sortowania służy `ORDER BY`.

```sql
SELECT Imie, Nazwisko, Pensja
FROM Pracownicy
ORDER BY Pensja DESC;
```

`DESC` sortuje malejąco, a `ASC` rosnąco.

## Ograniczenie liczby wyników

W SQL Server można użyć `TOP`, aby pobrać tylko określoną liczbę rekordów.

```sql
SELECT TOP 5 Imie, Nazwisko, Pensja
FROM Pracownicy
ORDER BY Pensja DESC;
```

## Grupowanie danych

Klauzula `GROUP BY` pozwala grupować rekordy i wykonywać obliczenia dla każdej grupy.

```sql
SELECT Stanowisko, COUNT(*) AS LiczbaPracownikow
FROM Pracownicy
GROUP BY Stanowisko;
```

## Filtrowanie grup

Do filtrowania wyników po grupowaniu używa się `HAVING`.

```sql
SELECT Stanowisko, AVG(Pensja) AS SredniaPensja
FROM Pracownicy
GROUP BY Stanowisko
HAVING AVG(Pensja) > 6000;
```

`WHERE` filtruje pojedyncze rekordy przed grupowaniem, a `HAVING` filtruje gotowe grupy.
