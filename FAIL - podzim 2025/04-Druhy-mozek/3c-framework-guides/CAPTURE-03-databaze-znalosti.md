# Spravovat databáze osobních i týmových znalostí

## Základní informace

Strukturované úložiště pro klíčové projekty a oblasti — inspirováno principy GitLab Handbook.

**Proč na tom záleží:** Když má každý projekt své místo a jasnou strukturu, nový člověk se zorientuje za pár minut místo pár hodin. Nemusíte pamatovat, kde je, co — systém vám to řekne.

**Základní princip:** Když někdo přijde, musí najít vše, co potřebuje. Dokumentace není „set and forget„ — je to živý dokument, který se průběžně aktualizuje.

## Realistická očekávání

Váš první handbook nebo knowledge base může vypadat skvěle, ale velmi brzy zjistíte, že potřebuje změny. To je přesně správně — iterace podle skutečných potřeb je součástí procesu.

## Quick Win

Nechte si pomoct od AI vytvořit strukturu:

**Varianta 1 — Nadiktování:**
1. Otevřete AI (ChatGPT, Claude, Gemini)
2. Nadiktujte nebo napište: „Potřebuji strukturu pro [váš projekt/oblast]. Mám tyto soubory a složky..." (popište, co máte)
3. AI navrhne strukturu
4. Vytvořte ji v Notion/OneNote

**Varianta 2 — Screenshoty:**
1. Udělejte 2-3 screenshoty svých současných složek/souborů
2. Nahrajte do AI s promptem: „Navrhni lepší strukturu pro tuto dokumentaci„
3. AI analyzuje a navrhne organizaci
4. Implementujte v Notion/OneNote

Hotovo — máte AI-navrženou strukturu za pár minut!

## Inspirace: GitLab Handbook

**GitLab Handbook:** https://handbook.gitlab.com/
- Největší veřejný firemní handbook na světě
- Vše dokumentované, přístupné všem
- "Handbook first„ kultura — když se něco změní, nejdřív se aktualizuje handbook

**Jak postavit handbook za jeden den:** https://www.linkedin.com/posts/katerinadejmalova_za-jeden-den-jsme-tÃ©mÄ›Å™-bez-vÃ½vojÃ¡Å™skÃ½ch-activity-7389186766378790913-N8Yj
- Firemní handbook s AI chatem za 1 den
- Veřejné i citlivé dokumenty
- AI odpovídá na otázky typu "Jak si vyúčtuju služebku?„

**Video o GitLab Handbook:** https://www.youtube.com/watch?v=mqIMCB4zJyc

## Nástroje

### Pro týmovou dokumentaci

**Notion:**
- Databáze s tagy a relacemi
- Snadné propojování stránek
- Týmová spolupráce v reálném čase

**SharePoint:**
- Pro organizace s Microsoft 365
- Bezpečnost a oprávnění na úrovni enterprise
- Integrace s Teams a Outlookem

**Confluence:**
- Pro větší organizace
- Pokročilé workflow a schvalování
- Rozšířená správa oprávnění

**Google Keep:**
- Jednoduché, rychlé poznámky
- Skvělé pro týmové quick notes a sdílení
- Integrace s Google ekosystémem

**Microsoft Loop:**
- Kolaborativní komponenty a stránky
- Propojení s Microsoft 365
- Real-time spolupráce v Teams a Outlooku

### Pro osobní knowledge base

**OneNote:**
- Nekonečné stránky
- Propojené sekce
- Jednoduchá organizace

**Obsidian:**
- Backlinks a graf poznámek
- Lokální ukládání (máte kontrolu nad daty)
- Markdown formát

**Notion:**
- Funguje i pro osobní použití
- Databáze a filtry
- Mobilní aplikace

**Evernote:**
- Osvědčený nástroj pro osobní znalosti
- Výborný web clipper
- Tagy a notebooky pro organizaci

## Principy dobré organizace

### 1. Podle projektů/aktivit

Každý projekt má své místo. Nesklízej všechno do jedné složky "Různé„.

```
📁 Projekt XYZ
📁 Projekt ABC
📁 Marketing Q4
📁 Onboarding nových lidí
```

### 2. Přehlednost

Když někdo přijde poprvé, musí se zorientovat. To znamená:
- Jasné názvy složek a stránek
- Popis na začátku každé sekce: "Co je v této části„
- Navigace je viditelná

### 3. Popis a kontext

Každá sekce má vysvětlení, k čemu slouží. README nebo úvodní stránka vysvětlí:
- Co najdu v této části
- Pro koho je to určené
- Jak s tím pracovat

**Tip:** Toto může udělat AI za vás! Nahrajte strukturu do ChatGPT/Claude a požádejte: „Vytvořte popis pro každou složku — co obsahuje, k čemu slouží, kdo to používá."

### 4. Bohatý obsah

Nebojte se přidat různé formáty:
- Videa
- Prezentace
- Tabulky
- Obrázky
- Odkazy na externí zdroje

### 5. Max 3-4 úrovně hloubky

Pokud musíte klikat víc, než 3krát, abyste se dostali k informaci, je to moc hluboko. Restrukturujte.

❌ **Špatně:**
```
Projekty → Marketing → Kampaně → Q4 → Social → Instagram → Plány → Listopad → Post 1
```

✅ **Dobře:**
```
Marketing → Q4 Kampaně → Instagram listopad
```

### 6. Živý dokument

Handbook není „udělám a zapomenu„. Je to živý dokument:
- Průběžně aktualizujte
- Když se něco změní v procesu, změňte to v handbook
- Udělejte si reminder na pravidelné review (např. jednou za měsíc)

## Doporučená struktura

```
📁 Projekt XYZ
  📝 Co je tento projekt, hlavní cíle, odpovědné osoby
  ├─ 📄 README (Podrobný popis projektu, jak to funguje)
  ├─ 📁 Dokumentace
  │   📝 Technické návody, postupy a best practices
  │   ├─ Návody
  │   ├─ Best practices
  │   └─ FAQ
  ├─ 📁 Zápisy ze schůzek
  │   📝 Záznamy z projektových schůzek a rozhodnutí
  ├─ 📁 Prezentace a materiály
  │   📝 Prezentace, grafika, podklady pro klienty
  └─ 📁 Kontakty a zdroje
      📝 Klíčové kontakty, externí zdroje, odkazy
```

**Důležité:** 
- **README** je jako "domovská stránka„ projektu. Obsahuje:
  - Co je tento projekt v 2-3 větách
  - Proč na něm děláme
  - Kdo je za, co zodpovědný
  - Nejdůležitější odkazy

- **Popis nad složkami** (📝): Pokud je to poznámkový blok, přidejte krátký popis přímo nad nebo vedle každé složky, aby bylo jasné, co v ní je

## Příklad z praxe

HR manažerka vytvořila jednoduchý onboarding handbook v Notion. Má 5 hlavních sekcí: Úvod do firmy, První týden, Systémy a nástroje, Lidé a týmy, FAQ. Každá sekce má README s popisem. Když přijde nový člověk, pošle mu odkaz a 80% otázek už nemusí řešit osobně. První měsíc ušetřila několik hodin času tím, že nemusela odpovídat na stejné otázky dokola.

## Tipy na dokumentaci

**Matt Palmer's 8 rules for better docs:** https://mattpalmer.io/posts/8-rules-for-better-docs/

Aplikuj na README soubory:
- Piš pro začátečníky
- Ukazuj, neříkej (příklady > teorie)
- Jeden dokument = jedna věc
- Struktura je důležitější, než styl

**Pro AI pomoc:** Vezměte Matt Palmerův článek a dejte ho jako součást promptu:
```
Přečti si tyto principy dobré dokumentace: [vlož článek]

Podle těchto principů vytvoř README pro můj projekt [popis projektu].
Zahrň: účel, strukturu, jak začít, a příklady.
```
AI vytvoří dokumentaci podle osvědčených pravidel.

## Quick Action Guide

### Klíčové závěry

- Když někdo přijde, musí najít vše, co potřebuje
- Max 3-4 úrovně hloubky jako princip
- Nebojte se přidat různé formáty (video, prezentace, ne jen text)
- Dokumentace je živý dokument, ne „set and forget"

### Co nedělat (a, co místo toho)

- ❌ Nevytvářejte hluboké hierarchie (víc, než 3-4 úrovně). ✅ Udržujte strukturu plochou a logickou.
- ❌ Nezapomeňte na README/popis každé sekce. ✅ Každá část má vysvětlení „co je tady".
- ❌ Nedokumentujte jen jednou a zapomeňte. ✅ Průběžně aktualizujte podle změn.

### Začněte tady

1. Vyberte jeden důležitý projekt, který potřebuje dokumentaci
2. Vytvořte pro něj strukturu podle doporučeného vzoru výše
3. Napište README — co je projekt, kdo je za, co zodpovědný
4. Přidejte 3-5 nejdůležitějších dokumentů nebo odkazů
5. Otestujte: dejte to někomu jinému a sledujte, jestli se zorientuje
6. Upravte podle zpětné vazby