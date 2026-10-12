# Animace splněných kroků na HP

Prototyp a specifikace animací, které se přehrají na HP, když uživatel splní krok denní cesty.
Jeden soubor bez závislostí: otevři [`index.html`](index.html) v prohlížeči.

V panelu vedle telefonu je pro každý krok:
- přehrávání v rychlosti 1×, 0,5× a 0,25×;
- časová osa s pružinami, křivkami, haptikou a zvukem;
- popis jednotlivých okamžiků s milisekundami.

Přepínačem jde zapnout zvuk a režim s omezeným pohybem. Klepnutí na telefon animaci dokončí, stejně jako v aplikaci.

## Zdroj

Figma → `Mobile-app-design`, sekce [Home](https://www.figma.com/design/phDRRozgW9HSte85GD2alO/Mobile-app-design?node-id=13860-84010):

- stavy Domů 0/3, 1/3, 2/3 a 3/3;
- Domů – nová gramatická karta;
- otevřené detaily uzlů.

Rozměry, barvy, ikony a tvar cest jsou z Figmy. Pohyb je návrh, ve Figmě není.

## Jak jsem zadání četl

Cesta má tři povinné kroky (počítadlo 0/3 → 3/3). Čtvrtý uzel Procvičování na cestu napojený není a **nejde dokončit**: po 3/3 se jen odkryje a zůstane aktivní (rozhodnutí 12. 10.).

| Krok | Co se mění | Síla oslavy |
|---|---|---|
| 1 · Lekce | 0/3 → 1/3 | malá: ukázat, kam dál |
| 2 · Slova z lekce | 1/3 → 2/3 + nová gramatická karta | malá + odměna obsahem |
| 3 · Denní test | 2/3 → 3/3, prodloužená série | **vrchol dne** |
| Procvičování | po 3/3 se odkryje (žuchne), splnit nejde | hravé odkrytí, žádný stav „hotovo“ |

Vrchol je u 3/3: tam se den uzavírá a prodlužuje se série, a ta uživatele přivede zítra.

## Varianty intenzity

V2 působila jako „moc“, proto jsou v prototypu tři varianty se stejnou kostrou. Stav se ve všech mění stejně, liší se jen „koření“. Přepínají se v panelu.

| | A · Klidná | B · Vyvážená (doporučená) | C · Výrazná (milníky) |
|---|---|---|---|
| Uzel | výplň od středu, bez přestřelení | zmáčknutí 93 %, na dně zezelená v jednom snímku, výskok 103 %, ikona dobíhá | 88 % → 106 %, výplň od středu, ikona 82 → 114 %, záblesk |
| Další uzel | prolnutí, pak dýchá | nádech 103,5 %, svatozář, pak dýchá | nádech 107 %, tekoucí čárky, pak dýchá |
| 3/3 kroužek | uzavře se a zezelená | zrychlí, zezelená, tah 6 px, pumpne 106 %, 1 záblesk | tah 7 px, pumpne 110 %, 3 záblesky, 8 konfet |
| Série | prolnutí | krátké smáčknutí a protažení (112 %) | plamínek doletí + plamen podle Duolinga (142 %) |
| Pátek v liště | prolnutí | plamen tiše naskočí | nádech a překlopení |
| Odkrytí Procvičování | prolnutí | třes, výskok, otočení, žuchnutí | totéž, výš a víc prachu |

Čísla spočítaná z časových os HP (výchozí nastavení: otočení mince, karta série po dokončení cesty; krok 3 = obě části HP bez karty; den 1–3 celkem):

| | A | B | C |
|---|---|---|---|
| Krok 3: délka na HP | 2,6 s | 4,1 s | 4,6 s |
| Krok 3: zastávky oka | 3 | 4 | 5 |
| Krok 3: dráha oka | 421 px | 1 074 px | 1 282 px |
| Krok 3: částice | 0 | 16 | 56 |
| Největší deformace | 0 | ± 30 % (žuchnutí) | ± 30 % |
| Den 1–3: čas · haptika · částice | 5,5 s · 4 · 0 | 7,5 s · 4 · 16 | 8,4 s · 7 · 73 |

Krok 3 je delší než dřív, protože obsahuje i přistání plamene z karty série a odkrytí Procvičování. Deformace 30 % je žuchnutí Procvičování (jednou denně). Aktuální čísla pro každý krok ukazuje tabulka „Porovnání variant“ v prototypu.

### Proč C působí jako „moc“
- **Problém není síla pohybu, ale počet míst.** Duolingo dává každý beat na vlastní obrazovku, kde oko stojí. Na HP se stejné množství rozprskne a oko skáče mezi uzlem, kroužkem, hlavičkou a lištou dnů.
- **Koření na každém kroku.** Záblesky, kosočtverečky a tekoucí čárky se opakují každý den.
- **Amplitudy pro jednorázový moment.** Plamen 142 % a číslo 116 % patří k milníku, ne k běžnému dni.

### Pravidla dávkování
1. **Jedno ohnisko na krok.** Ostatní změny jen tiše dosednou. Material 3 má sadu standard pro opakované interakce a expressive pro hrdinské momenty.
2. **Oko po cestě.** Ohniska blízko sebe a ve směru čtení, vzdálené změny tiše.
3. **Odměnou je změna stavu.** Částice jsou koření: nejvýš jedno na krok a ne na každém kroku.
4. **Amplituda podle četnosti.** Denně přestřelení 3–6 % a deformace do 15 %, na milníku i 40 %.
5. **Rozpočet času.** Opakovaný krok kolem 1 s, uzavření dne do 2 s.
6. **Haptika 1–2 impulzy na krok,** „úspěch“ jednou denně.
7. **Novost vyprchává.** Plnou show šetřit na milníky, jako to dělá Duolingo se sérií.
8. **Test stého dne:** bude to bavit i po stém?

### Co na to Duolingo samo
- Pět zásad jejich motion týmu ([Duolingo Design Studio](https://www.linkedin.com/posts/samiakhalaf_duolingocreator-duolingodesign-designstudio-activity-7486054269264203776-XugE)). Dvě z nich jsou o střídmosti: pohyb má odpovídat účelu bez ozdob pro ozdoby a má jít rovnou k věci, aby odměna nezapadla pod efekty.
- **Stav se mění v jednom snímku,** jeden snímek po nejhlubším smáčknutí, bez prolínání. „Šťáva“ je kolem přepnutí, ne v něm. Takhle to dělá varianta B.
- **Konfety jsou řídké:** 3–8 kusů, 2 tvary, 2 barvy, pryč do 0,6 s. Proto má i C jen 8 konfet.
- **Počítadlo přetočí jen změněnou číslici:** nová spadne shora za 70–80 ms a krátce podklesne. Nezměněná číslice přepne barvu v jednom snímku uprostřed přetočení.
- **Zvuky jsou v jedné tónině.** U Duolinga Fis dur, „správně“ zní jako stoupající velká tercie po 125 ms. Prototyp drží C dur: kroky hrají kadenci I – IV – V a 3/3 ji rozřeší na I.

### Doporučení
- **B jako výchozí každý den.**
- **C jen na milnících série:** první den, 7., 30. a 100. den a první splněný den po instalaci.
- **A pro nastavení „Méně animací“** a pro opožděnou oslavu, když je splnění staré.

Podrobné časy níže popisují variantu C. B a A z ní ubírají podle tabulky výše a jejich časy jsou v panelu prototypu u každého kroku.

## Hotová cesta jako plná čára (návrh)

Prošlá část cesty se mění z čárkované na plnou zelenou čáru. Každý styl čáry má vlastní význam:
- **plná zelená** = cesta, kterou uživatel prošel;
- **žlutá čárkovaná** = kudy jde dál;
- **šedá čárkovaná** = co ho čeká.

V prototypu se dá přepnout:

| Režim | Co se děje | Kdy |
|---|---|---|
| Čárkovaná (dnes) | zelené čárky se nalijí přes žluté | krok 2 od 250 ms (300 ms), krok 3 od 300 ms (450 ms) |
| **Plná · dokreslí se** (doporučuji) | plná zelená čára se dokreslí přes čárky od předchozího uzlu k právě splněnému | stejné časy |
| Plná · zacvaknutí | nejdřív zelené čárky, 160 ms za nimi se mezery zacvaknou do plné čáry | stejné časy + 160 ms |

- **Proč „dokreslí se“:** je to jeden pohyb s nejjasnější metaforou („prošel jsem“) a sedí ke střídmé variantě B. Zacvaknutí ukazuje proměnu čárek doslova, ale má dvě fáze, tedy víc pohybu.
- **Přístupnost:** hotové a další úseky se dnes liší jen barvou (zelená × žlutá čárkovaná). S plnou čarou se liší i stylem, takže je rozliší i člověk se sníženým vnímáním barev (WCAG 1.4.1).
- **Dopad do Figmy:** statické stavy 2/3 a 3/3 by měly mít plnou zelenou čáru. Je to nový stav cesty „prošlá“.

## Aktivní krok dýchá

Svatozář kolem žlutého aktivního uzlu je tu proto, aby přitáhla oko. V klidovém stavu HP proto pomalu dýchá, dokud uživatel na krok neklepne. Nahrazuje dřívější jednorázové „pozvání“ vlnkou, aby jeden prvek neměl dva různé pulzy.

| Část cyklu (2600 ms) | Co se děje |
|---|---|
| 0–35 % (910 ms) | svatozář se rozšíří na 107 % a zesílí: druhý stejný prstenec (žlutá 40 %) se prolne z 0 na 1, dohromady asi 64 % |
| 35–75 % (1040 ms) | vrátí se na 100 % a druhý prstenec zmizí |
| 75–100 % (650 ms) | stojí |

- **Křivka:** `cubic-bezier(.37,0,.63,1)` (sinus) na obou půlkách. Žádné blikání, žádné vlny ven, pohybuje se jen velikost a průhlednost (dá se počítat na GPU).
- **Proč takhle:** zve ke klepnutí, ale nekřičí. Pomalý dech (asi 23 za minutu) působí živě a nenaléhavě, rychlejší pulz už vypadá jako varování.
- **Kdy nedýchá:**
  - během oslavy: dech se zastaví na začátku a po ní začne znovu od klidu, takže nic neskočí;
  - u Procvičování po 3/3: den je hotový a nic by nemělo naléhat (viz otevřené otázky);
  - při omezeném pohybu;
  - když HP není vidět nebo je aplikace na pozadí.
- Dech je klidový stav HP, ne oslava, proto ho mají všechny tři varianty.
- V prototypu jde vypnout přepínačem „Dýchání aktivního kroku“.

## Otočení mince (nástřel)

Splněný uzel se otočí o 180° jako mince: žlutý líc („udělat“) se otočí na zelený rub („hotovo“). **Nejdřív přijede cesta, pak se otočí mince, a to ze strany, odkud cesta přijela.** V prototypu je to přepínač „Splnění uzlu“, výchozí je Otočení mince.

Krok 2 (krok 3 stejně, jen zprava):

| ms | Co se děje |
|---|---|
| 0–375 | zelená cesta doteče od Lekce ke Slovům, ke konci zrychluje (`cubic-bezier(.45,0,.9,.6)`), aby do mince „ťukla“ |
| 375 | svatozář se vsákne; mince se otáčí kolem svislé osy, hrana na straně příjezdu (vlevo) ucukne dozadu a mince se o 3 px posune ve směru jízdy cesty, přiblíží se na 107 % (170 ms) |
| 545 | hrana: ztmavne na 86 %, v jednom snímku se vymění žlutá za zelenou a ikona zbělá |
| 545–750 | zelený rub se dotočí čelem (204 ms) |
| **750** | dopad 95 %, haptika a znělka; teprve pak kroužek dne, text a žlutá cesta k dalšímu uzlu (všechno o 500 ms později než u zmáčknutí) |

- **Směr se počítá z konce cesty** (posledních 10 px). Při vodorovném příjezdu se mince otáčí kolem svislé osy, při svislém kolem vodorovné. Ke Slovům cesta přijíždí zleva, k testu zprava. Při jiném tvaru cesty se směr přizpůsobí sám.
- **Další uzel se rozsvítí, až k němu dojede žlutá.** Cesta je spoušť: když dojede, něco se stane.
- **K Lekci žádná cesta nevede.** Mince se tam otočí hned a výchozím směrem (zleva doprava) a dopadne ve 375 ms.
- **Proč to sedí:** změnu stavu nese jediný pohyb, kterému člověk rozumí bez vysvětlení (otočit kartičku nebo minci). Cesta a mince jsou jeden pohyb: čára doteče a mince se překlopí ve směru, kterým jela. Stejně se překlápí den v kalendáři série.
- **Flat:** bez stínu a lesku, hrana je naznačená jen ztmavnutím. Perspektiva 300 px, aby bylo vidět, ze které strany se mince otáčí.
- **Druhá půlka otočení jde z −84° do 0°,** aby ikona na rubu nebyla zrcadlově.
- Varianta A a omezený pohyb se netočí, jen prolnou barvu (pořadí cesta → uzel zůstává).

## Odkrytí Procvičování (krok 3)

Když se po splnění dne odkryje Procvičování, „probudí se“: zatřese se, vystřelí ze země, ve vzduchu se otočí jako mince a žuchne zpátky. (Roztočení o 540° bylo moc, zůstalo jedno otočení o 180°.) Z neaktivního se stane aktivní, a s chutí.

| ms od začátku | Co se děje |
|---|---|
| 0–180 | **třes:** šedý uzel se zakývá ±5°, ±5°, ±3° (něco se dere ven) |
| 180–280 | **nádech:** zamáčkne se do země na 110 × 82 % (accelerate) |
| 280–500 | **výskok** o 34 px (C 44 px) a přiblížení na 118 % (C 124 %) (decelerate) |
| 310–660 | **otočení o 180° zleva doprava** jako mince se dvěma líci: šedý líc → hrana → žlutý rub (ease-in-out). Před dopadem je dotočená, aby žuchla naplocho. Hrana je tenký šedý pruh. Stín na zemi se při výskoku zmenší na 50 % |
| 500–720 | **pád** (accelerate), stín naroste a ztmavne |
| **720** | **žuchnutí:** rozplácnutí na 126 × 70 %, odpružení na 94 × 110 % a dosednutí; ze země do stran vyletí 8 obláčků prachu (C 10), obrazovka se otřese o 3 px (C 5 px), vlnka na zemi, **haptika medium** a tupé „bum“ |
| 900 | svatozář vyroste |

- V toku „karta série po dokončení cesty“ začíná v 655 ms po přistání plamene a žuchnutí je na úderu 1375 ms.
- **Mince je opravdová 3D (dva líce a hrana)**, ale plochá: plné barvy bez stínování a lesku. Prach jsou plná světle šedá kolečka, stín je plochá elipsa jako pod plamenem na kartě série.
- **Otřes obrazovky je jen jednou denně** a malý (3 px, 240 ms). Při omezeném pohybu odpadá.
- Splnění kroku se otáčí ze strany příjezdu cesty, odkrytí Procvičování skokem a žuchnutím. Každý význam má vlastní pohyb.
- Varianta A a omezený pohyb: jen prolnutí na aktivní stav.
- Technická poznámka: průhlednost se animuje na obalu mince. Animovaná opacity přímo na 3D prvku ho zploští a místo rubu by byl vidět zrcadlový líc.
- Technická poznámka: po dopadu se dočasná 3D mince vymění za skutečný uzel. Ten musí být pod mincí už v cílovém stavu (aktivní, žlutý), jinak na jeden snímek probleskne šedý. Výměna je bez prolnutí: uzel se ukáže o 2 ms dřív, než mince zmizí.

## Karta série (po splnění denní cesty)

Nejdřív příčina, pak odměna. Sérii prodlužuje splnění celého dne, proto karta série ([Figma](https://www.figma.com/design/phDRRozgW9HSte85GD2alO/Mobile-app-design?node-id=13994-95997)) přijde až po dokončení cesty na HP. Karta je vrchol i závěr dne.

Tok kroku 3:
1. **„Výborně!“** po testu.
2. **HP dokončí cestu:** uzel testu zezelená, cesta se dokreslí, kroužek 3/3, „Pecka, máš hotovo!“, lehká haptika. Série v hlavičce zůstává šedá 12.
3. **Pauza 450 ms,** pak zdola vyjede karta série (list přes ztmavenou HP, 420 ms).
4. **Na kartě:**

| ms od vyjetí karty | Co se děje |
|---|---|
| 670 | zapálení plamene. B: smáčknutí 116 × 82 %, protažení 94 × 116 %, šedá → žlutá → oranžová. C: plné poměry z Duolinga. A: prolnutí barvy |
| 840 (B) | vrchol: „2“ spadne shora na „3“, „1“ se přebarví uprostřed přetočení, oranžové paprsky a záblesk, **haptika success** (jediná za den) |
| +400 | pátek se připojí do kapsle (kapsle přestřelí o třetinu dne a vrátí se, žeton dopadne z 150 %), C: světlo přeběhne kapslí |
| +500 | tlačítko **„Pokračovat“** vyjede jako poslední |

5. **Po klepnutí** karta sjede dolů (320 ms) a plamen odletí obloukem do počítadla v hlavičce HP, kde se zmenší na velikost ikony (560 ms).
6. **HP převezme dopad:** plamen dosedne (122 × 78 %), série 13, po 300 ms pátek v liště, po 655 ms se Procvičování odkryje a v 1375 ms žuchne.

Proč tak:
- Krok 3 nejdřív ukáže, že je den hotový, a teprve pak sérii. Pořadí příčina → následek je u nás logičtější než u Duolinga, kde sérii prodlužuje už samotná lekce.
- Karta jako list přes HP drží uživatele „doma“ a po zavření může plamen přistát rovnou v hlavičce.
- „Jdeme na to!“ zní po splnění dne jako začátek, proto **„Pokračovat“**: říká, co se stane.

V prototypu jde přepínačem „Karta série“ porovnat i původní pořadí (série hned po „Výborně!“, před HP) nebo kartu vypnout.

Poznámky k Figmě:
- dny jsou na kartě anglicky (Mo, Tu…), na HP česky;
- „224 dny“ je správně, pro 13 je to „dní“ (prototyp skloňuje);
- na HP je pondělí zmeškané, na kartě splněné.

## Přechodová success obrazovka

Před návratem na HP se ukáže přepoužitá obrazovka z Figmy, [Přechodové success obrazovky](https://www.figma.com/design/phDRRozgW9HSte85GD2alO/Mobile-app-design?node-id=13994-58748). Skládá se z instancí Header section, Loading dots a odznaku s paprsky. Nadpis je „Výborně!“, popis se mění podle kroku:

| Krok | Popis |
|---|---|
| 1 · Lekce | Lekce je za vámi. Dnes jsme spolu 7 minut mluvili o cestování. |
| 2 · Slova | Prošli jste 12 nových slov z dnešní lekce. |
| 3 · Test | Denní test máte hotový, 8 z 10 odpovědí bylo správně. |

Pohyb:

| ms | Co se děje |
|---|---|
| 0 | nadpis a popis vyjedou o 8 px (300 ms, decelerate); při ukládání se vlní tečky (±4 px, perioda 900 ms, posun fáze 150 ms) |
| +0 | tečky se slijí do středu odznaku (160 ms, accelerate) |
| +60 | odznak vyskočí ze 40 % s pootočením −20° (pružina M3 Expressive fast) |
| +200 | vrchol odznaku: haptika light, krátký tón, fajfka se nakreslí (200 ms) |
| +140 | paprsky se rozvinou ze 70 % (520 ms); ve variantě C se pak pomalu otáčejí o 12° |
| +1200 | fade through: obrazovka zmizí (220 ms), HP dosedne z 98 % (320 ms), po 300 ms animace kroku |

- **Tečky jen tehdy, když ukládání trvá déle než 400 ms.** Když už se ukážou, tak aspoň 500 ms, jinak problikne. Jinak rovnou odznak: Duolingo ukazuje oslavu hned a ukládá na pozadí.
- **Klepnutím jde obrazovka přeskočit.**
- **Varianta A:** odznak se jen prolne (90 → 100 %) a fajfka je vidět hned.
- **Otázka:** nadpis podle výsledku? Například „Výborně!“ od 8/10 a „Hotovo“ pod tím.

## Kostra (stejná pro všechny kroky)

Časy a poměry jsou změřené po snímcích na uzlu cesty Duolinga a převedené do flat stylu.

1. **Vsáknutí:** svatozář se za 90 ms stáhne do uzlu (na 84 %) a zmizí, nezmizí jen prolnutím.
2. **Zmáčknutí:** uzel se za 100 ms zmáčkne na 88 % (accelerate).
3. **Výskok:** za 150 ms vyskočí na 106 % (decelerate), pak dosedne pružinou M3 Expressive default.
4. **Výplň a ikona:** zelená se rozlije od středu (220 ms) a ikona zbělá. Ikona dobíhá o 40 ms později (82 % → 114 % → 100 %). To je překrývající se pohyb: celek a detail nedorazí najednou.
5. **Vrchol v 250 ms:** lehká haptika, tón kroku a **záblesk**. Paprsky střídavě dlouhé a krátké, žluté a zelené, vyrazí ven, 70 ms drží a smažou se směrem od uzlu.
6. **Štafeta:** cesta k dalšímu uzlu se nalije žlutou a čárky krátce tečou k cíli. Další uzel se nadechne na 107 %, zežloutne a svatozář z něj vyroste (M3 Expressive fast). Ve 750 ms přijde haptika selection. Pak svatozář v klidu dýchá (viz [Aktivní krok dýchá](#aktivní-krok-dýchá)).

## Kroky v milisekundách

Čas 0 = začátek oslavy. To je 300 ms poté, co dosedne přechod zpět na HP. Haptika a zvuky leží na mřížce 250 ms (osminy při 120 BPM).

### 1 · Lekce (hlavní část ≈ 0,9 s)
| ms | Co se děje |
|---|---|
| 0 | uzel Lekce: vsáknutí svatozáře, zmáčknutí |
| 100 | výskok a zelená výplň, ikona dobíhá |
| **250** | **haptika light**, tón C, záblesk ze 6 paprsků |
| 300 | kroužek dne 0 → 1/3 (500 ms), cesta ke Slovům se nalije žlutou (520 ms), čárky tečou 1200 ms |
| 400 | text karty „Dobrý začátek!“ (fade through 150 + 280 ms) |
| 500 | číslo 0 → 1 se přetočí a při dopadu ťukne (116 %) |
| 620 | uzel Slova: nádech 107 %, žlutá výplň, svatozář vyroste |
| **750** | **haptika selection** |
| 1180 | svatozář dosedne a začne dýchat |

### 2 · Slova z lekce (hlavní část ≈ 0,9 s, karta do 1,4 s)
Stejná kostra a k tomu:
| ms | Co se děje |
|---|---|
| **250** | haptika light, tón D, záblesk z 8 paprsků a 3 kosočtverečky, které pomalu odplují (740 ms) |
| 250 | cesta od Lekce zezelená až ke Slovům (300 ms) |
| 400 | od Slov se nalije žlutá k testu (500 ms) |
| 1000 | zespodu vyjede zpráva „Přibyla nová gramatická karta“ (380 ms) |
| **1250** | odznak 1 na tabu Gramatika pípne (vrchol popu přesně na úder) a ikona se zhoupne, bez haptiky |

### 3 · Denní test, den hotový (≈ 2,9 s)
| ms | Co se děje |
|---|---|
| 0–250 | uzel Test: kostra, **v 250 ms haptika light**, tón E, záblesk |
| 300 | poslední úsek cesty zezelená (450 ms) |
| 420 | **vlna:** uzly 1, 2, 3 po řadě poskočí o 9 px (rozestup 90 ms) |
| 600–1000 | kroužek 2/3 → 3/3 **zrychluje** k uzavření (accelerate), nikdy nezpomalí u cíle |
| **1000** | kroužek zezelená, tah zesílí 4,4 → 7 px a zpět, pumpne na 110 % (pružina hero), číslo 3/3 ťukne. **Haptika success** a akord C dur |
| 1010 | 12 konfet z kroužku (žlutá, zelená, plátky citronu), při pádu se třepotají. 3 záblesky kolem kroužku po 120 ms |
| 1060 | text „Pecka, máš hotovo!“ |
| 1250 | malý plamen doletí obloukem z kroužku k počítadlu série (500 ms) |
| 1750 | plamen v hlavičce: smáčknutí na 128 × 66 % (70 ms), drží a mění barvu šedá → žlutá → oranžová (180 ms), protažení na 92 × 142 % (50 ms), vznáší se o 5 px výš (160 ms) |
| **2250** | **dopad** na 136 × 86 %, odraz a dosednutí. Série 12 → 13 ťukne, oranžový záblesk, **haptika medium** |
| 2450 | pátek v liště: nádech na 116 %, překlopení (90 ms), na rubu plamen, oranžový záblesk |
| 2900 | Procvičování se odkryje (žuchne) |

## Zvuk

Zvuky v prototypu jsou syntetické a slouží jen k ukázce rytmu. Návrh pro zvukaře:
- **Jedna tónina pro všechno** (prototyp C dur, Duolingo Fis dur), aby se překrývající zvuky nehádaly.
- **Znělka kroku:** stoupající velká tercie, tóny 125 ms po sobě, druhý hlasitější. Ve variantě B zazní první tón na dopad (přepnutí barvy) a druhý na vrchol výskoku.
- **Kroky 1–3** hrají kadenci I – IV – V (C, F, G) a **3/3** ji rozřeší akordem C dur.
- **Žuchnutí Procvičování:** tupé „bum“ (nízký tón s poklesem a krátký šum).
- **Plamen série:** krátký švih a otevřená kvinta přesně na dopad.

## Pohybové tokeny

Edoo stojí na Material 3, proto jsou pružiny přímo z M3 Expressive (androidx `ExpressiveMotionTokens`).

| Token | Tlumení / tuhost | SwiftUI | Compose | Použití |
|---|---|---|---|---|
| `fast` (M3 Expressive fast spatial) | 0,6 / 800 | `.spring(response: 0.222, dampingFraction: 0.6)` | `spring(0.6f, 800f)` | pop dalšího uzlu, svatozář, poskok, odznak, plamen pátku |
| `default` (M3 Expressive default spatial) | 0,8 / 380 | `.spring(response: 0.322, dampingFraction: 0.8)` | `spring(0.8f, 380f)` | dosednutí mince a splněného uzlu, odpružení Procvičování po žuchnutí, dosednutí plamene v hlavičce |
| `hero` (vlastní, jen 3/3) | 0,5 / 420 | `.spring(response: 0.307, dampingFraction: 0.5)` | `spring(0.5f, 420f)` | pumpnutí kroužku |

Křivky:
- decelerate `cubic-bezier(.05,.7,.1,1)`: příchody a výplně;
- accelerate `cubic-bezier(.3,0,.8,.15)`: odchody, nádech a dojezd kroužku do 3/3;
- standard `cubic-bezier(.2,0,0,1)`: kroužek a čísla;
- draw `cubic-bezier(.65,0,.35,1)`: nalití cesty, druhá půlka otočení mince, otočení Procvičování;
- breath `cubic-bezier(.37,0,.63,1)`, cyklus 2600 ms: dech svatozáře aktivního kroku;
- arrive `cubic-bezier(.45,0,.9,.6)`: zelená cesta dojíždí k minci, ke konci zrychlí a „ťukne“.

Pružiny se používají jen pro polohu a velikost. Barva a průhlednost nikdy nepřestřelují.

## Haptika

| Okamžik | iOS | Android |
|---|---|---|
| uzel splněný (light) | `UIImpactFeedbackGenerator(.light)` | `KEYBOARD_TAP` |
| další krok (selection) | `UISelectionFeedbackGenerator` | `CLOCK_TICK` |
| den hotový (success) | `UINotificationFeedbackGenerator(.success)` | `CONFIRM` |
| série +1 (medium) | `UIImpactFeedbackGenerator(.medium)` | `CONTEXT_CLICK` |
| Procvičování žuchlo (medium) | `UIImpactFeedbackGenerator(.medium)` | `CONTEXT_CLICK` |

Haptika a zvuk patří na vrchol pohybu, nejpozději 50 ms po něm. Dřív než 15 ms před ním už je to poznat. Zvuky v prototypu jsou syntetické a slouží jen k ukázce synchronizace.

## Pravidla pro vývoj

- **Odložená oslava.**
  - Po splnění kroku se uloží příznak „čeká oslava“.
  - HP se po návratu vykreslí ve stavu *před* splněním, počká na dosednutí přechodu a dalších 300 ms. Pak oslavu přehraje a příznak smaže, takže se přehraje jen jednou.
  - Když uzel není vidět, HP k němu nejdřív odroluje.
  - Když uživatel už scrolluje nebo je splnění staré (aplikace byla zavřená), ukáže se rovnou koncový stav.
- **Nečekat na server.** Stav se zapíše lokálně, animace jede hned a synchronizace běží na pozadí.
- **Nikdy neblokovat.** Klepnutí kamkoli animaci dokončí do koncového stavu. HP jde ovládat po celou dobu.
- **Omezený pohyb** (iOS Reduce Motion, Android „Odstranit animace“): stejné stavy, jen prolnutí 240 ms. Bez poskoků, pružin a částic, svatozář nedýchá. Haptika zůstává.
- **Dech svatozáře** je nekonečná animace, proto běží jen tehdy, když je uzel vidět a aplikace je v popředí. Po oslavě začíná vždy od klidového stavu.
- **Technika.**
  - Uzly, cesty, kroužek a čísla jsou nativní pružiny (SwiftUI `Spring`, Compose `MotionScheme.expressive()`). Řídí se tokeny a omezený pohyb dostanou zadarmo.
  - Plamen série a konfety jdou udělat i v Rive se stavy *šedý → zapálení → hoří* a vstupem `reducedMotion`. Duolingo dělá odměny právě v Rive.

## Otevřené otázky

1. **Série 12 → 13.** Ve Figmě zůstává ve stavu 3/3 číslo 12 a mění se jen barva. Navrhuji, aby číslo naskočilo. Pokud 12 už dnešek započítává, zůstane jen zapálení plamene.
2. **Pátek v liště dnů** je ve Figmě i ve stavu 3/3 čárkovaný kruh. Měl by tam být plamen, stejně jako na konci animace.
3. **Série za lekci, nebo za celý den?**
   - Duolingo sérii oddělilo od denního cíle a prodlouží ji už jedna lekce. Retence po 14 dnech díky tomu stoupla o 3,3 %.
   - Kdybyste šli stejnou cestou, karta série a zapálení plamene se přesunou ke kroku 1 a 3/3 si nechá kroužek. Animace jsou z bloků, takže to jde bez předělávky.
4. **Tykání** ve stavu 3/3: „Pecka, máš hotovo!“ tyká, zbytek karty vyká. Prototyp přebírá text z Figmy beze změny.
5. **Vzácná varianta.** Na milnících série (7, 30, 100 dní) může mít 3/3 jinou oslavu. V nastavení by šly oslavy vypnout, jako v Asaně.
6. **Má dýchat i Procvičování?** Po 3/3 je to jediný aktivní prvek. Navrhuji, aby nedýchalo, protože den je hotový. Kdybyste chtěli víc tlačit do procvičování, stačí dech zapnout i pro něj.

## Z rešerše

### Duolingo

Časy jsou odečtené po snímcích z nahrávek 60fps.design, protože Duolingo žádné hodnoty nezveřejňuje.

- **Oslava místo čekání.** Konec lekce ukáže oslavu hned a síťové volání běží za ní. Vnímané čekání kleslo o víc než 60 %. ([blog](https://blog.duolingo.com/android-app-performance/))
- **Na animaci série záleží.** Nová animace prodloužení zvedla retenci nováčků po 7 dnech o 1,7 %. Nejvíc se slaví první dny, velké oslavy jsou jen na milnících. ([blog](https://blog.duolingo.com/how-duolingo-streak-builds-habit/))
- **Plamen série.** Šedý plamen se smáčkne do placky (asi 100 ms) a zbarví do oranžové (150 ms). Pak se vytáhne a asi 250 ms visí. Dopadne smáčknutý a teprve potom naskočí číslo a odletí jiskry (asi 600 ms). ([60fps.design](https://60fps.design/shots/duolingo-2-day-streak-animation))
- **Odměny po jedné.** Drahokamy letí k počítadlu s rozestupem 50 ms a každý přičte 1 až při dopadu. ([60fps.design](https://60fps.design/shots/duolingo-daily-quest-complete-trail-animation))
- **Uzel na cestě.** Zmáčknutí, pop s přestřelením a jiskřičky asi 400 ms. Celý beat trvá zhruba 1,3 s, pak se cesta asi za 500 ms posune dál. ([60fps.design](https://60fps.design/shots/duolingo-section-unit-complete-trophy-morph-animation))
- **Gradace.** Reakce postavy, pak N správně v řadě, konec lekce, série +1 a nakonec milník přes celou obrazovku (asi 6 s). Páky intenzity jsou velikost plochy, barva pozadí, proměna postavy, částice a pauza před tlačítkem.
- **Varování.** Jedna lekce umí zřetězit asi 11 obrazovek s „Pokračovat“ a existují rozšíření, která je proklikávají.

### Ostatní
- **Headspace, záložka Today:** čárkovaná osa s hotovými, aktuálním a budoucími kroky. Po návratu se „aktuální“ předá dál. Je to skoro náš komponent. ([Mobbin](https://mobbin.com/flows/7763b37d-c5e6-4394-9471-f8f1823c9fc7))
- **NN/g:** odezva do 100 ms a běžné animace 100–400 ms. Od 500 ms výš působí pohyb jako zdržení. ([NN/g](https://www.nngroup.com/articles/animation-duration/))
- **Apple:** odskok nad 0,4 působí u UI přehnaně. ([WWDC23](https://developer.apple.com/videos/play/wwdc2023/10158/)) Zvuk, haptika a obraz mají sedět přesně na sebe. ([WWDC19](https://developer.apple.com/videos/play/wwdc2019/810/))
- **Ukazatel postupu** působí rychleji, když ke konci zrychluje. ([Harrison, UIST 2007](https://www.chrisharrison.net/projects/progressbars/ProgBarHarrison.pdf))
- **Kdy oslava škodí:**
  - Robinhood odstranil konfety po kritice gamifikace.
  - Strava stáhla točící se kudos po stížnostech, že z toho je lidem špatně.
  - Asana slaví jen občas a dá se to vypnout. ([Asana](https://asana.com/inside-asana/new-celebrations))

## Vědomé odchylky od Figmy

- Popisy na success obrazovce jsou návrh, ve Figmě je jen příklad z ohodnocení úrovně.
- Ve stavu 3/3 je série 13 a pátek má plamen (viz otázky 1 a 2).
- Zpráva o gramatické kartě se ve 3/3 nezobrazuje, stejně jako ve Figmě.
- Prototyp ukazuje jen světlý režim.
