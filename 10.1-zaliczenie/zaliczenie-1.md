# Zadanie 1

Organizacja planuje ulepszyć działanie istniejącej sieci biurowej.

1. Zaprojektuj oraz udokumentuj konfigurację prototypu rozwiązania z wykorzystaniem oprogramowania ``VirtualBox`` lub podobnego. 

## Schemat

![zadanie 1](office.svg)

## Wymagania

W sieci pracują komputery biurowe oraz urządzenia siecowe współdzielące zasoby. Do tej pory organizacja borykała się z ręczna konfiguracją urządzeń oraz adresami IP które dla ludzi z poza kadry technicznej były niezrozumiałe. Postanowiono:

* Wykorzystać usługę DHCP do nadawania adresów w sposób automatyczny dla wszystkich stacji roboczych
* Serwer oraz durządzenia IP tj: drukarka muszą posiadać stałe adresy celem zminimalizowanai potrzeby rekonfiguracji ustawiań klientów
* Wprowadzić translację pomiędzy Adresami IP oraz nazwami domenowymi dla kluczowych zasobów
   - erp.mojaorganizacja.pl
   - drukarka.mojaorganizacja.pl
   - router.mojaorganizacja.pl
* Wszystkie urządzenia łączą się z siecią internet z wykorzystaniem bramy NAT
* Wykorzystać podsieć rozmiaru /22 pozwalającej zaadresować co najmniej 600 urządzeń

## Zawartość dokumentacji

 * Charakterystyka rozwiazania 
 
 Wykorzystano serwer DHCP do automatycznego przydzielania adresów z puli 192.168.100.100 - 192.168.103.254, drukarce ustawiono stały adres IP - 192.168.100.200. Serwer pełni również rolę routera o stałym adresie IP 192.168.100.1. Wprowadzono translacje adresów na nazwy domenowe dla drukarki, routera oraz erp przy użyciu serwera DNS, by były bardziej zrozumiałe dla przeciętnego użytkownika. Cała sieć 192.168.100.0/22 łączy się z siecią rozległą przy wykorzystaniu bramy NAT.
 
 * Adresy sieci IP
 
 ![zadanie 1](zdj0.png)
 
 * Oprogramowanie wykorzystane do realizacji poszczególnych wymagań
 
      * serwer DHCP - dhcpd
      * serwer DNS - dnsmasq
      * brama NAT - iptables
      
 * Kluczowa konfiguracja oprogramowania pozwalająca na odtworzenie stanu po reinstalacji środowiska
    1. Konfiguracja NAT z iptables
    
    ![zadanie 1](zdj1.png)
    
    2. Konfiguracja DHCP
    
    ![zadanie 1](zdj2.png)
    
    3. Konfiguracja DNS
    
    ![zadanie 1](zdj3.png)
    
    4. Konfiguracja interfejsów sieciowych
    
    SERWER
    
    ![zadanie 1](zdj4_1.png)
    
    DRUKARKA
    
    ![zadanie 1](zdj4_2.png)
    
    URZĄDZENIE 1
    
    ![zadanie 1](zdj4_3.png)
    
    URZĄDZENIE 2
    
    ![zadanie 1](zdj4_4.png)
    
    5. Efekty
    
    ![zadanie 1](zdj5_1.png)
    ![zadanie 1](zdj5_2.png)
    ![zadanie 1](zdj5_3.png)
    ![zadanie 1](zdj5_4.png)
    ![zadanie 1](zdj5_5.png)
    ![zadanie 1](zdj5_6.png)
    ![zadanie 1](zdj5_7.png)
    ![zadanie 1](zdj5_8.png)

