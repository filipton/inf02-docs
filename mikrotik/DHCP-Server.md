# DHCP Server
Przed konfiguracja nalezy skonfigurowac [bridge](/mikrotik/Bridge.md).

- [Konfigurujemy adres IP](/mikrotik/Addressess.md) dla naszego interfejsu (bridge/vlan)
- Wchodzimy w zakladke `IP > DHCP Server`
- Naciskamy przycisk `DHCP Setup`
- ![](/images/dhcp_server_setup_btn.png)
- Wybieramy jako interfejs - interfejs na ktorym wczesniej ustawilismy IP (czyli pewnie bridge lub VLAN)
- Przeklikujemy i zmieniamy co potrzeba

## Rezerwacje IP
- Wchodzimy w podzakladke `Leases` (tutaj mamy lise wszystkich clientow DHCP)
- Mozemy albo dodac nowe zastrzezenie lub zmodyfikowac aktywnie polaczonego clienta aby mial statyczny adres ip (jezeli edytujemy to double click i przycisk `Make Static`)

## Modyfikacja DNS/Zakresow servera DHCP
- Wchodzimy w podzakladke `Networks`
- "Namierzamy" nasza siec ktora chcemy zmodyfikowac i double click na nia
- W okienku ktore nam sie utworzylo mozemy zmodyfikowac zakresy ip, dns etc.
- ![](/images/dhcp_server_modify_networks.png)

## Konfiguracja DHCP dla kilku VLANow
Jezeli chcemy miec ta sama adresacje DHCP'kow dla kilku roznych vlanow poprostu ustawiamy te same adresy ip dla tych vlanow.

Potem tak jak wczesniej poprostu konfigurujemy na tych vlanach DHCP server.

![](/images/dhcp_multiple_vlans.png)

## Uwagi
- Przy konfiguracji DHCP server'a na VLAN'ie w interfejsach wybieramy naszego VLAN'a