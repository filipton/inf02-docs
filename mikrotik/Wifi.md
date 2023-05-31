# Wifi (bez Quick Set)
**Na samym poczatku nalezy dodac nasze wlan'y do [brige'a](/mikrotik/Bridge.md)!**

![](/images/wifi_add_to_bridge.png)

Jak widzimy na zdjeciu wyzej mamy osobnego bridge'a dla wlan'ow, **nie musimy tak robic**. (Robimy to tylko w celu odseparowania portow ethernet od wlan'ow).

## Tworzenie Security Profile (czyli jakby haslo)
- Wchodzimy w zakladke `Wireless` i podzakladke `Secruity Profiles`
- ![](/images/wifi_security_profiles_tab.png)
- Dodajemy nowy Security Profile
  - ![](/images/wifi_new_security_profile.png)
  - Tutaj wybieramy co nas interesuje - zazwyczaj `WPA2` i wtedy nizej wpisujemy haslo
  - Zazwyczaj zostawiamy `aes.ccm` jako naszego cipher'a

## Tworzenie sieci WIFI
- Wchodzimy w zakladke `Wireless` i podzakladke `WiFi interfaces`
- ![](/images/wifi_wifi_inter_tab.png)
- Modyfikujemy nasze interfejsy WLAN (double click)
  - Wchodzimy w zakladke `Wireless` i modyfikujemy
    - **Klikamy `Advanced Mode` po prawej stronie**
    - `Mode` - ustawiamy **ap_bridge**
    - `Band` - ustawiamy jaka chcemy
    - `Channel Width` - zazwyczaj zostawiamy domyslne
    - `SSID` - nazwa sieci wifi
    - **`Security Profile` - ustawiamy wczesniej ustawiony [Security Profile](#tworzenie-security-profile-czyli-jakby-haslo)**
    - `WPS Mode` - mozemy wylaczyc jezeli nie potrzebny
    - `Country` - ustawiamy na poland
    - `VLAN ID` - tutaj tez mamy cos z vlanem, wydaje mi sie ze jak chcemy miec vlan na tym WLAN'ie to musimy tutaj ustawic rowniez
    - ![](/images/wifi_modify_wireless.png)
    
  - Wchodzimy w zakladke `HT` i upewniamy sie ze wszystkie chainy dla Rx i Tx sa wlaczone!
  - ![](/images/wifi_modify_ht.png)

## Uwagi
- **Nie musimy konfigurowac obu interfejsow WLAN jezeli nie ma tego w zadaniu (czyli np tylko jedna czestotliwosc 2.4GHz lub 5.0GHz)**
- Jeden WLAN to **TYLKO 2.4GHz** a drugi to **TYLKO 5GHz**
- Jezeli mamy zrobic wifi na danym vlan'ie to poprostu w zakladce `Bridge` i podzakladce `Ports` ustawiamy nasze pvid oraz w podzakladce `VLANs` dodajemy nasze interfejsy `wlan` do danego vlan'a!