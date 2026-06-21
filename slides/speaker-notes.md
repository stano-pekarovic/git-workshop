# Speaker script — Git Workshop 1

> Podklad k prezentácii `slides/index.html`. Po slajdoch.
> Ovládanie decku: **← →** alebo medzerník medzi slajdami · **S** = zobraziť tieto poznámky priamo v deku · **F** = fullscreen.
> Publikum: ženy z testerskej akadémie (WTA-A-24), s gitom ešte nerobili. Hovor pomaly, neformálne, žiadny žargón bez analógie.
> Celkový čas ~2h. Cieľ: **mentálny model** — čo git je, na čo a ako.

---

## Slajd 1 — Titulka *(úvod, ~1 min)*
**Povedz:** Vitajte. Dnes sa prvýkrát pozrieme na Git. Nečakajte žiadne predošlé znalosti — ideme od nuly, pomaly a po krokoch.

**Tón:** upokoj ich — nič sa nepokazí, všetko si vyskúšame.

---

## Slajd 2 — Niečo málo o mne *(úvod, ~1 min)*
**Povedz:** Volám sa **Stano Pekarovič**. V IT pôsobím už viac ako **8 rokov** — značnú časť kariéry som robil ako **developer**, posledné roky pôsobím ako **Solutions Architect**. Mimo práce občas školím pre **Aj Ty v IT** kurz programovania v **Jave**.

Pokojne pridaj vetu, prečo ťa git baví a že dnes ideme spolu od úplného začiatku.

---

## Slajd 3 — Čo dnes spravíme *(úvod, ~8 min)*
**Hlavná správa:** dnes sa **zoznámime so základnými konceptami gitu**. Žiadna mágia — len pár jasných pojmov a jeden základný workflow, ktorý si rovno vyskúšame.

**Cieľ nie je** naučiť sa všetko, ale **pochopiť, čo git je, na čo a ako**.

**Štyri slová, ktoré dnes spoznáme:** `clone → commit → push → pull`.

**Ohraničenie:** branching a merge requesty dnes nebudú — to necháme na druhý workshop. Dnes držíme jednu líniu.

---

## Slajd 4 — Problém bez gitu *(~10 min)*
**Povedz:** Poznáte to? *(ukáž chaos kópií)* `projekt-final`, `projekt-final-v2`, `naozaj-final`, `od-janky`...

**Otázky do pléna:** Ktorá je tá pravá? Kto čo zmenil? Čo keby ste sa chceli vrátiť k verzii spred dvoch dní?

**Pointa:** Keď robíme kópie súborov, stratíme prehľad. Git to rieši inak — **nerobíme kópie**. Máme jednu pracovnú verziu a Git si pamätá jej historické stavy.

---

## Slajd 5 — Riešenie = jeden zdroj pravdy *(srdce modelu, ~3 min)*
**Povedz (kľúčová veta):** *„Git je ako časová os projektu — jeden spoločný zdroj pravdy, ktorý si pamätá celú históriu. Každý bod na osi je uložený stav, ku ktorému sa viem kedykoľvek vrátiť alebo sa pozrieť, čo sa vtedy zmenilo."*

**Ukáž os:** body sa objavujú postupne s popismi (prvá verzia → pridaná stránka → oprava textu → dnešný stav) — to je tá história.

**Zdôrazni:** žiadne kópie súborov. Tento obrázok časovej osi sa bude vracať celou prezentáciou.

---

## Slajd 6 — Git vs GitHub vs GitKraken *(pojmy, ~4 min)*
Najčastejší zmätok začiatočníkov — venuj tomu čas. Prejdi tri logá:

- **Git** = **systém na kontrolu verzií**. Žije na **tvojom počítači**.
- **GitHub** = **cloudová služba na ukladanie git repozitárov a zdieľanie s tímom**. (Analógia, ak treba: ako Google Drive, ale pre projekt.)
- **GitKraken** = **grafické rozhranie nad gitom** — appka, aby sme nemuseli písať príkazy.

**Zopakuj nahlas:** Nie sú to to isté. Sú to tri rôzne veci, ktoré spolupracujú.

---

## Slajd 7 — Repozitár *(pojmy, ~2 min)*
**Povedz:** Repozitár, skrátene „repo", je projekt, ktorý Git sleduje. Je to priečinok s tvojimi súbormi **a zároveň** celá história zmien, ktorá k nim patrí. Súbory aj história žijú spolu.

---

## Slajd 8 — Commit *(pojmy, ~5 min)*
**Povedz:** Commit je uložený balíček zmien s popisom.

**Najdôležitejšie rozlíšenie:** commit **nie je** obyčajný „save". Save uloží súbor. Commit uloží **významový krok v histórii** — bod na časovej osi, s vetou, čo a prečo sa zmenilo.

**Ukáž dobré vs zlé správy:**
- ✓ `Add my introduction`, `Fix typo in README` — budúce ja (aj kolegovia) hneď vie, čo sa stalo.
- ✗ `changes`, `update`, `stuff` — nepovie nič.

**Pre testerky pridaj:** dobrá história commitov ti neskôr pomôže nájsť, *kedy* a *prečo* sa niečo pokazilo.

---

## Slajd 9 — Tri oblasti gitu *(model, ~5 min)*
**Povedz:** Kým sa zmena uloží do histórie, prejde na tvojom počítači cez tri oblasti:
1. **Pracovný priečinok** (working directory) — súbory, ktoré práve upravuješ.
2. **Staging** (staging area) — sem vyberieš, čo presne pôjde do najbližšieho commitu. Môžeš tak uložiť aj len časť zmien.
3. **Repozitár** — história uložených commitov.

**Prechody:** `stage` = pridám zmenu do staging · `commit` = uložím pripravené do histórie.

**V GitKrakene:** stage = zaškrtnem súbor, commit = tlačidlo Commit. Netreba memorovať pojmy — dôležitý je **tok**: upravím → vyberiem do staging → uložím.

---

## Slajd 10 — Lokálne vs vzdialené *(model, ~3 min)*
**Ukáž diagram:** hore **GitHub** = vzdialené (remote) úložisko v cloude — jedna spoločná kópia projektu. Dole má **každá svoju lokálnu kópiu** na počítači (ty aj napr. kolegyňa).
- Chcem, aby moje commity videli ostatní → **push** (pošlem ich na GitHub).
- Chcem zmeny od ostatných → **pull** (stiahnem si ich z GitHubu).

**Zdôrazni:** push aj pull = pohyb **commitov (histórie)** medzi tvojím počítačom a GitHubom. (Mimochodom, `clone` na začiatku je presne to stiahnutie spoločnej kópie k sebe.)

---

## Slajd 11 — DEMO: clone *(hands-on, ~15 min)*
**Prepni do GitKrakenu.** Kroky:
1. Otvor GitKraken.
2. Prihlás sa do GitHubu.
3. **Clone** repo → vyber **`wta-a-24`**.
4. Otvor lokálny priečinok a ukáž, že súbory sú fyzicky na počítači.

**Veta:** *„Clone = zoberiem existujúci repozitár z GitHubu a vytvorím si jeho lokálnu kópiu na počítači."*

**Úloha:** každá si naklonuje `wta-a-24`. Počkaj, kým to majú všetky.

---

## Slajd 12 — DEMO: prvá zmena a commit *(hands-on, ~25 min blok)*
**Úloha pre každú:** uprav `about-me.md`:
```
# About me
Meno:
Obľúbený nápoj:
Jedna vec, ktorú sa chcem naučiť:
```
Potom v GitKrakene:
1. Vyber súbor do **staging** (zaškrtni ho).
2. Napíš **zmysluplnú** commit message, napr. `Add my introduction`.
3. **Commit.**

Ukáž, ako sa na časovej osi objaví **nový bod**.

**Pripomeň:** teraz je to uložené — ale **stále len na tvojom počítači**.

---

## Slajd 13 — DEMO: diff (až po commite) *(hands-on)*
**Teraz, keď už máš prvý commit:** uprav `about-me.md` ešte raz (napr. doplň nápoj). V GitKrakene sa súbor objaví ako **changed** a Git ukáže **diff voči poslednému commitu**.

**Vysvetli diff:** *„Diff je porovnanie starej a novej verzie. Zelené riadky sú pridané, červené odobrané alebo zmenené."*

**Pointa:** keď máš commit, Git ti presne ukáže, čo si **odvtedy** zmenila — to je tá história v akcii. (Preto má zmysel diff až teraz — bez commitu nie je voči čomu porovnávať.)

---

## Slajd 14 — DEMO: push *(hands-on, ~15 min)*
**Veta:** *„Commit = uložila som zmenu do histórie na svojom počítači. Push = poslala som túto históriu na GitHub."*

V GitKrakene ukáž, že lokálna vetva je **ahead** (má commit navyše). Daj **push**. Potom otvor repo na GitHube v prehliadači a ukáž, že zmena je **aj tam**.

**Aha-moment:** teraz to vidia ostatní.

---

## Slajd 15 — DEMO: pull *(hands-on, ~15 min)*
**Priprav situáciu:** ty (alebo druhý účet) zmeníš niečo na GitHube — napríklad pridáš riadok do `README.md`.

**Veta:** *„Pull = stiahnem si nové commity z GitHubu do svojho lokálneho repozitára."*

**Dôležité rozlíšenie:** pull **nie je** download súborov — je to stiahnutie **commitov/histórie**.

Workflow: *niekto zmenil remote → ja dám pull → mám to lokálne.*

---

## Slajd 16 — Celý kolobeh *(súhrn, ~5 min)*
**Klikaním** rozsvecuj body na osi: `clone` (mám projekt) → `edit` (upravím) → `commit` (uložím krok) → `push` (zdieľam) → `pull` (beriem zmeny ostatných) → a znova.

**Povedz:** Toto je celý dnešný kolobeh. *(Nechaj ich zopakovať vlastnými slovami.)*

---

## Slajd 17 — Slovníček *(súhrn, ~2 min)*
**Povedz:** Ak si z dneška zapamätáte len štyri slová a čo robia, splnili sme účel:
- `clone` — stiahnem projekt z GitHubu na počítač
- `commit` — uložím krok do histórie (lokálne)
- `push` — pošlem svoje commity na GitHub
- `pull` — stiahnem si commity ostatných

---

## Slajd 18 — Nabudúce *(teaser, ~2 min)*
**Povedz:** Dnes sme pracovali v jednej línii. Nabudúce si otvoríme vlastné **vetvy (branches)** — bezpečný priestor, kde si skúšaš zmeny bez toho, aby si zasiahla spoločnú verziu. Naučíme sa **merge requesty** (návrh zlúčenia späť) a ako riešiť **konflikty**.

**Povzbuď:** to najťažšie — mentálny model — máte už za sebou.

---

## Slajd 19 — Záver + otázky *(~10 min)*
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
| Úvod + predstavenie + demystifikácia | 1–3 | 10 |
| Problém bez gitu | 4–5 | 10 |
| Mentálny model | 6–10 | 20 |
| Clone | 11 | 15 |
| Zmena + commit | 12–13 | 25 |
| Push | 14 | 15 |
| Pull | 15 | 15 |
| Súhrn + otázky | 16–19 | 10 |
