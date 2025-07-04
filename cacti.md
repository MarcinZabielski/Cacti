## Cel ćwiczenia 📖

Celem ćwiczenia jest instalacja i konfiguracja oprogramowania Cacti oraz monitorowanie zużycia zasobów komputera z systemem Windows w sieci lokalnej (LAN).

---

## 2. Instalacja Cacti 🌵

```bash
sudo apt-get install cacti
```
Podczas instalacji pojawią się 2 okna:
1. Web server - wybierz Apache2 i naciśnij Enter.
2. Database (dbconfig-common) - tu  wybierz "Yes" a następnie wpisz hasło, które należy zapamiętać.

Instalacja usługi SNMP:

```bash
sudo apt-get install snmpd
```

## 3. Uruchomienie Cacti 🚀
W przeglądarce internetowej należy wpisać: localhost/cacti

Login - admin

Hasło - hasło podane podczas instalacji

## 4. Monitorowanie komputera w sieci LAN z systemem Windows ⊞

### 4.1 Instalacja i konfiguracja SNMP na Windows 🌐
1. Uruchom komputer z systemem Windows.
2. Uruchom PowerShell jako i administrator i wpisz polecenie:
  ```PowerShell
  Add-WindowsCapability -Online -Name "SNMP.Client~~~~0.0.1.0"
  ```
4. Naciśnij kombinacje klawiszy Windows + R i wpisz services.msc.
5. Znajdź i kliknij prawym na "Usługa SNMP", następnie kliknij "Właściwości".
6. W zakładce "Ogólne" upewnij się, że usługa działa (Stan usługi).
7. W zakładce "Agent" w polu "Kontakt" i "Lokalizacja" wpisz "example" oraz zaznacz wszystkie checkboxy w sekcji Usługi.
8. W zakładce "Zabezpieczenia" dodaj nazwę społeczności "public" z prawem "Tylko do odczytu" i wybierz "Zaakceptuj pakiety SNMP od dowolnego hosta".

### 4.2 Dodanie komputera z Windowsem do Cacti ✅

1. Przejdź do komputera z Cacti.
2. Zakładka Create -> New Device.
3. Description:  Nazwa komputera (dowolna).
4. Hostname:  adres IP komputera.
5. Device Template:  Windows Device.
6. Kliknij przycisk "Create".

### 4.3 Monitorowanie komputera 🔎

1. Przejdź do Management -> Devices
2. Kliknij w utworzone wcześniej urządzenie, następnie Create Graphs for this Device (prawy górny róg strony).
3. W tabeli "Data Query [SNMP - Interface Statistics]" znajdź kartę sieciową urządzenia i zaznacz checkbox (wskazówka: w komórce "IP Address" powinien znajdować się adres ip komputera).
4. Na dole tabeli - "Select a Graph Type to Create" wybierz "In/Out Bits" a następnie kliknij przycisk Create.
5. Przejdź do Management -> Graphs i wybierz pozycję: Nazwa_Komputera - Traffic - Ethernet.
6. Na komputerze z Windows wygeneruj ruch sieciowy (np. odtwarzanie filmu na youtube).
7. Domyślny Polling Time w Cacti to 5 minut - należy chwilę poczekać aż dane pojawią się na wykresie.

<img width="639" alt="traffic" src="https://github.com/user-attachments/assets/4e3fc35b-da1e-4ae3-b418-5ecb72592af6" />

### 4.4 Podgląd wykresów 📈

Przejdź do zakładki "Graphs" znajdującej się na samej górze strony, następnie kliknij ikonę znajdującą się w prawym górnym rogu (Preview)

<img width="642" alt="preview" src="https://github.com/user-attachments/assets/4b33e342-c2b3-4b95-a961-fca3031e4025" />


   
