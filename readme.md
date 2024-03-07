# Napotkane problemy

Początkowo instalacja wykonywana była na Ubuntu 22.04, które domyślnie ma Python w wersji 3.10.
Ryu jest już w stanie depracated i taka wersja była dla niego zbyt duża. Instalacje powtórzono na Ubuntu 20.04, na którym domyślny Python to już 3.8.10. Instalacja przebiegła bez problemu.

# Wykonane czynności
## Instalacja ryu
Instalacja wg https://github.com/faucetsdn/ryu?tab=readme-ov-file w opcji "z kodu źródłowego". 
Test instalacji za pomocą komedny:
```sh
ryu-manager --version
```
oraz napisanie prostej apki
```python
from ryu.base import app_manager

class L2Switch(app_manager.RyuApp):
    def __init__(self, *args, **kwargs):
        super(L2Switch, self).__init__(*args, **kwargs)
```
I uruchomienie jej:
```sh
ryu-manager yourapp.py
```
## Instalacja mininet
```sh
sudo apt update
sudo apt upgrade -y
sudo apt install mininet -y
sudo mn --test pingall

