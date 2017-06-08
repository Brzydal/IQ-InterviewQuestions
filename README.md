# IQ-InterviewQuestions
Questions from different interviews put all together for reference and future generations.
Pytania z różnistych rozmów kwalifikacyjnych zebrane razem dla przyszłych pokoleń.

# Spis Treści
1. [Pytania Ogólne](#pytania-ogólne)
2. [Python](#python)
3. [Bazy Danych](#bazy-danych)
4. [Internet](#internet)

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

### 2. Co to jest projektowanie obiektowe?
https://pl.wikipedia.org/wiki/Programowanie_obiektowe

Programowanie obiektowe (ang. object-oriented programming) – paradygmat programowania, w którym programy definiuje się za pomocą obiektów – elementów łączących stan (czyli dane, nazywane najczęściej polami) i zachowanie (czyli procedury, tu: metody). Obiektowy program komputerowy wyrażony jest jako zbiór takich obiektów, komunikujących się pomiędzy sobą w celu wykonywania zadań. Podejście to różni się od tradycyjnego programowania proceduralnego, gdzie dane i procedury nie są ze sobą bezpośrednio związane. Programowanie obiektowe ma ułatwić pisanie, konserwację i wielokrotne użycie programów lub ich fragmentów. Największym atutem programowania, projektowania oraz analizy obiektowej jest zgodność takiego podejścia z rzeczywistością – mózg ludzki jest w naturalny sposób najlepiej przystosowany do takiego podejścia przy przetwarzaniu informacji.

Podstawowe założenia paradygmatu obiektowego:

- Abstrakcja - każdy obiekt w systemie służy jako model abstrakcyjnego „wykonawcy”, który może wykonywać pracę, opisywać i zmieniać swój stan oraz komunikować się z innymi obiektami w systemie bez ujawniania, w jaki sposób zaimplementowano dane cechy. Procesy, funkcje lub metody mogą być również abstrahowane, a kiedy tak się dzieje, konieczne są rozmaite techniki rozszerzania abstrakcji.

 - Hermetyzacja - czyli ukrywanie implementacji, enkapsulacja. Zapewnia, że obiekt nie może zmieniać stanu wewnętrznego innych obiektów w nieoczekiwany sposób. Tylko własne metody obiektu są uprawnione do zmiany jego stanu. Każdy typ obiektu prezentuje innym obiektom swój interfejs, który określa dopuszczalne metody współpracy. Pewne języki osłabiają to założenie, dopuszczając pewien poziom bezpośredniego (kontrolowanego) dostępu do „wnętrzności” obiektu. Ograniczają w ten sposób poziom abstrakcji. Przykładowo w niektórych kompilatorach języka C++ istnieje możliwość tymczasowego wyłączenia mechanizmu enkapsulacji; otwiera to dostęp do wszystkich pól i metod prywatnych, ułatwiając programistom pracę nad pośrednimi etapami tworzenia kodu i znajdowaniem błędów.

 - Polimorfizm - referencje i kolekcje obiektów mogą dotyczyć obiektów różnego typu, a wywołanie metody dla referencji spowoduje zachowanie odpowiednie dla pełnego typu obiektu wywoływanego. Jeśli dzieje się to w czasie działania programu, to nazywa się to późnym wiązaniem lub wiązaniem dynamicznym. Niektóre języki udostępniają bardziej statyczne (w trakcie kompilacji) rozwiązania polimorfizmu – na przykład szablony i przeciążanie operatorów w C++.

 - Dziedziczenie - porządkuje i wspomaga polimorfizm i enkapsulację dzięki umożliwieniu definiowania i tworzenia specjalizowanych obiektów na podstawie bardziej ogólnych. Dla obiektów specjalizowanych nie trzeba redefiniować całej funkcjonalności, lecz tylko tę, której nie ma obiekt ogólniejszy. W typowym przypadku powstają grupy obiektów zwane klasami, oraz grupy klas zwane drzewami. Odzwierciedlają one wspólne cechy obiektów.

### 3. Co to jest wzorzec projektowy?
https://pl.wikipedia.org/wiki/Wzorzec_projektowy_(informatyka)

Wzorzec projektowy (ang. design pattern) – uniwersalne, sprawdzone w praktyce rozwiązanie często pojawiających się, powtarzalnych problemów projektowych. Pokazuje powiązania i zależności pomiędzy klasami oraz obiektami i ułatwia tworzenie, modyfikację oraz pielęgnację kodu źródłowego. Jest opisem rozwiązania, a nie jego implementacją. Wzorce projektowe stosowane są w projektach wykorzystujących programowanie obiektowe.

np. https://pl.wikipedia.org/wiki/Model-View-Controller
Model-View-Controller (pol. Model-Widok-Kontroler) – wzorzec architektoniczny służący do organizowania struktury aplikacji posiadających graficzne interfejsy użytkownika[1]. Wiele prac traktuje go jako pojedynczy wzorzec, lecz może on być także traktowany jako złożony wzorzec wykorzystujący idee wzorców prostych, takich jak Obserwator, Strategia czy Kompozyt. Oba te podejścia nie wykluczają się[1]. MVC nie był traktowany jako samodzielny wzorzec również w pracy „Design Patterns: Elements of Reusable Object-Oriented Software“ autorstwa „Bandy Czworga”[2].

Model-View-Controller zakłada podział aplikacji na trzy główne części:
- Model – jest pewną reprezentacją problemu bądź logiki aplikacji.
- Widok – opisuje, jak wyświetlić pewną część modelu w ramach interfejsu użytkownika. Może składać się z podwidoków odpowiedzialnych za mniejsze części interfejsu.
- Kontroler – przyjmuje dane wejściowe od użytkownika i reaguje na jego poczynania, zarządzając aktualizacje modelu oraz odświeżenie widoków.

### 4. Co to jest ORM?
https://en.wikipedia.org/wiki/Object-relational_mapping

Mapowanie obiektowo-relacyjne (ang. Object-Relational Mapping ORM) – sposób odwzorowania obiektowej architektury systemu informatycznego na bazę danych (lub inny element systemu) o relacyjnym charakterze.

Implementacja takiego odwzorowania stosowana jest między innymi w przypadku, gdy tworzony system oparty jest na podejściu obiektowym, a system bazy danych operuje na relacjach. Z ORM związany jest szereg problemów wydajnościowych.

### 6. Co to są wyrażenia regularne?
http://grabun.pl/wyrazenia-regularne/

Za pomocą wyrażeń regularnych (ang. regular expressions albo w skrócie regexp) można opisywać pewne skomplikowane wzorce wyszukiwania na przykład treści dokumentów.

>Przykładowo, za pomocą wzorca:
```
[a-zA-Z0-9._-]+@[a-zA-Z0-9-]+\.[a-zA-Z]{2,4}
```
można próbować sprawdzać poprawność wpisanego w formularz adresu e-mail.

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

### 2. Co to są *args i **kwargs i kiedy ich używamy?
https://pythontips.com/2013/08/04/args-and-kwargs-in-python-explained/

Identyfikator *args jest używany, gdy nie jesteśmy pewni, jak wiele argumentów zostanie przekazanych do funkcji, lub jeśli chcemy przekazać listę lub krotkę argumentów do funkcji. Identyfikator ** kwargs jest używany, gdy nie wiemy, jak wiele nazwanych argumentów zostanie przekazanych do funkcji . Może być również użyty do przekazywania wartości słownika. Identyfikatory args i kwargs są konwencją, można również użyć * bob i ** billy, ale to nie byłoby mądre.

np.
```python
    def f(*args,**kwargs): print(args, kwargs)

    l = [1,2,3]
    t = (4,5,6)
    d = {'a':7,'b':8,'c':9}

    f()
    f(1,2,3)                    # (1, 2, 3) {}
    f(1,2,3,"groovy")           # (1, 2, 3, 'groovy') {}
    f(a=1,b=2,c=3)              # () {'a': 1, 'c': 3, 'b': 2}
    f(a=1,b=2,c=3,zzz="hi")     # () {'a': 1, 'c': 3, 'b': 2, 'zzz': 'hi'}
    f(1,2,3,a=1,b=2,c=3)        # (1, 2, 3) {'a': 1, 'c': 3, 'b': 2}

    f(*l,**d)                   # (1, 2, 3) {'a': 7, 'c': 9, 'b': 8}
    f(*t,**d)                   # (4, 5, 6) {'a': 7, 'c': 9, 'b': 8}
    f(1,2,*t)                   # (1, 2, 4, 5, 6) {}
    f(q="winning",**d)          # () {'a': 7, 'q': 'winning', 'c': 9, 'b': 8}
    f(1,2,*t,q="winning",**d)   # (1, 2, 4, 5, 6) {'a': 7, 'q': 'winning', 'c': 9, 'b': 8}

    def f2(arg1,arg2,*args,**kwargs): print(arg1,arg2, args, kwargs)

    f2(1,2,3)                       # 1 2 (3,) {}
    f2(1,2,3,"groovy")              # 1 2 (3, 'groovy') {}
    f2(arg1=1,arg2=2,c=3)           # 1 2 () {'c': 3}
    f2(arg1=1,arg2=2,c=3,zzz="hi")  # 1 2 () {'c': 3, 'zzz': 'hi'}
    f2(1,2,3,a=1,b=2,c=3)           # 1 2 (3,) {'a': 1, 'c': 3, 'b': 2}

    f2(*l,**d)                   # 1 2 (3,) {'a': 7, 'c': 9, 'b': 8}
    f2(*t,**d)                   # 4 5 (6,) {'a': 7, 'c': 9, 'b': 8}
    f2(1,2,*t)                   # 1 2 (4, 5, 6) {}
    f2(1,1,q="winning",**d)      # 1 1 () {'a': 7, 'q': 'winning', 'c': 9, 'b': 8}
    f2(1,2,*t,q="winning",**d)   # 1 2 (4, 5, 6) {'a': 7, 'q': 'winning', 'c': 9, 'b': 8}
```

### 3. Co to są dekoratory?
http://blog.heintze.pl/tag/dekorator/

Dekoratory sa to specjalne funkcje, które jako argument przyjmują inna funkcję i zwracają funkcję lub jako argument przyjmują klasę i zwracają klasę.
```python
@my_decorator
def my_func(stuff):
    do_things
```

lub
```python
def my_func(stuff):
    do_things

my_func = my_decorator(my_func)
```
Przykłady dekoratorów:
- @classmethod,
- @staticmethod,
- @property

### 4. Co to jest PEP8?
https://www.python.org/dev/peps/pep-0008/

PEP8 jest to zestaw zasad określających jak ma wyglądać kod Pythona. Określa między innymi jak duże mają być wcięcia, jak pisać komentarze, maksymalną ilość znaków w jednej linii itp.

### 5. Jakie znasz typy danych w Pythonie?
https://pl.wikipedia.org/wiki/Python#Typy_i_struktury_danych

|   Typ     | 	Opis        | 	Przykład    |
|-----------|---------------|---------------|
|str        |Napis          | 'Python'      |
|list       |Lista (zmienna, zawartość, długość)|[4.0, 'string', True]|
|tuple 	    |Krotka (niezmienna)|(4.0, 'string', True)|
|set        |Zbiór różnych elementów (zmienny)| {4.0, 'string', True}|
|frozenset 	|Zbiór różnych elementów (niezmienny)|frozenset({4.0, 'string', True})|
|dict       |Słownik, czyli tablica asocjacyjna (zmienny)|	{'key1': 1.0, 3: False}|
|int     	|Liczba całkowita o dowolnej wartości| 	42|
|float 	    |Liczba zmiennoprzecinkowa 	|3.1415927|
|complex 	|Liczba zespolona 	|3+2.7j|
|bool 	    |Prawda lub fałsz 	|True False|
|type(None) |Nic (odpowiednik null) 	|None|

### 6. Co to znaczy, że jedne zmienne są mutable, a inne immutable?
https://codehabitude.com/2013/12/24/python-objects-mutable-vs-immutable/

Nie wszystkie typy zmiennych w Pythonie reagują tak samo na zmiany. Jedne typy są mutable, czyli zmienne, a inne immutable, czyli niezmienne i zwracają raczej nowy obiekt tego samego typu, ale same pozostają takie same.

Obiekty niezmienne:
    - int
    - float
    - decimal
    - complex
    - bool
    - string
    - tuple
    - range
    - frozenset
    - bytes

Obiekty zmienne:
Markdown
Toggle Zen Mode
Preview

    - list
    - dict
    - set
    - bytearray

### 7. Dlaczego i kiedy używać generatorów w Pythonie?
https://wiki.python.org/moin/Generators

Generator w Pythonie jest funkcją, która zwraca iterowalny obiekt. Możemy iterować po tym obiekcie za pomocą słowa kluczowego <yield>. Ale możemy to zrobić tylko raz, ponieważ wartości zwracane przezgenerator nie są trzymane w pamięci, ale są tworzone w locie i zapominane.

 Oto kilka przykładów, w których korzystanie z generatorów jest korzystne:

- Możemy zastąpić pętle generatorami w celu wydajnego obliczania wyników z użyciem dużych zbiorów danych.
- Generatory są użyteczne, gdy nie chcemy otrzymać wszystkich wyników i kiedy chcemy wstrzymać iterację na jakiś czas.
- Zamiast używać funkcji callback możemy zastąpić ją generatorem. Możemy napisać pętlę wewnątrz funkcji robi to samo co wywołanie zwrotne i przekształca ją w generator.


## Bazy Danych
### 1. Co to jest SQL?
https://pl.wikipedia.org/wiki/SQL

SQL (ang. Structured Query Language wym. /ɛskjuːˈɛl/) – strukturalny język zapytań używany do tworzenia, modyfikowania baz danych oraz do umieszczania i pobierania danych z baz danych.

### 2. Jak i kiedy stosować indeksy w bazach danych?
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

### 3. Jaka jest różnica między widokiem (View), a tabelą (Table)?
https://pl.wikipedia.org/wiki/Widok_(bazy_danych)
https://pl.wikipedia.org/wiki/Tabela_(bazy_danych)

Widok (perspektywa) to logiczny byt (obiekt), osadzony na serwerze baz danych. Umożliwia dostęp do podzbioru kolumn i wierszy tabel lub tabeli na podstawie zapytania w języku SQL, które stanowi część definicji tego obiektu. Przy korzystaniu z widoku jako źródła danych należy odwoływać się identycznie jak do tabeli. Operacje wstawiania, modyfikowania oraz usuwania rekordów nie zawsze są możliwe ( np. w sytuacji gdy widok udostępnia część kolumn dwóch tabel tb_A oraz tb_B bez kolumny z kluczem głównym tabeli tb_B ). W niektórych SZBD widok służy wyłącznie do pobierania wyników i ograniczania dostępu do danych.

Składnia SQL do utworzenia widoku:
    ```
    CREATE VIEW nazwa_widoku [(kolumna1, kolumna2,  ..., kolumnaN )]
    AS
    SELECT ...;
    ```
Składnia SQL do pobrania danych z widoku:
    ```
    SELECT * FROM nazwa_widoku;
    ```
Tabela (relacja) – wydzielony logicznie zbiór danych, zorganizowanych w formie tabeli składającej się z wierszy dzielonych na kolumny. Jest to obiekt teoretyczny i nie należy go mylić z jej graficzną reprezentacją, czy miejscem zajmowanym w pamięci komputera. W zależności od typu bazy danych wewnętrzna organizacja podziału danych na kolumny i wiersze jest różna i często umowna.

Pojedyncza tabela może być reprezentacją pewnej encji (np. książek, mieszkań, ludzi), relacji między nimi, albo może stanowić zawartość całej bazy danych. Pojedynczy wiersz tabeli nazywany jest rekordem i stanowi najczęściej zbiór danych o pojedynczym obiekcie (ew. grupie obiektów).

### 4. Jakie znasz relacje w bazach danych
http://www.teacher.webd.pl/kurs_mysql/k_2_2_3.php

 -  #### Relacja jeden do jednego
    Relacja jeden do jednego pomiędzy tabelami A i B występuje wtedy, gdy każdemu rekordowi z tabeli A jest przyporządkowany dokładnie jeden rekord z tabeli B i na odwrót – każdemu rekordowi z tabeli B jest przyporządkowany dokładnie jeden rekord z tabeli A.

 -  #### Relacja jeden do wielu
    Relacja jeden do wielu jest najczęściej używanym typem połączenia. Pomiędzy tabelami A i B występuje wtedy, gdy pojedynczemu rekordowi z tabeli A jest przyporządkowany jeden lub wiele rekordów z tabeli B, natomiast pojedynczemu rekordowi z tabeli B jest przyporządkowany dokładnie jeden rekord z tabeli A. Zmodyfikujmny wcześniejszy przykład, zmieniając tabelę przewodniczących klas na tabelę wychowawców. Może niektórzy nie znają takich sytuacji, więc wyjaśniam, że w mojej szkole funkcjonują klasy łączone. Dwie klasy mają oddzielną domunentację (np. dzienniki lekcyjne), ale jednego wychowawcę.

 -  #### Relacja wiele do wielu
    Relacja wiele do wielu pomiędzy tabelami A i B występuje wtedy, gdy pojedynczemu rekordowi z tabeli A jest przyporządkowany jeden lub wielu rekordów z tabeli B, i na odwrót - pojedynczemu rekordowi z tabeli B jest przyporządkowany jeden lub wielu rekordów A. Taką sytuację będziemy mieli w realcji nauczycieli do uczniów. Każdy nauczyciel uczy wielu uczniów, natomiast każdego ucznia uczą różni nauczyciele.

## Internet

### 1. Jak działa Internet?
https://www.youtube.com/watch?v=7_LPdttKXPc
http://kobietydokodu.pl/niezbednik-juniora-jak-dziala-internet/

Internet - to połączone ze sobą tysiące sieci działające według odmiennych standardów, które dzięki temu, że potrafią „rozmawiać” ze sobą we „wspólnym języku” (protokole internetowym), potrafią przesłać dane z punktu A w dowolnej z tych sieci do punktu B w dowolnej z tych sieci.
- Internet jest siecią złożoną z tysięcy oddzielnych sieci połączonych za sobą.
- Wspólne  dla  nich  wszystkich  jest  używania  jednego  języka  –  protokołu  internetowego (TCP/IP).
- Internet  jest  metasiecią  –  służy  do  przesyłania  pakietów  IP  wykorzystując  do  tego  celu różnorodne sieci znajdujące się „pod” Internetem.
- Sieć  jest  „głupia”  –  zajmuje  się  przesyłaniem  pakietów,  dzięki  czemu  robi  to  szybko i efektywnie.
- „Mądrość”  i  zaawansowane  funkcje  zlokalizowane  są  w urządzeniach  końcowych (komputery, serwery itp.) i aplikacjach na nich uruchamianych. Dzięki schematowi „głupia sieć – mądre urządzenie końcowe”, czyli zasadzie
end-to-end, Internet jest otwartą platformą dla innowacji, nowych aplikacji i zastosowań.

### 2. Jakie znasz protokoły internetowe?
https://pl.wikipedia.org/wiki/Protok%C3%B3%C5%82_komunikacyjny#Protoko.C5.82y_internetowe

Protokoły służące programom komputerowym do porozumiewania się między sobą poprzez Internet są określone przez IETF w dokumentach zwanych RFC.

Przesyłanie danych komputerowych to niezwykle trudny proces, dlatego rozdzielono go na kilka "etapów", warstw. Warstwy oznaczają w istocie poszczególne funkcje spełniane przez sieć. Najbardziej powszechny sposób organizacji warstw komunikacji sieciowej to Model OSI.

Poniżej wyszczególniono niektóre, popularne protokoły komunikacyjne wraz z numerem portu:
- DNS – 53
- FTP – 21
- HTTP – 80 (HTTP Proxy używa zwykle portu 8080)
- HTTPS – 443 (HTTP na SSL)
- IRC – 6667
- NNTP – 119
- POP3 – 110
- SPOP3 – 995 (POP3 na SSL)
- SMTP – 25
- SSH – 22
- Telnet – 23
- IMAP - 143

Osobną klasą protokołów komunikacyjnych są protokoły do komunikacji grupowej (multicast), używane m.in. do transmisji telewizyjnych przez Internet, telekonferencji itp. Przykładami takich protokołów są RMTP (Reliable Multicast Transport Protocol), TOTEM, XTP, Muse i inne.

### 3. Co to jest DNS?
https://pl.wikipedia.org/wiki/Domain_Name_System

Domain Name System (DNS, pol. „system nazw domenowych”) – system serwerów, protokół komunikacyjny oraz usługa obsługująca rozproszoną bazę danych adresów sieciowych. Pozwala na zamianę adresów znanych użytkowników Internetu na adresy zrozumiałe dla urządzeń tworzących sieć komputerową. Dzięki DNS nazwa mnemoniczna, np. pl.wikipedia.org jest tłumaczona na odpowiadający jej adres IP, czyli 91.198.174.192.

DNS to złożony system komputerowy oraz prawny. Zapewnia z jednej strony rejestrację nazw domen internetowych i ich powiązanie z numerami IP. Z drugiej strony realizuje bieżącą obsługę komputerów odnajdujących adresy IP odpowiadające poszczególnym nazwom. Jest nieodzowny do działania prawie wszystkich usług sieci Internet.

### 4. Co się dzieję, kiedy wpiszesz w przeglądarce jakiś adres?
https://youtu.be/M2wvvLmRkwo
http://kobietydokodu.pl/niezbednik-juniora-protokol-http/

To pytanie ma drugie dno – poza tym, że jest pewnego rodzaju podsumowaniem powyższych informacji, pada ono bardzo często na rozmowach rekrutacyjnych :) Zacznijmy więc od początku.

Pierwsze co się wydarzy to przeglądarka spróbuje przetłumaczyć adres url (www.kobietydokodu.pl) na adres IP (np. 188.128.171.252) . Aby to zrobić, najpierw sprawdzana jest pamęć podręczna. Tam przeglądarka (lub system operacyjny) przechowuje m.in. ostatnie wyniki takiego tłumaczenia. Jeśli nie znajdzie go w pamięci podręcznej, wysyła zapytanie do serwera DNS. Serwery DNS służą właśnie do tego, aby tłumaczyć nazwy domen na adresy IP. Po otrzymaniu odpowiedzi przeglądarka zna już adres IP (czyli adres serwera w sieci) pod jaki ma wysłać zapytania.

Drugim krokiem jest wysłanie zapytania do serwera działającego pod wskazanym adresem. Zapytanie to wysyłane jest na port 80 (jest to domyślny port protokołu HTTP) i jest to zapytanie typu GET. Serwer przetwarza zapytanie i jeśli wszystko jest w porządku odpowiada treścią (np.  stroną HTML) oraz statusem 200 – OK.

Jeśli chodzi o to, co dzieje się po stronie serwera, to zależy od użytej technologii. My przeanalizujemy oczywiście serwer aplikacji Java EE.

Wstępem jest zamiana zapytania HTTP na obiekt typu HttpServletRequest. Dopiero wtedy ma miejsce właściwe przetwarzanie.
Na początku serwer aplikacji analizuje adres URI – bierze jego pierwszy segment (do pierwszego /) weryfikując, czy istnieje aplikacja uruchomiona pod takim adresem. Jeśli tak, ta część jest usuwana z adresu URI, a zapytanie jest przekazywane do tej aplikacji, jeśli nie to zapytanie jest kierowane do aplikacji o ścieżce / (jeśli oczywiście istnieje). Następnie serwer aplikacji na podstawie informacji z pliku XML kieruje zapytanie do odpowiedniego obiektu, który implementuje interfejs Servlet. Tutaj już przychodzi czas na naszą aplikację – Servlety to obiekty, których implementacja jest częścią aplikacji.

W przypadku aplikacji napisanych z użyciem Spring’a, wszystkie zapytania (najczęściej) trafiają do jednego obiektu typu DispatcherServlet, który na podstawie adnotacji nad kontrolerami, plików konfiguracji oraz plików XML wywołuje metody odpowiednich klas.

To trochę uproszczony obraz, w grę wchodzą jeszcze filtry, intrceptory, potencjalnie mogą też aspekty, jednak nie zmieniają one idei i dokładniejszym ich omówieniem zajmiemy się przy innej okazji.


do opracowania
https://github.com/tvandame/back-end-developer-interview-questions


author @brzydal
