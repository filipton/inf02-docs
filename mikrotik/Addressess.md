# Reczne ustawianie adresow
Jak chcemy recznie ustawic adres danego portu / bridge'a / VLAN'u wchodzimy w zakladke `IP > Addressess`.

Z tego miejsca mozemy dodawac nowe adresy ip - pamietaj ze dodajesz **adres mikrotika** dla danego portu.

![](/images/addressess_new.png)

`Address` - **adres IP mikrotika** z maska po "/"
`Network` - adres sieci, po klikneicu Apply sam sie uzupelni
`Interface` - interfejs na ktorym na byc ten adres

**Jezeli w arkuszu bylo by napisane zeby nadac adres IP dla interfejsu powiazanego z VLAN X to wybieramy W `Interface` VLAN'a!**

## Uwagi
 - Jezeli inaczej konfigurujesz VLAN'y (tzn, ze dajesz VLAN'y nie do bridge tylko na interfejs - ja tak nie pokazuje) to ostatnie pogrobione zdanie sie ciebie nie aplikuje.