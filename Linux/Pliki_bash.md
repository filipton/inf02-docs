# Pliki bash

Tworzymy plik z rozszerzeniem .sh, np: `Plik_wsadowy.sh`

```bash
#!/bin/bash

jakies
komendy
tutaj
```

`echo cos_do_wyswietlenia` wyswietla cos do konsoli

## Zmienne
```bash
X="jakas_zmienna"
echo $X # wywolanie zmiennej
read X # wprowadzanie wartosci z klawiatury do zmiennej X
```

## IF
```bash
if <warunek> ; then
  polecenia1
else
  polecenia2
fi
```

Przyklad:
```bash
#!/bin/bash
if [ -e ~/.bashrc ]
then
  echo "Masz plik .bashrc"
else
  echo "Nie masz pliku .bashrc"
fi
```
![image](/images/bash_operators.png)

## For loop
```bash
#!/bin/bash
for i in 1 2 3 4 5
do
  echo "Weclome $i times"
done
```

## While loop
```bash
while [ condition ]
do
  command1
  command2
  ...
done
```

Przyklad:
```bash
#!/bin/bash
x=1
while [ $x -le 5 ]
do
  echo "Welcome $x times"
  x=$(( $x + 1 ))
done
```
