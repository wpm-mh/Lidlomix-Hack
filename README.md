> [!WARNING]
> PL: Ten poradnik jest jedynie bazowany na repo [Monsieur-Cuisine-Connect-Hack](https://github.com/EliasKotlyar/Monsieur-Cuisine-Connect-Hack)\
> EN: This tutorial is based on original repo [Monsieur-Cuisine-Connect-Hack](https://github.com/EliasKotlyar/Monsieur-Cuisine-Connect-Hack)


> 

# Android na Monsieur Cuisine Connect
Poradnik modyfikacji urządzenia SilverCrest Monsieur Cuisine Connect Trend (Lidlomix)

![MCS](/mcs.png)

## Wymagania
1. Urządzenie Monsieur Cuisine Connect
2. Komputer z systemem Windows
3. Kabel USB A - USB A
4. Mały torx 

### Windows 
Potrzebny będzie program [SP-Flash Tools](https://spflashtool.com/)

Do tego również przyda się narzędzie [ADB](https://xdaforums.com/t/tool-minimal-adb-and-fastboot-2-9-18.2317790/) 

## Instalacja 

1. Wyłącz urządzenie
2. U spodu urządzenia znajduje się zaślepka, należy ją odkręcić aby dostać się do portu USB 
3. Podłącz kabel USB do portu podpisanego **"Android USB"**. Podłączenie do drugiego portu może uszkodzić urządzenie. 
4. Uruchom SP-Flash tools. Użyj dołączonego w repo pliku scatter *l706_dfbh_v_695scatter.txt* aby przygotować program do działania z urządzeniem. 
5. Wykonaj **pełny** backup urządzenia. Można go wykonać w zakładce Readback dodając partycje na bazie adresów pamięci zawartych w pliku scatter. 

> Najważniejszy 