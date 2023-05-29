# Instalacja mikrotik na Virtualbox/VMware

Jezeli chcemy porobic mikortiki w domu mozemy je wirtualizowac. Plik .ova mozemy pobrac [tutaj](https://mikrotik.com/download) - szukamy na dole `Cloud Hosted Router` i pobieramy `OVA template`. (Najlepiej najnowsza)

**Do zarzadzania mikrotikiem wykorzystujemy program [WinBox](https://mt.lv/winbox64)**.

## Uwagi
 - Jezeli chcemy miec wiecej niz 4 interfejsy (czyli tak jak na virtualbox) najlepiej poprostu pobrac `vmware` ktory nam pozwoli dodac wiecej interfejsow. 
 - Pamietaj, ze zeby dostac sie za pomoca winbox do mikrotika musisz miec karte sieciowa z `bridge` ustawiona na jakims porcie - najlepiej na ostatnia.
 - Pamietaj, ze pierwszy port (karta siecowa) jest domyslnie zazwyczaj konfigurowany jako `WAN`.