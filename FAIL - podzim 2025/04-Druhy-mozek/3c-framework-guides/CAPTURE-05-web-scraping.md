# Ovládat web scraping — hromadné stahování dat z webu

## Základní informace

Automatické stahování velkých objemů dat z webů místo manuálního kopírování.

**Proč na tom záleží:** Místo strávení hodin kopírováním dat z webu můžete mít všechno za pár minut. 200 LinkedIn profilů? 500 produktů z e-shopu? Konkurenční ceny? Scraping to udělá automaticky.

**Základní princip:** Použijte nejjednodušší nástroj, který zvládne úkol. Začněte s pluginy do prohlížeče, pokud to nejde, použij specialized nástroje. AI browser jen když nic jiného nefunguje.

## Realistická očekávání

Ne každý web půjde snadno scrapovat. Některé mají ochranu, některé se mění struktura. První scraping **nebude fungovat napoprvé** — to je normální. Může vám trvat hodinu ladění, než začne fungovat správně. Začněte s jednoduchými weby a postupně přidávejte složitější.

## Quick Win

1. Nainstalujte si browser extension pro web scraping (např. Data Miner, Web Scraper nebo Scraper)
2. Najděte si jednoduchou tabulku na webu (např. seznam firem)
3. Klikni na extension → Select data → Scrape
4. Exportuj do CSV
5. Hotovo - máte první scraping!

## Úrovně scrapingu

### 1. Pluginy do prohlížeče (nejjednodušší)

**Pro koho:** Začátečníci, jednorázové stahování, rychlé testy.

**Nástroje:**
- Browser extensions pro quick scraping
- Ideální pro jednorázové stažení
- Konkrétní doporučení: Scraper, Data Miner, Web Scraper

**Jak na to:**
1. Nainstalujte extension (např. Data Miner z Chrome Web Store)
2. Jdi na web s daty
3. Klikni na extension ikonu
4. „Select data" nebo „Auto-detect"
5. Preview výsledků
6. Export do CSV nebo Excel

**Kdy použít:** Když potřebujete rychle stáhnout data z jedné stránky nebo jedné tabulky. Není to na opakované použití nebo složité weby.

### 2. Specialized nástroje (doporučená cesta)

**Pro koho:** Pro pravidelné scraping, složitější weby, automatizaci.

**Doporučené nástroje z našeho přehledu:**

#### Firecrawl (doporučeno)

**Co to je:** Moderní API pro crawling webů a převod stránek do formátu přátelského pro AI s automatickým čištěním obsahu.

**Kdy použít:** Když připravuješ data pro AI modely, potřebujete čistý text bez HTML noise, nebo chcete vytěžit celé weby strukturovaně.

**Jak to funguje:**
- API nebo Python/JS knihovna
- Automaticky čistí HTML a vrací clean markdown
- Ideální pro RAG systémy a AI zpracování

**Web:** https://www.firecrawl.dev

#### Exa (doporučeno)

**Co to je:** AI-powered vyhledávač navržený speciálně pro získávání strukturovaných dat z webu pro AI aplikace.

**Kdy použít:** Když potřebujete najít a stáhnout specifický typ obsahu z mnoha webů pomocí natural language queries (např. „najdi všechny články o AI z posledního měsíce").

**Jak to funguje:**
- API přístup s natural language dotazy
- AI-enhanced vyhledávání a extrakce
- Vrací strukturovaná data připravená pro AI

**Web:** https://exa.ai

#### Apify (doporučeno)

**Co to je:** Platforma pro web scraping a automatizaci s hotovými „actory" pro stahování dat z Instagramu, LinkedInu, Google Maps a dalších populárních služeb.

**Kdy použít:** Když potřebujete scrapovat populární weby (LinkedIn, e-shopy, sociální sítě) — už má hotové skripty, nemusíš nic programovat.

**Jak to funguje:**
- Najdeš „Actor" pro konkrétní web (např. „LinkedIn Profile Scraper")
- Nastavíš parametry (co chcete stáhnout)
- Spustíš a dostanete data

**Příklad:**
1. Jdi na Apify Store (https://apify.com)
2. Najděte „LinkedIn Company Scraper"
3. Zadej URL firem nebo search kritéria
4. Spusťte Actor
5. Za pár minut máte CSV se všemi daty

**Web:** https://apify.com

#### Phantombuster (specializovaně pro LinkedIn)

**Co to je:** Automatizační platforma specializovaná na sociální sítě, zejména LinkedIn scraping a outreach.

**Kdy použít:** Když potřebujete vytěžit data z LinkedInu (profily, kontakty, company info) nebo automatizovat LinkedIn aktivity.

**Jak to funguje:**
- Hotové „Phantomy" pro různé LinkedIn use cases
- Export kontaktů, sledování profilů, messaging
- Bezpečné rate limiting pro dodržení LinkedIn pravidel

**Web:** https://phantombuster.com

### 3. AI prohlížeče a AI coding nástroje (pokročilé)

**Pro koho:** Když standardní nástroje selhávají, potřebujete custom řešení nebo automatizaci.

⚠️ **Bezpečnostní upozornění:** AI prohlížeče mají přístup ke všemu, co děláte online. Před použitím v práci si ověřte kompatibilitu s bezpečnostními pravidly vaší firmy a nikdy nesdílejte citlivá data.

**AI prohlížeče z našeho přehledu:**

- **Comet** — AI-first prohlížeč zaměřený na produktivitu s vestavěným asistentem (https://www.comeet.com)
- **Dia Browser** — Inteligentní organizace a práce s webovým obsahem (https://www.diabrowser.com)
- **OpenAI Atlas** — AI prohlížeč od OpenAI s pokročilými konverzačními schopnostmi (https://openai.com/index/introducing-chatgpt-atlas/)
- **Cursor (Browser mode)** — Rozšíření AI code editoru pro inteligentní browsing (https://www.cursor.com)

**Jak AI nástroje použít pro scraping:**

Místo psaní vlastního kódu **nech AI napsat celý script za tebe**. Řekneš AI (ChatGPT, Claude, Cursor): „Napište mi script který stáhne X z Y" a AI napíše funkční Python/JavaScript kód.

**Kdy použít:**
- Nestandardní web, který nepodporují běžné nástroje
- Potřebuješ velmi specifické zpracování dat
- Chceš automatizovat scraping

**Příklad prompt:**

```
Napište Python script který:
1. Projde seznam URL z CSV souboru
2. Z každé stránky extrahuje nadpis a hlavní text
3. Uloží výsledky do nového CSV
4. Obsahuje error handling a progress bar
```

AI napíše kompletní funkční script, ty ho jen spustíš.

## Proces scrapingu

### Krok 1: Identifikujte zdroj

- Jaký web chcete scrapovat?
- Kolik stránek?
- Jak často potřebujete aktualizovat data?

### Krok 2: Zkontrolujte legalitu

**Důležité:** Než začneš scrapovat, zkontroluj:

- **robots.txt** — co web povoluje scrapovat
  - Příklad: `https://example.com/robots.txt`
- **Terms of Service** — pravidla webu
- **Rate limiting** — nespamuj servery

**Pravidlo:** Pokud web má API, použij API místo scrapingu.

### Krok 3: Vyberte nástroj

**Rozhodovací strom:**
1. Je to jednorázové? → Browser plugin
2. Je to populární web? → Apify (zkontroluj, jestli už má Actor)
3. Potřebuješ AI-ready data? → Firecrawl
4. Nestandardní požadavek? → Exa nebo AI browser

### Krok 4: Implementace

**Pro pluginy:** Viz Quick Win výše

**Pro Apify:**
1. Vytvořte účet na Apify (free tier dostupný)
2. Najděte Actor pro váš use case
3. Nastavte input parameters
4. Spusťte a stáhněte výsledky

**Pro Firecrawl/Exa:**
1. Získej API klíč
2. Požádej AI (ChatGPT/Claude): „Napište mi Python script který použije Firecrawl API k stažení dat z těchto URL"
3. AI napíše celý funkční kód
4. Spusťte script

### Krok 5: Testujte

- Začněte s malým vzorkem (3-5 stránek)
- Zkontrolujte kvalitu dat
- Upravte nastavení pokud potřeba
- Pak spusť na plný dataset

## Příklad z praxe

Recruiter potřeboval kontakty na 200 HR manažerů z LinkedIn. Použil Apify actor „LinkedIn Profile Scraper", zadal search kritéria, za 10 minut měl CSV se všemi kontakty včetně emailů a pozic. Manuálně by to bylo 8 hodin práce.

**Co konkrétně udělal:**
1. Apify.com → Store → „LinkedIn Profile Scraper"
2. Input: „HR Manager" + „Prague" + „Tech industry"
3. Nastavení: Scrape first 200 results
4. Start → 10 minut čekání
5. Download CSV s 200 profily

## Use cases

### LinkedIn profily → CRM

**Nástroj:** Apify LinkedIn Scraper
**Proces:** Search kritéria → export → import do CRM
**Čas:** 10 minut vs. 10 hodin manuálně

### E-shopy → monitoring cen

**Nástroj:** Apify E-commerce scrapers
**Proces:** List konkurenčních produktů → pravidelný scraping → alert na změny
**Kdy použít:** Chceš sledovat ceny konkurence

### Odvětvové weby → knowledge base

**Nástroj:** Firecrawl (pro AI-ready markdown)
**Proces:** Seznam zajímavých článků → clean text → do knowledge base
**Kdy použít:** Stavíš AI chatbota potřebujícího aktuální info z webů

### Veřejné databáze → analýza

**Nástroj:** Custom script (AI browser)
**Proces:** AI napíše script → scrape → zpracování v Pandas/Excel
**Kdy použít:** Nestandardní web, specifická potřeba

## Nechte AI napsat scraping script

Když žádný hotový nástroj neexistuje nebo nefunguje, **nech AI napsat celý script za tebe**.

**Příklad promptu pro AI:**

```
Napište Python script který:
1. Otevře seznam URL z products.csv
2. Z každé stránky extrahuje: název produktu, cenu, dostupnost
3. Zpracuje pagination (až 10 stránek)
4. Uloží do results.csv
5. Zahrnuje error handling a progress bar

Zeptej se mě, jak to udělat nejlíp a navrhni optimální řešení.
```

AI napíše kompletní funkční script. Ty ho jen spustíš.

## Quick Action Guide

### Klíčové závěry

- Vždy kontroluj legalitu (robots.txt, terms of service)
- **Postupnost:** Začněte s browser pluginy → specialized nástroje (Apify, Firecrawl) → nech AI napsat custom script
- **Nechte AI psát kód** — nepiš vlastní scraper jako první krok
- Respektuj rate limity (nespamuj servery)
- Nebude fungovat napoprvé — testuj na malém vzorku

### Co nedělat (a, co místo toho)

- ❌ Nescrapuj bez kontroly legality. ✅ Zkontrolujte robots.txt a terms of service.
- ❌ Neptej se „dá se to scrapovat?" ✅ Zkuste browser plugin, většinou ano.
- ❌ Nepiš vlastní scraper jako první krok. ✅ Zkontrolujte jestli už existuje (Apify Store).

### Začněte tady

1. Identifikujte konkrétní web a data, co potřebujete
2. Zkontrolujte robots.txt webu
3. Pro rychlý test: browser extension na pár stránkách
4. Pro větší objem: Apify Store → najdi Actor
5. Když nic neexistuje: Firecrawl API nebo AI browser
6. Vždy testuj na malém vzorku před full scraping