## Cel ćwiczenia 📖

Celem ćwiczenia jest instalacja i konfiguracja oprogramowania Cacti służącego do monitorowania sieci komputerowych.

---

## 2. Instalacja Cacti 🌵

```bash
sudo apt-get install cacti
```
Podczas instalacji pojawią się 2 okna:
1. Web server - wybierz Apache2 i naciśnij Enter.
2. Database (dbconfig-common) - tu  wybierz "Yes" a następnie wpisz hasło, które należy zapamiętać.

Instalacja agenta SNMP:

```bash
sudo apt-get install snmpd
```

## 3. Uruchomienie Cacti 🚀
W przeglądarce internetowej należy wpisać: localhost/cacti

Login - admin

Hasło - hasło podane podczas instalacji

## 4. Monitorowanie komputera w sieci LAN z systemem Windows

### Instalacja i konfiguracja SNMP na Windows
1. Uruchom komputer z systemem Windows.
2. Uruchom PowerShell jako i administrator i wpisz komendę:
  ```PowerShell
  Add-WindowsCapability -Online -Name "SNMP.Client~~~~0.0.1.0"
  ```
4. Naciśnij kombinacje klawiszy Windows + R i wpisz services.msc.
5. Znajdź i kliknij prawym na "Usługa SNMP", następnie kliknij "Właściwości".
6. W zakładce "Ogólne" upewnij się, że usługa działa (Stan usługi).
7. W zakładce "Agent" wpisz "example" w polu "Kontakt" i "Lokalizacja" oraz zaznacz wszystkie checkboxy w sekcji Usługi.
8. W zakładce "Zabezpieczenia" dodaj społeczność "public" z prawem "Tylko do odczytu" i wybierz "Zaakceptuj pakiety SNMP od dowolnego hosta".

### Dodanie i monitorowanie komputera z Windowsem do cacti

1. Przejdź do Cacti: Zakładka Create -> New Device
   Description:  Nazwa komputera (dowolna)
   Hostname:  adres IP komputera
   Device Template:  Windows Device
   Kliknij przycisk "Create"
   
2. Przejdź do Management -> Devices
   Kliknij w utworzone wcześniej urządzenie, następnie Create Graphs for this Device
   W tabeli "Data Query [SNMP - Interface Statistics] znajdź kartę sieciową urządzenia (w komórce IP Address - adres ip komputera) i zaznacz checkbox
Na dole tabeli
Select a Graph Type to Create In/Out Bits a następnie Create
Przejdź do  Management -> Graphs i wybierz Nazwa_komputera - Traffic - Ethernet
Na komputerze z Windows wygeneruj ruch sieciowy (np. odtwarzanie filmu na youtube)
