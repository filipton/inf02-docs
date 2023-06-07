`fdisk` do dyskow mbr

`gdisk` do dyskow gpt

`-l` wyswietla dyski i partycje (taki sam do `gdisk` i `fdisk`)

<br>

`fdisk nazwa_urzadzenia` odpala konfiguracje wskazanego uzadzenia

`parted -l` wyswietla info o partycjach

`mkfs.system_plikow sciezka_do_partycji` zmiana systemu plikow partycji
<br>
mkfs.btrfs   mkfs.cramfs  mkfs.ext2	mkfs.ext3	mkfs.ext4	mkfs.minix   mkfs.xfs 
<br>
jak nie pamietasz rodzajow partycji to piszesz mkfs. i 2 razy klikasz tab

`mount sciezka_do_partycji sciezka_do_pliku` montowanie partycji
