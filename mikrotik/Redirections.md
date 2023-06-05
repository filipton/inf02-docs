# Przekierowania
Robimy przekierowanie zeby bedac polaczanym z portem WAN mikrotika miec dostep np. do strony WWW postawionej na urzadzeniu w sieci LAN.

## Sposob z [Quick Set](/mikrotik/QuickSet.md)
**Do tego sposobu bedziemy potrzebowali miec skonfigurowanego NAT'a w Quick Set oraz adresow IP WAN i LAN**

- W zakladce `Quick Set` jezeli mam wlaczony `NAT` pojawi sie nowy button `Port Mapping` w ktorego wchodzimy
- ![](/images/redir_portmapping.png)
- Naciskamy tam "+" i dodajemy nowy mapping
  - `Protocol` - jaki chcemy (pewnie bedzie to TCP)
  - `Port` - port na mikrotiku (na WAN'ie)
  - `To Address` - adres LAN serwera
  - `To Port` - port np. WWW serwera 
  - ![](/images/redir_portmapping_new.png)

## Sposob bez Quick Set'a
**Do tego sposobu bedziemy potrzebowali ustawic [recznie regule NAT](/mikrotik/NAT.md#sposob-tworzac-regule-nat-recznie) i musimy recznie [ustawic adres IP naszego bridge'a i portu WAN](/mikrotik/Addressess.md)!**

- Wchodzimy w zakladke `IP > Firewall` i przechodzimy do podzakladki `NAT`
- Dodajemy nowa regule i ustawiamy:
  - `Chain` - dstnat
  - `Protocol` - jaki chcemy (pewnie bedzie to TCP)
  - `In. Interface` - port WAN **WAZNE**
  - `Dst. Port` - port na mikrotiku (na WAN'ie)
  - W podzakladce `Action` zmieniamy `Action` na `dst-nat`
    - Ustawiamy `To Addresses` oraz `To Ports` na adres i port serwera w sieci **LAN**
- Wiadomo na koncu `Apply`

![](/images/redir_general_tab.png)
![](/images/redir_action_tab.png)
