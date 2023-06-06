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

## Pliki bash

Tworzymy plik z rozszerzeniem .sh, np: `Plik_wsadowy.sh`

```bash
#!/bin/bash

jakies
komendy
tutaj
```

`echo cos_do_wyswietlenia` wyswietla cos do konsoli

### Zmienne
```bash
X="jakas_zmienna"
echo $X # wywolanie zmiennej
read X # wprowadzanie wartosci z klawiatury do zmiennej X
```

### IF
```bash
if <warunek> ; then
  polecenia1
else
  polecenia2
fi
```

Przyklad:
```bash
#!/bin/bash
if [ -e ~/.bashrc ]
then
  echo "Masz plik .bashrc"
else
  echo "Nie masz pliku .bashrc"
fi
```
![image](/images/bash_operators.png)

### For loop
```bash
#!/bin/bash
for i in 1 2 3 4 5
do
  echo "Weclome $i times"
done
```

### While loop
```bash
while [ condition ]
do
  command1
  command2
  ...
done
```

Przyklad:
```bash
#!/bin/bash
x=1
while [ $x -le 5 ]
do
  echo "Welcome $x times"
  x=$(( $x + 1 ))
done
```

## Użytkownicy Grupy Hasła

`useradd nazwa_uzytkownika` tworzy uzytkownika

`-c` komentarz

`-e` YYY-MM-DD data wygasniecia konta

`-m` tworzy katalog domowy w standardowej lokalizacji

`-s` zmiana powłoki 

<br>

`userdel nazwa_uzytkownika` usuwa uzytkownika

`-r` usuwa katalog domowy

<br>

`usermod nazwa_urzytkownika` - do modyfikacji uzytkownika

`-g` grupa podstawowa

`-G` usuwa wszytkie gurpy dodatkowe i ustawia podane

`-aG` dodaje gurpy dodatkowe

`-e` YYY-MM-DD data wygasniecia konta

`-c` komentarz

`-L` blokowanie konta

`-U` odlokowywanie konta

`-m` przenoszenie katalogu domowego

`-s` zmiana powloki 

`-u` zmiana UID

<br>

`groupadd nazwa_grupy` dodawanie grupy

`groupdel nazwa_grupy` usuwanie grupy

`groupmod nazwa_grupy` modyfikacja grupy

`passwd nazwa_uzytkownika` zmiana hasła uzytkownika

`chage nazwa_uzytkownika` zmiana ustawien hasla

## Zarządzanie dyskami

`fdisk` do dyskow mbr

`gdisk` do dyskow gpt

`-l` wyswietla dyski i partycje (taki sam do `gdisk` i `fdisk`)

<br>

`fdisk nazwa_urzadzenia` odpala konfiguracje wskazanego uzadzenia

`parted -l` wyswietla info o partycjach

`mkfs.system_plikow sciezka_do_partycji` zmiana systemu plikow partycji
<br>
mkfs.btrfs   mkfs.cramfs  mkfs.ext2	mkfs.ext3	mkfs.ext4	mkfs.minix   mkfs.xfs 
<br>
jak nie pamietasz rodzajow partycji to piszesz mkfs. i 2 razy klikasz tab

`mount sciezka_do_partycji sciezka_do_pliku` montowanie partycji

## Tar

`tar nazwa_archiwum pliki_do_archiwizacji`

`-c` tworzenie archiwum

`-v` wypisuje co robi

`-f` sciezka do archiwum

`-z` kompresowanie gzip

`-j` kompresowanie bzip2

`-C` zmienia katalog w którym domyslnie pracuje tar

`-x` wypakowywanie archiwum 

`-t` wyswietla zawartosc archiwum

`-r` dolaczanie do archiwum

`-u` uaktualnanie archiwum

## Konfiguracja sieci z pliku (netplan)

Sprawdzanie nazw i konfiguracji kart sieciowych 

`ip a`

Plik konfiguracyjny

/etc/netplan/\*.yaml

### Przykładowa konfiguracja

![](/images/netplan_ex_1.png)
![](/images/netplan_ex_2.png)
![](/images/netplan_ex_3.png)

**Po konfiguracji trzeba wpisac komende** `sudo netplan apply`


## Net-tools

`qrp` do sprawdzania adresow mac i ip

`ifconfig` wyswietla konfigruacje interfejsu (między innymi ip)

`ipmaddr` wyswietla mac

`iptunnel` 

`route` pokazuje trasy routingu

`nameif` 

`mii-tool` 


## Lynx 

Do przeglądania stron internetowych

`lynx adres_strony`

## Diagnostyka

`lshw` wyswietla informacje o calych hardwere 

`lshw | more` wyswietla lshw z podzialem na czesci

`uname` wyswietla informacje o systemie

`cat /etc/*-release` wyswietla dokladniejsze informacje o systemie 

`tty` wyswietla nazwe terminala

Zmiana nazwy hosta
plik konfiguracyjny
`/etc/hostname`
usuwamy nazwe i wpisujemy nowa
potem restartujemy maszyne

`.nazwa_katalogu` tworzenie katalogu ukrytego

`lscpu` dokladniejsze informacje o procesorze

`umask` wyswietla aktualna maske uprawnien do plikow

`echo $USER` wyswietla nazwe aktualnego uzytkownika

`cat /etc/passwd | nazwauzytkownika` wyswietlanie uid i gid 
![](/images/udigid.png)

`top` wyswietla informacje o procesach uzyciu procesora i ramu

`uname -r` wyswietla nazwe kernela
