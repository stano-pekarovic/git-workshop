# Speaker script — Git Workshop 1

> Podklad k prezentácii `slides/index.html`. Po slajdoch.
> Ovládanie decku: **← →** alebo medzerník medzi slajdami · **S** = zobraziť tieto poznámky priamo v deku · **F** = fullscreen.
> Publikum: ženy z testerskej akadémie (WTA-A-24), s gitom ešte nerobili. Hovor pomaly, neformálne, žiadny žargón bez analógie.
> Celkový čas ~2h. Cieľ: **mentálny model** — čo git je, na čo a ako.

---

## Slajd 1 — Titulka *(úvod, ~2 min)*
**Povedz:** Vitajte. Dnes sa prvýkrát pozrieme na Git. Nečakajte žiadne predošlé znalosti — ideme od nuly, pomaly a po krokoch.

**Hlavná veta na otvorenie:** *„Git nie je len nástroj na ukladanie súborov. Je to systém, ktorý si pamätá históriu projektu."*

**Tón:** upokoj ich — nič sa nepokazí, všetko si vyskúšame.

---

## Slajd 2 — Čo dnes zvládneme *(úvod, ~3 min)*
**Povedz:** Na konci tejto session budete vedieť stiahnuť projekt, uložiť doň zmenu a poslať ju ostatným. To je celé.

**Štyri slová, ktoré dnes spoznáme:** `clone → commit → push → pull`.

**Dôležité ohraničenie:** branching a merge requesty dnes **nebudú** — to necháme na druhý workshop. Dnes držíme jednu líniu.

---

## Slajd 3 — Problém bez gitu *(~10 min)*
**Povedz:** Poznáte to? *(ukáž chaos kópií)* `projekt-final`, `projekt-final-v2`, `naozaj-final`, `od-janky`...

**Otázky do pléna:** Ktorá je tá pravá? Kto čo zmenil? Čo keby ste sa chceli vrátiť k verzii spred dvoch dní?

**Pointa:** Keď robíme kópie súborov, stratíme prehľad. Git to rieši inak — **nerobíme kópie**. Máme jednu pracovnú verziu a Git si pamätá jej historické stavy.

---

## Slajd 4 — Riešenie = časová os *(srdce modelu, ~3 min)*
**Povedz (kľúčová veta):** *„Git je ako časová os projektu. Každý bod na tejto osi je uložený stav, ku ktorému sa viem kedykoľvek vrátiť alebo sa pozrieť, čo sa vtedy zmenilo."*

**Zdôrazni:** Žiadne kópie súborov — jedna pracovná verzia + história. Tento obrázok časovej osi s bodmi sa bude vracať celou prezentáciou.

---

## Slajd 5 — Git vs GitHub vs GitKraken *(pojmy, ~4 min)*
Najčastejší zmätok začiatočníkov — venuj tomu čas.

- **Git** = samotný nástroj/systém. Žije na **tvojom počítači**.
- **GitHub** = služba v cloude, kde repozitár **zdieľame**. Analógia: *ako Google Drive, ale pre projekt*.
- **GitKraken** = grafická appka — **pohodlné okno do gitu**, aby sme nemuseli písať príkazy.

**Zopakuj nahlas:** Nie sú to to isté. Sú to tri rôzne veci, ktoré spolupracujú.

---

## Slajd 6 — Repozitár *(pojmy, ~2 min)*
**Povedz:** Repozitár, skrátene „repo", je projekt, ktorý Git sleduje. Je to priečinok s tvojimi súbormi **a zároveň** celá história zmien, ktorá k nim patrí. Súbory aj história žijú spolu.

---

## Slajd 7 — Commit *(pojmy, ~5 min)*
**Povedz:** Commit je uložený balíček zmien s popisom.

**Najdôležitejšie rozlíšenie:** commit **nie je** obyčajný „save". Save uloží súbor. Commit uloží **významový krok v histórii** — bod na časovej osi, s vetou, čo a prečo sa zmenilo.

**Ukáž dobré vs zlé správy:**
- ✓ `Add my introduction`, `Fix typo in README` — budúce ja (aj kolegovia) hneď vie, čo sa stalo.
- ✗ `changes`, `update`, `stuff` — nepovie nič.

**Pre testerky pridaj:** dobrá história commitov ti neskôr pomôže nájsť, *kedy* a *prečo* sa niečo pokazilo.

---

## Slajd 8 — Mentálny model: tri miesta *(model, ~5 min)*
**Povedz:** Predstav si, že zmena cestuje cez tri miesta:
1. **Tvoj počítač** — pracovná verzia, tu súbory upravuješ.
2. **Commit** — uložíš krok do histórie (pozor, stále len na tvojom počítači!).
3. **GitHub** — keď chceš, aby zmeny videli ostatní, pošleš ich do cloudu.

**Poznámka pre teba (nehovor nahlas, ak sa nepýtajú):** zámerne nezavádzam „staging area" ako samostatný pojem — v GitKrakene to bude len „vyberiem, čo ide do commitu". Drž to jednoduché, aby sa nepreťažili.

---

## Slajd 9 — Lokálne vs vzdialené *(model, ~3 min)*
**Analógia knižnice:** Lokálne repo je tvoj **pracovný zošit na stole** — doma si robíš poznámky. Remote repo na GitHube je **spoločná verzia v knižnici**.
- Chcem, aby moje poznámky videli ostatní → **push** (pošlem do knižnice).
- Chcem zmeny od ostatných → **pull** (vezmem si z knižnice).

**Zdôrazni:** push aj pull = pohyb **histórie/commitov** medzi tvojím počítačom a GitHubom.

---

## Slajd 10 — DEMO: clone *(hands-on, ~15 min)*
**Prepni do GitKrakenu.** Kroky:
1. Otvor GitKraken.
2. Prihlás sa do GitHubu.
3. **Clone** repo → vyber **`wta-a-24`**.
4. Otvor lokálny priečinok a ukáž, že súbory sú fyzicky na počítači.

**Veta:** *„Clone = zoberiem existujúci repozitár z GitHubu a vytvorím si jeho lokálnu kópiu na počítači."*

**Úloha:** každá si naklonuje `wta-a-24`. Počkaj, kým to majú všetky.

---

## Slajd 11 — DEMO: prvá zmena + diff *(hands-on, súčasť ~25 min bloku)*
**Úloha pre každú:** uprav `about-me.md`:
```
# About me
Meno:
Obľúbený nápoj:
Jedna vec, ktorú sa chcem naučiť:
```
V GitKrakene ukáž: súbor sa objaví ako **changed**.

**Vysvetli diff:** *„Diff je porovnanie starej a novej verzie. Zelené riadky sú pridané, červené odobrané alebo zmenené."* Presne toto Git „vidí".

---

## Slajd 12 — DEMO: commit *(hands-on)*
V GitKrakene:
1. Vyber zmenu (čo ide do commitu).
2. Napíš **zmysluplnú** commit message, napr. `Add my introduction`.
3. Vytvor commit.

Ukáž, ako sa na časovej osi v GitKrakene objaví **nový bod**.

**Pripomeň:** teraz je to uložené — ale **stále len na tvojom počítači**.

---

## Slajd 13 — DEMO: push *(hands-on, ~15 min)*
**Veta:** *„Commit = uložila som zmenu do histórie na svojom počítači. Push = poslala som túto históriu na GitHub."*

V GitKrakene ukáž, že lokálna vetva je **ahead** (má commit navyše). Daj **push**. Potom otvor repo na GitHube v prehliadači a ukáž, že zmena je **aj tam**.

**Aha-moment:** teraz to vidia ostatní.

---

## Slajd 14 — DEMO: pull *(hands-on, ~15 min)*
**Priprav situáciu:** ty (alebo druhý účet) zmeníš niečo na GitHube — napríklad pridáš riadok do `README.md`.

**Veta:** *„Pull = stiahnem si nové commity z GitHubu do svojho lokálneho repozitára."*

**Dôležité rozlíšenie:** pull **nie je** download súborov — je to stiahnutie **commitov/histórie**.

Workflow: *niekto zmenil remote → ja dám pull → mám to lokálne.*

---

## Slajd 15 — Celý kolobeh *(súhrn, ~5 min)*
**Klikaním** rozsvecuj body na osi: `clone` (mám projekt) → `edit` (upravím) → `commit` (uložím krok) → `push` (zdieľam) → `pull` (beriem zmeny ostatných) → a znova.

**Povedz:** Toto je celý dnešný kolobeh. *(Nechaj ich zopakovať vlastnými slovami.)*

---

## Slajd 16 — Slovníček *(súhrn, ~2 min)*
**Povedz:** Ak si z dneška zapamätáte len štyri slová a čo robia, splnili sme účel:
- `clone` — stiahnem projekt z GitHubu na počítač
- `commit` — uložím krok do histórie (lokálne)
- `push` — pošlem svoje commity na GitHub
- `pull` — stiahnem si commity ostatných

---

## Slajd 17 — Nabudúce *(teaser, ~2 min)*
**Povedz:** Dnes sme pracovali v jednej línii. Nabudúce si otvoríme vlastné **vetvy (branches)** — bezpečný priestor, kde si skúšaš zmeny bez toho, aby si zasiahla spoločnú verziu. Naučíme sa **merge requesty** (návrh zlúčenia späť) a ako riešiť **konflikty**.

**Povzbuď:** to najťažšie — mentálny model — máte už za sebou.

---

## Slajd 18 — Záver + otázky *(~10 min)*
**Zopakovanie vlastnými slovami (spýtaj sa pléna):**
- Čo je commit?
- Aký je rozdiel medzi commit a push?
- Čo je remote?
- Čo znamená pull?

**Uzavri:** poďakuj, pripomeň, že `wta-a-24` majú naklonované a inštalačný návod je v `git/INSTALL.md`. Uvidíme sa na workshope 2.

---

### Orientačný timing (zo osnovy)
| Blok | Slajdy | Min |
|---|---|---|
| Úvod + nastavenie | 1–2 | 10 |
| Problém bez gitu | 3–4 | 10 |
| Mentálny model | 5–9 | 20 |
| Clone | 10 | 15 |
| Zmena + commit | 11–12 | 25 |
| Push | 13 | 15 |
| Pull | 14 | 15 |
| Súhrn + otázky | 15–18 | 10 |
