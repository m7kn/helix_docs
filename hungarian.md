# Helix Editor Dokumentáció

## Bevezetés

A Helix egy modern, modális szövegszerkesztő. A modális szerkesztés azt jelenti, hogy különböző módokban dolgozhatunk a szöveggel. A két fő mód:

- Normál mód: A billentyűk nem karaktereket írnak, hanem parancsokat hajtanak végre
- Insert mód: Karakterek beírására szolgál

## Alapvető mozgás

A kurzor mozgatása a Normál módban:

- `h` - balra 
- `j` - le
- `k` - fel 
- `l` - jobbra

## Kilépés

- `:q` vagy `:quit` - kilépés (csak ha nincs mentetlen változtatás)
- `:q!` vagy `:quit!` - kilépés mentetlen változtatások eldobásával 
- `:wq` vagy `:write-quit` - mentés és kilépés

## Törlés és beszúrás

- `d` - karakter törlése a kurzor alatt
- `i` - Insert módba lépés a kurzor előtt
- `a` - Insert módba lépés a kurzor után (append)
- `I` - Insert módba lépés a sor elején
- `A` - Insert módba lépés a sor végén
- `o` - új sor beszúrása alulra és Insert módba lépés
- `O` - új sor beszúrása felülre és Insert módba lépés

## Mentés

- `:w` vagy `:write` - aktuális fájl mentése
- Opcionálisan megadható fájlnév/útvonal is

## Mozgás és kijelölés

- `w` - előre a következő szó elejéig
- `e` - előre az aktuális szó végéig  
- `b` - hátra az aktuális szó elejéig
- `W`, `E`, `B` - ugyanaz mint a kisbetűs változatok, de csak whitespace-nél áll meg

## Változtatás parancsok

- `c` - kijelölt szöveg törlése és Insert módba lépés
- `d` - kijelölt szöveg törlése
- Szám + parancs: parancs többszöri végrehajtása (pl. `2w`)

## Kijelölés mód 

- `v` - kijelölés mód be/ki
- `x` - teljes sor kijelölése
- `;` - kijelölés összecsukása kurzorrá

## Másolás és beillesztés

- `y` - kijelölt szöveg másolása (yank)
- `p` - beillesztés a kurzor után
- `P` - beillesztés a kurzor elé
- `Space + y/p` - rendszer vágólapjával való műveletek

## Keresés

- `/` - keresés előre
- `?` - keresés hátra
- `n` - következő találat
- `N` - előző találat
- Reguláris kifejezéseket is támogat

## Többszörös kurzor

- `C` - kurzor duplikálása következő megfelelő sorra
- `Alt-C` - kurzor duplikálása előző megfelelő sorra
- `s` - kijelölt szövegben az egyezések kijelölése
- `&` - kijelölések igazítása

## Egyéb funkciók

- `u` - visszavonás
- `U` - mégis 
- `.` - utolsó beszúrás ismétlése
- `~` - kisbetű/nagybetű váltás
- `` ` `` - kisbetűsítés
- `Alt-`` ` ``- nagybetűsítés
- `Ctrl-c` - sor kommentelése/komment eltávolítása

## Ablakok kezelése

- `Ctrl-w nv` - új függőleges split
- `Ctrl-w ns` - új vízszintes split
- `Ctrl-w h/j/k/l` - mozgás az ablakok között
- `Ctrl-w q` - aktuális ablak bezárása
- `Ctrl-w o` - minden más ablak bezárása
- `:vs` / `:hs` - split megnyitása fájlnévvel

## Match mód

A `m` billentyűvel aktiválható match mód különböző zárójelek és más páros karakterek kezelésére szolgál:

- `mm` - ugrás a páros karakterhez
- `mi(` - zárójelek közötti tartalom kijelölése
- `ma(` - zárójelek és tartalmuk kijelölése
- `ms(` - kijelölt szöveg körülvétele zárójelekkel
- `md(` - körülvevő zárójelek törlése
- `mr([` - zárójelek cseréje másik típusra

A zárójelek helyett használható más páros karakter is, pl. `{}`, `[]`, `""`, `''`.

## Regiszterek használata

A regiszterek karakterrel azonosított tárolók, amelyek különböző célokat szolgálhatnak:
- Szöveg másolása/kivágása 
- Keresési kifejezések tárolása
- Makrók tárolása

- `"<ch>` - regiszter kiválasztása (pl. `"a`)
- A kiválasztott regiszterbe menthetünk a `y` paranccsal
- A kiválasztott regiszterből beilleszthetünk a `p` vagy `P` paranccsal

## Makrók

A makrók olyan parancssorozatok, amiket később újra végrehajthatunk:

- `Q` - makró rögzítésének kezdése (alapértelmezetten a `@` regiszterbe)
- `Q` - makró rögzítésének befejezése 
- `q` - makró lejátszása a `@` regiszterből
- `"<ch>Q` - makró rögzítése adott regiszterbe
- `"<ch>q` - makró lejátszása adott regiszterből

## Keresés és kijelölés

- `*` - kurzor alatti szó keresése
- `v` módban `n`/`N` - új kijelölés hozzáadása a következő/előző találatra
- `Ctrl-s` - pozíció mentése a jumplistbe
- `Ctrl-i`/`Ctrl-o` - előre/hátra lépés a jumplistben
- `gw` - két karakteres címkék megjelenítése gyors navigációhoz

## Kijelölések kezelése

- `)` / `(` - elsődleges kijelölés mozgatása előre/hátra 
- `Alt-,` - elsődleges kijelölés eltávolítása
- `Alt-)` / `Alt-(` - kijelölések tartalmának cseréje
- `S` - kijelölések felosztása regex minta alapján

## Sorok manipulálása

- `J` - kijelölt sorok összefűzése
- `>` / `<` - sor behúzása/behúzás csökkentése
- `Ctrl-a` / `Ctrl-x` - szám növelése/csökkentése

## Haladó ablakkezelés

- `Ctrl-w t` - ablakelrendezés transzponálása
- `Ctrl-w H/J/K/L` - ablak áthelyezése adott irányba
- `Space f` - fájl kereső megnyitása
  - `Ctrl-v` - kiválasztott fájl megnyitása függőleges splitben
  - `Ctrl-s` - kiválasztott fájl megnyitása vízszintes splitben

## Tippek és trükkök

1. A legtöbb parancs kombinálható:
   - Szám + parancs: többszöri végrehajtás
   - Regiszter + parancs: művelet adott regiszterrel
   - Mozgás + művelet: művelet a mozgással kijelölt szövegen

2. Hatékony szerkesztési stratégiák:
   - Használjuk a `.` parancsot ismétlődő változtatásokhoz
   - Többszörös kurzor a párhuzamos szerkesztéshez
   - Match mód a strukturált szöveg kezeléséhez
   - Makrók komplex műveletsorozatokhoz

3. A keresés és csere művelet:
   - Kijelölés az érintett területen
   - `s` parancs a mintával egyező részek kijelöléséhez
   - `c` parancs a változtatás végrehajtásához

4. Ablakkezelési minták:
   - Vertikális split kód és dokumentáció párhuzamos szerkesztéséhez
   - Horizontális split a különböző fájlrészek összehasonlításához
   - Több ablak használata referencia anyagok megtekintéséhez

## Konfigurálás

A Helix konfigurálható a következő fájlokon keresztül:
- `~/.config/helix/config.toml` - általános beállítások
- `~/.config/helix/languages.toml` - nyelv-specifikus beállítások

A részletes konfigurációs lehetőségekért érdemes megtekinteni a hivatalos dokumentációt.

## Összefoglalás

A Helix egy hatékony, modern szövegszerkesztő, amely:
- Modális szerkesztést használ a hatékonyság érdekében
- Gazdag parancs- és funkciókezelést biztosít
- Támogatja a többszörös kurzort és kijelölést
- Rugalmas ablakkezelést tesz lehetővé
- Konfigurálható és bővíthető

A hatékony használathoz érdemes:
1. Megtanulni az alapvető mozgási és szerkesztési parancsokat
2. Fokozatosan elsajátítani a haladóbb funkciókat
3. Kialakítani a saját munkafolyamatokhoz illeszkedő konfigurációt
4. Rendszeresen gyakorolni az új parancsok használatát
