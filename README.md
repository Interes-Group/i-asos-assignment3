# I-ASOS Zadanie 3 - SOAP klient a dokončenie servera
![License MIT](https://img.shields.io/badge/License-MIT-green)
![Java 1.8](https://img.shields.io/badge/Java-1.8-blue)

Cieľom zadania je overiť znalosti používania webových služieb typu SOAP a ich definovania pomocou WSDL.

## 1. Perzistentná vrstva
Pomocou jazyka Java a frameworku Spring rozšírte druhé zadanie o perzistentnú vrstvu. 
Doménové objekty zo zadania 2 (používateľ a zmluva) ukladajte do embedovanej databázy H2 ([pozri spring-course-data](https://github.com/Interes-Group/spring-course-data/tree/h2)). 
Aplikácia musí dodržiavať štruktúru `Controller <--> Service <--> Repository`.

Jednotlivé podtriedy zmluvy môžete ukladať jedným z nasledujúcich spôsobov:
 - každý typ zmluvy má vlastnú tabuľku a tak aj vlastnú triedu repozitáru
 - všetky zmluvy zdieľajú jednu tabuľku a tak je jedna trieda repozitáru pre ich spoločného rodiča (trieda Zmluva).
   [Baeldung - An inheritance hierarchy to one table](https://www.baeldung.com/hibernate-tips-how-to-map-an-inheritance-hierarchy-to-one-table)

Vzťah medzi používateľom a zmluvou nemusí byť zachytený na perzistentnej vrstve (nemusíte používať cudzie kľúče). Referenciu na používateľa v zmluve môžete riešiť pomocou hodnoty ID, rovnako aj referenciu zmlúv v triede používateľa. ID perzistovaných tried nech je automaticky generované databázou. 

## 2. SOAP klient
Pomocou jazyka Java a frameworku Spring rozšírte druhé zadanie. K SOAP webovým službám zo zadania 2 vytvorte klientskú aplikáciu z implementovaných WSDL schém. V klientskej aplikácii pomocou volaní webových služieb implementujte nasledovné úkony:
Vytvorenie aspoň dvoch používateľov.
Vytvorenie každému používateľovi aspoň jednu zmluvu podľa vlastného výberu, avšak typy zmlúv musia byť rozdielne.
Vypísanie všetkých používateľov uložených v systéme aj spolu s ich zmluvami. Zmluvy musia byť celé objekty, nie len ID hodnoty.

## Hodnotenie
**Zadanie je hodnotené 20 bodmi. Zadanie je nutné odovzdať do 13.12.2020 23:59!**

Zadanie si naklonujte z repozitára zadania. Svoje vypracovanie nahrajte do vášho repozitára pre toto zadanie pomocou programu Git (git commit + git push). Vypracovanie môžete “pusho-vať” priebežne.

Hodnotiť sa bude iba master branch. Kvôli testom a zrýchleniu opravovania je nutné dodržať cesty (xsd, wsdl, generované classy) a štruktúru projektu, ako je stanovené v zadaní! Iba body získané z poslednej verzie vypracovania (t.j. z posledného commitu) do termínu odovzdania sa berú do úvahy. Okrem testov sa bude kód kontrolovať aj ručne.

Projekt musí dodržiavať zaužívané konvencie:
 - XSD schémy v priečinku `src/main/resources/xsd`
 - WSDL schémy v priečinku `src/main/resources/wsdl`
 - Vygenerované triedy pomocou `jaxws-maven-plugin` v priečinku `target/generated-sources/main`

Manuálne hodnotenie bude brať do úvahy správne použitie XSD schémy a WSDL. Správne použitie frameworku Spring. Správne dedenie, prepoužitie kódu, použité typy elementov, vhodné pomenovanie elementov a služieb.
