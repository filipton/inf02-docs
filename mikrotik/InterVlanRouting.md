# InterVlan Routing
**Domyslnie routing intervlan'owy jest wlaczony!** - oznacza to, ze VLAN'y z osobnymi adresami sieci moga sie z soba komunikowac!

## Wylaczanie routingu miedzy VLANami
- Wchodzimy do zakladki `IP > Firewall`
- W podzakladce `Filter Rules` dodajemy nowy filtr
  - `Chain` - dajemy na `forward`
  - `Src. Address` - adres sieci jednego vlan'a z maska
  - `Dst. Address` - adres sieci drugiego vlan'a z maska
  - W zakladce `Action` wybieramy `Action` na `drop`
  - ![](/images/intervlan_routing_firewall_general.png)
  - ![](/images/intervlan_routing_firewall_action.png)

**TAK DZIALA TO W DWIE STRONY JAK COS**