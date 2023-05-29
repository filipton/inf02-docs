# SSH Linux

`/etc/ssh/sshd_config` plik konfiguracyjny

## Logowanie do ssh z innego komputera
```bash
ssh nazwa_uzytkownika@adres_ip_serwera

# Przyklad
ssh Administrator@192.168.0.1
```

## Logowanie do ssh z zmienionym portem
```bash
ssh nazwa_uzytkownika@adres_ip_serwera -p numer_portu

# Przyklad
ssh Administrator@192.168.0.1 -p 8080
```

## Restartowanie ssh
```bash
sudo systemctl restart ssh
sudo systemctl status ssh
```

![image](/images/systemctl_status_ssh.png)

Patrzycie tylko czy wyświetla active (running) na zielono jeśli tak to działa nie patrzycie na nic innego.

## Zmiana portu ssh
Otwieramy plik konfiguracyjny
```bash
sudo nano /etc/ssh/sshd_config
```

Szukamy linijki `#Port 22`, usuwamy `#` i w miejscu 22 wpisujemy port ktory kazano nam ustawic
```bash
#Port 22
#AddressFamily any
#ListenAddress 0.0.0.0
#ListenAddress ::
```

Przyklad:
```bash
Port 8080
#AddressFamily any
#ListenAddress 0.0.0.0
#ListenAddress ::
```

Na samym koncu [restartujemy](#restartowanie-ssh) i sprawdzamy czy nam wszystko dziala. 
W tym momencie mozemy sprobowac [zalogowac sie z zmienionym portem](#logowanie-do-ssh-z-zmienionym-portem).

## Logowanie do ssh jako root

Tworzymy haslo dla roota `sudo passwd root`

Otwieramy plik konfiguracyjny `sudo nano /etc/ssh/sshd_config`

Szukamy takiej linijki

![image](/images/sshd_config_find_permitrootlogin.png)

Przy `PermitRootLogin` usuwamy `#` i w miejsce `prohibit-password` wpisujemy `yes`

![image](/images/sshd_config_permirootlogin_yes.png)

Na samym koncu [restartujemy](#restartowanie-ssh) i sprawdzamy czy nam wszystko dziala.
W tym momencie mozemy sprobowac [zalogowac sie](#logowanie-do-ssh-z-innego-komputera) na konto `root`.

## Blokowanie i zezwalanie na logowanie
Otwieramy plik konfiguracyjny `sudo nano /etc/ssh/sshd_config` i dodajemy/modifikujemy

`AllowUsers nazwa_uzytkownika1 nazwa_uzytkownika2 ...` zezwala tym uzytkownkom na zalogowanie do ssh

`DenyUsers nazwa_uzytkownika1 nazwa_uzytkownika2 ...` blokuje tym uzytkownikom mozliwosc
zalogowania do ssh

`AllowGroups nazwa_grupy1 nazwa_grupy2 ...` zezwala uzytkownikom z tych grup na
zalogowanie do ssh

`DenyGroups nazwa_grupy1 nazwa_grupy2 ...` blokuje uzytkownikom z tych grup mozliwosc
zalogowania do ssh

Na samym koncu [restartujemy](#restartowanie-ssh) i sprawdzamy czy nam wszystko dziala. 

## Ustawianie maxymalnej ilosci prob wpisania hasla i maxymalnej ilosci sesji
Otwieramy plik konfiguracyjny `sudo nano /etc/ssh/sshd_config`

Szukamy i modifikujemy odpowiednie linijki (wiadomo usuwamy `#` jezeli sa przed opcja)

![image](/images/sshd_config_find_permitrootlogin.png)

`MaxAuthTries` maxymalna ilosc prob wpisania hasla (zmieniamy z 6 na ile chcemy)
`MaxSessions` maxymalna ilosc sesji (zmieniamy z 10 na ile chcemy)

Na samym koncu [restartujemy](#restartowanie-ssh) i sprawdzamy czy nam wszystko dziala. 

## Włączanie i wyłączanie uwierzytelniania hasłem
Otwieramy plik konfiguracyjny `sudo nano /etc/ssh/sshd_config`

![image](/images/sshd_config_password_auth.png)

Szukamy `PasswordAuthentication` i usuwamy `#` jezeli on tam jest, jak chcemy wlaczyc autoryzajce haslem zostawiamy `yes` a jeśli
chcemy wylaczyc to zmieniamy na `no`

## Generowanie i Logowanie kluczem ssh
**Robimy to na kliencie nie na serwerze**

### Tworzenie klucza prywatnego i publicznego (taka sama komenda i na linuxie i
na windowsie)

```bash
ssh-keygen -t rsa
```

![image](/images/ssh_generate_key.png)

Przeysłamy klucz ssh na serwer. Scieżka do pliku z kluczem jest podana przy tworzeniu klucza

```bash
scp sciezka_do_pliku nazwa_urzytkownika_na_serwerze@adres_ip_serwera:/home/nazwa_urzytkownika_na_serwerze/.ssh

# Przyklad
scp /home/kwakwa/.ssh/id_rsa.pub Administrator@192.168.0.1:/home/Administrator/.ssh
```
Dodajemy na zaraz po scp `–P nr_portu` jeśli mamy zmieniony port

Potem na serwerze
```bash
sudo cat .ssh/id_rsa.pub >> .ssh/authorized_keys
```

(Nadal na serwerze) otwieramy plik `/etc/ssh/sshd_config` i szukamy `PubKeyAuthentication`, usuwamy `#` i ustawiamy wartosc na `yes` jezeli taka nie jest

Na samym koncu [restartujemy](#restartowanie-ssh) i sprawdzamy czy nam wszystko dziala. 
