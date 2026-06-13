# Teoria SQL

SQL, czyli Structured Query Language, jest językiem używanym do komunikacji z relacyjnymi bazami danych. Za pomocą SQL można tworzyć tabele, dodawać dane, pobierać informacje, aktualizować rekordy oraz usuwać dane z bazy.

## Relacyjna baza danych

Relacyjna baza danych przechowuje informacje w tabelach. Każda tabela składa się z kolumn i wierszy:

- kolumna określa rodzaj przechowywanej informacji, na przykład imię, nazwisko albo cena,
- wiersz reprezentuje pojedynczy rekord, czyli jeden zapis w tabeli,
- klucz podstawowy jednoznacznie identyfikuje każdy rekord,
- klucz obcy pozwala połączyć dane z różnych tabel.

Przykład tabeli `Pracownicy`:

| ID | Imie | Nazwisko | Stanowisko |
| --- | --- | --- | --- |
| 1 | Jan | Kowalski | Programista |
| 2 | Anna | Nowak | Analityk |

## Najważniejsze grupy poleceń SQL

Polecenia SQL można podzielić na kilka grup:

| Grupa | Zastosowanie | Przykłady |
| --- | --- | --- |
| DDL | tworzenie i zmiana struktury bazy | `CREATE`, `ALTER`, `DROP` |
| DML | praca na danych | `INSERT`, `UPDATE`, `DELETE` |
| DQL | pobieranie danych | `SELECT` |
| DCL | zarządzanie uprawnieniami | `GRANT`, `REVOKE` |

## Podstawowe typy danych

W SQL Server często używa się następujących typów:

- `INT` - liczby całkowite,
- `DECIMAL` - liczby z częścią dziesiętną,
- `VARCHAR` - tekst o zmiennej długości,
- `DATE` - data,
- `BIT` - wartość logiczna, najczęściej `0` albo `1`.

## Przykładowa tabela do ćwiczeń

```sql
CREATE TABLE Pracownicy (
    ID INT PRIMARY KEY,
    Imie VARCHAR(50),
    Nazwisko VARCHAR(50),
    Stanowisko VARCHAR(50),
    Pensja DECIMAL(10, 2),
    DzialID INT
);
```

Ta tabela będzie wykorzystywana w dalszych rozdziałach do prezentowania zapytań.
