# Postavit automatizaci, která pravidelně zpracovává data za vás

## Obecné informace

Čistě automatizace — **všechno, co se dá dělat manuálně, se dá automatizovat**. Trigger (spouštěč) → AI zpracování → Automatická akce. Běží bez tebe, v pozadí, pravidelně.

**Co je trigger (spouštěč)?** Událost, která automaticky spustí workflow. Může to být čas (každý den v 9:00), akce (nový email, nový soubor), nebo změna dat (nový řádek v tabulce).

**Proč na tom záleží:** Pravidelné úkoly (monitoring, zpracování emailů, reporting) můžete pustit z hlavy. Automatizace je udělá bez vašeho zásahu.

**Základní princip:** Identifikujte pravidelnou činnost → Zkuste manuálně 2-3× → Navrhni automatizaci → Implementujte → Monitoruj.

## ⚠️ Realistická očekávání

První automatizace párkrát selže, než začne běžet stabilně. Triggery nefungují, API mění formáty, ošetření chyb (error handling) chybí. Je normální strávit 4-6 hodin, než máte robustní automatizaci. Ale pak běží měsíce bez zásahu!

## 🚀 Quick Win

1. Vyberte si automatizační nástroj (pokud to zatím neděláš, zkus **Relay.app** — je nejjednodušší)
2. Vytvořte jednoduchou automatizaci na něčem, co děláte pravidelně
3. Aktivuj workflow a vyzkoušej zda funguje
4. Sledujte první spuštění a uprav pokud je potřeba
5. Hotovo — máte první automatizaci!

## Doporučené nástroje

### Relay.app (doporučeno pro začátek)

**Proč Relay:**
- AI-enhanced automatizace
- Nejjednodušší drag & drop
- Vestavěné AI kroky
- Ideální pro začátečníky

**Free plán:**
- Základní automatizace
- Omezené AI kroky

**Kdy použít:** Chceš začít s automatizací a potřebujete něco jednoduchého s AI podporou.

### Make.com

**Proč Make:**
- Vizuální workflow builder
- Tisíce integrací
- Pokročilejší workflows
- Více kontroly nad logikou

**Free plán:**
- 1000 operací měsíčně
- Základní moduly

**Kdy použít:** Složitější workflows s více podmínkami, větvemi a pokročilou logikou.

### Power Automate

**Proč Power Automate:**
- Pro Microsoft ekosystém
- Nativní integrace s Teams, Outlook, SharePoint
- Enterprise features

**Kdy použít:** Pracuješ primárně s Microsoft 365 nástroji nebo potřebujete enterprise řešení.

### N8N

**Proč N8N:**
- Open-source a self-hosted možnost
- Velká flexibilita
- Vlastní integrace a kód
- Kontrola nad daty

**Kdy použít:** Potřebuješ maximální kontrolu, vlastní hosting nebo specifické custom integrace.

## Proces krok za krokem

### 1. Identifikujte pravidelnou činnost

Co děláte opakovaně?
- Každé ráno checknout emaily a vytřídít
- Týdně vytvořit report
- Denně stáhnout data z webu
- Po každém meetingu udělat zápis

### 2. Zkuste to nejdřív ručně

**Důležité:** Udělejte 2-3× manuálně
- Pochop všechny kroky
- Identifikujte, co se opakuje
- Najděte vzor
- **Vylaďte prompty pro AI kroky** — v automatizaci budete muset vložit prompt do AI kroku, takže je mnohem lepší ho nejdřív otestovat a vyladit ručně, než ladit v automatizaci

### 3. Navrhni automatizaci

**Struktura:**
```
TRIGGER (Co spustí workflow)
  ↓
AI KROK 1 (První zpracování)
  ↓
PODMÍNKA (Rozhodnutí)
  ↓
AI KROK 2 (Další zpracování)
  ↓
AKCE (Výsledek)
```

**Příklad — Email processing:**
```
TRIGGER: Nový email přijde
  ↓
AI: Kategorizuj (zákazník/dodavatel/spam)
  ↓
PODMÍNKA: Pokud kategorie = zákazník
  ↓
AI: Extrahuj info (jméno, firma, požadavek)
  ↓
AI: Vygeneruj draft odpovědi
  ↓
AKCE: Uložte do tabulky (např. Google Sheets pokud soukromý projekt)
AKCE: Vytvořte draft v emailu
```

### 4. Postav v nástroji

**V Relay.app:**

1. **New Workflow** → Pojmenuj
2. **Trigger:**
   - Gmail: „New email"
   - Podmínka: From obsahuje „@customer-domain.com"
3. **AI Step:**
   - „Analyze email and categorize"
   - Prompt: „Kategorizuj tento email jako: urgent/normal/low priority"
4. **Condition:**
   - If priority = „urgent"
5. **AI Step:**
   - „Generate response"
   - Prompt: „Vytvořte profesionální odpověď"
6. **Action:**
   - Send to: Notion (uložení)
   - Gmail: Create draft

### 5. Testujte a laď

**První test:**
- Spusťte manuálně s test daty
- Sledujte, co se stane v každém kroku
- Identifikujte chyby

**Iterujte:**
- Upravte AI prompty
- Přidejte error handling
- Vylaďte conditions

**Monitoruj první týden:**
- Denně kontroluj výstupy
- Opravuj, co nefunguje

## 💡 Příklad z praxe

Customer success manager měl každý týden procházet 50+ zpráv od klientů a kategorizovat je pro report. 

Postavil automatizaci:
- **Trigger:** Každé pondělí ráno 8:00
- **Krok 1:** Stáhněte zprávy z Zendesku (poslední týden)
- **AI krok:** Claude kategorizuje podle urgentnosti a typu problému
- **AI krok:** Vytvořte tabulku se statistikami
- **Akce:** Uložte do Google Sheets a pošli týmu

**Na začátku:** Musel ladit kroky, prompty, podmínky a formátování výstupu. Automatizace občas zahlásila chybu kvůli API limitům nebo neočekávaným datům.

**Po vyladění:** Běží 8 měsíců bez problému. Šetří 3 hodiny týdně.

## Další příklady automatizací

### Email monitoring

```
TRIGGER: Nový email (každou hodinu check)
  ↓
AI: Je to důležité? Kategorizuj urgent/normal
  ↓
POKUD urgent:
  AI: Extrahuj klíčové info
  Pošlete notifikaci do Slacku
  Vytvořte task v CRM
  
POKUD normal:
  AI: Jen stručné shrnutí
  Přidejte do weekly digest
```

### Web content monitoring

```
TRIGGER: Denně v 7:00
  ↓
Krok: Perplexity API — najdi nové články o [tématu]
(nebo web scraping konkrétních stránek)
  ↓
AI: Vyberte 5 nejrelevantnějších článků
AI: Shrň každý do 2 vět
  ↓
AKCE: Pošlete email digest
AKCE: Uložte do Notion reading listu
```

### Document processing

```
TRIGGER: Nový soubor ve složce „Incoming"
  ↓
AI: Detekuj typ dokumentu (invoice/contract/report)
  ↓
PODMÍNKA podle typu:
  Invoice → AI extrahuj data → Uložte do účetnictví
  Contract → AI najdi klíčové body → Alert právníkovi
  Report → AI shrň → Pošlete týmu
  ↓
AKCE: Přesuň do správné složky
```

### Social media auto-posting

```
TRIGGER: Každý všední den 10:00
  ↓
AI: Vygeneruj post podle šablony a current trend
AI: Optimalizuj pro engagement
  ↓
PODMÍNKA: Pokud relevance score > 7/10
  ↓
AKCE: Post na LinkedIn
AKCE: Uložte do content kalendáře
```

## Ošetření chyb (error handling) — důležité!

**Co je error handling?** Ošetření situací, kdy něco selže — API nereaguje, data jsou v jiném formátu, služba je nedostupná. Bez tohoto ošetření se automatizace zastaví a ty se o tom nedozvíš.

**Vždy přidej:**

```
TRY:
  [Hlavní workflow]
CATCH error:
  Pošlete notifikaci (aby ses dozvěděl že něco selhalo)
  Uložte error log (abys věděl, co se stalo)
  Zkuste znovu (max 3×)
  Pokud fail → Fallback na manuální řešení
```

**V Relay/Make/N8N:**
- „Error handler" modul
- „Retry" s podmínkami
- Notification pokud selže (email, Slack, SMS)

**Proč je to kritické:** Automatizace může běžet měsíce bez problému a pak náhle selhat. Bez error handlingu to zjistíte až když někdo řekne „kde jsou data?"

## Kdy použít pokročilejší nástroje?

Začněte s **Relay.app** — je nejjednodušší a pokryje většinu základních automatizací.

**Přejdi na pokročilejší nástroje (Make, Power Automate, N8N) když:**
- Potřebuješ **složitější logiku** s více podmínkami a větvemi
- Máš **specifické integrace** které Relay nepokrývá
- Chceš **více kontroly** nad každým krokem workflow
- Pracuješ v **enterprise prostředí** (Power Automate pro Microsoft ekosystém)
- Potřebuješ **vlastní hosting a kontrolu nad daty** (N8N)

## Quick Action Guide

### Klíčové závěry
- Všechno pravidelné = lze automatizovat
- Začněte s Relay.app (nejjednodušší)
- AI kroky dělají rozdíl
- Ošetření chyb (error handling) je kritické
- Začněte s 1 automatizací, pak přidávaj

### Co se vyhnout (a udělat místo toho)
- ❌ Neautomatizujte, co jste neudělali ručně 2-3×. ✅ Nejdřív pochopte proces a vylaďte prompty.
- ❌ Nezapomeňte na error handling. ✅ Co když API selže?
- ❌ Nespusť a zapomeň. ✅ První týden denně monitoruj.

### Start zde
1. Identifikujte 1 opakující se činnost (denní/týdenní)
2. Udělejte ji ručně 2× a zapiš kroky + vylaď prompty
3. Zvolte nástroj (Relay.app pro start)
4. Postav workflow s AI kroky
5. Přidejte error handling
6. Testujte na fake datech
7. Spusťte a první týden denně kontroluj
