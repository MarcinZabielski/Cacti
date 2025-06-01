## Cel ćwiczenia 📖

Celem ćwiczenia jest instalacja i konfiguracja oprogramowania Cacti służącego do monitorowania sieci komputerowych.

---

## 2. Instalacja Cacti 🌵

```bash
sudo apt-get install cacti
```
Podczas instalacji pojawią się 2 okna:
1. Web server - wybieramy Apache2 i OK.
2. Baza danych - tu  wybieramy "Yes" a następnie wpisujemy hasło, które musimy zapamiętać.

## 3. Uruchomienie Cacti 🚀
W przeglądarce internetowej należy wpisać: https://localhost/cacti

Login - admin

Hasło - Hasło podane podczas instalacji

## 4. Monitorowanie komputera w sieci LAN z systemem Windows

Instalacja i konfiguracja SNMP na Windows
1. Uruchom komputer z systemem Windows.
2. Uruchom PowerShell jako i administrator i wpisz komendę:
  ```PowerShell
  Add-WindowsCapability -Online -Name "SNMP.Client~~~~0.0.1.0"
  ```
4. Naciśnij kombinacje klawiszy Windows + R i wpisz services.msc.
5. Znajdź i kliknij prawym na "Usługa SNMP", następnie kliknij "Właściwości".
6. W zakładce "Ogólne upewnij się, że usługa działa (Stan usługi).
7. W zakładce "Agent" "example" w polu "Kontakt" i "Lokalizacja" oraz zaznacz wszystkie checkboxy w sekcji Usługi.
8. W zakładce "Zabezpieczenia" dodaj społeczność "public" z prawem "Tylko do odczytu" i wybierz "Zaakceptuj pakiety SNMP od dowolnego hosta".



## 6. Ćwiczenie 3 - Stworzenie własnego prostego grafu (ping 🏓)
