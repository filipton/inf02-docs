# PRZEŁĄCZNIKI DO KOMEND SZUKAMY WPISUJĄC MAN POLECENIE - WSZYSTKIE PRZELACZNIKI SA W MAN NIE TRZEBA ICH PAMIETAC

## Pliki i Katalogi

`cd` zmiana katalogu w którym jesteśmy

`~` katalog domowy użytkownika na którym jesteśmy zalogowani `/home/nazwa_uzytkownika`

`.` Aktualny katalog

`..` katalog nadrzędny

`/` katalog główny

## Najważniejsze katalogi

`/home` domyslne miejsce przechowywania katalogow domowych

`/dev` miejsce plikow urzadzen

`/etc` pliki konfigruacyjne

## Komendy

`mkdir nazwa` worzenie katalogow

`rm nazwa` usuwanie katalogow i plikow

`cp polozenie_pliku miejsce_docelowe` kopiowanie

`mv nazwa_pliku miejsce_docelowe` przenoszenie plikow

`mv nazwa nowa_nazwa` zmiana nazwy

`ln nazwa_pliku miejsce_dowiazania` tworzenie dowiazania (domyslnie twarde dowiazanie, przelacznik `-s` aby bylo symboliczne) 

`ls` wysietlanie zawartosci katalogu 

`ls -l` ls z wiecej informacji

`touch nazwa_pliku` tworzenie plikow

`nano nazwapliku` edycja zawartosci pliku

`chmod uprawnienia nazwapliku` ustalanie praw do pliku

Kolejnosc:

Właściciel pliku | Grupa pliku | Reszta

Ustalanie uprawnien 
| Odczyt | Zapis | Wykonanie |
|--------|-------|-----------|
| 4      | 2     | 1         |

Dodajemy liczby odpowiednie dla uprawnien jakie chcemy nadac np. Jak chcemy odczyt i wykonanie to 4 + 1 = 5  zapis odczyt 2 + 4 = 6

I tak dla wlasciciela grupy i reszty

Np.. Jak chcemy dla wlasciciela pelne prawa(odczyt zapis wykonanie) grupy odczyt i zapis a dla reszty odczyt to uzywamy komendy `chmod 764 nazwa`

`chown nazwa_uzytkownika nazwa_pliku` zmiana wlasciciela pliku

`chgrp nazwa_grupy nazwa_pliku` zmiana grupy pliku

`chown nazwa_wlasciciela:nazwa_grupy nazwa_pliku` Zmiana wlasciciela i grupy na raz 

`chown nobody:nogroup nazwa_pliku` Ustawienie na brak wlasciciela i brak grupy
