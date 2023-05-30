# NAT

## Sposob uzywajac [Quick Set](/mikrotik/QuickSet.md)
![](/images/nat_quickset.png)

**Zakladam ze inne opcje w Quick Set sa juz skonfigurowane - inaczej nie bedzie mozna zapisac zmian!**

- Wlaczamy opcje `Bridge All LAN Ports` - jezeli chcemy [konfigurowac bridge recznie](/mikrotik/Bridge.md) to zostawiamy ta opcje wylaczona (po konfiguracji bridge ona znika, wiec mozemy wogole nie miec tej opcji)
- Wlaczamy opcje `NAT` - spowoduje ona utworzenie reguly NAT, portem WAN bedzie `ether1` no chyba ze ustawimy na gorze inny `Port`

## Sposob tworzac regule NAT recznie
Jezeli nie chcemy uzywac opcji Quick Set to mozemy recznie dodac regule firewall'a dla NAT.

- [Tworzymy bridge](/mikrotik/Bridge.md) jezeli nie mamy i przypisujemy do niego **TYLKO** porty LAN

- Wchodzimy w zakladke `IP > Firewall` i w "kartach" szukamy `NAT`
![](/images/nat_firewall_bm.png)

- Dodajemy tutaj "+" nowa regule

- W okienku i zakladce `General`
  - `Chain` - srcnat
  - `Out. Interface` - tutaj dajemy nasz port **WAN**
  ![](/images/nat_new_rule_general.png)

- W zakladce `Action` ustawiamy `masquerade`
![](/images/nat_new_rule_action.png)

- Klikamy `Apply`