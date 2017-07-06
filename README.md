# IQ-InterviewQuestions
Questions from different interviews put all together for reference and future generations.
Pytania z różnistych rozmów kwalifikacyjnych zebrane razem dla przyszłych pokoleń.

# Spis Treści
1. [Pytania Ogólne](#pytania-ogólne)
    * [Czym się różni wątek od procesu?](#question1.1)
    * [Co to jest projektowanie obiektowe?](#question1.2)
    * [Co to jest wzorzec projektowy?](#question1.3)
    * [Co to jest ORM?](#question1.4)
    * [Co to są wyrażenia regularne?](#question1.5)
    * [Co to jest rekurencja i kiedy warto jej używać?](#question1.6)
    * [Jakie znasz paradygmaty programowania?](#question1.7)
    * [Co to jest wstrzykiwanie zależności?](#question1.8)
    * [Jakie znasz drzewa i jakie operacje można na nich wykonać?](#question1.9)
    * [Co to są testy jednostkowe?](#question1.10)
    * [Co to jest SOLID?](#question1.11)
    * [Co to jest zasada DRY?](#question1.12)
    * [Co to jest zasada KISS?](#question1.13)
    * [Co to jest API?](#question1.14)
2. [Python](#python)
    * [Jakie są óżnice pomiędzy Pythonem 2.x i 3.x ?](#question2.1)
    * [Co to są dekoratory?](#question2.2)
    * [Co to są dekoratory?](#question2.3)
    * [Co to jest PEP8?](#question2.4)
    * [Jakie znasz typy danych w Pythonie?](#question2.5)
    * [Co to znaczy, że jedne zmienne są mutable, a inne immutable?](#question2.6)
    * [Jakie znasz rodzaje metod w Pythonie?](#question2.7)
    * [Jakie znasz rodzaje metod w Pythonie?](#question2.8)
    * [Co to jest lambda w Pythonie i jak jej używać ?](#question2.9)
    * [Typowanie dynamiczne vs. statyczne](#question2.10)
    * [Jaka jest różnica między range() i xrange()?](#question2.11)
3. [Django](#django)
    * [Co to jest Django?](#question3.1)
    * [Jakie znasz funkcje dostępne w Django?](#question3.2)
    * [Opisz strukturę Django?](#question3.3)
    * [Dlaczego warto używać Django do tworzenia stron WWW?](question3.4)
    * [Co to są Middleware?](#question3.5)
4. [Bazy Danych](#bazy-danych)
    * [](#question4.1)
5. [Internet](#internet)
    * [](#question5.1)

## Pytania Ogólne:

### 1. Czym się różni wątek od procesu? <a name="question1.1"></a>
 http://www.zsoiz.home.pl/pliki/Procesy.htm

- Proces - jedno z najbardziej podstawowych pojęć w informatyce, definiowane jako egzemplarz wykonywanego programu, jednak każdy nowo powstały proces otrzymuje unikalny numer, który go jednoznacznie identyfikuje, tzw. numer PID (ang. process IDentifier).
- Wątek (ang. thread) - część programu wykonywana współbieżnie w obrębie jednego procesu; w jednym procesie może istnieć wiele wątków.

     W celu wykonania programu system operacyjny przydziela procesowi zasoby (pamięć, czas procesora i inne), ale także może być konieczne współbieżne wykonywanie pewnych fragmentów programu. Aby to zrealizować program może zażądać utworzenia określonej liczby wątków, wykonujących wskazane części programu - o ich współbieżne wykonanie dba system operacyjny (albo sam program, wówczas mówi się o zielonych wątkach). Wątki współdzielą prawie wszystkie zasoby zarezerwowane dla danego procesu, wyjątkiem jest czas procesora, który jest przydzielany indywidualnie każdemu wątkowi.

   > Różnica między zwykłym procesem a wątkiem polega na współdzieleniu przez wszystkie wątki działające w danym procesie przestrzeni adresowej oraz wszystkich innych struktur systemowych (np. listy otwartych plików, gniazd, itp.) - z kolei procesy posiadają niezależne zasoby.

    Ta cecha ma dwie ważne konsekwencje:

    - Wątki wymagają mniej zasobów do działania i też mniejszy jest czas ich tworzenia.
    - Dzięki współdzieleniu przestrzeni adresowej (pamięci) wątki jednego zadania mogą się między sobą komunikować w bardzo łatwy sposób, niewymagający pomocy ze strony systemu operacyjnego. Przekazanie dowolnie dużej ilości danych wymaga przesłania jedynie wskaźnika, zaś odczyt (a niekiedy zapis) danych o rozmiarze nie większym od słowa maszynowego nie wymaga synchronizacji (procesor gwarantuje atomowość takiej operacji).

    [Spis Treści](#spis-treści)

### 2. Co to jest projektowanie obiektowe?<a name="question1.2"></a>
https://pl.wikipedia.org/wiki/Programowanie_obiektowe

Programowanie obiektowe (ang. object-oriented programming) – paradygmat programowania, w którym programy definiuje się za pomocą obiektów – elementów łączących stan (czyli dane, nazywane najczęściej polami) i zachowanie (czyli procedury, tu: metody). Obiektowy program komputerowy wyrażony jest jako zbiór takich obiektów, komunikujących się pomiędzy sobą w celu wykonywania zadań. Podejście to różni się od tradycyjnego programowania proceduralnego, gdzie dane i procedury nie są ze sobą bezpośrednio związane. Programowanie obiektowe ma ułatwić pisanie, konserwację i wielokrotne użycie programów lub ich fragmentów. Największym atutem programowania, projektowania oraz analizy obiektowej jest zgodność takiego podejścia z rzeczywistością – mózg ludzki jest w naturalny sposób najlepiej przystosowany do takiego podejścia przy przetwarzaniu informacji.

Podstawowe założenia paradygmatu obiektowego:

- Abstrakcja - każdy obiekt w systemie służy jako model abstrakcyjnego „wykonawcy”, który może wykonywać pracę, opisywać i zmieniać swój stan oraz komunikować się z innymi obiektami w systemie bez ujawniania, w jaki sposób zaimplementowano dane cechy. Procesy, funkcje lub metody mogą być również abstrahowane, a kiedy tak się dzieje, konieczne są rozmaite techniki rozszerzania abstrakcji.

 - Hermetyzacja - czyli ukrywanie implementacji, enkapsulacja. Zapewnia, że obiekt nie może zmieniać stanu wewnętrznego innych obiektów w nieoczekiwany sposób. Tylko własne metody obiektu są uprawnione do zmiany jego stanu. Każdy typ obiektu prezentuje innym obiektom swój interfejs, który określa dopuszczalne metody współpracy. Pewne języki osłabiają to założenie, dopuszczając pewien poziom bezpośredniego (kontrolowanego) dostępu do „wnętrzności” obiektu. Ograniczają w ten sposób poziom abstrakcji. Przykładowo w niektórych kompilatorach języka C++ istnieje możliwość tymczasowego wyłączenia mechanizmu enkapsulacji; otwiera to dostęp do wszystkich pól i metod prywatnych, ułatwiając programistom pracę nad pośrednimi etapami tworzenia kodu i znajdowaniem błędów.

 - Polimorfizm - referencje i kolekcje obiektów mogą dotyczyć obiektów różnego typu, a wywołanie metody dla referencji spowoduje zachowanie odpowiednie dla pełnego typu obiektu wywoływanego. Jeśli dzieje się to w czasie działania programu, to nazywa się to późnym wiązaniem lub wiązaniem dynamicznym. Niektóre języki udostępniają bardziej statyczne (w trakcie kompilacji) rozwiązania polimorfizmu – na przykład szablony i przeciążanie operatorów w C++.

 - Dziedziczenie - porządkuje i wspomaga polimorfizm i enkapsulację dzięki umożliwieniu definiowania i tworzenia specjalizowanych obiektów na podstawie bardziej ogólnych. Dla obiektów specjalizowanych nie trzeba redefiniować całej funkcjonalności, lecz tylko tę, której nie ma obiekt ogólniejszy. W typowym przypadku powstają grupy obiektów zwane klasami, oraz grupy klas zwane drzewami. Odzwierciedlają one wspólne cechy obiektów.

 [Spis Treści](#spis-treści)

### 3. Co to jest wzorzec projektowy?<a name="question1.3"></a>
https://pl.wikipedia.org/wiki/Wzorzec_projektowy_(informatyka)

Wzorzec projektowy (ang. design pattern) – uniwersalne, sprawdzone w praktyce rozwiązanie często pojawiających się, powtarzalnych problemów projektowych. Pokazuje powiązania i zależności pomiędzy klasami oraz obiektami i ułatwia tworzenie, modyfikację oraz pielęgnację kodu źródłowego. Jest opisem rozwiązania, a nie jego implementacją. Wzorce projektowe stosowane są w projektach wykorzystujących programowanie obiektowe.

np. https://pl.wikipedia.org/wiki/Model-View-Controller
Model-View-Controller (pol. Model-Widok-Kontroler) – wzorzec architektoniczny służący do organizowania struktury aplikacji posiadających graficzne interfejsy użytkownika[1]. Wiele prac traktuje go jako pojedynczy wzorzec, lecz może on być także traktowany jako złożony wzorzec wykorzystujący idee wzorców prostych, takich jak Obserwator, Strategia czy Kompozyt. Oba te podejścia nie wykluczają się[1]. MVC nie był traktowany jako samodzielny wzorzec również w pracy „Design Patterns: Elements of Reusable Object-Oriented Software“ autorstwa „Bandy Czworga”[2].

Model-View-Controller zakłada podział aplikacji na trzy główne części:
- Model – jest pewną reprezentacją problemu bądź logiki aplikacji.
- Widok – opisuje, jak wyświetlić pewną część modelu w ramach interfejsu użytkownika. Może składać się z podwidoków odpowiedzialnych za mniejsze części interfejsu.
- Kontroler – przyjmuje dane wejściowe od użytkownika i reaguje na jego poczynania, zarządzając aktualizacje modelu oraz odświeżenie widoków.

[Spis Treści](#spis-treści)

### 4. Co to jest ORM? <a name="question1.4"></a>
https://en.wikipedia.org/wiki/Object-relational_mapping

Mapowanie obiektowo-relacyjne (ang. Object-Relational Mapping ORM) – sposób odwzorowania obiektowej architektury systemu informatycznego na bazę danych (lub inny element systemu) o relacyjnym charakterze.

Implementacja takiego odwzorowania stosowana jest między innymi w przypadku, gdy tworzony system oparty jest na podejściu obiektowym, a system bazy danych operuje na relacjach. Z ORM związany jest szereg problemów wydajnościowych.

[Spis Treści](#spis-treści)


### 5. Co to są wyrażenia regularne? <a name="question1.5"></a>
http://grabun.pl/wyrazenia-regularne/

Za pomocą wyrażeń regularnych (ang. regular expressions albo w skrócie regexp) można opisywać pewne skomplikowane wzorce wyszukiwania na przykład treści dokumentów.

>Przykładowo, za pomocą wzorca:
```
[a-zA-Z0-9._-]+@[a-zA-Z0-9-]+\.[a-zA-Z]{2,4}
```
można próbować sprawdzać poprawność wpisanego w formularz adresu e-mail.

[Spis Treści](#spis-treści)

### 6. Co to jest rekurencja i kiedy warto jej używać? <a name="question1.6"></a>
https://pl.wikipedia.org/wiki/Rekurencja

 Jedna funkcja może wywołać inną. Funkcja może wywołać nawet samą siebie. Może nie być oczywiste, dlaczego to jest dobra rzecz, ale okazuje się, że to jedna z najbardziej magicznych rzeczy, które program może zrobić. Na przykład, spójrz na poniższą funkcję:
```Python
def odlicz(n):
    if n <= 0:
        print('Odpalamy!')
    else:
        print(n)
        odlicz(n - 1)
```
Jeśli n jest ujemne lub równe 0, to wyświetla ona słowo 'Odpalamy!'. W przeciwnym wypadku wyświetla n i wywołuje funkcję o nazwie odlicz (samą siebie) przekazując jej n - 1 jako argument.

Co się stanie, gdy wywołamy tą funkcję w taki sposób?

>odlicz(3)
  Wykonywanie odlicz zaczyna się od n = 3. n jest większe niż 0, więc wyświetla wartość 3 i wywołuje samą siebie...
  Wykonywanie odlicz zaczyna się od n = 2. n jest większe niż 0, więc wyświetla wartość 2 i wywołuje samą siebie...
  Wykonywanie odlicz zaczyna się od n = 1. n jest większe niż 0, więc wyświetla wartość 1 i wywołuje samą siebie...
  Wykonywanie odlicz zaczyna się od n = 0. n nie jest większe niż 0, więc wyświetla tamto słowo i wywołuje samą siebie...
  odlicz, które dostało n = 1, kończy się.
  odlicz, które dostało n = 2, kończy się.
  odlicz, które dostało n = 3, kończy się.

I wtedy wracamy do __main__. Całe wyjście wygląda tak:

>3
2
1
Odpalamy!

[Spis Treści](#spis-treści)

#### 7. Jakie znasz paradygmaty programowania ? <a name="question1.7"></a>
https://pl.wikipedia.org/wiki/Paradygmat_programowania

   - programowanie proceduralne
   - programowanie strukturalne
   - programowanie funkcyjne
   - programowanie imperatywne
   - programowanie obiektowe
   - programowanie uogólnione
   - programowanie sterowane zdarzeniami
   - programowanie logiczne (np. Prolog)
   - programowanie aspektowe (np. AspectJ)
   - programowanie deklaratywne
   - programowanie agentowe
   - programowanie modularne

Paradygmat programowania (ang. programming paradigm) — wzorzec programowania komputerów przedkładany w danym okresie rozwoju informatyki ponad inne lub ceniony w pewnych okolicznościach lub zastosowaniach.

Paradygmat programowania definiuje sposób patrzenia programisty na przepływ sterowania i wykonywanie programu komputerowego. Przykładowo, w programowaniu obiektowym jest on traktowany jako zbiór współpracujących ze sobą obiektów, podczas gdy w programowaniu funkcyjnym definiujemy, co trzeba wykonać, a nie w jaki sposób.

Różne języki programowania mogą wspierać różne paradygmaty programowania. Przykładowo, Smalltalk i Java są ściśle zaprojektowane dla potrzeb programowania obiektowego, natomiast Haskell jest językiem funkcyjnym. Istnieją także języki wspierające kilka paradygmatów, np. Common Lisp oraz Python.

[Spis Treści](#spis-treści)

#### 8. Co to jest wstrzykiwanie zależności? <a name="question1.8"></a>
http://devstyle.pl/2014/05/26/kilka-postw-o-dependency-injection/

Wstrzykiwanie zależności (ang. Dependency Injection, DI) – wzorzec projektowy i wzorzec architektury oprogramowania polegający na usuwaniu bezpośrednich zależności pomiędzy komponentami na rzecz architektury typu plug-in. Polega na przekazywaniu gotowych, utworzonych instancji obiektów udostępniających swoje metody i właściwości obiektom, które z nich korzystają (np. jako parametry konstruktora). Stanowi alternatywę do podejścia, gdzie obiekty tworzą instancję obiektów, z których korzystają np. we własnym konstruktorze.

Jest on często utożsamiany z odwróceniem sterowania (ang. Inversion of Control, IoC), jakkolwiek z technicznego punktu widzenia DI jest jedną ze szczególnych (obecnie najpopularniejszą) realizacji paradygmatu IoC.

DI silnie preferuje zewnętrzne tworzenie połączeń (zależności) pomiędzy komponentami oprogramowania (np. asocjacje w klasach), nad zlecaniem tworzenia zależności im samym. Jest to wzorzec, w którym odpowiedzialność za tworzenie obiektów i łączenie jest przeniesiona z obiektów do fabryki (np. kontenera IoC). Na żądanie kodu fabryka tworzy obiekt, lub udostępnia obiekt z puli obiektów, ustawiając mu powiązania z innymi obiektami (np. wstrzykiwanie konstruktorem –- Constructor Injection, wstrzykiwanie mutatorami – Setter Injection, użycie interfejsu Interface Injection lub w mieszany sposób). DI jest więc realizacją "odwrócenia sterowania" w sensie tworzenia i wiązania obiektów.

W rozbudowanych implementacjach fabryka może wykonywać czynności dodatkowe, np. Spring Framework pozwala na używanie aspektów, można więc do obiektu dodać automatycznie obsługę transakcji, logowania, itp.

DI jest sposobem osiągnięcia luźnych powiązań (ang. loose coupling).

Użycie tej techniki pozwala tworzyć łatwo testowalne obiekty. Sprawdza się szczególnie w powiązaniu z programowaniem sterowanym testami (ang. test-driven development). Polega ono w skrócie na następującym tworzeniu oprogramowania: opracowujemy interfejsy (diagram klas), opracowujemy testy jednostkowe, które testują funkcjonalność interfejsu (w jaki sposób przetestować, czy działanie jest poprawne), a dopiero później piszemy implementację. Unikanie zależności od konkretnych implementacji współpracujących klas, a bazowanie tylko na interfejsach umożliwia tworzenie kontrolowanych testów - jesteśmy w stanie skupić się wyłącznie na funkcjonalności wybranej klasy; zwłaszcza, gdy wykorzystamy obiekty-zaślepki (ang. mock-objects, proste pseudoimplementacje, używane w celu testowania). DI pozwala wstrzyknąć do obiektów testowanych zależności od obiektów-zaślepek. W środowisku produkcyjnym do obiektów tych wstrzykiwane są zależności od prawdziwych obiektów.

[Spis Treści](#spis-treści)

#### 9. Jakie znasz drzewa i jakie operacje można na nich wykonać ? <a name="question1.9"></a>
https://pl.wikipedia.org/wiki/Drzewo_(informatyka)
http://eduinf.waw.pl/inf/alg/001_search/0108.php

Drzewo – struktura danych reprezentująca drzewo matematyczne. W naturalny sposób reprezentuje hierarchię danych (obiektów fizycznych i abstrakcyjnych, pojęć, itp.) jest więc stosowane głównie do tego celu. Drzewa ułatwiają i przyspieszają wyszukiwanie, a także pozwalają w łatwy sposób operować na posortowanych danych.

Znaczenie tych struktur jest bardzo duże i ze względu na swoje własności drzewa są stosowane praktycznie w każdej dziedzinie informatyki (np. bazy danych, grafika komputerowa, przetwarzanie tekstu, telekomunikacja).

##### Budowa drzewa

Drzewa składają się z wierzchołków (węzłów) oraz łączących je krawędzi. Jeśli drzewo nie jest puste, tzn. liczba wierzchołków jest większa od zera, jeden z nich jest wyróżniony i nazywany korzeniem drzewa; na rysunku jest oznaczony literą F. Ciąg krawędzi łączących węzły nazywa się ścieżką. Istnieje dokładnie jedna ścieżka łącząca korzeń z każdym pozostałym wierzchołkiem. Liczba krawędzi w ścieżce od korzenia do węzła jest nazywana długością – liczba ta określa poziom węzła. Wysokością drzewa jest największy poziom istniejący w drzewie. Np. korzeń znajduje się na 0. poziomie, węzły A, D i I na poziomie 2.; wysokość drzewa to 3. Wszystkie wierzchołki połączone z danym wierzchołkiem, a leżące na następnym poziomie są nazywane dziećmi tego węzła (np. dziećmi wierzchołka F są B i G, natomiast wierzchołka B: A i D). Wierzchołek może mieć dowolną liczbę dzieci, jeśli nie ma ich wcale nazywany jest liściem. Liśćmi w przykładowym drzewie są A, C, E, H. Wierzchołek jest rodzicem dla każdego swojego dziecka. Każdy węzeł ma dokładnie jednego rodzica, wyjątkiem jest korzeń drzewa, który nie ma rodzica.

#### Podstawowe operacje na drzewach to:

- wyliczenie wszystkich elementów drzewa,
- wyszukanie konkretnego elementu,
- dodanie nowego elementu w określonym miejscu drzewa,
- usunięcie elementu.

[Spis Treści](#spis-treści)

#### 10. Co to są testy jednostkowe? <a name="question1.10"></a>
https://pl.wikipedia.org/wiki/Test_jednostkowy
http://devstyle.pl/2011/08/11/ut-1-co-to-sa-testy-i-po-co-sa-testy-jednostkowe/

Test jednostkowy (ang. unit test) – metoda testowania tworzonego oprogramowania poprzez wykonywanie testów weryfikujących poprawność działania pojedynczych elementów (jednostek) programu – np. metod lub obiektów w programowaniu obiektowym lub procedur w programowaniu proceduralnym. Testowany fragment programu poddawany jest testowi, który wykonuje go i porównuje wynik (np. zwrócone wartości, stan obiektu, zgłoszone wyjątki) z oczekiwanymi wynikami – tak pozytywnymi, jak i negatywnymi (niepowodzenie działania kodu w określonych sytuacjach również może podlegać testowaniu).

Zaletą testów jednostkowych jest możliwość wykonywania na bieżąco w pełni zautomatyzowanych testów na modyfikowanych elementach programu, co umożliwia często wychwycenie błędu natychmiast po jego pojawieniu się i szybką jego lokalizację zanim dojdzie do wprowadzenia błędnego fragmentu do programu. Testy jednostkowe są również formą specyfikacji. Z powyższych powodów są szczególnie popularne w programowaniu ekstremalnym.

Testy można podzielić na następujące warianty:

-    analiza ścieżek
-    użycie klas równoważności
-    testowanie wartości brzegowych
-    testowanie składniowe

[Spis Treści](#spis-treści)

### 11. Co to jest SOLID? <a name="question1.11"></a>
https://www.p-programowanie.pl/paradygmaty-programowania/zasady-solid/
https://sii.pl/blog/solid-dobre-praktyki-programowania/

SOLID jest skrótem opisującym podstawowe założenia programowania obiektowego.

#### 1.   Zasada pojedynczej odpowiedzialności (ang. Single-Responsibility Principle – SRP)

Zasadę pojedynczej odpowiedzialności można w sumie opisać jednym prostym zdaniem, a brzmi ono następująco: „Żadna klasa nie może być modyfikowana z więcej niż jednego powodu”.

Z mojego doświadczenia wynika, iż jeśli jakaś klasa jest odpowiedzialna za więcej niż jeden obszar naszego projektu jest to bardzo niekorzystne. Może się zdarzyć bowiem, że modyfikując jeden obszar mimowolnie wpłyniemy na zupełnie inny, który nie jest w żaden sposób związany z pierwszym. Dodatkowo, każdy taki związek wpływa negatywnie na cały projekt poprzez zmniejszenie jego elastyczności, a co za tym idzie – prowadzi do nieoczekiwanych rezultatów wprowadzanych przez nas zmian.

Zasada pojedynczej odpowiedzialności w teorii jest jedną z najprostszych ze wszystkich wymienionych przeze mnie reguł, jednakże, jeśli chodzi o praktykę jest najtrudniejsza. Muszę przyznać, że sporo czasu minęło, zanim w 100% nauczyłem się ją wykorzystywać.

#### 2.    Zasada otwarte – zamknięte (ang. Open/Closed Principle – OCP)

Zasada otwarte – zamknięte brzmi następująco: „Składniki oprogramowania (klasy, moduły, funkcje itp.) powinny być otwarte na rozbudowę, ale zamknięte dla modyfikacji”.

Rozbijając powyższą definicję na mniejsze części, można wydobyć dwa kluczowe atrybuty, którymi powinny się charakteryzować tworzone przez nas moduły, są nimi: „otwarte na rozbudowę” oraz „zamknięte dla modyfikacji”.

Co należy rozumieć przez stwierdzenie, że moduł musi być „otwarty na rozbudowę”? Mianowicie to, że musi istnieć stosunkowo prosty sposób rozbudowy zachowań takiego modułu.

„Zamknięte dla modyfikacji” oznacza z kolei, że rozbudowa modułu nie może być przeprowadzona w sposób, który spowoduje zmianę istniejącego kodu źródłowego.

Jestem pewien, że każdy z nas podczas swojej pracy miał do czynienia ze zmieniającymi się wymaganiami aplikacji. Zgodność naszego projektu z tą zasadą jest jednym z warunków, które zagwarantują nam takie korzyści jak: elastyczność, możliwość wielokrotnego wykorzystywania istniejącego kodu, czy łatwość konserwacji naszego projektu.

#### 3.    Zasada podstawiania Liskov (ang. Liskov Substitution Principle – LSP)
Można powiedzieć, że Zasada podstawiania Liskov jest jednym z warunków zasady otwarte – zamknięte. Jej definicja wygląda następująco: „Musi istnieć możliwość zastępowania typów bazowych ich podtypami”.

Dlaczego uważam, że zasada podstawiania Liskov jest jednym z warunków zasady otwarte – zamknięte? Między innymi dlatego, że możliwość zastępowania podtypów umożliwia rozbudowę modułów (klas, typów bazowych) bez konieczności ich bezpośredniego modyfikowania.

W celu zobrazowania działania zasady podstawiania Liskov, posłużę się prostym przykładem. Załóżmy, że posiadamy dwie klasy, w których znajdujemy wiele wspólnych składowych. Wspólnymi składowymi mogą być: zbiór właściwości, metod itd. Co w takiej sytuacji należałoby zrobić? Zgodnie z zasadą podstawiania Liskov, wypadałoby wyodrębnić wspólne elementy obu klas do jednej klasy – najlepiej abstrakcyjnej.

Wyodrębnianie składowych jest niezwykle silną bronią każdego programisty. Jeżeli bowiem istnieje możliwość wyodrębnienia identycznych składowych z dwóch lub większej ilości klas, to jest wielce prawdopodobne, że przyjdzie taki moment, w którym inne klasy będą do tych składowych się odwoływały.

#### 4.   Zasada segregacji interfejsów (ang. Interface Segregation Principle – ISP)
Zasada segregacji interfejsów ma za zadanie przede wszystkich wyeliminowanie nieporęcznych, niepotrzebnie rozbudowanych interfejsów. Do tej grupy można zaliczyć nadmiernie rozbudowane i niespójne interfejsy klas. Każdy taki interfejs zgodnie z tą zasadą powinien zostać podzielony na mniejsze grupy metod.

Przeanalizujmy teraz mały przykład. Załóżmy, że posiadamy pewien interfejs oraz dwie klasy, które go implementują. Klasa A implementuje nasz przykładowy interfejs w całości – wszystkie funkcje, natomiast klasa B posiada pełną implementację tylko części z nich, pozostałe, które są niepotrzebne pozostają puste lub zwracają domyśle wartości. Jeśli mamy do czynienia z taką sytuacją, powinniśmy rozważyć rozdzielenie interfejsu na mniejsze tak, aby każdy z nich deklarował tylko te funkcje, które rzeczywiście są wywoływane przez danego klienta lub grupę klientów (klasa/grupy klas implementujące dany interfejs).

Opisany powyżej model eliminuje zależność obiektów klienckich od metod, których nie wywołują. Umożliwia to zapewnianie wzajemnej niezależności samych klientów.

#### 5.   Zasada odwracania zależności (ang. Dependency Inversion Principle – DIP
Zasada odwracania zależności składa się z dwóch następujących części:

-    Moduły wysokopoziomowe nie powinny zależeć od modułów niskopoziomowych. Obie grupy modułów powinny zależeć od abstrakcji.
-    Abstrakcje nie powinny zależeć od szczegółowych rozwiązań. To szczegółowe rozwiązania powinny zależeć od abstrakcji.

Wydaje mi się, że powyższa definicja zasady odwracania zależności powinna być łatwa do zrozumienia.

Zastanówmy się jednak przez chwile, jakie mogą być skutki zależności modułów wysokopoziomowych od niskopoziomowych, czyli co by się działo, gdybyśmy nie postępowali według pierwszej części definicji zasady odwracania zależności. Moduły wysokiego poziomu z natury rzeczy zawierają ważne decyzje strategiczne i modele biznesowe danej aplikacji. Myślę, że wszyscy się ze mną zgodzą, iż te właśnie moduły w największym stopniu odpowiadają za funkcjonowanie aplikacji. Gdyby okazało się, iż zależą one od modułów niskiego poziomu, to zmiany elementów niskiego poziomu mogłyby mieć wpływ na funkcjonowanie modułów wysokopoziomowych, a co za tym idzie wymuszałyby zmiany na wyższych poziomach. Dodatkowo, gdy moduły wysokopoziomowe zależą od niskopoziomowych, ponowne ich wykorzystanie staje się niezwykle trudne. Jeśli jednak odwrócimy tę zależność w drugą stronę, to bardzo łatwo będzie można wielokrotnie je wykorzystywać.

Jeśli chodzi o zależność od abstrakcji, można to zamknąć w jednej prostej formule: pisany przez nas kod nie powinien być uzależniony od konkretnej klasy, zależności takie powinny kończyć się na klasach abstrakcyjnych bądź interfejsach. Zasadę zależności od abstrakcji (ang. depend on abstractions) można również streścić w trzech prostych punktach:

-    Żadna zmienna nie powinna zawierać referencji do konkretnej klasy.
-    Żadna klasa nie powinna dziedziczyć po konkretnej klasie.
-    Żadna metoda nie powinna przykrywać metody zaimplementowanej w którejkolwiek z klas bazowych.

Podstawowymi zaletami zasady odwracania zależności jest to, że właściwe jej stosowanie jest kluczowe, jeśli chcemy tworzyć frameworki wielokrotnego użytku. Ma ona również duży wpływ na odporność kodu źródłowego na przyszłe zmiany, ponieważ zgodnie z tą zasadą abstrakcje, a także szczegółowe mechanizmy są od siebie odizolowane, co z kolei wpływa na to, że tworzony kod jest dużo prostszy w konserwacji.

[Spis Treści](#spis-treści)

### 12. Co to jest zasada DRY? <a name="question1.12"></a>
https://pl.wikipedia.org/wiki/DRY

Nie powtarzaj się to zasada, która mówi, że należy unikać powtarzania tych samych części kodu w różnych miejscach. Pozwala to na uniknięcie kopiowania lub kopiowania i delikatnego zmieniania części kodu w inne miejsca. Główną zaletą DRY (Don't repeat yourself) jest uniknięcie błędów popełnianych w trakcie kopiowania powtarzających się fragmentów kodu. Pozwala to zaoszczędzić czas, który tracimy, aby wprowadzić mało znaczące zmiany do kopiowanego kodu a następnie czas, który tracimy na szukanie zmian, które przeoczyliśmy w trakcie kopiowania. W zasadzie DRY chodzi również o unikanie powtórzeń czynności, które są wykonywane przez programistów. Takie czynności powinny być robione poprzez generatory kodu lub skrypt automatyzujące pracę.

[Spis Treści](#spis-treści)

### 13. Co to jest zasada KISS? <a name="question1.13"></a>
http://czas.ebiznes.org.pl/KISS.htm

Celem tej zasady jest utrzymanie kodu, tak by był on prosty i zrozumiały. Unikając jakichkolwiek niepotrzebnych skomplikowanych zapisów. Zasada ta kieruje postępowanie na skuteczną prostą drogę. Załóżmy, że podczas projektowania strony internetowej poświęcamy dużo rzeczy na kompletnie nie istotne jej części. Zadaniem informacyjnej strony internetowej powinno być dostarczanie informacji, wg zasady KISS powinna być ona prosta i aż głupia w swojej prostocie. Podczas gdy często możemy zaobserwować, kompletnie nie potrzebny stopień skomplikowania, dodatkowe "bajery" kompletnie nikomu nie potrzebne. Projekt powinien być prosty i łatwy w użyciu, poprostu KISS (bo działa)!

[Spis Treści](#spis-treści)

### 14. Co to jest API? <a name="question1.14"></a>
https://pl.wikipedia.org/wiki/Application_Programming_Interface

API - Application Programming Interface (ang. Interfejs Programowania Aplikacji) - Pozwala na komunikowanie się aplikacji między sobą (np. twojego programu z systemem operacyjnym). Zdefiniowane jest na poziomie kodu źródłowego (np. biblioteka dla danego języka programowania). Zadaniem API jest dostarczenie odpowiednich specyfikacji podprogramów (np. funkcji w bibliotece), struktur danych (np. co zawiera dana tablica), klas obiektów (definiują obiekt w j. programowania) i wymaganych protokołów komunikacyjnych (np. http).

Na chłopski rozum można powiedzieć, że API pozwala na korzystanie z funkcjonalności udostępnianych przez inną aplikację w twojej aplikacji. Przykładem jest Windows API, które pozwala na tworzenie aplikacji korzystających z możliwości, które oferuje Windows (np. w C++ możesz otworzyć okno za pomocą funkcji zdefiniowanej przez API). Gdy grałeś w gry to zapewne obiła się tobie o uszy nazwa DirectX lub OpenGL. To są biblioteki, dzięki którym można tworzyć aplikacje 2D i 3D w językach programowania, a one już standardowo komunikują się z kartą graficzną. Jest to duże ułatwienie, ponieważ API jakim jest DirectX i OpenGL pozwala na jednakowe pisanie programów pod różne karty graficzne (producenci muszą się dostosować).

API często ma zastosowanie w aplikacjach sieciowych. Prostym przykładem może być pobieranie tweetów z twittera za pomocą Twitter API. W swoim programie piszesz zapytanie HTTP na odpowiedni adres i otrzymujesz upragnione tweety danej osoby.

API jest ogólnie świetną sprawą, ponieważ pozwala na ujednolicenie rozwiązywania problemów przez co mogą powstawać społeczności, które będą ulepszać już powstałe koło i pomagać innym, chcącym zrozumieć działanie tego koła.

[Spis Treści](#spis-treści)

## Python
### 1. Jakie są óżnice pomiędzy Pythonem 2.x i 3.x ? <a name="question2.1"></a>
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

[Spis Treści](#spis-treści)

### 2. Co to są args i kwargs i kiedy ich używamy ? <a name="question2.2"></a>
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

[Spis Treści](#spis-treści)

### 3. Co to są dekoratory? <a name="question2.3"></a>
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

[Spis Treści](#spis-treści)

### 4. Co to jest PEP8? <a name="question2.4"></a>
https://www.python.org/dev/peps/pep-0008/

PEP8 jest to zestaw zasad określających jak ma wyglądać kod Pythona. Określa między innymi jak duże mają być wcięcia, jak pisać komentarze, maksymalną ilość znaków w jednej linii itp.

[Spis Treści](#spis-treści)

### 5. Jakie znasz typy danych w Pythonie? <a name="question2.5"></a>
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

[Spis Treści](#spis-treści)

### 6. Co to znaczy, że jedne zmienne są mutable, a inne immutable? <a name="question2.6"></a>
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

    [Spis Treści](#spis-treści)

### 7. Dlaczego i kiedy używać generatorów w Pythonie? <a name="question2.7"></a>
https://wiki.python.org/moin/Generators

Generator w Pythonie jest funkcją, która zwraca iterowalny obiekt. Możemy iterować po tym obiekcie za pomocą słowa kluczowego <yield>. Ale możemy to zrobić tylko raz, ponieważ wartości zwracane przezgenerator nie są trzymane w pamięci, ale są tworzone w locie i zapominane.

 Oto kilka przykładów, w których korzystanie z generatorów jest korzystne:

- Możemy zastąpić pętle generatorami w celu wydajnego obliczania wyników z użyciem dużych zbiorów danych.
- Generatory są użyteczne, gdy nie chcemy otrzymać wszystkich wyników i kiedy chcemy wstrzymać iterację na jakiś czas.
- Zamiast używać funkcji callback możemy zastąpić ją generatorem. Możemy napisać pętlę wewnątrz funkcji robi to samo co wywołanie zwrotne i przekształca ją w generator.

[Spis Treści](#spis-treści)

### 8. Jakie znasz rodzaje metod w Pythonie? <a name="question2.8"></a>
http://xion.org.pl/2011/10/03/trzy-rodzaje-metod-w-pythonie/

- Metody instancyjne - zaryzykuję stwierdzenie, że metody instancyjne są domyślnym typem, który w Pythonie jest dodatkowo zaznaczony obecnością specjalnego parametru – self – występującego zawsze jako pierwszy argument. To odpowiednik this z języków C++, C# czy Java i reprezentuje instancję obiektu, na rzecz której wywoływana jest metoda:
    ```Python
    class Counter(object):
        def __init__(self, value = 0):
            self._value = value
        def increment(self, by = 1):
            self._value += by
    ```

- Metody statyczne - istnieją również takie metody, które nie operują na konkretnej instancji klasy. Nazywa się je metodami statycznymi. W Pythonie nie posiadają one parametru self, lecz są opatrzone dekoratorem @staticmethod. Statyczną metodę można wywołać zarówno przy pomocy nazwy klasy (Counter.format_string()), jak i jej obiektu (Counter().format_string()), ale w obu przypadkach rezultat będzie ten sam. Technicznie jest to bowiem zwyczajna funkcja umieszczona po prostu w zasięgu klasy zamiast zasięgu globalnego.
    ```Python
    @staticmethod
    def format_string():
        return "%d"
    ```

- Metody klasowe - trzeci typ, mieści się w pewnym sensie pomiędzy dwoma opisanymi powyżej. Nazywają się tak, bo są wywoływane na rzecz całej klasy (a nie jakiejś jej instancji) i przyjmują ową klasę jako swój pierwszy parametr. (Argument ten jest często nazywany cls, ale jest to o wiele słabsza konwencja niż ta dotycząca self).
W celu odróżnienia od innych rodzajów, metody klasowe oznaczone są dekoratorem @classmethod. Podobnie jak metody statyczne, można je wywoływać na dwa sposoby – przy pomocy klasy lub obiektu – ale w obu przypadkach do cls trafi wyłącznie klasa. Tutaj akurat będzie to Counter, lecz w ogólności może to być także klasa pochodna.
    ```Python
    class BoundedCounter(Counter):
        MAX = 100

        def __init__(self, value = 0):
            if value > self.MAX:
                raise ValueError, "Initial value cannot exceed maximum"
            super(BoundedCounter, self).__init__(value)

        def increment(self, by = 1):
            super(BoundedCounter, self).increment(by)
            self._value = min(self._value, self.MAX)

        @classmethod
        def from_other(cls, counter):
            value = min(counter._value, cls.MAX)
            return cls(value)
    ```

    [Spis Treści](#spis-treści)

### 9. Co to jest lambda w Pythonie i jak jej używać ? <a name="question2.9"></a>
https://pl.wikibooks.org/wiki/Zanurkuj_w_Pythonie/Wyra%C5%BCenia_lambda

Python za pomocą pewnych wyrażeń pozwala nam zdefiniować jednolinijkowe mini-funkcje. Te tzw. funkcje lambda są zapożyczone z Lispa i mogą być użyte wszędzie tam, gdzie potrzebna jest funkcja. Lambda pobiera dowolną liczbę argumentów (włączając argumenty opcjonalne) i zwraca wartość, którą otrzymujemy po wykonaniu pojedynczego wyrażenia. Funkcje lambda nie mogą zawierać poleceń i nie mogą zawierać więcej niż jednego wyrażenia. Nie próbujmy upchać zbyt dużo w funkcję lambda; zamiast tego jeśli potrzebujemy coś bardziej złożonego.

Zdefiniujmy normalną funkcję:

```Python
def f(x):
    return x*2
```
  W ten sposób tworzymy funkcję lambda, która daje ten sam efekt jak normalna funkcja nad nią. Zwróćmy uwagę na skróconą składnię: nie ma nawiasów wokół listy argumentów, brakuje też słowa kluczowego return (cała funkcja może być tylko jednym wyrażeniem). Funkcja nie posiada również nazwy, ale może być wywołana za pomocą zmiennej, do której zostanie przypisana.
```Python
g = lambda x: x*2
```
Możemy użyć funkcji lambda bez przypisywania jej do zmiennej. Może taki sposób korzystania z wyrażeń lambda nie jest zbyt przydatny, ale w ten sposób możemy zobaczyć, że za pomocą tego wyrażenia tworzymy funkcję jednolinijkową.
```Python
(lambda x: x*2)(3)
```

[Spis Treści](#spis-treści)

### 10. Typowanie dynamiczne vs. statyczne <a name="question2.10"></a>

https://pl.wikipedia.org/wiki/Typowanie_dynamiczne
https://pl.wikipedia.org/wiki/Typowanie_statyczne

Zalety:

-    Łatwość programowania: dynamiczne typowanie pozwala programiście nie  przejmować się jeszcze jednym detalem przy pisaniu kodu i skupić się na ważniejszych aspektach (takich jak logiczna poprawność kodu). Tym samym może nawet przyczynić się do zmniejszenia ilości popełnianych błedów.
-   Większą przejrzystość kodu: dzięki dynamicznemu typowaniu składnia języka programowania jest krótsza, bardziej zwięzła, np. z tego powodu Ruby i Python nie muszą uciekać sie do stosowania generyczności, która niekiedy sprawia, że kod jest nieczytelny i trudny do rozszyfrowania.
-    Lepsze wsparcie dla zaawansowanych technik programowania jak: metaprogramowanie, deklaratywna składnia, języki dziedzinowe itp.
-    Implementacje ORM i RPC są bardziej naturalne i łatwiejsze w użyciu w przypadku dynamicznych języków.
-    Wsparcie dla "duck typing": dzięki luźniejszemu podejściu do interfejsów i struktur danych API często są potężniejsze, a sam kod  łatwiejszy w refaktoringu.

Wady:

-    Gorsza wydajność: w przypadku języków statycznych kompilator może wykorzystać wiedzę o typach do przeprowadzenia szerokiej gamy optymizacji.  Brak dynamicznego typowania jest prawdopodobnie podstawowym powodem, dla którego języki takie jak C i Java są dużo szybsze od Pythona i Rubiego.  Zaawansowane kompilatory dla języków dynamicznych ("tracing JIT", np. V8 lub PyPy) potrafią dokonywać optymizacji typowych dla języków statycznych, jednak narzut związany ze "śledzeniem" typów wciąz pozostaje.
-    Jak wspomniałeś: mniej błędów wychwytywanych jest już przy kompilacji.  Nawet w przypadku języków dynamicznych możliwe jest jednak stworzenie narzędzi potrafiących wyłapać większość najczęstszych błędów bez wykonywania kodu.  Jednym z takich narzędzi jest np. pylint.

[Spis Treści](#spis-treści)

### 11. Jaka jest różnica między range() i xrange()? <a name="question2.11"></a>
https://code-maven.com/range-vs-xrange-in-python

Różnica polega na tym, że range() zwraca listę,a xrange() zwraca iterator, więc jest wydajniejsze.
Od Pythona 3.0 nie ma xrange(), a range zwraca iterator.

[Spis Treści](#spis-treści)

## Django
### 1. Co to jest Django?
http://django.pl/
https://pl.wikipedia.org/wiki/Django_(framework)

>Framework webowy dla perfekcjonistów (z terminami)
Django ułatwia szybsze tworzenie aplikacji webowych z mniejszą ilością kodu


Django to webowy framework wysokiego poziomu napisany w Pythonie z myślą o szybkim rozwoju aplikacji, posiadający przejrzystą i pragmatyczną architekturę.

Django powstało dla szybko rozwijającego się, dynamicznego portalu z newsami. Musiał się on zmierzyć z dwoma zadaniami: dotrzymywaniem krótkich terminów redakcji i spełnianiem surowych wymagań autorów -- doświadczonych developerów webowych. Django pozwala na budowanie wydajnych i eleganckich aplikacji internetowych w krótkim czasie.

Zasada DRY (ang. "Don't Repeat Yourself" - nie powtarzaj się) i automatyzacja możliwie wszystkiego to dwie główne domeny Django.

[Spis Treści](#spis-treści)

### 2. Jakie znasz funkcje dostępne w Django?
https://pl.wikipedia.org/wiki/Django_(framework)#Cechy_Django

-    Interfejs administratora (CRUD)
-    Templates
-    Obsługa formularzy
-    Zarządzanie użytkownikami, nadawanie uprawnienień
-    Mapowanie obiektowo-relacyjne (ORM)
-    Narzędzia do testowania
-    Fantastyczna dokumentacja

[Spis Treści](#spis-treści)

### 3. Opisz strukturę Django?
https://docs.djangoproject.com/pl/1.11/

-    Modele - opisują schemat bazy danych i strukturę danych
-    Widoki - kontrolują to, co użytkownik widzi, widok pobiera dane z odpowiednich modeli i wykonuje obliczenia dokonane na danych i przekazuje je do szablonu
-    Szablony: określają, w jaki sposób użytkownik widzi. Szablony opisują, jak dane otrzymane z widoków powinny zostać zmienione lub sformatowane do wyświetlania na stronie
-    Kontroler: framework Django i analiza adresów URL

[Spis Treści](#spis-treści)

### 4.Dlaczego warto używać Django do tworzenia stron WWW?

-    Pozwala na dzielenie modułów kodu na grupy logiczne, aby z kolei umożliwić elastyczne zmiany w przyszłości.
-    Ułatwia zarządzanie witryną, zapewniając automatycznie generowanego administratora.
-    Dostarcza wstępnie pakiet API dla zwykłych zadań użytkownika.
-    Daje system szablonów do definiowania HTMLa dla swojej strony internetowej (pozwala to na uniknięcie duplikowania kodu).
-    Umożliwia określenie adresu URL dla danej funkcji.
-    Umożliwia oddzielenie logiki biznesowej od HTML.
-    Wszystko jest w Pythonie :)

[Spis Treści](#spis-treści)

### 5. Co to są Middleware?
https://pl.wikipedia.org/wiki/Oprogramowanie_po%C5%9Brednicz%C4%85ce

Middleware w Django to niskopoziomowy system "wtyczek" wpływających na dane przesyłane do i z aplikacji Django. Obrazując middleware to kod, który będzie automatycznie wykonywany przed/po wykonaniu widoku, przed wysłaniem odpowiedzi do klienta (przeglądarki) itp. Django posiada zestaw gotowych skryptów middleware opisanych w jego dokumentacji, lecz oprócz nich możemy również tworzyć własne skrypty middleware. Obsługa własnych klas middleware w aplikacjach Djangopozwala operować na nadpływających do widoku żądaniach HTTP, czy wynikach zwracanych przez te widoki.
np.
```Python
MIDDLEWARE_CLASSES = (
    'django.middleware.common.CommonMiddleware',
    'django.contrib.sessions.middleware.SessionMiddleware',
    'django.contrib.auth.middleware.AuthenticationMiddleware',
    'django.middleware.doc.XViewMiddleware',
    'stats.statsMiddleware.statsMiddleware',)
```
#### Skrypty middleware moga być wykonywane w określonych okolicznościach - zależnie od zastosowanej metody middleware:

-    process_request(self, request) - Ta metoda wykonywana jest przy każdym żądaniu zanim Django określi widok do wykonania. Powinna zwrócić None (Django będzie kontynuować wykonywanie kodu, widoku) lub HttpResponse - zwrócony zostanie podany obiekt HttpResponse.
-    process_view(self, request, view_func, view_args, view_kwargs) - "view_func" to obiekt funkcji widoku jaki ma być wykonany, "view_arg" i "view_kwargs" zawierają argumenty jakie będą przekazane do widoku. Metoda ta zostanie wykonana przed samym wykonaniem widoku. Powinna zwrócić None (Django będzie kontynuować wykonywanie kodu, widoku) lub HttpResponse - zwrócony zostanie podany obiekt HttpResponse.
-    process_response(self, request, response) - metoda ta musi zwrócić obiekt HttpResponse, czy to oryginalną odpowiedź "response" lub też inną określoną przez programistę.
-    process_exception(self, request, exception) - "exception" to obiekt Exception. Metoda ta zostanie wykonana w przypadku wystąpienia wyjątku w widoku. Powinna zwrócić None (wtedy do przeglądarki zwrócony zostanie standardowy widok dla wyjątków) lub inny obiekt HttpResponse określony przez programistę.

[Spis Treści](#spis-treści)

## Bazy Danych
### 1. Co to jest SQL?
https://pl.wikipedia.org/wiki/SQL

SQL (ang. Structured Query Language wym. /ɛskjuːˈɛl/) – strukturalny język zapytań używany do tworzenia, modyfikowania baz danych oraz do umieszczania i pobierania danych z baz danych.

[Spis Treści](#spis-treści)

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

[Spis Treści](#spis-treści)

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

[Spis Treści](#spis-treści)

### 4. Jakie znasz relacje w bazach danych
http://www.teacher.webd.pl/kurs_mysql/k_2_2_3.php

 -  #### Relacja jeden do jednego
    Relacja jeden do jednego pomiędzy tabelami A i B występuje wtedy, gdy każdemu rekordowi z tabeli A jest przyporządkowany dokładnie jeden rekord z tabeli B i na odwrót – każdemu rekordowi z tabeli B jest przyporządkowany dokładnie jeden rekord z tabeli A.

 -  #### Relacja jeden do wielu
    Relacja jeden do wielu jest najczęściej używanym typem połączenia. Pomiędzy tabelami A i B występuje wtedy, gdy pojedynczemu rekordowi z tabeli A jest przyporządkowany jeden lub wiele rekordów z tabeli B, natomiast pojedynczemu rekordowi z tabeli B jest przyporządkowany dokładnie jeden rekord z tabeli A. Zmodyfikujmny wcześniejszy przykład, zmieniając tabelę przewodniczących klas na tabelę wychowawców. Może niektórzy nie znają takich sytuacji, więc wyjaśniam, że w mojej szkole funkcjonują klasy łączone. Dwie klasy mają oddzielną domunentację (np. dzienniki lekcyjne), ale jednego wychowawcę.

 -  #### Relacja wiele do wielu
    Relacja wiele do wielu pomiędzy tabelami A i B występuje wtedy, gdy pojedynczemu rekordowi z tabeli A jest przyporządkowany jeden lub wielu rekordów z tabeli B, i na odwrót - pojedynczemu rekordowi z tabeli B jest przyporządkowany jeden lub wielu rekordów A. Taką sytuację będziemy mieli w realcji nauczycieli do uczniów. Każdy nauczyciel uczy wielu uczniów, natomiast każdego ucznia uczą różni nauczyciele.

[Spis Treści](#spis-treści)

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

[Spis Treści](#spis-treści)

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

[Spis Treści](#spis-treści)

### 3. Co to jest DNS?
https://pl.wikipedia.org/wiki/Domain_Name_System

Domain Name System (DNS, pol. „system nazw domenowych”) – system serwerów, protokół komunikacyjny oraz usługa obsługująca rozproszoną bazę danych adresów sieciowych. Pozwala na zamianę adresów znanych użytkowników Internetu na adresy zrozumiałe dla urządzeń tworzących sieć komputerową. Dzięki DNS nazwa mnemoniczna, np. pl.wikipedia.org jest tłumaczona na odpowiadający jej adres IP, czyli 91.198.174.192.

DNS to złożony system komputerowy oraz prawny. Zapewnia z jednej strony rejestrację nazw domen internetowych i ich powiązanie z numerami IP. Z drugiej strony realizuje bieżącą obsługę komputerów odnajdujących adresy IP odpowiadające poszczególnym nazwom. Jest nieodzowny do działania prawie wszystkich usług sieci Internet.

[Spis Treści](#spis-treści)

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

[Spis Treści](#spis-treści)

### 5. Co to jest model OSI i jakie ma warstwy?
http://egzamin-e13.pl/projektowanie-lokalnych-sieci-komputerowych-2/warstwy-sieci-komputerowych-model-osi-i-tcpip

Model wzorcowy ISO OSI (angielskie Open System Interconnection Reference Model), jest kompleksowy standard komunikacji sieciowej (ISO 7498). Proces komunikacji wg tego modelu został podzielony na 7 etapów, zwanych warstwami, ze względu na sposób przechodzenia informacji pomiędzy nimi. Według modelu OSI każdy protokół komunikuje się ze swoim odpowiednikiem, będącym implementacją tego samego protokołu w równorzędnej warstwie komunikacyjnej systemu odległego. Dane przekazywane są od wierzchołka stosu, poprzez kolejne warstwy, aż do warstwy fizycznej, która przesyła je poprzez sieć do odległego hosta.

#### Warstwa fizyczna

Zapewnia transmisję danych pomiędzy węzłami sieci. Definiuje interfejsy sieciowe i medium transmisji. Określa m.in. sposób połączenia mechanicznego, elektrycznego, standard fizycznej transmisji danych. W skład jej obiektów wchodzą min.: przewody, karty sieciowe, modemy, wzmacniacze, koncentratory.

#### Warstwa łącza danych

Zapewnia niezawodność łącza danych. Definiuje mechanizmy kontroli błędów w przesyłanych ramkach lub pakietach - CRC (Cyclic Redundancy Check). Jest ona ściśle powiązana z warstwą fizyczną, która narzuca topologię. Warstwa ta często zajmuje się również kompresją danych. W skład jej obiektów wchodzą sterowniki urządzeń sieciowych, np.: sterowniki kart sieciowych oraz mosty i przełączniki.

#### Warstwa sieciowa

Zapewnia metody ustanawiania, utrzymywania i rozłączania połączenia sieciowego. Obsługuje błędy komunikacji. Ponadto jest odpowiedzialna za trasowanie pakietów w sieci, czyli wyznaczenie optymalnej trasy dla połączenia. W niektórych warunkach dopuszczalne jest gubienie pakietów przez tę warstwę. W skład jej obiektów wchodzą min.: rutery.

#### Warstwa transportowa

Zapewnia przezroczysty transfer danych typu point-to-point. Dba o kolejność pakietów otrzymywanych przez odbiorcę. Sprawdza poprawność przesyłanych pakietów i w przypadku ich uszkodzenia lub zaginięcia, zapewnia ich retransmisję.

#### Warstwa sesji

Zapewnia aplikacjom na odległych komputerach realizację wymiany danych pomiędzy nimi. Kontroluje nawiązywanie i zrywanie połączenia przez aplikację. Jest odpowiedzialna za poprawną realizację zapytania o daną usługę. Do warstwy tej można zaliczyć funkcje API udostępniane programiście przez bibliotekę realizującą dostęp do sieci na poziomie powyżej warstwy transportowej takie jak np. biblioteka strumieni i gniazdek BSD.

#### Warstwa prezentacji

Zapewnia tłumaczenie danych, definiowanie ich formatu oraz odpowiednią składnię. Umożliwia przekształcenie danych na postać standardową, niezależną od aplikacji. Rozwiązuje takie problemy jak niezgodność reprezentacji liczb, znaków końca wiersza, liter narodowych itp. Odpowiada także za kompresję i szyfrowanie.

#### Warstwa aplikacji

Zapewnia aplikacjom metody dostępu do środowiska OSI. Warstwa ta świadczy usługi końcowe dla aplikacji, min.: udostępnianie zasobów (plików, drukarek). Na tym poziomie rezydują procesy sieciowe dostępne bezpośrednio dla użytkownika.

[Spis Treści](#spis-treści)

### 6. Co zawiera nagłówek protokołu HTTP?
http://kobietydokodu.pl/niezbednik-juniora-protokol-http/

#### Czym jest protokół HTTP

HTTP to skrót od Hypertext Transfer Protocol i jest to główny protokół używany współcześnie w przegladarkach. Jest to protokół bezstanowy, tzn. ani serwer (ani klient) nie przechowuje informacji o tym, jakie były wcześniej zapytania pomiędzy określonym serwerem i klientem oraz nie posiada stanu wewnętrznego. Powoduje to, że każde zapytanie do serwera traktowane jest jako ‚nowe’, z punktu widzenia serwera aplikacji niemożliwe do powiązania z informacjami np. o zalogowanym użytkowniku. Tą bezstanowość można obejść, obecnie głównie za pomocą tzw. ciasteczek (będzie o nich nieco dalej), należy jednak pamiętać, że HTTP sam w sobie jest bezstanowy.

#### Nagłówki HTTP

Nagłówki HTTP spotkamy zarówno w zapytaniach, jak i w odpowiedziach. Są one pierwszymy liniami, oddzielone od ciała jedną pustą linią. Nagłówki są opcjonalne – protokół nie wymaga ich obecności. Nagłówki to pewnego rodzaju metadane i polecenia wymieniane przez przeglądarkę i serwer – mogą się w nich znaleźć informacje takie jak rodzaj przesyłanych treści (np. czy jest to obrazek czy plik JSON), sugestia dotycząca traktowania zawartości (czy przeglądarka ma wyświetlić daną treść, czy np. potraktować to jako pobieranie), jaki jest rozmiar przesyłanych danych, kiedy były modyfikowane, jakiego rodzaju odpowiedzi druga strona się spodziewa itp.

Nagłówki przyjmują postać klucz-wartość, zapisywane w postaci:

Klucz: wartość

Najpierw jest klucz (przeważnie zaczyna się dużą literą, ale nie jest to wymagane), następnie dwukropek, spacja oraz wartość.

W przeważającej większości nagłówki są automatycznie ustawiane przez serwer i aplikacja nie musi ich modyfikować / uzupełniać. Są jednak sytuacje, w których możemy chcieć wysłać określony nagłówek, mamy wtedy taką możliwość.

Pełną listę standardowych nagłówków możesz znaleźć np. na Wikipedii, my omówimy sobie tylko te najważniejsze. Co ważne – nagłówek może mieć dowolną nazwę (klucz), nie musi ona być spośród tych określonych standardami. Dzięki temu możliwe jest implementowanie dodatkowej funkcjonalności pomiędzy serwerami, które się ze sobą komunikują. Możemy też dołaczać dowolne nagłówki – jeśli odbiorca wiadomości nie wie, jak je zinterpretować, po prostu je zignoruje.

Poniższa tabela podsumowuje najczęściej używane nagłówki

|Nagłówek| 	Opis| 	Przykład|
|------------|-------|-----|
|Content-Type| 	W zapytaniu oraz odpowiedzi określa, jakiego typu dane są przesyłane| 	Content-Type: application/json
|Content-Length |	W zapytaniu oraz odpowiedzi zawiera informacje ile danych jest przesyłanych |	Content-Length: 20
|Cookie 	|W zapytaniu przesyła zawartość Cookies przechowywanych dla danej witryny. Może przechowywać wiele wartości w postaci klucz=wartość, pary oddzielane są od siebie średnikami. |	Cookie: AcceptedCookiePolicy=1; Country=Poland;
|Set-Cookie |	W odpowiedzi jest to polecenie serwera, aby przeglądarka ustawiła wartości Cookie; podobnie jak nagłówek |Cookie może zawierać wiele par postaci klucz=wartość oddzielonych średnikami |	Set-Cookie: UserID=JanNowak; SeenTutorial=1
|Location 	|W odpowiedzi instuuje przeglądarkę o tym, że ma wykonać zapytanie pod inny adres. W ten sposób (w połaczeniu ze statusem np. 302) w aplikacji możemy przekierowywać pod inny adres |	Location: http://calieminnaaplikacja.com.pl/nowawersja
|Last-Modified| 	W odpowiedzi serwer może poinformować, kiedy nastąpiła ostatnia zmiana zawartości. Format daty jest specyficzny dla protokołu HTTP i określony w dokumencie RCF 7231 	|Last-Modified: Tue, 15 May 2015 12:45:26 GMT
|Content-Disposition| 	W odpowiedzi serwer może poinstuować przeglądarkę, aby zamiast wyświelać treść, pobrała ją. Można też określić nazwę, pod jaką przeglądarka powinna zasugerować zapisanie pliku 	|Content-Disposition: attachment; filename=”raport_roczny.pdf”
|Host 	|W zapytaniu jest to nagłówek obowiązkowy, informuje serwer pod jaki adres domeny chcemy wysłać zapytanie (może to być też adres IP). Pomaga to serwerom obsługującym wiele domen prawidłowo przekierowywać zapytania |	Host: www.kobietydokodu.pl
|Accept 	|W zapytaniu klient może poinformować serwer, jakiego typu odpowiedzi akceptuje. Dzięki temu serwer może zadecydować o wysłaniu odpowiedzi np. w XML a nie JSON, co ma zastosowanie w wielu API 	|Accept: application/xml

[Spis Treści](#spis-treści)

### 7. Czym różni się Http od Https ?
https://poradnikprzedsiebiorcy.pl/-roznice-miedzy-http-a-https-i-ich-wplyw-na-pozycje-strony

#### Protokół http

Protokół http (skrót od angielskiego Hypertext Transfer Protocol) to protokół pozwalający na przesyłanie danych dla sieci internetowej. Za jego pomocą możliwe jest żądanie przesłania klientowi dokumentów znajdujących się w sieci.

Http jest wykorzystywany już od lat 90. XX wieku właśnie w celu umożliwienia komunikacji pomiędzy klientem a serwerem. Początkowo możliwe było wysyłanie jednego żądania i otrzymanie danych w ramach jednego połączenia. Nie miały one dużej wagi ani rozmiaru. Rozbudowanie tego protokołu zgodnie z formatem MIME sprawiło, że wysyłanie większych ilości danych, w dodatku opartych na różnorodnych parametrach, stało się możliwe.

Komunikacja w ramach protokołu http, a więc pomiędzy klientem a serwerem, opiera się na wysyłaniu danych pomiędzy nimi. Klient wysyła zapytanie, na co serwer odpowiada poprzez przesłanie tych danych zainteresowanemu. W tym miejscu warto zauważyć, że omawiany protokół należy do tak zwanych protokołów bezstanowych, co oznacza, że nie przechowuje on danych. Z jednej strony pozwala to na nieobciążanie serwera zbyt dużą ich ilością. Z drugiej natomiast okazuje się to kłopotliwe przy kilkukrotnym korzystaniu z witryny. Z tego powodu strony WWW oparte na tym protokole wspierane są przez system ciasteczek, które pozwalają na gromadzenie danych na temat osób odwiedzających witrynę.

#### Protokół https

Rozważając różnice pomiędzy protokołami http a https, musimy również przyjrzeć się wersji https. Hypertext Transfer Protocol Secure to wersja szyfrowana protokołu http. W odróżnieniu od swojej nieszyfrowanej wersji, gdzie komunikacja pojawia się pomiędzy klientem a serwerem bez wykorzystania specyficznych ustawień wysyłającego zapytanie, protokół https szyfruje dane. Początkowo odbywało się to przy pomocy protokołu SSL. Obecnie w użyciu jest protokół TLS. Ich wykorzystanie pozwala unikać sytuacji przechwycenia danych oraz ich ewentualnego zmienienia.

W standardzie tworzenia stron internetowych oznaczenie protokołu https znajduje się w polu wyszukiwania tuż przed adresem internetowym strony. Protokół ten stosuje się do witryn, w przypadku których wymagane jest większe zaufanie co do serwera. Będzie on zatem zawsze obecny przy adresach URL sklepów internetowych, stron bankowości internetowej, kantorów oraz wszelkich witryn, w których następuje płatność kartą płatniczą. Co bardzo interesujące, protokół https wykorzystywany jest również przez wyszukiwarkę Google. Ponadto https stosuje się także do zabezpieczenia wszelkiego rodzaju forów internetowych, portali społecznościowych oraz wszelkiego rodzaju portali, na których użytkownicy dostają możliwość komentowania treści.

#### Http a https

W trakcie wykorzystywania zasobów internetu nie zastanawiamy się zbytnio nad tym, jaki protokół wykorzystywany jest do przesyłania danych. Różnica między http a https może mieć natomiast wpływ na nasze bezpieczeństwo w sieci.

Https, oznaczający połączenia szyfrowane, pozwala na przesłanie danych w taki sposób, że są one trudniejsze do przechwycenia, i co za tym idzie – niemożliwe do zmiany jeszcze w trakcie ich transferowania. Nie będą również wykorzystywane później przez niepowołane do tego osoby. Z kolei przy wykorzystaniu połączenia nieszyfrowanego, a więc strony, której protokół to http, istnieje spore prawdopodobieństwo, że nasze dane dostaną się w niepowołane ręce. Z tego powodu specjaliści od zabezpieczeń zalecają użytkownikom sprawdzanie, czy połączenie wykorzystywane do płacenia zawiera skrót „https” i symbol zielonej kłódki. Oznacza to, że wszelkie strony internetowe, które wymagają od nas podania hasła lub loginu, zostają zabezpieczone. Ochrona danych klientów jest z kolei jednym z podstawowych warunków, które musi spełnić właściciel strony lub sklepu internetowego.

Dużą różnicę pomiędzy protokołami http a https stanowi wykorzystywany przez nie port domyślny. W przypadku protokołu https jest to port 80. Dla szyfrowanego https portem właściwym jest ten o numerze 443.

#### Http a https – pozycja strony internetowej

Mimo że algorytmy Google’a dla pozycjonowania zmieniają się dość regularnie, możemy stwierdzić, że wykorzystywanie przez właścicieli stron szyfrowanego protokołu https jest jednym z tych czynników, które mogą wpłynąć na pozycje portali w wynikach wyszukiwania Google’a. Takie stwierdzenie pojawiło się w trakcie prezentowania nowych zmian w ramach zmian w algorytmach. Niemniej jednak, jak pokazują wyniki zaprezentowane przez Searchmetrics, bazujące na danych od momentu wprowadzania zmian związanych z protokołem https, nie odnotowano żadnych różnic pomiędzy pozycjami stron wykorzystujących http lub https. Oznacza to, że ten algorytm nie wprowadza dużych zmian, jeżeli chodzi o poprawę pozycji witryn internetowych wobec wyszukiwarek internetowych. A różnice w otrzymanych danych mogą zostać złożone na karb błędu statystycznego.

Jak zapowiadają pracownicy Google’a, znaczenie algorytmu wykorzystującego protokół https ma wzrosnąć w przyszłości. Jednak specjaliści od pozycjonowania twierdzą, że istnieje wiele innych czynników, które wpływają na pozycję stron w internecie, na przykład: linki do strony, wartościowa treść czy liczba polubień na portalach społecznościowych, dzięki którym strony mogą piąć się wyżej w tym rankingu. Znaczenie protokołu https jako czynnika poprawiającego pozycję w wynikach wyszukiwania powinno być większe, jeżeli ma on być brany pod uwagę w trakcie pozycjonowania. Z tego powodu specjaliści od pozycjonowania przewidują, że mimo wprowadzonych zmian w algorytmach Google’a, przewaga stron posiadających protokół https nad tymi zarządzanymi poprzez http nie będzie się zwiększała.

[Spis Treści](#spis-treści)

inspiration:
https://github.com/tvandame/back-end-developer-interview-questions


author @brzydal
