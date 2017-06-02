# IQ-InterviewQuestions
Questions from different interviews put all together for reference and future generations.
Pytania z różnistych rozmów kwalifikacyjnych zebrane razem dla przyszłych pokoleń.

# Spis Treści
1. [Pytania Ogólne](#pytania-ogólne)
2. [Python](#python)
3. [Bazy Danych](#bazy-danych)

## Pytania Ogólne:

### 1. Czym się różni wątek od procesu?
 http://www.zsoiz.home.pl/pliki/Procesy.htm

- Proces - jedno z najbardziej podstawowych pojęć w informatyce, definiowane jako egzemplarz wykonywanego programu, jednak każdy nowo powstały proces otrzymuje unikalny numer, który go jednoznacznie identyfikuje, tzw. numer PID (ang. process IDentifier).
- Wątek (ang. thread) - część programu wykonywana współbieżnie w obrębie jednego procesu; w jednym procesie może istnieć wiele wątków.

     W celu wykonania programu system operacyjny przydziela procesowi zasoby (pamięć, czas procesora i inne), ale także może być konieczne współbieżne wykonywanie pewnych fragmentów programu. Aby to zrealizować program może zażądać utworzenia określonej liczby wątków, wykonujących wskazane części programu - o ich współbieżne wykonanie dba system operacyjny (albo sam program, wówczas mówi się o zielonych wątkach). Wątki współdzielą prawie wszystkie zasoby zarezerwowane dla danego procesu, wyjątkiem jest czas procesora, który jest przydzielany indywidualnie każdemu wątkowi.

   > Różnica między zwykłym procesem a wątkiem polega na współdzieleniu przez wszystkie wątki działające w danym procesie przestrzeni adresowej oraz wszystkich innych struktur systemowych (np. listy otwartych plików, gniazd, itp.) - z kolei procesy posiadają niezależne zasoby.

    Ta cecha ma dwie ważne konsekwencje:

    - Wątki wymagają mniej zasobów do działania i też mniejszy jest czas ich tworzenia.
    - Dzięki współdzieleniu przestrzeni adresowej (pamięci) wątki jednego zadania mogą się między sobą komunikować w bardzo łatwy sposób, niewymagający pomocy ze strony systemu operacyjnego. Przekazanie dowolnie dużej ilości danych wymaga przesłania jedynie wskaźnika, zaś odczyt (a niekiedy zapis) danych o rozmiarze nie większym od słowa maszynowego nie wymaga synchronizacji (procesor gwarantuje atomowość takiej operacji).

## Python
### 1. Jakie są óżnice pomiędzy Pythonem 2.x i 3.x ?
 http://sebastianraschka.com/Articles/2014_python_2_3_key_diff.html
- funkcja print
- dzielenie liczb całkowitych
- obsługa unicode
- funkcja xrange
- wywoływanie wyjątków
- obsługa wyjątków
- funkcja next() oraz metoda .next()
- zmienne pętli for
- "przeciekanie/przysłanianie" zmiennych globalnych
- porównywanie nieuporządkowanych typów danych
- parsownie danych wejściowych poprzez input()
- zwracanie obiektów iterowalnych zamiast list
- zaokrąglanie

## Bazy Danych
### 1. Jak i kiedy stosować indeksy w bazach danych?
https://msdn.microsoft.com/pl-pl/library/baza-danych-sql-server--indeksy--kiedy-i-jak-je-stosowac.aspx

- Indeks - jest specjalną strukturą danych wprowadzoną w celu zwiększenia prędkości wykonywania operacji na tabeli. Indeks w bazie danych jest odpowiednikiem spisu treści w książce. Po co kartkować całą książkę dla znalezienia jednej interesującej nas informacji, jeśli możemy zajrzeć do spisu treści i na jego podstawie odnaleźć stronę, na której znajduje się to, czego szukamy. Zaoszczędzimy w ten sposób cenny czas choćby dlatego, że spis treści jest zwykle zorganizowany w sposób alfabetyczny, co znacznie upraszcza wyszukanie frazy, która nas interesuje. Indeks w bazie danych wykorzystuje się przy zapytaniach typu DQL (SELECT), które mają na celu wyszukiwanie odpowiednich wartości w bazie danych. Podczas realizowania zapytania optymalizator (SQL Server) najpierw przeszukuje indeks, który jest uporządkowany, a następnie na podstawie indeksu odczytuje odpowiednie rekordy. Indeks posiada strukturę logiczną i fizyczną niezależną od tabeli, do jakiej się odwołuje. Posiada również własną przestrzeń dyskową oraz jest automatycznie utrzymywany przez system zarządzania bazą danych.

    Definicja tworzenia indeksu:

         CREATE INDEX name_index ON user (name);

    lub

         ALTER TABLE user ADD INDEX (name);

- Zastosowanie - ktoś mógłby powiedzieć, że tak naprawdę SQL Server nie potrzebuje indeksów, ponieważ bez nich również otrzymamy dane, o które zapytamy. W tym momencie jednak kłania nam się słowo „wydajność” – dzięki indeksom szybciej odnajdujemy dane w tabeli. Podczas wykonywania polecenia typu DQL (SELECT) serwer bazy danych musi wykonać bardzo dużo operacji – wybieranie danych, sortowanie wyników itd. SQL Server może pracować z bardzo dużą ilością rekordów, a często z dziesiątkami milionów rekordów w tabeli, dlatego niezwykle ważną rolę odgrywa w nim optymalizacja wszelkiego rodzaju wyszukiwania oraz sortowania. Jak łatwo zauważyć, rekordy ułożone są w tabeli w takiej kolejności, w jakiej zostały dodane, co oznacza, że jeśli spróbujemy wyszukać w bazie danych np. sklepu ceny danego produktu, to SQL Server musi za każdym razem na nowo przetrząsać od początku do końca wszystko, co tam się znajduje. Kiedy produktów będzie parę tysięcy, może to potrwać dosyć długo. W takiej sytuacji pomocą służą nam indeksy. Indeks nałożony na pole jest niczym innym jak kopią jego zawartości, tyle że posortowaną i odpowiednio ułożoną. Teraz w momencie wyszukiwania jakiejś wartości SQL Server po prostu zajrzy do indeksów jak czytelnik do spisu treści w książce, co pozwoli mu znacznie przyspieszyć wyszukiwanie.

- Zysk - dzięki posortowaniu rekordów SQL Server na wstępie odrzucił całe mnóstwo rekordów, które nie pasują do naszego zapytania. Dodatkowo mamy zrealizowaną automatycznie funkcję sortowania, bez uruchamiania jakiejkolwiek funkcji sortującej.

- Strata - niestety, nie do końca. To dlatego, że ceną za udogodnienia, jakie oferuje nam indeks, jest zwiększenie rozmiarów bazy, gdyż indeks również potrzebuje trochę miejsca. Przestrzeń dyskowa jest z kolei kluczowym aspektem podczas projektowania bazy danych. A zatem już na początku została obalona postawiona teza o popieraniu rozrzutności podczas indeksowania danych. Należy się zastanowić, na których polach indeks będzie nam potrzebny, a na których jest zwyczajnie zbędny. W tym momencie pomocne będzie środowisko SQL Server, które udzieli nam diagnostycznej informacji o wykonywaniu zapytania, na podstawie której przekonamy się, czy wykorzystał on nasze indeksy. Wystarczy zapytanie SELECT poprzedzić słowem EXPLAIN, a odpowiedź na nasze pytanie mamy gotową.

- Różnica - wyobraźmy sobie zapytanie, które ma wybrać dane z 15 tabel, z których największa ma np. milion rekordów. Przypuszczam, że operacja wyszukiwania będzie trwała ok. 5 minut. Po założeniu indeksu na tej największej tabeli czas wykonywania zapytania może się skrócić nawet o 10 razy.


do opracowania
https://github.com/tvandame/back-end-developer-interview-questions


author @brzydal
