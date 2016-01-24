# Pracownia P3 - Systemy Operacyjne

## Problem przeprawy przez rzekę (*River crossing*)
Pewna przeprawa przez rzekę dzielona jest zarówno przez linuxowych Hakerów, jak i pracowników Microsoftu. Do przeprawy używana jest **jedna** łódka, która mieści tylko **czterech** programistów i zawsze płynie **w pełni** załadowana. Łódka napędzana jest przez **jedną** osobę wiosłującą.<br />
Aby zagwarantować bezpieczeństwo programistów w łódce, nie może dojść do następujących sytuacji:

1. Trzech linuxowych Hakerów przebywa w łódce z trzema pracownikami Microsoftu.
2. Trzech pracowników Microsoftu przebywa w łódce z trzema linuxowymi Hakerami.

Wszystkie pozostałe kombinacje są bezpieczne.<br />
Dodatkowo programiści wprowadzili zasadę "kto pierwszy ten lepszy", a więc ostatnia zgłoszona do łódki osoba będzie wioślarzem. Łódka ma być gospodarowana **optymalnie**, tzn. powinnna odpłynąć, gdy zgłoszone osoby będą mogły utworzyć poprawny ładunek. Ponieważ może się okazać, że wśród ostatnich programistów nie da się utworzyć ładunku (np. pozostanie trzech programistów), powinni oni zaniechać prób dostania się na łódź.
#### Zadanie
Zaimplementować rozwiązanie powyższego konfliktu zasobów z użyciem wątków. Każdy programista powinien być reprezentowany przez osobny wątek Hakera / pracownika Microsoftu wykonującym odpowiednio jedną z funkcji **_linHackerArrives()_** i **_windowserArrives()_**. Wątek może zakończyć działanie, gdy wystąpi jedna z sytuacji:

1. Programista przeprawi się przez rzekę.
2. Programista nie ma możliwości przeprawy przez rzekę (pula programistów skończyła się i nie może on już dobrać sobie odpowiedniej ekipy).

Wejście programisty na łódkę odbywa się z użyciem funkcji **_boardBoat()_**. Ostatni ze zgłoszonych programistów wywołuje funkcję **_boardAndRow()_** ("wejdź na pokład i wiosłuj"). Należy zadbać, żeby funkcja **_boardAndRow()_** została wywołana, gdy pozostali programiści zajęli już swoje miejsca w łódce. W czasie wodowania należy powstrzymać pozostałych programistów od wchodzenia do łódki. <br />
Rozwiązanie może korzystać z **tylko jednej** zmiennej typu *mutex*.

## Kompilacja
Aby skompilować program oraz tester należy uruchomić:
```Makefile
make
```
lub
```Makefile
make compile
```
## Uruchamianie
Program przyjmuje następujące parametry:
```Makefile
-s <wartość> # prędkość generowania programistów [0...12] (domyślnie 9)
-p <wartość> # ilość programistów do wygenerowania [0...] (domyślnie 100)
-t <wartość> # [0 lub 1] gdy 1 do pliku tekstowego drukuje raport do testów (domyślnie 1) 
```
Przykładowe uruchomienie:
```Makefile
./river
```
## Testowanie
```Makefile
make test1 # parametry
```
```Makefile
make test2
```
```Makefile
make test3
```
```Makefile
make test4
```
```Makefile
make test5
```
## Usuwanie
