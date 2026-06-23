# Speaker script — Git Workshop 2 (vetvenie a spolupráca)

> Podklad k prezentácii `slides2/index.html`. Po slajdoch.
> Ovládanie: **← →** / medzerník · **S** = poznámky v deku · **F** = fullscreen.
> Publikum: ženy z testerskej akadémie (WTA-A-24), majú za sebou Workshop 1 (clone/commit/push/pull).
> Celkový čas ~2h. Cieľ: pochopiť **vetvenie a tímový workflow** — branch, pull request, merge, konflikt.

---

## Slajd 1 — Titulka *(úvod, ~1 min)*
Vitajte späť. Minule sme zvládli základný workflow. Dnes pridáme **tímový rozmer**: vetvenie, pull requesty, merge a konflikty.

## Slajd 2 — Rýchle zopakovanie *(~10 min)*
Nechaj ich odpovedať **vlastnými slovami**, neodpovedaj hneď. Správne:
- **commit** = uložený krok v histórii (+ popis).
- **commit vs push** = commit je lokálne, push pošle na GitHub.
- **remote** = vzdialené úložisko (GitHub).
- **pull** = stiahnem commity ostatných.

## Slajd 3 — Čo dnes pridáme *(~2 min)*
Nad rámec základov: `branch → commit → push → pull request → merge`, plus riešenie konfliktov. Cieľ: vedieť bezpečne pracovať vo viacerých naraz.

## Slajd 4 — Prečo nie všetko priamo do main *(vetvy, ~3 min)*
Minule sme išli v jednej línii — fajn, kým si sama. V tíme: ak všetci píšu naraz do spoločnej verzie, rozbijú si prácu alebo tam pristane nedokončené. **main má ostať stabilná.** Potrebujeme bezpečný priestor.

## Slajd 5 — Branch = bezpečná línia *(~20 min blok)*
Kľúčový mentálny model. **main** = oficiálna spoločná verzia. Keď chcem skúsiť novú vec, **odbočím si vlastnú vetvu (branch)** — paralelnú časovú os. Tam robím bez zásahu do main. Keď je hotovo, navrhnem zlúčenie späť. *(Technickejšie, len ak treba: branch = pomenovaný ukazovateľ na commit.)*

## Slajd 6 — Dve vetvy, dva účely
**main** = stabilná spoločná verzia, nepracujem do nej priamo. **feature vetva** = moja pracovná línia, nové commity idú sem. Kým robím na vetve, main stojí v bezpečí.

## Slajd 7 — Názvy vetiev
Výstižný názov podľa toho, čo na vetve robím (`add-about-page`, `fix-header-typo`). Krátko, bez diakritiky a medzier — tím sa ľahšie orientuje.

## Slajd 8 — DEMO: vytvor vetvu *(~20 min blok)*
GitKraken: najprv **pull na main** (najnovšie), potom **Branch** → pomenuj `add-tvojemeno`. Každá si vytvorí vlastnú vetvu v repe **wta-a-24**.

## Slajd 9 — DEMO: commit na vetve + push
Uprav súbor (napr. `about-me.md`), stage, commit — ako minule. Ukáž v grafe, že **vetva sa posunula**, main stojí. Potom **push** vetvy → vznikne na GitHube.

## Slajd 10 — Pull request *(~25 min blok)*
**PR = návrh „zlúčte moju vetvu do main"** + miesto, kde tím vidí zmenu, okomentuje ju, navrhne úpravy a schváli. Nie je to len tlačidlo — je to priestor na **spätnú väzbu pred** tým, než sa zmena dostane do spoločnej verzie.

## Slajd 11 — Načo je PR
- **Review** — niekto sa pozrie skôr, než to ide do main.
- **Spätná väzba a kvalita** — priestor navrhnúť úpravy.
- **História „prečo"** — zostane zapísané, čo a načo sa menilo.

## Slajd 12 — DEMO: otvor PR
Po pushi vetvy: GitHub repo **wta-a-24** → žltý pruh **Compare & pull request** → názov + popis (čo a prečo) → **Create pull request**. Ukáž záložku **Files changed** (diff vetvy).

## Slajd 13 — Merge *(~15 min)*
**Merge = zlúčenie.** Po schválení PR klikneš **Merge** → vetva sa spojí do main, tvoja práca je v spoločnej verzii. Po merge si daj lokálne **pull na main** (a vetvu môžeš zmazať).

## Slajd 14 — DEMO: merge PR
GitHub: **Merge pull request** → **Confirm**. Ukáž, že zmena je na main. Voliteľne **Delete branch**. Potom GitKraken: **pull** na main.

## Slajd 15 — Konflikt: kedy *(~25 min blok)*
Konflikt vzniká, keď **dvaja zmenia to isté miesto v tom istom súbore**. Git nevie rozhodnúť, ktorá verzia je správna → spýta sa teba. **Nie je to chyba.** Pripomeň: rôzne súbory git spojí sám (z minula), konflikt je len pri rovnakom mieste.

## Slajd 16 — Ako konflikt vyzerá
Git vloží do súboru **značky**: hore (`<<<<<<<`) tvoja verzia, dole (`>>>>>>>`) verzia kolegyne, oddelené `=======`. Úloha: **rozhodni → zmaž značky → nechaj správny obsah → ulož → commit.** GitKraken na to má aj vizuálny nástroj.

## Slajd 17 — DEMO: vyrieš konflikt
Dve z vás zmeňte **ten istý riadok**. Pri merge GitKraken nahlási konflikt → otvor súbor → vyber/skombinuj verziu → ulož → commit. Nechaj ich vyskúšať **vo dvojiciach**.

## Slajd 18 — Tímový workflow *(súhrn, ~5 min)*
Klikaním rozsvecuj: **pull** (najnovší main) → **branch** (vlastná vetva) → **commit** → **push** → **PR** (návrh + review) → **merge** (do main). A pri ďalšej úlohe zase od začiatku. Presne takto fungujú reálne tímy.

## Slajd 19 — Pár tímových zvykov *(~2 min)*
- **Jedna vetva = jedna téma** (nemiešaj nesúvisiace zmeny).
- **Pull main pred novou vetvou** (vychádzaj z aktuálu).
- **Do main cez PR**, nie priamo.
- **Po merge zmaž vetvu** — poriadok v repe.

## Slajd 20 — Slovníček *(~2 min)*
- `branch` — vlastná bezpečná pracovná línia.
- `pull request` — návrh zlúčiť vetvu do main + miesto na review.
- `merge` — zlúčenie vetvy späť do main.
- `conflict` — dve verzie toho istého miesta, rozhodneš ty.

## Slajd 21 — Záver + otázky *(~10 min)*
Spýtaj sa vlastnými slovami: Čo je branch a načo? Čo je pull request? Kedy vzniká konflikt? Pochváľ ich — zvládli základný aj tímový git. Pripomeň materiály (GitHub Pages, INSTALL).

---

### Orientačný timing (zo osnovy)
| Blok | Slajdy | Min |
|---|---|---|
| Zopakovanie | 1–3 | 10 |
| Branch ako bezpečný priestor | 4–7 | 20 |
| Vytvorenie branche (demo) | 8–9 | 20 |
| Pull request | 10–12 | 25 |
| Merge | 13–14 | 15 |
| Konflikt | 15–17 | 25 |
| Tímový workflow + zhrnutie | 18–21 | 10 |
