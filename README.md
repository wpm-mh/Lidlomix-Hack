> [!WARNING]
> PL: Ten poradnik jest jedynie bazowany na repo [Monsieur-Cuisine-Connect-Hack](https://github.com/EliasKotlyar/Monsieur-Cuisine-Connect-Hack). W moim repo znajduje się przeprotowane przeze mnie TWRP\
> EN: This tutorial is based on original repo [Monsieur-Cuisine-Connect-Hack](https://github.com/EliasKotlyar/Monsieur-Cuisine-Connect-Hack). In my repo you can find TWRP reprotated by me


# Android na Monsieur Cuisine Connect
Poradnik modyfikacji urządzenia SilverCrest Monsieur Cuisine Connect Trend (Lidlomix)

![MCS](/assets/mcs.png)

## Wymagania
1. Urządzenie Monsieur Cuisine Connect
2. Komputer z systemem Windows
3. Kabel USB A - USB A
4. Mały torx 

### Windows 
* Potrzebny będzie program [SP-Flash Tool](https://spflashtool.com/)
* Do tego również przyda się narzędzie [ADB](https://xdaforums.com/t/tool-minimal-adb-and-fastboot-2-9-18.2317790/) 

## Instalacja 

1. Wyłącz urządzenie
2. U spodu urządzenia znajduje się zaślepka, należy ją odkręcić aby dostać się do portu USB 
![USB](/assets/usb.png)
3. Podłącz kabel USB do portu podpisanego **"Android USB"**. Podłączenie do drugiego portu może uszkodzić urządzenie. 
4. Uruchom SP-Flash tools. Użyj dołączonego w repo pliku scatter *l706_dfbh_v_695scatter.txt* aby przygotować program do działania z urządzeniem. 
5. Wykonaj **pełny** backup urządzenia. Można go wykonać w zakładce Readback dodając partycje na bazie adresów pamięci zawartych w pliku scatter. Więcej o tym możecie przeczytać [tutaj](https://www.hovatek.com/forum/thread-526.html).
![Backup](/assets/backup.png)

> [!IMPORTANT]
> Najważniejsze to zrobić backup partycji "boot" ze względu na to, że będziemy ją nadpisywać. \
>``Start Address: 0x0000000001d20000 lenght: 0x0000000001000000``

> [!CAUTION]
> Wyżej wymienione kroki są kluczowe dla całego procesu. Nie pomijaj ich!

6. Korzystając z zakładki Download w SP-Flash Tool, wgraj plik **recovery.img** jako partycję **boot**. 
![Flash boot](/assets/boot.png)
7. Kiedy proces wgrywania zakończy się, uruchom ponownie urządzenie. Po ponownym uruchomieniu automatycznie uruchomi się TWRP
![TWRP](/assets/twrp.png)
8. Uruchom ADB Shell 
* ``adb shell``
* Zamontuj partycję system ``mount / system /``
* Włącz ADB w systemie\
``echo "persist.service.adb.enable = 1" >> /system/build.prop``\
``echo "persist.service.debuggable = 1" >> /system/build.prop``\
``echo "persist.sys.usb.config = mtp, adb" >> /system/build.prop``
* Włącz przyciski ekranowe\
``echo "qemu.hw.mainkeys = 0" >> /system/build.prop``
9. Wgraj oryginalny **boot.img**, podobie jak w punkcie 6.
10. Uruchom ponownie urządzenie 
11. Zainstaluj launcher przez ADB. Można go pobrać z [tego linku](https://www.apkmirror.com/apk/cyanogenmod/trebuchet-2/trebuchet-2-8-1-0-16-release/trebuchet-8-1-0-16-android-apk-download/).
* Przy pomocy ADB wykonaj komendy:\
``adb install ścieżka_do_pliku_z_launcherem.apk``
12. Kiedy launcher będzie zainstalowany, wykonaj tę komendę, aby go włączyć:\
``adb shell at start -a android.intent.action.MAIN -c android.intent.category.HOME com.lineageport.trebuchet``
13. Gratulacje, twój Lidlomix jest wolny :D
