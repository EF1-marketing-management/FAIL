# Súhrn Stories - Spolupráca s AI

Toto je zbierka 21 príbehov o tom, ako sme spolu s AI riešili rôzne úlohy. Každý príbeh je jedna konkrétna úloha, ktorú sme dokončili.

---

## 📚 Vzdelávanie a Skills (5 príbehov)

Tieto príbehy sú o vytváraní a vylepšovaní vzdelávacieho obsahu a systémov.

1. **JSON briefy pre tímy** - Vytvorili sme šesť prispôsobených briefov pre rôzne tímy (CEO, HR, IT, Marketing, Finance, Management). Hlavne sme sa snažili, aby boli konzistentné a mali správne diakritiky.

2. **Optimalizácia promptov** - Aimee AI Coach mal v promptoch veľa duplikátov. Upravili sme to tak, aby bol systém modulárny s jasnou hierarchiou: Core > Mode > Tone.

3. **Transformácia skillov** - Mali sme 7 markdown dokumentov so skillmi, ktoré sme premenili na štruktúrované JSON súbory podľa Aimee Skills Framework. Každý skill má teraz príklady a micro-learning tipy.

4. **Expertný skill** - Vytvorili sme najvyššiu úroveň skillu "Prompt Engineering Pro" s 15 príkladmi a 20 tipmi. Počas toho sme opravili nekonzistentné ID v súboroch a prepojili všetky tri úrovne skillov.

5. **Pokročilé promptovanie** - Vytvorili sme intermediate skill s 20 príkladmi, ktoré pokrývajú techniky ako few-shot prompting, chain-of-thought, decomposition a podobne.

---

## 🔄 Spracovanie a Transformácia Dát (4 príbehy)

Tieto príbehy sú o konverzii a spracovaní dát medzi rôznymi formátmi.

1. **Export AI analýz** - Mali sme CSV s analýzami pre 376+ používateľov a 28 tímov. Vytvorili sme skript, ktorý to premenil na čitateľné markdown súbory.

2. **CSV do Markdown** - Transformovali sme CSV s 68 riadkami komplexných JSON dát do 54 markdown súborov. Skript automaticky určil jazyk a naformátoval všetky sekcie.

3. **Zjednotenie popisov** - Popisy členstiev boli roztrúsené po rôznych miestach. Zjednotili sme ich a aktualizovali v Stripe produktoch pomocou mapovania cez metadata.

4. **Tímový playbook** - Transformovali sme individuálny AI adoption playbook na tímovú úroveň. Adaptovali sme 5-úrovňový framework a 7-krokový proces pre organizačné AI transformácie.

---

## 🤖 Automatizácia (3 príbehy)

Tieto príbehy sú o automatizácii manuálnych úloh.

1. **Automatizácia reportov** - Každý mesiac sa museli manuálne sťahovať reporty z Multisport portálu. Napísali sme skript, ktorý to robí automaticky pre obe pobočky pomocou Playwright.

2. **Stiahnutie webstránky** - Potrebovali sme kompletnú kópiu webstránky listenlabs.ai pre offline analýzu. Stiahli sme všetko - HTML, CSS, fonty, obrázky, animácie pomocou wget.

3. **Odstránenie pozadia z obrázkov** - Stiahli sme 28 obrázkov fitness vybavenia a pomocou AI (rembg s u2net modelom) sme im odstránili pozadie.

---

## 📊 Analýza (2 príbehy)

Tieto príbehy sú o analýze dát a zisťovaní insights.

1. **Analýza use case-ov** - Prešli sme cez 3965 scenárov od používateľov, vytvorili sme z nich taxonómiu a vypočítali sme, čo sa používa najčastejšie. To pomohlo pri rozhodnutiach pre marketing a produkt.

2. **Analýza reklamnej kampane** - Chceli sme vedieť, či reklamy fungujú. Analyzovali sme predajnosť pred a po spustení kampane pre dve pobočky (Příbram a Chodov).

---

## 💻 Vývoj Aplikácií (2 príbehy)

Tieto príbehy sú o vytváraní nových aplikácií a systémov.

1. **Rezervačný systém** - Navrhli sme kompletný systém na rezervácie osobných tréningov. Vytvorili sme 21 sekvenčných promptov pre Lovable, ktoré pokrývajú rezervácie, Stripe platby a synchronizáciu s Google Calendarom.

2. **UI style guide** - Potrebovali sme design systém pre nový projekt. Analyzovali sme existujúcu METAGYM webstránku a extrahovali sme z nej farby, fonty a štýly.

---

## ⚙️ Optimalizácia a Refaktoring (5 príbehov)

Tieto príbehy sú o vylepšovaní a čistení existujúcich projektov.

1. **Standardizácia súborov** - Zistili sme, že niektoré skill config súbory nemali referencie na obrázky. Pridali sme ich, aby všetko bolo konzistentné.

2. **Čistenie Multisport projektu** - Projekt bol plný duplikátov a starých súborov. Vyčistili sme ho na jednu čistú FastAPI aplikáciu, automatizovali sme reporty a doplnili sme kontaktné údaje do výstupov.

3. **Clean verzia pre lokálny vývoj** - Vytvorili sme verziu projektu bez Docker závislostí, ktorá sa dá jednoducho spustiť lokálne. Pridali sme dokumentáciu a automatizovaný setup skript.

4. **Optimalizácia cache** - Aplikácia sťahovala Retool dáta pre každú pobočku zvlášť, hoci dáta boli rovnaké. Implementovali sme cache, čo znížilo čas spracovania z 90-180 sekúnd na 30-60 sekúnd.

5. **Zlúčenie n8n workflow** - Mali sme dva komplexné workflow, ktoré sme zlúčili do jedného. Zachovali sme orchestráciu z prvého a implementovali sme analýzu z druhého.

---

## Čo sa tu deje?

Celkovo je to **21 príbehov** z obdobia **september 2024 - november 2025**.

**Najčastejšie scenáre:**
- **Optimalizácia a Refaktoring** (5 príbehov) - vylepšovanie existujúcich projektov
- **Vzdelávanie a Skills** (5 príbehov) - vytváranie vzdelávacieho obsahu
- **Spracovanie dát** (4 príbehy) - konverzia a transformácia dát
- **Automatizácia** (3 príbehy) - nahradenie manuálnej práce
- **Analýza** (2 príbehy) - zisťovanie insights z dát
- **Vývoj aplikácií** (2 príbehy) - vytváranie nových systémov

Všetky tieto príbehy majú spoločné to, že sme použili AI ako partnera pri riešení konkrétnych úloh - od analýzy dát cez automatizáciu až po vytváranie nových systémov.
