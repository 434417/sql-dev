# Microsoft SQL Server



## Wprowadzenie



Microsoft SQL Server to relacyjny system zarządzania bazami danych (RDBMS) opracowany przez Microsoft. Jest wykorzystywany do przechowywania, zarządzania oraz przetwarzania danych w aplikacjach biznesowych, systemach internetowych oraz rozwiązaniach analitycznych.



SQL Server obsługuje język SQL (Structured Query Language), który umożliwia tworzenie baz danych, wykonywanie zapytań oraz zarządzanie danymi. Dzięki wysokiej wydajności, bezpieczeństwu i skalowalności jest jednym z najpopularniejszych systemów bazodanowych na świecie.



## Główne cechy Microsoft SQL Server



### Wydajność



SQL Server umożliwia szybkie przetwarzanie dużych ilości danych oraz obsługę wielu użytkowników jednocześnie. Mechanizmy indeksowania i optymalizacji zapytań pozwalają na efektywną pracę nawet z bardzo dużymi bazami danych.



### Bezpieczeństwo



System oferuje zaawansowane funkcje zabezpieczeń, takie jak:



* uwierzytelnianie użytkowników,

* zarządzanie uprawnieniami,

* szyfrowanie danych,

* tworzenie kopii zapasowych,

* monitorowanie aktywności użytkowników.



### Skalowalność



SQL Server może być wykorzystywany zarówno w małych projektach edukacyjnych, jak i w dużych przedsiębiorstwach obsługujących miliony rekordów.



### Integracja z narzędziami Microsoft



System współpracuje z wieloma rozwiązaniami firmy Microsoft, takimi jak:



* Azure,

* Power BI,

* Excel,

* Visual Studio,

* .NET.



## Architektura SQL Server



Podstawowe elementy systemu to:



### Instancja



Instancja SQL Server jest uruchomioną kopią serwera baz danych. Na jednym komputerze może działać kilka niezależnych instancji.



### Baza danych



Baza danych zawiera tabele, widoki, procedury składowane, funkcje oraz inne obiekty służące do przechowywania i organizowania danych.



### Tabele



Tabela jest podstawowym elementem przechowywania danych. Składa się z:



* kolumn (atrybutów),

* wierszy (rekordów).



Przykład tabeli **Pracownicy**:

| ID | Imię | Stanowisko  |
| -- | ---- | ----------- |
| 1  | Jan  | Programista |
| 2  | Anna | Analityk    |




## SQL Server Management Studio (SSMS)



SQL Server Management Studio (SSMS) jest graficznym narzędziem służącym do zarządzania serwerem SQL Server.



Za pomocą SSMS można:



* tworzyć bazy danych,

* wykonywać zapytania SQL,

* zarządzać użytkownikami,

* monitorować działanie serwera,

* wykonywać kopie zapasowe.



## Tworzenie bazy danych



Przykład utworzenia nowej bazy danych:



```sql

CREATE DATABASE Firma;

```



Wybór bazy danych do pracy:



```sql

USE Firma;

```



## Tworzenie tabeli



Przykład utworzenia tabeli pracowników:



```sql

CREATE TABLE Pracownicy (

     ;   ID INT PRIMARY KEY,

     ;   Imie VARCHAR(50),

     ;   Nazwisko VARCHAR(50),

     ;   Stanowisko VARCHAR(50)

);

```



## Wstawianie danych



```sql

INSERT INTO Pracownicy

VALUES (1, 'Jan', 'Kowalski', 'Programista');

```



## Odczytywanie danych



```sql

SELECT \* FROM Pracownicy;

```




Wynik zapytania:

| ID | Imię | Nazwisko | Stanowisko  |
| -- | ---- | -------- | ----------- |
| 1  | Jan  | Kowalski | Programista |



## Zalety Microsoft SQL Server



Najważniejsze zalety systemu:



* wysoka wydajność,

* zaawansowane zabezpieczenia,

* łatwa administracja,

* integracja z produktami Microsoft,

* rozbudowane możliwości analityczne,

* szerokie zastosowanie w przedsiębiorstwach.



