# Quick Set w mikrotik
Ta opcja nam sie jedynie sprawdzi jezeli zadanie w arkuszu bedzie bardzo proste np. bez vlanow. 

Po wejsciu w zakladke `Quick Set` wyswietli nam sie takie okienko.

![](/images/quickset_window.png)
![](/images/quickset_options.png)

`WISP AP` - pozwala na konfiguracji sieci wifi tylko w jeden czestotliwosci

`Home AP Dual` - rozni sie tym, ze mozna wybrac dwie czestotliwosci WIFI.

## Konfiguracja WIFI
![](/images/quickset_wifi_conf.png)

Jakby wydaje mi sie ze tutaj nie ma czego tlumaczyc, wszystko jest raczej jasne.

## Konfiguracja WAN/LAN
### Internet (WAN)
`Port` - port jaki chcemy miec WAN (idk czy na mikrotikach w szkole jest ta opcja)

`Address Acquisition` - wybieramy czy chcemy miec statyczny adres IP czy dynamiczny (przydzielany z serwera DHCP)

`IP Address` - adres ip mikrotika w sieci WAN

`Netmask` - maska adresu mikrotika w sieci WAN

`Gateway` - adres bramy w sieci WAN

`MAC Address` - adres mac portu WAN

`Firewall Router` - zaznaczone doda to kilka regul do firewalla odnosnie jego zabezpieczenia (nie potrzebne na egzaminie)

### Local Network (LAN)
`IP Address` - adres ip mikrotika w sieci LAN

`Netmask` - maska adresu mikrotika w sieci LAN

`Bridge All LAN Ports` - automatycznie utworzy bridge na wszystkich portach LAN

`DHCP Server` - po zaznaczeniu bedziemy mogli skonfigurowac prosto server DHCP

`NAT` - doda regule NAT (raczej kazdy powinien wiedziec co to NAT XD), po jej zaznaczeniu bedziemy mogli robic np **[przekierowania](/mikrotik/Redirections.md)**.

## Uwagi
 - Czasem klikajac przycisk Apply niektore opcje zmieniaja sie i je trzeba na nowo ustawic