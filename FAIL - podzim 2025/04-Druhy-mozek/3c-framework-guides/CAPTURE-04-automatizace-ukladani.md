# Automatizovat ukládání informací z různých zdrojů

## Základní informace

Automatické ukládání z e-mailů, RSS, Slacku do centrálního systému s AI zpracováním.

**Co je automatizace ukládání?** Systém, který v pozadí sleduje zdroje dat (emaily, RSS, Slack) a automaticky je zpracovává a ukládá tam, kde je potřebujete. Místo ruční práce každý den.

**Proč na tom záleží:** Místo kopírování informací ručně každý den necháš automatizaci dělat práci za tebe. Ráno se probudíš a důležité informace jsou už zpracované a uložené.

**Základní princip:** AI krok v automatizaci dělá rozdíl. Nejen mechanický přesun dat, ale zpracování — kategorizace, shrnutí, extrakce klíčových bodů.

## Realistická očekávání

První automatizace vám bude trvat 2-3 hodiny nastavit a **nebude fungovat napoprvé** — to je zcela normální. Budete ladit triggery (spouštěče), AI prompty, výstupy. Po 3-4 iteracích to začne fungovat spolehlivě. Důležité je vyladit prompty ručně předem, abyste je nemuseli ladit až v automatizaci.

## Quick Win

Vytvořte obecnou automatizaci podle vzoru: **Zdroj dat → AI Shrnutí → Uložení**

1. Vyberte automatizační nástroj (pokud začínáte, zkuste **Relay.app** — je nejjednodušší)
2. Vytvořte workflow: Váš zdroj dat (Gmail/Slack/RSS) → AI shrnutí → Vaše úložiště (Google Sheets/Notion)
3. Nejdřív **ručně vyzkoušejte**, jak chcete, aby AI zpracovávalo data, a vylaďte prompt
4. Pošlete si test data přes automatizaci
5. Sledujte, jak automatizace běží, a upravte, co nefunguje
6. Hotovo — máte první automatizaci!

**Důležité:** Nejdřív udělejte 2-3× ručně, abyste pochopili proces a vyladili AI prompty. Pak teprve automatizujte.

## Nástroje

**Focus na tyto 4 nástroje:** Relay, Make, Power Automate, N8N

Pokud máte jiný nástroj, který vám vyhovuje, můžete použít i ten. Důležité je, aby to nebylo moc komplikované a splňovalo vaše potřeby.

### Relay.app (preferovaný)

**Proč:** AI-enhanced automatizace, nejjednodušší na nastavení, AI kredity v každém tarifu.

**Kdy použít:** Když chcete jednoduše propojit aplikace s AI kroky. Ideální pro začátečníky.

**Cena:** Free tier dostupný, placené od $16/měsíc.

### Make (dříve Integromat)

**Proč:** Vizuální workflow builder, komplexní scénáře, velká komunita.

**Kdy použít:** Když potřebujete více kontroly nebo složitější workflow s podmínkami a větvením.

**Cena:** Free tier s omezeními, placené od $9/měsíc.

### Power Automate

**Proč:** Pro Microsoft ekosystém, hluboká integrace s Microsoft 365.

**Kdy použít:** Když máte Microsoft 365 a chcete automatizovat kolem SharePointu, Teams, Outlooku.

**Cena:** Součást Microsoft 365 nebo samostatné plány.

### N8N

**Proč:** Open-source automatizační platforma, self-hosted nebo cloud, velká flexibilita.

**Kdy použít:** Když chcete plnou kontrolu nad automatizacemi, potřebujete self-hosted řešení, nebo chcete pokročilé workflow s custom logikou.

**Cena:** Free self-hosted, cloud od $20/měsíc.

## Zdroje dat k automatizaci

### E-maily

**Co automatizovat:**
- Důležité e-maily od klientů → AI kategorizace → CRM
- Newsletter → AI shrnutí → Reading list
- Přílohy z e-mailů → automatické uložení do správné složky

### Slack/Teams zprávy

**Co automatizovat:**
- Zprávy označené emoji → AI extrakce → FAQ databáze
- Důležité vlákna → AI shrnutí → projektová dokumentace
- Připomínky z kanálu → automatické úkoly

### RSS feedy

**Co automatizovat:**
- Nové články z oblíbených blogů → AI shrnutí → Notion databáze
- Novinky z oboru → AI extrakce klíčových bodů → týdenní report
- Produktové update od konkurence → AI analýza → alert týmu

## Vysvětlení technických termínů

**Trigger (spouštěč):** Událost, která automaticky spustí workflow. Může to být čas (každý den v 9:00), akce (nový email), nebo změna dat (nový řádek v tabulce).

**Webhook:** Způsob, jak jedna aplikace automaticky oznámí druhé aplikaci že se něco stalo. Místo pravidelného dotazování „stalo se něco?" aplikace pošle zprávu „hele, stalo se tohle!" okamžitě když k tomu dojde.

**API:** Rozhraní (interface), které umožňuje aplikacím komunikovat mezi sebou. Je to jako menu v restauraci — vidíte, co si můžete objednat, ale nemusíš rozumět, jak to kuchař připravuje.

## Workflow s AI

Standardní tok automatizace:

```
1. Trigger (Zdroj)
   ↓
2. AI krok (Zpracování)
   ↓
3. Akce (Cíl)
```

**Příklad:**
```
Nový email (Gmail)
   ↓
AI: Analyzuj, kategorizuj, vytvoř shrnutí (Claude/GPT)
   ↓
Uložte do CRM + vytvoř draft odpovědi (Notion/Tabulka)
```

## Praktické use cases

### 1. Analýza příchozích e-mailů

**Trigger:** Nový email v Gmailu
**AI krok:** 
- Kategorizuj: klient/dodavatel/spam
- Extrahuj: jméno, firma, požadavek
- Navrhni draft odpovědi
**Akce:** 
- Uložte do CRM
- Vytvořte úkol pro odpovědného člověka
- Pošlete draft odpovědi

### 2. Aktualizace z webu

**Trigger:** RSS feed, nový článek
**AI krok:**
- Udělejte shrnutí v 3 bodech
- Extrahuj klíčové insights
- Přiřaď kategorii (marketing/tech/business)
**Akce:**
- Uložte do Notion databáze „Inspirace"
- Přidejte do reading listu
- Pošlete notifikaci týmu

### 3. Zprávy ze Slacku do databáze

**Trigger:** Slack zpráva označená 📌 emoji
**AI krok:**
- Extrahuj důležité info
- Kategorizuj podle typu (bug/feature/question)
- Vytvořte strukturovanou poznámku
**Akce:**
- Uložte do FAQ databáze
- Vytvořte ticket v Jira (pokud je to bug)

## Jak to nastavit (krok za krokem)

### V Relay.app

1. **Vytvořte nový workflow:**
   - Klikni na „Create Workflow"
   - Vyberte trigger (např. „Gmail - New Email")

2. **Nastavte trigger:**
   - Připoj Gmail účet
   - Nastavte filtr (např. pouze od konkrétních odesílatelů)

3. **Přidejte AI krok:**
   - Přidejte krok „AI Assistant"
   - Napište prompt: „Analyzuj tento email a vytvoř shrnutí v 3 bodech"
   - Vyberte model (Claude Sonnet doporučeno)

4. **Přidejte akci:**
   - Přidejte krok pro cílovou aplikaci (Notion, Airtable, etc.)
   - Namapuj pole z AI kroku do cílové aplikace

5. **Testujte:**
   - Pošlete si test email
   - Sledujte běh workflow
   - Upravte podle potřeby

### V Make

1. **Vytvořte nový scénář:**
   - Klikni na „Create a new scenario"
   - Přidejte první modul (Gmail, RSS, Slack)

2. **Přidejte HTTP modul pro AI:**
   - Přidejte HTTP → Make a request
   - Endpoint: `https://api.anthropic.com/v1/messages`
   - Připoj API klíč (musíš mít vlastní od Anthropic nebo OpenAI)

3. **Nastavte request:**
   - Method: POST
   - Body: JSON s promptem a daty z předchozího kroku

4. **Zpracuj response:**
   - Přidejte JSON parser
   - Extrahuj potřebná pole

5. **Přidejte cílový modul:**
   - Notion, Airtable, Google Sheets
   - Namapuj data

## Ošetření chyb (error handling)

**Co je error handling?** Ošetření situací, kdy něco selže — API nereaguje, data jsou v jiném formátu, zdroj je nedostupný. Bez tohoto ošetření se automatizace zastaví a ty se o tom nedozvíš.

**Proč je to důležité:** Automatizace může běžet týdny bez problému a pak náhle selhat kvůli změně v API, výpadku služby, nebo neočekávaným datům.

**Co přidat do automatizace:**
- **Notifikace při chybě** — pošli si email/Slack když něco selže
- **Retry logika** — zkus to znovu (max 3×) než vzdáš
- **Fallback řešení** — co se má stát když opravdu nejde automatizace
- **Log chyb** — zaznamenej, co se pokazilo, abys to mohl opravit

## Příklad z praxe

Content manager má automatizaci: každé ráno stáhne top 10 článků z RSS feedů o AI, Claude udělá shrnutí každého článku a extrahuje klíčové insights, vše se uloží do Notion databáze „Inspirace". Šetří 45 minut denně.

**Co automatizace dělá konkrétně:**
- 6:00 - Trigger (spouštěč) se aktivuje
- 6:01-6:05 - Stáhne 10 článků z 3 RSS feedů
- 6:05-6:10 - Claude zpracuje každý článek (paralelně)
- 6:10 - Všech 10 shrnutí je v Notion
- 8:00 - Content manager otevře Notion a má všechno připravené

**Na začátku:** Musel ladit AI prompty (aby shrnutí měla správnou strukturu), triggery (aby se to spouštělo správně), a přidat error handling (co když RSS feed neodpovídá).

## Quick Action Guide

### Klíčové závěry

- Focus na Relay, Make, Power Automate, N8N 
- AI krok je klíčový - nejen mechanický přesun, ale zpracování
- Začněte s jednou automatizací, ověř funkčnost, pak přidávej další
- Monitoruj první týden denně, pak týdně

### Co nedělat (a, co místo toho)

- ❌ Nevytvárej složité automatizace napoprvé. ✅ Začněte jednoduchým flow 3 kroků: trigger → AI → akce.
- ❌ Nezapomeňte testovat před spuštěním. ✅ Pošlete si test data, sleduj celý běh.
- ❌ Neignoruj chyby prvního týdne. ✅ První týden kontroluj denně, laď podle problémů.

### Začněte tady

1. Identifikujte jednu opakující se činnost (např. čtení newsletterů)
2. **Udělejte ji ručně 2-3× a vylaď AI prompty**
3. Vyberte nástroj (Relay.app pro začátečníky)
4. Vytvořte účet a připoj 2 aplikace (zdroj + cíl)
5. Nastavte jednoduchý workflow: trigger → AI shrnutí → ulož
6. **Přidejte error handling** (notifikace při chybě)
7. Testujte s reálnými daty
8. Sledujte týden, uprav, co nefunguje
9. Když běží stabilně, přidej další automatizaci