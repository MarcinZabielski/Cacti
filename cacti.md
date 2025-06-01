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

## 4. Ćwiczenie 1 - Monitorowanie komputera lokalnego (Linux 🐧)

## 5. Ćwiczenie 2 - Monitorowanie komputera w sieci LAN (Windows ⊞)

Instalacja i konfiguracja SNMP na Windows
1. Uruchom komputer z systemem Windows.
2. Uruchom PowerShell jako i administrator i wpisz komendę:
  ```PowerShell
  Add-WindowsCapability -Online -Name "SNMP.Client~~~~0.0.1.0"
  ```
4. Naciśnij kombinacje klawiszy Windows + R i wpisz services.msc
5. Znajdź "Usługa SNMP", kliknij prawym -> Właściwości -> Agent
6. Wpisz Kontakt i Lokalizacja oraz zaznacz wszystkie checkboxy w sekcji Usługi

## 6. Ćwiczenie 3 - Stworzenie własnego prostego grafu (ping 🏓)
