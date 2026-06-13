# Instrukcja JOIN w SQL

## Wprowadzenie

Instrukcja JOIN w SQL służy do łączenia danych z dwóch lub więcej tabel na podstawie powiązań między nimi. Najczęściej wykorzystuje się relacje oparte na kluczu głównym (PRIMARY KEY) oraz kluczu obcym (FOREIGN KEY).

Dzięki JOIN możliwe jest pobieranie danych z wielu tabel jednocześnie bez konieczności ich duplikowania.

---

## Dlaczego używamy JOIN

W relacyjnych bazach danych informacje są przechowywane w osobnych tabelach, np.:

- tabela Klienci
- tabela Zamówienia

JOIN pozwala połączyć te dane w jednym zapytaniu i uzyskać pełny obraz informacji.

---

## Ogólna składnia JOIN

```sql
SELECT kolumny
FROM tabela1
JOIN tabela2
ON tabela1.kolumna = tabela2.kolumna;

```
## INNER JOIN

INNER JOIN zwraca tylko te rekordy, które mają dopasowanie w obu tabelach.

```sql
SELECT k.Imie, z.DataZamowienia
FROM Klienci k
INNER JOIN Zamowienia z
ON k.ID = z.KlientID;

```
## LEFT JOIN

LEFT JOIN zwraca wszystkie rekordy z lewej tabeli oraz dopasowane rekordy z prawej tabeli. Jeśli brak dopasowania, zwracana jest wartość NULL.

```sql
SELECT k.Imie, z.DataZamowienia
FROM Klienci k
LEFT JOIN Zamowienia z
ON k.ID = z.KlientID;

```
## RIGHT JOIN

RIGHT JOIN zwraca wszystkie rekordy z prawej tabeli oraz dopasowane rekordy z lewej tabeli.

```sql
SELECT k.Imie, z.DataZamowienia
FROM Klienci k
RIGHT JOIN Zamowienia z
ON k.ID = z.KlientID;

```
## FULL OUTER JOIN

FULL OUTER JOIN zwraca wszystkie rekordy z obu tabel, niezależnie od tego, czy występuje dopasowanie.

```sql
SELECT k.Imie, z.DataZamowienia
FROM Klienci k
FULL OUTER JOIN Zamowienia z
ON k.ID = z.KlientID;

```
## JOIN z aliasami

JOIN z aliasami pozwala skrócić nazwy tabel, co poprawia czytelność zapytań.

```sql
SELECT k.Imie, z.DataZamowienia
FROM Klienci k
JOIN Zamowienia z
ON k.ID = z.KlientID;

```
## Podsumowanie

JOIN pozwala łączyć dane z wielu tabel na podstawie wspólnych kolumn.

Najważniejsze typy JOIN:

- INNER JOIN – tylko dopasowane rekordy
- LEFT JOIN – wszystkie rekordy z lewej tabeli
- RIGHT JOIN – wszystkie rekordy z prawej tabeli
- FULL OUTER JOIN – wszystkie rekordy z obu tabel
- JOIN z aliasami – skracanie nazw tabel dla czytelności
