# Takács Balázs Levente

## Hogyan kezdj neki?

1. Jelentkezz be a GitHub szolgáltatásába a böngésződben és a VSCode szerkesztőben
2. A böngészőben forkold ezt a repository-t
3. A Settings > Pages oldalon a Source értékét állítsd gh-pages-re és mentsd el (Save)
4. Clone-ozd a saját(!) repodat a VSCode-ba
5. Írd át a Readme.md elején a [Név] részt a saját nevedre, majd commitolj és pusholj.
6. Telepítsd a függőségeket
```
  npm install
```
7. Indítsd el a fejlesztői szervert
```
  npm run serve
```
8. Indíts egy új VSCode vagy terminal ablakot.
9. Clone-ozd egy másik könyvtárba a backendet: https://github.com/hgabor/MuzeumBackend
10. Az ott leírtaknak megfelelően indítsd el, hogy elérhető legyen a kliens kódod számára.

## Hogyan dolgozz?

A főbb pontokon commitolj és pushold fel a változtatásokat. Ezt érdemes minél sűrűbben megtenni, hisz így adod majd be a feladatot.

## Hogyan fejezd be?

Add be a repod linkjét. Figyelj oda, hogy az utolsó commit idejét fogjuk nézni.

# Feladat

Készíts alkalmazást, ami a MuzeumBackend szobraineak (statues) adminisztrációjára alkalmas. Az alábbiak szerint:

1. Legyen egy lista, amiben megjelennek az adatok az adatbázisból letöltve. A listának legyen fejléce és a fejlécben a következő oszlopok: Személy, Magasság, Ár, Műveletek. Az oszlopokban a nekik megfelelő adatok jelenjenek meg(person, height, price), valamint a Művelet oszlopban legyen egy Törlés és Szerkesztés gomb. (2p)

2. A lista alján legyen egy új elem létrehozására alkalmas űrlap Mentés és Mégse gombbal. (2p)

3. A Törlés gomb megnyomására törlődjön az adott rekord az adatbázisból, valamint frissüljön a lista. (2p)

4. A szerkesztő űrlap segítségével lehesen felvenni új rekordot az adatbázisba. A lista frissüljön. (2p)

5. A Szerkesztés gomb megnyomására töltődjön be az adott rekord az adatbázisból az űrlapba, majd a Mentés gomb megnyomására tárolódjon el a változtatás az adatbázisban és törlődjön az űrlap. A Mégse gomb megnyomására törlődjön az űralp. Figyelj arra, hogy a mégse gomb megnyomása után az új rekord létrehozása működjön. (10p)

6. Figyelj oda, hogy izlésesen legyen formázva az oldal. (1p)

7. Figyelj oda, hogy értelmes commit üzenetek legyenek. Értelmesnek tekintjük a commit üzenetet, ha a "Miért?" kérdésre válaszol. (1p)

8. Amint látod a listázást, új létrehozást, módosítást jól elkülöníthető HTML és JavaScript kódokkal rendelkeznek. Készíts három komponenst. (+5p)
    1. Táblázat a rekordok listájával. Innen elérhető a szerkesztés, törlés és az új létrehozás.
    2. Űrlap, amivel új entitást lehet létrehozni
    3. Űrlap, amivel meglévő entitást lehet szerkeszteni.

9. Készíts alkalmazást, amivel a két entitás(Paintings, Statues) listázó komponense megjeleníthető. Használd a VueRouter-t ehhez. (+5p)

Figyellj oda, hogy először a sima pontos feladatoknak láss neki, a plusz pontok (pl. +1p) hagyd a végére.

Sima pontok értékelése:
*  0p -  9p: 1
* 10p - 12p: 2
* 13p - 14p: 3
* 15p - 16p: 4
* 17p - 20p: 5

Plusz pontok értékelése:

* (+5p - +10p): 5
