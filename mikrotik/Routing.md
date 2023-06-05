# Routing - Trasa Statyczna
Jezeli w arkuszu mamy podane ustawienie routingu (statycznego) dla danej sieci i dla danego adresu bramu to musimy skonfigurowac to w taki sposob.

- Wchodzimy w zakladke `IP > Routes`
- Dodajemy nowy
  - `Dst. Address` - adres sieci docelowej
  - `Gateway` - adres bramy (tutaj tez mozna wpisac nazwe portu/bridge'a itp)
- ![](/images/routing_new_route.png)

## Co oznacza ta konfiguracja?
Jezeli w `Dst. Address` mamy `192.168.1.0/24` a w `Gateway` mamy `192.168.0.10` oznacza to ze chcac sie laczyc do sieci wskazanej powyzej laczymy sie poprzez adres bramy `192.168.0.10`.

## Routing domyslny
W `Dst. Address` dajemy **0.0.0.0/0** a w `Gateway` adres wskazany przez arkusz.

## Przyklad z polecenia
```
ustawiona trasa statyczna dla podsieci 192.168.1.0/24 z dostępem przez bramę 192.168.0.15
```
