# Ćwiczenia

Poniższe zadania pozwalają sprawdzić znajomość podstaw języka SQL. Przed wykonaniem ćwiczeń można utworzyć przykładowe tabele.

## Przygotowanie danych

```sql
CREATE TABLE Dzialy (
    ID INT PRIMARY KEY,
    Nazwa VARCHAR(50)
);

CREATE TABLE Pracownicy (
    ID INT PRIMARY KEY,
    Imie VARCHAR(50),
    Nazwisko VARCHAR(50),
    Stanowisko VARCHAR(50),
    Pensja DECIMAL(10, 2),
    DzialID INT
);
```

```sql
INSERT INTO Dzialy (ID, Nazwa)
VALUES
    (1, 'IT'),
    (2, 'Administracja'),
    (3, 'Sprzedaz');

INSERT INTO Pracownicy (ID, Imie, Nazwisko, Stanowisko, Pensja, DzialID)
VALUES
    (1, 'Jan', 'Kowalski', 'Programista', 6500.00, 1),
    (2, 'Anna', 'Nowak', 'Analityk', 5800.00, 1),
    (3, 'Piotr', 'Zielinski', 'Tester', 4700.00, 1),
    (4, 'Katarzyna', 'Wisniewska', 'Specjalista', 5200.00, 2),
    (5, 'Marek', 'Lewandowski', 'Handlowiec', 4900.00, 3);
```

## Zadania

1. Wyświetl wszystkich pracowników.
2. Wyświetl imiona, nazwiska i pensje pracowników zarabiających więcej niż 5000.
3. Posortuj pracowników malejąco według pensji.
4. Dodaj nowego pracownika do tabeli.
5. Zmień pensję pracownika o identyfikatorze `3`.
6. Usuń pracownika o identyfikatorze `5`.
7. Połącz tabelę `Pracownicy` z tabelą `Dzialy` i wyświetl nazwę działu.
8. Policz liczbę pracowników w każdym dziale.

## Przykładowe rozwiązania

```sql
SELECT *
FROM Pracownicy;
```

```sql
SELECT Imie, Nazwisko, Pensja
FROM Pracownicy
WHERE Pensja > 5000;
```

```sql
SELECT Imie, Nazwisko, Pensja
FROM Pracownicy
ORDER BY Pensja DESC;
```

```sql
INSERT INTO Pracownicy (ID, Imie, Nazwisko, Stanowisko, Pensja, DzialID)
VALUES (6, 'Ewa', 'Mazur', 'Ksiegowa', 5100.00, 2);
```

```sql
UPDATE Pracownicy
SET Pensja = 5000.00
WHERE ID = 3;
```

```sql
DELETE FROM Pracownicy
WHERE ID = 5;
```

```sql
SELECT p.Imie, p.Nazwisko, d.Nazwa AS Dzial
FROM Pracownicy AS p
INNER JOIN Dzialy AS d
    ON p.DzialID = d.ID;
```

```sql
SELECT d.Nazwa AS Dzial, COUNT(p.ID) AS LiczbaPracownikow
FROM Dzialy AS d
LEFT JOIN Pracownicy AS p
    ON d.ID = p.DzialID
GROUP BY d.Nazwa;
```
