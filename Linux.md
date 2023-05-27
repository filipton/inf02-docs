# PRZEŁĄCZNIKI DO KOMEND SZUKAMY WPISUJĄC MAN POLECENIE - WSZYSTKIE PRZELACZNIKI SA W MAN NIE TRZEBA ICH PAMIETAC

## Pliki i Katalogi

`cd` -  zmiana katalogu w którym jesteśmy

`~` - katalog domowy użytkownika na którym jesteśmy zalogowani `/home/nazwa_uzytkownika`

`.` - Aktualny katalog

`..` - katalog nadrzędny

`/` - katalog główny

## Najważniejsze katalogi

`/home` - domyslne miejsce przechowywania katalogow domowych

`/dev` -  miejsce plikow urzadzen

`/etc` - pliki konfigruacyjne

## Komendy

`mkdir nazwa` - tworzenie katalogow

`rm nazwa` -  usuwanie katalogow i plikow

`cp polozenie_pliku miejsce_docelowe` - kopiowanie

`mv nazwa_pliku miejsce_docelowe` - przenoszenie plikow

`mv nazwa nowa_nazwa` - zmiana nazwy

`ln nazwa_pliku miejsce_dowiazania` - tworzenie dowiazania (domyslnie twarde dowiazanie, przelacznik `-s` aby bylo symboliczne) 

`ls` - wysietlanie zawartosci katalogu 

`ls -l` - ls z wiecej informacji

touch nazwa\_pliku tworzenie plikow

nano nazwapliku edycja zawartosci pliku

chmod uprawnienia nazwapliku ustalanie praw do pliku

Kolejność

Właściciel\_pliku Grupa\_pliku Reszta

Ustalanie uprawnien 

Odczyt zapis wykonanie 

`     `4          2          1

Dodajemy liczby odpowiednie dla uprawnien jakie chcemy nadac np. Jak chcemy odczyt i wykonanie to 4 + 1 = 5  zapis odczyt 2 + 4 = 6

I tak dla wlasciciela grupy i reszty

Np.. Jak chcemy dla wlasciciela pelne prawa(odczyt zapis wykonanie) grupy odczyt i zapis a dla reszty odczyt to uzywamy komendy chmod 764 nazwa

Zmiana wlasciciela pliku 

chown nazwa\_uzytkownika nazwa\_pliku

Zmiana grupy pliku

chgrp nazwa\_grupy nazwa\_pliku

Zmiana wlasciciela i grupy na raz 

chown nazwa\_wlasciciela:nazwa\_grupy nazwa\_pliku

Ustawienie na brak wlasciciela i brak grupy

chown nobody:nogroup nazwa\_pliku

Pliki wsadowe

Tworzymy plik z rozszerzeniem .sh

Np.. Plik\_wsadowy.sh

![](Aspose.Words.d1642233-c50d-4460-8554-42d738192727.001.png)

Echo cos\_do\_wyswietlenia wyswietla 

Zmienne

X=”jakas\_zmienna”

Echo $X wywolanie zmiennej

Read X wprowadzanie wartosci z klawiatury do zmiennej X

IF

![](Aspose.Words.d1642233-c50d-4460-8554-42d738192727.002.png)

![](Aspose.Words.d1642233-c50d-4460-8554-42d738192727.003.png)

![](Aspose.Words.d1642233-c50d-4460-8554-42d738192727.004.png)

For

![](Aspose.Words.d1642233-c50d-4460-8554-42d738192727.005.png)

While

![](Aspose.Words.d1642233-c50d-4460-8554-42d738192727.006.png)

![](Aspose.Words.d1642233-c50d-4460-8554-42d738192727.007.png)


Użytkownicy Grupy Hasła

useradd nazwa\_uzytkownika  tworzy uzytkownika

-c komentarz

-e YYY-MM-DD data wygasniecia konta

-m tworzy katalog domowy w standardowej lokalizacji

-s zmiana powłoki 

userdel nazwa\_uzytkownika  usuwa uzytkownika

-r usuwa katalog domowy

usermod nazwa\_urzytkownika do modyfikacji uzytkownika

-g grupa podstawowa

-G usuwa wszytkie gurpy dodatkowe i ustawia podane

-aG dodaje gurpy dodatkowe

-e YYY-MM-DD data wygasniecia konta

-c komentarz

-L blokowanie konta

-U odlokowywanie konta

-m przenoszenie katalogu domowego

-s zmiana powloki 

-u zmiana UID

groupadd nazwa\_grupy dodawanie grupy

groupdel nazwa\_grupy usuwanie grupy

groupmod nazwa\_grupy modyfikacja grupy

passwd nazwa\_uzytkownika zmiana hasła uzytkownika

chage nazwa\_uzytkownika zmiana ustawien hasla

Zarządzanie dyskami

fdisk do dyskow mbr

gdisk do dyskow gpt

Takie  same podstawowe przelaczniki

-l wyswietla dyski i partycje

fdisk nazwa\_urzadzenia odpala konfiguracje wskazanego uzadzenia

Tar

Tar nazwa\_archiwum pliki\_do\_archiwizacji

-c tworzenie archiwum

-v wypisuje co robi

-f sciezka do archiwum

-z kompresowanie gzip

-j kompresowanie bzip2

-C zmienia katalog w którym domyslnie pracuje tar

-x wypakowywanie archiwum 

-t wyswietla zawartosc archiwum

-r dolaczanie do archiwum

-u uaktualnanie archiwum

Konfiguracja sieci z pliku (netplan)

Sprawdzanie nazw i konfiguracji kart sieciowych 

Ip a

Plik konfiguracyjny

/etc/netplan/\*.yaml

Przykładowa konfiguracja

![](Aspose.Words.d1642233-c50d-4460-8554-42d738192727.008.png)

![](Aspose.Words.d1642233-c50d-4460-8554-42d738192727.009.png)

![](Aspose.Words.d1642233-c50d-4460-8554-42d738192727.010.png)

Po konfiguracji trzeba wpisac komende

sudo netplan apply


Net-tools

qrp do sprawdzania adresow mac i ip

ifconfig wyswietla konfigruacje interfejsu (między innymi ip)

ipmaddr wyswietla mac

iptunnel 

route pokazuje trasy routingu

nameif 

mii-tool 


Lynx 

Do przeglądania stron internetowych

lynx adres\_strony

DIagnostyka

lshw wyswietla informacje o calych hardwere 

lshw | more wyswietla lshw z podzialem na czesci

uname wyswietla informacje o systemie

cat /etc/\*-release wyswietla dokladniejsze informacje o systemie 
