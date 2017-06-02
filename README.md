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

### 2. Jak działa Internet?
https://www.youtube.com/watch?v=7_LPdttKXPc
http://kobietydokodu.pl/niezbednik-juniora-jak-dziala-internet/

Internet - to połączone ze sobą tysiące sieci działające według odmiennych standardów, które dzięki temu, że potrafią „rozmawiać” ze sobą we „wspólnym języku” (protokole internetowym), potrafią przesłać dane z punktu A w dowolnej z tych sieci do punktu B w dowolnej z tych sieci.
- Internet jest siecią złożoną z tysięcy oddzielnych sieci połączonych za sobą.
- Wspólne  dla  nich  wszystkich  jest  używania  jednego  języka  –  protokołu  internetowego (TCP/IP).
- Internet  jest  metasiecią  –  służy  do  przesyłania  pakietów  IP  wykorzystując  do  tego  celu różnorodne sieci znajdujące się „pod” Internetem.
- Sieć  jest  „głupia”  –  zajmuje  się  przesyłaniem  pakietów,  dzięki  czemu  robi  to  szybko i efektywnie.
- „Mądrość”  i  zaawansowane  funkcje  zlokalizowane  są  w urządzeniach  końcowych (komputery, serwery itp.) i aplikacjach na nich uruchamianych. Dzięki schematowi „głupia sieć – mądre urządzenie końcowe”, czyli zasadzie
end-to-end, Internet jest otwartą platformą dla innowacji, nowych aplikacji i zastosowań.

### 3. Co to jest projektowanie obiektowe?
https://pl.wikipedia.org/wiki/Programowanie_obiektowe

Programowanie obiektowe (ang. object-oriented programming) – paradygmat programowania, w którym programy definiuje się za pomocą obiektów – elementów łączących stan (czyli dane, nazywane najczęściej polami) i zachowanie (czyli procedury, tu: metody). Obiektowy program komputerowy wyrażony jest jako zbiór takich obiektów, komunikujących się pomiędzy sobą w celu wykonywania zadań. Podejście to różni się od tradycyjnego programowania proceduralnego, gdzie dane i procedury nie są ze sobą bezpośrednio związane. Programowanie obiektowe ma ułatwić pisanie, konserwację i wielokrotne użycie programów lub ich fragmentów. Największym atutem programowania, projektowania oraz analizy obiektowej jest zgodność takiego podejścia z rzeczywistością – mózg ludzki jest w naturalny sposób najlepiej przystosowany do takiego podejścia przy przetwarzaniu informacji.

Podstawowe założenia paradygmatu obiektowego:

- Abstrakcja - każdy obiekt w systemie służy jako model abstrakcyjnego „wykonawcy”, który może wykonywać pracę, opisywać i zmieniać swój stan oraz komunikować się z innymi obiektami w systemie bez ujawniania, w jaki sposób zaimplementowano dane cechy. Procesy, funkcje lub metody mogą być również abstrahowane, a kiedy tak się dzieje, konieczne są rozmaite techniki rozszerzania abstrakcji.

 - Hermetyzacja - czyli ukrywanie implementacji, enkapsulacja. Zapewnia, że obiekt nie może zmieniać stanu wewnętrznego innych obiektów w nieoczekiwany sposób. Tylko własne metody obiektu są uprawnione do zmiany jego stanu. Każdy typ obiektu prezentuje innym obiektom swój interfejs, który określa dopuszczalne metody współpracy. Pewne języki osłabiają to założenie, dopuszczając pewien poziom bezpośredniego (kontrolowanego) dostępu do „wnętrzności” obiektu. Ograniczają w ten sposób poziom abstrakcji. Przykładowo w niektórych kompilatorach języka C++ istnieje możliwość tymczasowego wyłączenia mechanizmu enkapsulacji; otwiera to dostęp do wszystkich pól i metod prywatnych, ułatwiając programistom pracę nad pośrednimi etapami tworzenia kodu i znajdowaniem błędów.

 - Polimorfizm - referencje i kolekcje obiektów mogą dotyczyć obiektów różnego typu, a wywołanie metody dla referencji spowoduje zachowanie odpowiednie dla pełnego typu obiektu wywoływanego. Jeśli dzieje się to w czasie działania programu, to nazywa się to późnym wiązaniem lub wiązaniem dynamicznym. Niektóre języki udostępniają bardziej statyczne (w trakcie kompilacji) rozwiązania polimorfizmu – na przykład szablony i przeciążanie operatorów w C++.

 - Dziedziczenie - porządkuje i wspomaga polimorfizm i enkapsulację dzięki umożliwieniu definiowania i tworzenia specjalizowanych obiektów na podstawie bardziej ogólnych. Dla obiektów specjalizowanych nie trzeba redefiniować całej funkcjonalności, lecz tylko tę, której nie ma obiekt ogólniejszy. W typowym przypadku powstają grupy obiektów zwane klasami, oraz grupy klas zwane drzewami. Odzwierciedlają one wspólne cechy obiektów.

### 4. Co to jest wzorzec projektowy?
https://pl.wikipedia.org/wiki/Wzorzec_projektowy_(informatyka)

Wzorzec projektowy (ang. design pattern) – uniwersalne, sprawdzone w praktyce rozwiązanie często pojawiających się, powtarzalnych problemów projektowych. Pokazuje powiązania i zależności pomiędzy klasami oraz obiektami i ułatwia tworzenie, modyfikację oraz pielęgnację kodu źródłowego. Jest opisem rozwiązania, a nie jego implementacją. Wzorce projektowe stosowane są w projektach wykorzystujących programowanie obiektowe.

np. https://pl.wikipedia.org/wiki/Model-View-Controller
Model-View-Controller (pol. Model-Widok-Kontroler) – wzorzec architektoniczny służący do organizowania struktury aplikacji posiadających graficzne interfejsy użytkownika[1]. Wiele prac traktuje go jako pojedynczy wzorzec, lecz może on być także traktowany jako złożony wzorzec wykorzystujący idee wzorców prostych, takich jak Obserwator, Strategia czy Kompozyt. Oba te podejścia nie wykluczają się[1]. MVC nie był traktowany jako samodzielny wzorzec również w pracy „Design Patterns: Elements of Reusable Object-Oriented Software“ autorstwa „Bandy Czworga”[2].

Model-View-Controller zakłada podział aplikacji na trzy główne części:
- Model – jest pewną reprezentacją problemu bądź logiki aplikacji.
- Widok – opisuje, jak wyświetlić pewną część modelu w ramach interfejsu użytkownika. Może składać się z podwidoków odpowiedzialnych za mniejsze części interfejsu.
- Kontroler – przyjmuje dane wejściowe od użytkownika i reaguje na jego poczynania, zarządzając aktualizacje modelu oraz odświeżenie widoków.

### 5. Co to jest ORM?
https://en.wikipedia.org/wiki/Object-relational_mapping

Mapowanie obiektowo-relacyjne (ang. Object-Relational Mapping ORM) – sposób odwzorowania obiektowej architektury systemu informatycznego na bazę danych (lub inny element systemu) o relacyjnym charakterze.

Implementacja takiego odwzorowania stosowana jest między innymi w przypadku, gdy tworzony system oparty jest na podejściu obiektowym, a system bazy danych operuje na relacjach. Z ORM związany jest szereg problemów wydajnościowych.

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
