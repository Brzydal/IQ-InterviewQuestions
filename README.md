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


author @brzydal
