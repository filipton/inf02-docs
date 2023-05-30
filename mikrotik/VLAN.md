# VLAN'y
**Na samym poczatku bedziemy musieli utworzyc [bridge'a](/mikrotik/Bridge.md)!**

## "Definicje" vlanow dla bridge'a
- W pierwszej kolejnosci musimy utworzyc nasze VLAN'y wiec wchodzimy w zakladke `Interfaces` a w niej w podzakladke `VLAN`.
- ![](/images/vlan_tab_interfaces.png)
- Tutaj tworzymy nasze VLAN'y - pamietajmy o ustawieniu `VLAN ID` na jakie chcemy ID vlan'a oraz `Interface` na Bridge'a
- ![](/images/vlan_add_new_interface.png)

## Przypisanie portow
- Wchodzimy w zakladke `Bridge` a w niej w podzakladke `VLANs`
- Dodajemy nowa definicje portu VLAN'a
  - `Bridge` - dajemy nasz bridge
  - `VLAN ID's` - id naszego/naszych vlanow (zazwyczaj pewnie lepiej nie dodawac wiecej niz jeden zeby sobie nie zaciemniac konfiguracji)
  - `Tagged` - porty tagowane inaczej trunki (porty ktore maja w ramce id vlanu), **dodajemy tutaj zawsze rowniez naszego bridge'a!**
  - `Untagged` - porty accessowe czyli poprostu porty ktore trafiaja do clientow
  - ![](/images/vlan_add_port_def.png)
- Nastepnie wchodzimy w podzakladke `Ports` (nadal w zakladce `Bridge`)
- Dodajemy tam (lub modyfikujemy) porty ktore wczesniej wpisalismy w `Tagged` i `Untagged` **TAK TRUNKI TEZ**
  - `Interface` - dajemy dany port
  - `Bridge` - nasz bridge

## Uwagi
- Jezeli mamy vlan'y to musimy miec osobne DHCP server'y, DHCP server na bridge nie bedzie juz nam przydzielal adresow