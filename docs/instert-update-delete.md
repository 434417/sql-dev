# INSERT, UPDATE, DELETE

Instrukcje `INSERT`, `UPDATE` oraz `DELETE` należą do grupy DML, czyli poleceń służących do modyfikowania danych w tabelach.

## INSERT

Instrukcja `INSERT` dodaje nowy rekord do tabeli.

```sql
INSERT INTO Pracownicy (ID, Imie, Nazwisko, Stanowisko, Pensja, DzialID)
VALUES (1, 'Jan', 'Kowalski', 'Programista', 6500.00, 1);
```

Można dodać kilka rekordów jednocześnie:

```sql
INSERT INTO Pracownicy (ID, Imie, Nazwisko, Stanowisko, Pensja, DzialID)
VALUES
    (2, 'Anna', 'Nowak', 'Analityk', 5800.00, 2),
    (3, 'Piotr', 'Zielinski', 'Tester', 4700.00, 1);
```

## UPDATE

Instrukcja `UPDATE` zmienia dane w istniejących rekordach.

```sql
UPDATE Pracownicy
SET Pensja = 7000.00
WHERE ID = 1;
```

Warunek `WHERE` jest bardzo ważny. Bez niego zmienione zostaną wszystkie rekordy w tabeli.

Przykład aktualizacji kilku kolumn:

```sql
UPDATE Pracownicy
SET Stanowisko = 'Starszy programista',
    Pensja = 8200.00
WHERE ID = 1;
```

## DELETE

Instrukcja `DELETE` usuwa rekordy z tabeli.

```sql
DELETE FROM Pracownicy
WHERE ID = 3;
```

Bez warunku `WHERE` usunięte zostaną wszystkie dane z tabeli:

```sql
DELETE FROM Pracownicy;
```

## Dobre praktyki

- przed `UPDATE` i `DELETE` warto wykonać zapytanie `SELECT` z tym samym warunkiem,
- należy zawsze sprawdzić, czy warunek `WHERE` wskazuje właściwe rekordy,
- w ważnych bazach danych powinno się wykonywać kopie zapasowe,
- modyfikacje danych najlepiej testować najpierw w środowisku developerskim.

Przykład sprawdzenia danych przed aktualizacją:

```sql
SELECT *
FROM Pracownicy
WHERE ID = 1;
```
