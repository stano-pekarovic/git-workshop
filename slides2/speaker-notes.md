# Speaker script — Git Workshop 2 (vetvenie a spolupráca)

> Podklad k prezentácii `slides2/index.html`. Po slajdoch.
> Ovládanie: **← →** / medzerník · **S** = poznámky v deku · **F** = fullscreen.
> Publikum: ženy z testerskej akadémie (WTA-A-24), majú za sebou Workshop 1 (clone/commit/push/pull + že rôzne súbory git spojí bez problému).
> Celkový čas ~2h. **Oblúk dňa: od chaosu (konflikt) k poriadku (branch → merge → pull request).** Každý koncept hneď vyskúšame.

---

## Slajd 1 — Titulka *(úvod, ~1 min)*
Vitajte späť. Minule základný workflow + že rôzne súbory git spojí sám. Dnes nadviažeme: čo keď meníte to isté miesto, a ako si v tíme nešliapať po prácach.

## Slajd 2 — Rýchle zopakovanie *(~10 min)*
Nechaj ich odpovedať **vlastnými slovami**. Správne: commit = uložený krok (+ popis); commit vs push = lokálne vs. na GitHub; remote = vzdialené úložisko; pull = stiahnem zmeny ostatných. Na záver pripomeň: **rôzne súbory git spojil bez problému** — to nás dovedie k dnešku.

## Slajd 3 — Čo dnes prejdeme *(~2 min)*
Oblúk: najprv **chaos** (konflikt + ako ho vyriešiť), potom **poriadok** (vetvy, merge, pull request). Dôraz: každú tému si **hneď vyskúšame**.

---

## Slajd 4 — Konflikt: kedy *(konflikt blok, ~25 min)*
Nadviaž na WS1: rôzne súbory = git ich spojil sám. Ale **ten istý riadok v tom istom súbore**? Git nevie rozhodnúť → spýta sa teba. Zdôrazni: **konflikt nie je chyba**, je to rozhodnutie pre človeka. Toto je ten „chaos", ktorý nás motivuje k vetvám a PR.

## Slajd 5 — Konflikt: ako vyzerá
Git vloží do súboru **značky**: hore (`<<<<`) tvoja verzia, dole (`>>>>`) verzia kolegyne, oddelené `=====`. Úloha: **rozhodni → zmaž značky → nechaj správny obsah → ulož → commit.** GitKraken má aj vizuálny nástroj (klikáš, ktorú verziu chceš).

## Slajd 6 — DEMO: vyrieš konflikt *(vo dvojiciach)*
Bez vetiev, rovno na main (nadväzuje na WS1):
1. Obe v páre upravte **ten istý riadok** v rovnakom súbore (napr. `about-me.md`).
2. Jedna **commit + push**.
3. Druhá **commit**, skúsi **push** → GitKraken vypýta najprv **pull** → pri pulle **konflikt**.
4. Otvor konfliktný súbor → vyber/skombinuj verziu → ulož → commit → push.

> Naschvál ten „chaos" — vzápätí ukážeme poriadok (vetvy, PR).

---

## Slajd 7 — Branch = bezpečná línia *(vetvy blok, ~20 min)*
Z konfliktu plynie motivácia: keď všetci píšu naraz do main, stúpame si na nohy. Riešenie = **vetva**. main = oficiálna spoločná verzia; keď chcem skúsiť novú vec, **odbočím si vlastnú vetvu** — paralelnú líniu, kde robím bez zásahu do main. (Ak treba: branch = pomenovaný ukazovateľ na commit, nie fyzická kópia.)

## Slajd 8 — Dve vetvy, dva účely
**main** = stabilná spoločná verzia, nepracujem do nej priamo. **feature vetva** = moja pracovná línia, nové commity idú sem; kým robím, main stojí. Názvy výstižne: `add-about-page`, `fix-header-typo` — krátko, bez diakritiky a medzier.

## Slajd 9 — DEMO: vytvor vetvu + commit + push
GitKraken: na `main` **pull** → **Branch** `add-tvojemeno` → uprav súbor → stage → commit → ukáž, že vetva sa posunula a main stojí → **push** vetvy (vznikne na GitHube). **Túto vetvu si necháme na pull request.**

---

## Slajd 10 — Merge: koncept *(merge blok, ~15 min)*
**Merge = zlúčenie vetvy späť do main.** Po dokončení spojíme vetvu do main, zmena je v spoločnej verzii. **Callback:** ak vetva a main zmenili to isté miesto, merge spôsobí konflikt — ale ten **už vieš vyriešiť**. Väčšinou prebehne hladko.

## Slajd 11 — DEMO: merge vetvy do main
Najjednoduchšie ukáž na svojej obrazovke: **checkout `main`** → pravý klik na vetvu → **Merge into main**. V grafe vidno spojenie línií. Voliteľne nech si skúsia.
> ⚠️ Choreografia: ak vetvu zmergujú lokálne, na PR demo (ďalej) použite **novú malú vetvu** — tú istú nepoužívajte dvakrát.

---

## Slajd 12 — Pull request: koncept *(PR blok, ~25 min)*
**PR = ten istý merge, ale cez GitHub a s review.** Návrh „zlúčte moju vetvu do main" + miesto, kde tím vidí zmenu, okomentuje ju a schváli **pred** zlúčením. Lokálny merge je rýchly pre seba; PR pridáva tímovú kontrolu.

## Slajd 13 — Načo je PR
- **Review** — niekto sa pozrie skôr, než to ide do main.
- **Spätná väzba a kvalita** — priestor navrhnúť úpravy.
- **História „prečo"** — zostane zapísané, čo a načo sa menilo.
> V reálnych tímoch ide do main takmer všetko cez PR.

## Slajd 14 — DEMO: otvor PR, review, zlúč
(novou malou) vetvou: vytvor → commit → push. GitHub repo **wta-a-24** → **Compare & pull request** → názov + popis (čo a prečo) → **Create**. Ukáž **Files changed**. Vo dvojiciach si PR **navzájom pozrite (review)** → **Merge pull request** → **Confirm**. Nakoniec GitKraken: **pull** na main.

---

## Slajd 15 — Tímový workflow *(súhrn, ~5 min)*
Klikaním rozsvecuj: **pull** → **branch** → **commit** → **push** → **PR** (návrh + review) → **merge**. A pri ďalšej úlohe zase od začiatku. Keď cestou narazíš na konflikt, vieš ho vyriešiť. Takto fungujú reálne tímy.

## Slajd 16 — Pár tímových zvykov *(~2 min)*
- **Jedna vetva = jedna téma.**
- **Pull main pred novou vetvou** (vychádzaj z aktuálu → menej konfliktov).
- **Do main cez PR**, nie priamo.
- **Po merge zmaž vetvu** — poriadok v repe.

## Slajd 17 — Slovníček *(~2 min)*
- `conflict` — dve verzie toho istého miesta, rozhodneš ty.
- `branch` — vlastná bezpečná pracovná línia.
- `merge` — zlúčenie vetvy späť do main.
- `pull request` — merge cez GitHub + miesto na review.

## Slajd 18 — Záver + otázky *(~10 min)*
Spýtaj sa vlastnými slovami: Kedy vzniká konflikt a ako ho vyriešiš? Čo je branch a načo? Čím sa líši merge od pull requestu? Pochváľ — zvládli základný aj tímový git. Pripomeň materiály (GitHub Pages, INSTALL).

---

### Orientačný timing
| Blok | Slajdy | Min |
|---|---|---|
| Zopakovanie + úvod | 1–3 | 12 |
| Konflikt (koncept + demo) | 4–6 | 25 |
| Branch (koncept + demo) | 7–9 | 20 |
| Merge (koncept + demo) | 10–11 | 15 |
| Pull request (koncept + demo) | 12–14 | 25 |
| Workflow + zvyky + zhrnutie | 15–18 | 13 |
