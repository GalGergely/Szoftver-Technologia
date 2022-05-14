# Build - ANT
Az alábbi módon build-elj:
(0. lépés: Ha nincs telepítve a java ant környezet, akkor le kell töltened.
    Linux: sudo apt install ant
    Windows: https://ant.apache.org/bindownload.cgi oldalról töltsd le a legújabb verziót, majd állítsd be a környezeti változóknál a bin mappát elérésnek)
1. Ellenőrizd, hogy az our-special-td mappában állsz-e.
2. Futtasd le a "ant run" parancsot a program indításához vagy a "ant compile" parancsot a file fordításához.

* A futtatható jar file a build/jar mappában fog megjelleni.

# Build - Maven
Az alábbi módon build-elj:
(0. lépés: Ha nincs telepítve a maven, akkor le kell töltened.
    Windows: https://maven.apache.org/download.cgi oldalról töltsd le a legújabb verziót, unzip apache-maven-3.8.5-bin.zip parancsot futtasd le ahova telepíteni szertenéd
    majd állítsd be a környezeti változóknál a bin mappát elérésnek, mvn -v kapcsolóval ellenőrizheted, hogy működik-e)
1. Ellenőrizd, hogy az our-special-td mappában állsz-e.
2. Futtasd le a "mvn compile" parancsot a program fordításához vagy a "mvn install" parancsot a JAR file generálásához.

* A futtatható jar file a target mappában fog megjelleni .

# Our Special TD

# Alap koncepció
Az alap játék egy Tower Defense multiplayer játék, amiben kettő kastély van és a játékosok célja, hogy egymás kastélyát elfoglalják/lerombolják. Az nyer, aki hamarabb lerombolja a másik kastélyát. A játék lehet döntetlen is, ha mindkét játékos ugyan abban a körben rombolja le a másik kastélyát. A játéknak van UI-a (User Interface). 

# Körök
Egy kör kettő részből áll, a kör egyik felében védekeznek/építenek a játékosok, a második felében támadnak egymásra. 

# Játék terület
A játékterület egy N x M -es pálya, amin valahol elhelyezkedik a két játékos kastélya, amit védeniük kell. Továbbá vannak a pályán terepi akadályok, mint például hegyek, folyók, tavak stb., amelyek nehezítik a játokosok feladatát, ugyanis a támadó egységek nem tudnak rajtuk átmenni. Ezek a terepi akadályok nem kerülhetnek a kastélyok köré.

# Arany – Fizető eszköz
Az arany a játékban a fizetésre felhasznált eszköz. Ezzel lehet venni védekezésre tornyokat és támadásra egységeket. Egy játékos többféleképpen tud aranyat szerezni. Minden kör elején kap mindkettő játékos egy fix összeget, minél több egysége van lent, illetve minél több egységet pusztít el, annál többet kap.

# Tornyok
A tornyok a játékosok védekezési eszközei. Egy tornyot aranyért tud venni minden játékos és nem zárhatja el vele a kastélyhoz vezető utat. (Minimum) 3 féle tornyot tudnak lerakni a játékosok. Minden toronynak más sebzési sebessége van, más az is, hogy mennyit tud sebezni és hogy milyen messze lát el egy torony.

# Támadási egységek
A támadási egységekkel tudnak támadni a játékosok. Szintén aranyért tudnak venni ilyen egységeket. Az egységek a pályán automatikusan mozog az ellenséges kastély felé, a lehető legrövidebb úton és a lerakott tornyokat nem támadják meg. Egyszerre egy egység állhat egy pálya helyen, de állhat egy ellenséges egység mellé. Ha rákattintunk bármely egységre, látszódik, hogy mennyin vannak az adott egységbe. Ha kastély mezőre lép egy egység, akkor megsebzi a kastélyt és a kastély is megsebzi ez egységet, egyszerre.
 
# Extrák
•	A tornyokat lehet fejleszteni
•	A tornyokat lehet lebontani, ekkor kicsit kevesebb aranyat kap vissza a játékos, mint amennyiért építette a tornyot.
•	Mentési lehetőség
•	Navigálható egységek – Ki lehet jelölni, hogy egy adott egység merre menjen a pályán
•	Térképszerkesztő – A felhasználók tudnak saját térképet összeállítani és azon játszani, ezt el is lehet menteni.
•	Barakkok
o	Itt is megjelenhetnek új egységek
o	1 – 5 körig nincsenek barakkok
o	Fokozatosan nő a számuk a körök haladtával
o	Nem kerülhet olyan helyre, ami elzárja a kastélyhoz vezető utat
•	Speciális egységek:
o	Hegymászók – Át tud menni a pálya „hegy” elemein.
o	Úszók – Át tud úszni a pálya „folyó” és „tó” elemein.
o	Harcosok – Ha olyan mezőre lép, ahol ellenség van, akkor megtámadja azt.
o	Rombolók – Meg tud sebezni/Le tud rombolni tornyokat.
