# PRZEŁĄCZNIKI DO KOMEND SZUKAMY WPISUJĄC MAN POLECENIE - WSZYSTKIE PRZELACZNIKI SA W MAN NIE TRZEBA ICH PAMIETAC

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
