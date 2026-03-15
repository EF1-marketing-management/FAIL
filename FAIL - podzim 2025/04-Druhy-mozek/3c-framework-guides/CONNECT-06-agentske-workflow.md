# Jak navrhnout agentské workflow pro automatické vyhledávání, zpracování a ukládání informací

**Přehled:** Multi-step workflow s agentskými funkcemi, kde AI automaticky vyhledává, analyzuje, třídí a ukládá informace do vašeho druhého mozku.

**Proč na tom záleží:** Místo manuálního zpracování článků, dokumentů a poznámek máte inteligentní systém, který je automaticky shromažďuje, kategorizuje a ukládá ve správné struktuře.

**Základní princip:** Nastavíte agentské funkce v nástrojích jako Relay.app, Make, N8N nebo Copilot Studio, kde AI v každém kroku rozhoduje, jak informace zpracovat a kam je uložit – jako virtuální asistent pro váš druhý mozek.

---

## ⚠️ DŮLEŽITÉ UPOZORNĚNÍ

**Tento návod je o agentských workflow, ne o plně autonomních AI agentech.**

**Co je v tomto návodu:**
- 🔧 **Agentská workflow:** AI dělá rozhodnutí v rámci vašich nastavených automatizací
- 🎯 **Semi-autonomní:** AI rozhoduje, ale v rámci pravidel, která jste definovali
- 🛠️ **No-code nástroje:** Relay.app, Make, N8N, Copilot Studio, Lindy.ai

**Co NENÍ v tomto návodu (to je pro hodně pokročilé):**
- 🤖 **Plně autonomní agenti:** AI, kteří sami rozhodují o svých cílech a strategii
- 🧠 **Self-learning agenti:** Systémy, které se učí bez lidského dohledu
- 🚀 **Multi-agent systémy:** Desítky agentů komunikujících mezi sebou

**TL;DR:** Začínáme s agentskými workflow v no-code nástrojích. To je bezpečná a praktická cesta. Plně autonomní agenti jsou pro pokročilé použití.

---

## ⚠️ Realistická očekávání

Agentské workflow je nejkomplexnější implementace z celého modulu. První verze **nebude fungovat napoprvé a selže na edge cases** (neočekávané situace), které jste nepředvídali — to je normální. Error handling (ošetření chyb) bude vyžadovat desítky iterací. Očekávejte 3-6 týdnů vývoje a ladění, než workflow běží production-ready (připravené pro produkční nasazení). Každá iterace vás ale naučí, kde jsou slabá místa.

---

## 🚀 Quick Win

**DŮLEŽITÉ: Agentské workflow není „quick win".** Je to nejkomplexnější implementace.

**Nejjednodušší start – vyberte scénář a nástroj:**

**Scénář A: Zpracování zákaznických zpráv (jednodušší)**
1. **Relay.app** (doporučeno pro start):
   - Trigger: Nový email na support@
   - AI krok 1: Extrahuj kontaktní info + analyzuj typ dotazu
   - AI krok 2: Urči urgenci a přiřaď osobu
   - Akce: Přidej řádek do Google Sheets + pošli notifikaci Slack
   - AI kroky vestavěné, není třeba volat API manuálně

2. **Make.com**: Stejné workflow s HTTP voláním AI API

3. **Lindy.ai**: "Vytvoř mi asistenta, který zpracovává zprávy ze support emailu, kategorizuje je a přidává do tabulky s analýzou"

**Scénář B: Knowledge chatbot (pokročilejší)**
- Vyžaduje napojení na firemní zdroje (Confluence, Notion, Drive)
- Potřebuje MCP servery nebo API integrace
- Doporučeno: Claude Desktop s MCP nebo Copilot Studio

**To jsou nejjednodušší formy agentského workflow.**

**Reálné production-ready workflow s 85%+ přesností:** Týdny až měsíce práce a iterací.

---

## Jak funguje agent? Rozdíl mezi automatizací, AI automatizací a agentem

### 1️⃣ Automatizace (deterministická) – pevná pravidla

**Jak funguje:** IF-THEN logika. Žádná inteligence, jen pevné podmínky.

**Příklad – třídění souborů:**
```
Nový soubor přijde do složky 
→ IF název obsahuje "faktura" 
   → THEN přesuň do složky "Accounting"
→ IF přípona je .pdf A obsahuje "smlouva" 
   → THEN přesuň do složky "Legal"
→ IF přípona je .docx 
   → THEN přesuň do složky "Dokumenty"
```

**Charakteristika:**
- ✅ Spolehlivé (vždy stejné)
- ✅ Rychlé
- ❌ Nelze zpracovat neočekávané formáty nebo názvy
- ❌ Musíte předvídat všechny scénáře a vzory názvů

**Kdy použít:** Jednoduché třídění s pevnou strukturou názvů

---

### 2️⃣ Automatizace s AI – inteligentní analýza

**Jak funguje:** AI analyzuje obsah, ale workflow je stále pevně dané.

**Příklad – třídění dokumentů:**
```
Nový dokument v složce 
→ AI analyzuje: "Je to faktura, smlouva, článek nebo report?" 
→ IF AI řekne "faktura" 
   → THEN přesuň do složky "Accounting/2025"
→ IF AI řekne "článek" 
   → THEN přesuň do "Knowledge Base/Články"
→ IF AI řekne "smlouva" 
   → THEN přesuň do "Legal/Smlouvy"
```

**Charakteristika:**
- ✅ Rozumí obsahu dokumentu (ne jen názvu souboru)
- ✅ Zvládne nepředvídané formáty
- ❌ Workflow cesty jsou stále pevné (musíte definovat všechny větve)
- ❌ AI jen kategorizuje, nerozhoduje o dalším zpracování

**Kdy použít:** Automatické třídění s inteligentní kategorizací

---

### 3️⃣ Automatizace s agentem – inteligentní rozhodování

**Jak funguje:** AI nejen analyzuje, ale **rozhoduje, co dělat** na základě kontextu.

**Příklad – zpracování článku do druhého mozku:**
```
Článek přijde (RSS, Pocket, email) 
→ AI Agent: "Analyzuj celý kontext"
   - Téma: produktivita + AI nástroje
   - Relevance: 9/10 (přesně k tvému projektu)
   - Typ: praktický návod s příklady
   - Délka: 2500 slov
   - Kvalita: vysoká (odborný zdroj)

→ AI Agent rozhodne: "Uložit a zpracovat podrobně"
   → Vytvoří shrnutí (3 klíčové body)
   → Extrahuje nástroje a odkazy
   → Kategorizuje: "Produktivita > AI nástroje > Workflow"
   → Přidá tagy: #productivity, #AI, #workflow
   → Uloží do Notion/Obsidian ve správné struktuře
   → Vytvoří propojení s existujícími poznámkami
   → Pošle notifikaci: "Nový článek zpracován a uložen v kategorii Workflow"

→ Máš: Strukturovanou poznámku ready to use
```

**Charakteristika:**
- ✅ Rozumí obsahu a kontextu informací
- ✅ Rozhoduje se dynamicky o kategorizaci a zpracování
- ✅ Adaptuje se na různé typy obsahu (články, videa, poznámky)
- ❌ Složitější nastavení
- ❌ Potřebuje testování a iterace

**Kdy použít:** Automatické zpracování a organizace znalostí pro druhý mozek

---

### 📊 Srovnání v tabulce

| **Aspekt** | **Automatizace** | **Automatizace s AI** | **Agentské workflow** |
|------------|------------------|----------------------|----------------------|
| **Inteligence** | Žádná | Analýza a kategorizace | Rozhodování a akce |
| **Flexibilita** | Nízká | Střední | Vysoká |
| **Složitost setup** | Jednoduchá | Střední | Vysoká |
| **Spolehlivost** | 100% | 85-95% | 70-90% (zpočátku) |
| **Údržba** | Minimální | Občasná | Průběžná iterace |
| **Příklad** | "IF slovo X → akce Y" | "AI: kategorizuj → IF kategorie → akce" | "AI: analyzuj → AI: rozhodni → AI: jednej" |

**TL;DR:** Agent = AI nejen analyzuje, ale **rozhoduje, co dělat** na základě celého kontextu.

---

## Nástroje pro agentské workflow

**Přehled nástrojů:**
- **Relay.app:** Nejjednodušší pro začátek, AI kroky vestavěné
- **Make.com:** Visual builder, flexibilní, volání AI API
- **N8N:** Open-source, self-hosted, plná kontrola
- **Microsoft Copilot Studio:** Pro Microsoft 365 prostředí
- **Lindy.ai:** Extra tip – AI asistenti s natural language setup

---

### 1. Relay.app (doporučeno pro začátek)

**Co to je:** AI-first automatizační platforma s vestavěnými agentskými funkcemi.

**Principy práce:**
- **AI kroky:** Přidáte AI blok bez nutnosti volat API manuálně
- **Human-in-the-loop:** Vestavěné schvalování člověkem
- **Conditional routing:** AI výstupy určují, kterou cestou se workflow vydá
- **Structured outputs:** AI vrací data ve formátech, které můžete použít dál

**Jak funguje agentské workflow v Relay:**
1. **Trigger** (např. nový email, formulář)
2. **AI analyzuje** → vrátí kategorie, priority, sentiment
3. **Podmínky** → podle AI výstupu se rozhodne cesta
4. **Další AI kroky** → extrakce dat, generování odpovědí
5. **Human approval** (volitelně) → člověk schválí před akcí
6. **Finální akce** → uložení do CRM, odeslání emailu

**Web:** https://relay.app  
**Cena:** Free plan, od $15/měsíc  
**Kdy použít:** Chcete nejrychlejší cestu k agentskému workflow bez technických znalostí

---

### 2. Make.com (flexibilní workflow orchestrace)

**Co to je:** Visual workflow builder s integrací AI přes HTTP moduly.

**Principy práce:**
- **Drag & drop:** Vizuální sestavení workflow
- **HTTP modul:** Volání AI API (OpenAI, Claude, Gemini)
- **Routers a filters:** Podmíněné cesty podle AI výstupů
- **1000+ integrací:** Propojení s téměř všemi nástroji

**Jak funguje agentské workflow v Make:**
1. **Trigger modul** (Gmail, Webhook, Scheduler)
2. **HTTP Request → AI API** (posílá prompt, dostává odpověď)
3. **Router modul** → rozdělí flow podle AI výstupu
4. **Další HTTP → AI API** → pokračující rozhodování
5. **Akční moduly** → CRM, Email, Database, Slack

**Klíčové principy:**
- Musíte ručně volat AI API (OpenAI, Anthropic)
- Flexibilnější než Relay (můžete volat jakékoliv API)
- Vyžaduje víc technického nastavení (API keys, JSON)

**Web:** https://make.com  
**Cena:** Free plan (omezený), od $9/měsíc  
**Kdy použít:** Potřebujete flexibilní workflow s vlastními API integracemi

---

### 3. N8N (open-source, self-hosted)

**Co to je:** Open-source automatizační platforma pro plnou kontrolu.

**Principy práce:**
- **Self-hosted:** Běží na vašem serveru (nebo cloud)
- **400+ integrací:** Community extensions
- **AI nodes:** Přímá integrace s OpenAI, Anthropic, HuggingFace
- **Full code access:** Můžete upravit a rozšířit

**Jak funguje agentské workflow v N8N:**
1. **Trigger node** (Webhook, Email, Cron)
2. **AI node** → OpenAI, Claude, vlastní modely
3. **IF/Switch nodes** → podmíněné cesty
4. **Function nodes** → vlastní JavaScript logika
5. **Action nodes** → Database, API calls, notifications

**Klíčové principy:**
- Plná kontrola nad daty (self-hosted)
- Vyžaduje technické znalosti (server setup)
- Bezplatné (pokud hostujete sami)

**Web:** https://n8n.io  
**Cena:** Free (self-hosted), cloud od $20/měsíc  
**Kdy použít:** Chcete full control, máte technické know-how, nebo potřebujete data on-premise

---

### 4. Microsoft Copilot Studio (enterprise)

**Co to je:** Microsoft platforma pro tvorbu AI asistentů a agentských workflow.

**Principy práce:**
- **Topics:** Definujete konverzační scénáře
- **Power Automate:** Propojení s workflow automatizací
- **Microsoft Graph:** Přístup k firemním datům (SharePoint, Teams, Outlook)
- **AI Builder:** Vlastní AI modely pro specifické úkoly

**Jak funguje agentské workflow v Copilot Studio:**
1. **Trigger** (Teams message, Email, Form)
2. **Copilot analyzuje** → intent recognition
3. **Power Automate flow** → multi-step workflow s AI
4. **Microsoft services** → SharePoint, Dynamics, Power BI
5. **Response** → Teams, Email, nebo jiný kanál

**Klíčové principy:**
- Integrované do Microsoft 365 ekosystému
- Enterprise-grade bezpečnost a compliance
- Vyžaduje Microsoft licence

**Web:** https://www.microsoft.com/en-us/microsoft-copilot/microsoft-copilot-studio  
**Cena:** Od $200/tenant/měsíc (enterprise)  
**Kdy použít:** Pracujete v Microsoft 365 prostředí a potřebujete enterprise řešení

---

### 5. Lindy.ai (extra tip – natural language setup)

**Co to je:** AI asistenti, které nastavíte přirozeným jazykem.

**Principy práce:**
- **Natural language:** "Vytvoř mi asistenta, který analyzuje emaily a třídí je podle priority"
- **Lindy to pochopí** a vytvoří workflow
- **Můžete upravit** vizuálně nebo textem
- **Agentské chování:** Lindy rozhoduje podle kontextu

**Jak funguje:**
1. Popíšete, co chcete (text)
2. Lindy vytvoří workflow
3. Testujete a iterujete (v přirozeném jazyce)
4. Lindy se učí z vašich preferencí

**Klíčové principy:**
- Nejjednodušší setup (bez kódování)
- Adaptuje se podle vašich úprav
- Stále v early stage (může mít omezení)

**Web:** https://www.lindy.ai  
**Cena:** Od $29/měsíc  
**Kdy použít:** Chcete nejrychlejší setup bez technických znalostí, experimentální přístup

---

### 📊 Srovnání nástrojů

| **Nástroj** | **Jednoduchostí** | **Flexibilita** | **Cena** | **Nejlepší pro** |
|-------------|------------------|-----------------|----------|------------------|
| **Relay.app** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | $ | Rychlý start, AI-first |
| **Make.com** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | $ | Flexibilní workflow |
| **N8N** | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | Free/$ | Full control, self-hosted |
| **Copilot Studio** | ⭐⭐⭐ | ⭐⭐⭐⭐ | $$$ | Microsoft 365 enterprise |
| **Lindy.ai** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | $$ | Natural language setup |

**Doporučení:**
- **Začínáte:** Relay.app (nejjednodušší)
- **Potřebujete flexibilitu:** Make.com
- **Máte technické know-how:** N8N
- **Microsoft prostředí:** Copilot Studio
- **Chcete experimentovat:** Lindy.ai

---

## Proces: Navrhnout agentské workflow

### Fáze 1: Identifikace procesu

**1. Vyberte pravidelnou činnost:**

**Příklady agentských workflow:**
- **Zpracování zákaznických zpráv:** Email/formulář → analýza → routing → tabulka + notifikace
- **Knowledge chatbot:** Dotaz → vyhledávání v zdrojích → analýza → strukturovaná odpověď
- **Document processing:** Nové soubory → extrakce obsahu → třídění → archivace
- **Meeting notes processing:** Záznam/transkript → klíčové body → úkoly → uložení
- **Lead qualification:** Nový lead → scoring → obohacení dat → CRM + přiřazení

**2. Namapuj současný manuální proces:**

**Příklad – zpracování zákaznických zpráv:**
```
1. Dostanu email nebo notifikaci z formuláře
2. Přečtu zprávu
3. Rozhodnu: co to je? (podpora/prodej/fakturace/spam?)
4. Rozhodnu: je to urgentní?
5. Určím: komu to má jít? (Martin/Jana/účtárna?)
6. Zkopíruju kontakty do tabulky/CRM
7. Přepošlu nebo přiřadím správné osobě
8. Někdy napíšu draft odpovědi
9. Musím si pamatovat followup
```

**Čas:** 5-10 minut na zprávu → 5+ hodin týdně + riziko zapomenutých zpráv

**3. Identifikujte rozhodovací body:**

Kde děláte rozhodnutí? To jsou místa pro AI agenty:
- „Co to je za typ dotazu?" → AI agent 1 (kategorizuje)
- „Je to urgentní?" → AI agent 2 (určí prioritu)
- „Komu to patří?" → AI agent 3 (routing)
- „Jaká by měla být odpověď?" → AI agent 4 (generuje draft)

---

### Fáze 2: Design workflow

**1. Nakresli diagram:**

**Příklad – zpracování zákaznických zpráv:**

```
[Trigger: Nový email na support@ NEBO formulář na webu]
    ↓
[AI: Kompletní analýza zprávy]
  - Extrakce: jméno, firma, email, telefon, text
  - Typ: podpora/prodej/fakturace/feature/spam
  - Urgence: nízká/střední/vysoká/kritická
  - Sentiment: pozitivní/neutrální/negativní
    ↓
{Je to spam?}
    ├─ ANO → [Smaž] → KONEC
    │
    └─ NE → [AI: Inteligentní routing]
            ↓
            {Typ dotazu?}
            ├─ Technická podpora → [Přiřaď: Martin (CTO)]
            ├─ Prodejní dotaz → [Přiřaď: Jana (Sales)]
            ├─ Fakturace → [Přiřaď: Účtárna]
            └─ Feature request → [Přiřaď: Product tým]
            ↓
            [AI: Vygeneruj draft odpovědi]
            ↓
            [Uložte do Google Sheets/Airtable]
              Sloupce: | Datum | Jméno | Firma | Email | Typ | Urgence | Přiřazeno | Draft |
            ↓
            [Pošli notifikace]
              - Slack: "@osoba máš nový dotaz - urgence"
              - Email: Detail + draft odpovědi
            ↓
            {Confidence > 90% AND urgence = nízká?}
            ├─ ANO → [Automaticky pošli odpověď]
            └─ NE → [Čekej na lidské schválení]
```

**2. Definujte AI kroky:**

Pro každý AI krok specifikuj:
- **Input:** Co dostane (email text, metadata formuláře)
- **Prompt:** Co má udělat
- **Output:** Co vrátí (formát, JSON schema)
- **Následující akce:** Co se stane podle výstupu

**Příklad AI kroku – analýza zprávy:**

```json
{
  "name": "Kompletní analýza zákaznické zprávy",
  "input": "message_text, sender_email, subject, form_data",
  "prompt": "Analyzuj tuto zprávu a extrahuj: 1) Kontaktní info (jméno, firma, email, telefon), 2) Typ dotazu (technická_podpora/prodej/fakturace/feature_request/spam), 3) Urgence (1-4, kde 4=kritická), 4) Sentiment (pozitivní/neutrální/negativní), 5) Stručný popis problému/dotazu. Vrať JSON.",
  "output_format": "JSON: {kontakt: {jmeno, firma, email, telefon}, typ: string, urgence: number, sentiment: string, popis: string, confidence: number}",
  "next_step": "if typ==spam → delete, else → routing"
}
```

**Příklad AI kroku – generování odpovědi:**

```json
{
  "name": "Generování draft odpovědi",
  "input": "message_text, typ_dotazu, kontakt_info, company_knowledge_base",
  "prompt": "Na základě tohoto dotazu vygeneruj profesionální odpověď. Použij informace z naší knowledge base. Buď konkrétní, přátelský a nabídni řešení. Pokud je třeba další info, zeptej se. Max 200 slov.",
  "output_format": "TEXT: draft_odpovědi",
  "next_step": "add_to_spreadsheet_and_notify"
}
```

---

### Fáze 3: Implementace – obecné principy

**Nezávisle na nástroji (Relay, Make, N8N, Copilot Studio) platí:**

**1. Start s trigger:**
- Email přijde, formulář odeslán, webhook call, časový spouštěč
- Testuj trigger s dummy daty nejdřív

**2. První AI krok – analýza:**
- **Prompt:** Jasně definuj, co má AI udělat a jaký formát výstupu očekáváš
- **Příklad:** "Analyzuj tento email a vrať JSON: {kategorie: string, urgence: string, sentiment: string, confidence: number}"
- **Tip:** Structured outputs (JSON mode) = snadnější zpracování

**3. Podmíněné cesty (routing):**
- Podle AI výstupu se rozhodne, kterou cestou workflow pokračuje
- **Relay:** Conditional paths (vizuálně)
- **Make/N8N:** Router/Switch nodes
- **Copilot Studio:** Topics a conditions

**4. Další AI kroky – akce:**
- Extrakce dat, generování odpovědí, rozhodování o prioritě
- Každý AI krok dostává kontext z předchozích kroků
- **Řetězení:** Výstup kroku 1 → vstup do kroku 2

**5. Human-in-the-loop (volitelně):**
- Pokud confidence nízká nebo kritické rozhodnutí → člověk schválí
- **Relay:** Vestavěné approval steps
- **Make/N8N:** Slack/Teams notifikace + webhook callback
- **Copilot Studio:** Adaptive cards v Teams

**6. Finální akce:**
- CRM update, email odeslání, databáze zápis, notifikace
- Logování výsledků pro monitoring

**Klíčové principy implementace:**
- ✅ **Začni jednoduše:** 3 kroky workflow (trigger → AI → akce), pak rozšiřuj
- ✅ **Testuj po každém kroku:** Nestavěj celé workflow najednou
- ✅ **Structured outputs:** AI vrací JSON = snadnější zpracování
- ✅ **Fallback mechanismy:** Co se stane, když AI selže?
- ✅ **Logging:** Zaznamenávej každý běh pro debugging

---

### Fáze 4: Error handling (ošetření chyb)

**Co je error handling?** Ošetření situací kdy něco selže — AI vrátí neočekávanou odpověď, API nereaguje, data jsou v jiném formátu. Bez error handlingu se agent zastaví a ty se o tom nedozvíš.

**KRITICKÉ:** Agenti selhávají často, zvlášť na začátku. Musíš mít fallback (záložní řešení).

**1. Try-catch na AI krocích (zachycení chyb):**

```
if AI_response.error:
    → pošli notifikaci člověku
    → ulož pro manuální processing
    → loguj chybu pro debugging
```

**2. Confidence thresholds (prahové hodnoty důvěry):**

```
if AI_confidence < 0.8:
    → human-in-the-loop approval (člověk schvaluje)
else:
    → automatická akce
```

**3. Monitoring (sledování):**
- Kolik workflow uspělo?
- Kde selhávají?
- Časté error messages?
- První měsíc kontroluj denně!

---

### Fáze 5: Testování a iterace

**1. Testujte na historických datech:**
- Vezmi 50-100 reálných emailů/dokumentů
- Pusť je workflow
- Změř: kolik % správně zpracováno

**2. Edge cases:**
- Nejasné situace
- Neočekávané formáty
- Chybějící data

**3. Iterujte prompty:**
- První verze promptů nebude fungovat
- Testujte → uprav prompt → testuj znovu
- Minimum 5-10 iterací

---

## 💡 Hlavní příklady z praxe – agentské workflow ve firmě

### Příklad 1: Agent pro zpracování zákaznických zpráv a poptávek

**Situace:** Firma dostává 50-100 zpráv týdně z kontaktního formuláře na webu i z podporového emailu. Manuální třídění a směrování = 5+ hodin týdně + zpoždění v odpovědích.

**Agentské workflow:**

```
Nová zpráva přijde (formulář nebo email support@firma.cz) → 

AI Agent 1: Kompletní analýza zprávy
  - Extrahuje: jméno, firma, email, telefon, text dotazu
  - Analyzuje typ poptávky:
    * Technická podpora (problém s produktem)
    * Prodejní dotaz (chce koupit/demo)
    * Fakturace (otázka k platbě/faktuře)
    * Feature request (návrh na vylepšení)
    * Spam nebo irelevantní
  - Hodnotí urgenci: nízká/střední/vysoká/kritická
  - Analyzuje sentiment: pozitivní/neutrální/negativní/naštvaný
  - Určuje hodnotu zákazníka: nový lead / existující / VIP klient

→ AI Agent 2: Inteligentní routing (kam to směrovat?)
  - Technická podpora + vysoká urgence → Martin (CTO)
  - Prodejní dotaz + nový lead → Jana (Sales)
  - Fakturace → Účtárna + kopie pro Petru
  - Feature request + existující klient → Product tým
  - Spam → automaticky smaž, konec workflow

→ AI Agent 3: Příprava kontextu a draftu odpovědi
  - Vygeneruje draft odpovědi podle typu dotazu
  - Najde relevantní info v knowledge base
  - Přidá odkazy na dokumentaci/FAQ pokud relevantní

→ Uložte do Google Sheets / Airtable / Notion:
  Řádek s kompletními daty:
  | Datum | Jméno | Firma | Email | Typ | Urgence | Sentiment | Přiřazeno | Status | Draft odpovědi |

→ Notifikace:
  - Slack: "@Jana máš nový prodejní lead - vysoká urgence"
  - Email: Pro přiřazenou osobu s kompletním kontextem + draft

→ Human-in-the-loop:
  - Člověk zkontroluje draft a pošle (nebo upraví)
  - Pokud AI confidence > 90% A nízká urgence → pošli automaticky
```

**První měsíc:** 70% správně kategorizováno a směrováno  
**Po 3 měsících:** 90% přesnost, žádná zpráva nezapadne

**Investice:**
- 3 týdny setup workflow (definice kategorií, testování)
- 1 měsíc iterací (učení se z chyb)
- Pak stabilní běh s minimální údržbou

**ROI:** 
- Šetří 5+ hodin týdně na manuálním třídění
- Rychlejší reakce (notifikace okamžitě)
- Žádná zpráva se neztratí
- Kompletní historie a analytics v tabulce

---

### Příklad 2: Agent (chatbot) pro vyhledávání informací ve firemních zdrojích

**Situace:** Firma má informace roztříštěné v Confluence, Google Drive, Notion, interní wiki, PDF dokumentace. Zaměstnanci tráví 2-3 hodiny týdně hledáním informací "Kde to bylo?" "Kdo o tom rozhodl?" "Jaký je aktuální proces?"

**Řešení: Interní knowledge agent (chatbot) s agentským chováním**

**Jak funguje:**

```
Zaměstnanec se zeptá v Slacku: "/ask Jaký je proces schvalování slev nad 20%?"

→ AI Agent 1: Pochopení dotazu
  - Parsuje otázku: typ = proces, téma = slevy, limit = 20%
  - Identifikuje klíčová slova: "schvalování", "slevy", "20%"
  - Určí context: pravděpodobně sales proces

→ AI Agent 2: Inteligentní vyhledávání v múltiple zdrojích (paralelně)
  - Confluence: Hledá v kategorii "Sales procesy"
  - Google Drive: Hledá v "Dokumenty/Obchod"
  - Notion: Hledá v "Company Wiki > Processes"
  - PDF dokumentace: Prohledá "Sales_Handbook_2025.pdf"
  
→ AI Agent 3: Analýza a filtrování výsledků
  - Našlo: 
    * Confluence: "Schvalovací matice 2025" (relevance 95%)
    * Notion: "Sales playbook" (relevance 70%)
    * PDF: "Sales guidelines" (relevance 85%)
  - Vyhodnotí: nejrelevantnější = Confluence dokument
  - Zkontroluje: je aktuální? (updated: 2025-01-15 ✓)

→ AI Agent 4: Sestavení odpovědi
  - Vytvoří srozumitelnou odpověď
  - Cituje zdroj a datum poslední aktualizace
  - Přidá odkazy na plné dokumenty
  - Pokud nalezne konfliktní informace, upozorní

→ Odpověď ve Slacku:
```
📋 **Proces schvalování slev nad 20%:**

1. **Slevy 20-30%:** Schvaluje vedoucí sales (Jana nebo Martin)
2. **Slevy 30-50%:** Vyžaduje schválení Sales Director + CFO
3. **Slevy nad 50%:** Schvaluje pouze CEO

⏱️ SLA: Odpověď do 24h (standardní) / 4h (urgentní případy)

📌 **Zdroje:**
- [Schvalovací matrice 2025](link na Confluence) - aktualizováno 15.1.2025
- [Sales Handbook PDF](link) - strana 23

💡 **Související:** Máš také [proces pro výjimečné obchody](link) a [eskalační proces](link)
```

→ Logování:
  - Uloží dotaz + odpověď do knowledge analytics
  - Trackuje: kolik lidí se ptá na stejné téma (indikátor chybějící dokumentace)
```

**Pokročilé agentské chování:**
- Pokud najde zastaralé informace → pošle alert admin týmu
- Pokud najde konfliktní informace v různých zdrojích → upozorní
- Pokud nenajde odpověď → navrhne, kde by měla být dokumentace
- Učí se z feedbacku (👍/👎 na odpovědi)

**První měsíc:** 60% dotazů zodpovězeno správně  
**Po 3 měsících:** 85% úspěšnost, rapidní snížení "Kde to bylo?" otázek

**Investice:**
- 2 týdny setup (napojení na zdroje, MCP/API integrace)
- 1 měsíc iterací promptů a testování
- Průběžná údržba: aktualizace knowledge base

**ROI:**
- Šetří 2-3 hodiny/týden/osobu na hledání informací
- Pro 20 lidí = 40-60 hodin týdně úspory
- Rychlejší onboarding nových lidí
- Žádné "ztracené" informace

**Technické řešení:**
- **Platforma:** Claude Desktop s MCP / Copilot Studio / vlastní chatbot
- **Integrace:** MCP servery pro Confluence, Drive, Notion
- **Model:** GPT-4 nebo Claude 3.5 Sonnet
- **Rozhraní:** Slack bot nebo Teams bot

---

## Další příklady agentských workflow

### Příklad 3: Automatické zpracování meeting poznámek
```
Meeting skončí → Transcript z Zoom/Teams/Fireflies → 
AI Agent 1: Extrahuj klíčové body a rozhodnutí → 
AI Agent 2: Identifikuj úkoly a deadlines → 
AI Agent 3: Vytvoř akční položky s vlastníky → 
AI Agent 4: Propoj s existujícími projekty → 
Uložte do Notion/Obsidian:
  - Poznámka: Shrnutí meetingu
  - Úkoly: Exportuj do task manageru
  - Propojení: Související projekty
→ Notifikace účastníkům: "Meeting notes ready + 3 úkoly přiřazeny"
```

### Příklad 4: Automatické zpracování dokumentů a PDF
```
Nový soubor v složce (Dropbox, Drive) → 
AI Agent 1: Detekuj typ (faktura/smlouva/článek/report) → 
AI Agent 2: Extrahuj text (OCR pokud potřeba) → 
AI Agent 3: Podle typu:
  - Faktura → extrahuj částku, datum, dodavatel → accounting
  - Smlouva → extrahuj klíčové body, datum ukončení → legal folder
  - Článek/Research → shrnutí + tagy → knowledge base
  - Report → klíčové metriky + vizualizace → reports
→ AI Agent 4: Přejmenuj podle šablony (YYYYMMDD_Typ_Název) → 
→ Uložte do správné struktury → 
→ Notifikuj relevantní lidi
```

### Příklad 5: Automatický research assistant
```
Každé ráno 8:00 → 
AI Agent 1: Vyhledej nové info o mých tématech (Google Alerts, Reddit, Twitter) → 
AI Agent 2: Filtruj podle relevance (>7/10) → 
AI Agent 3: Stáhni a analyzuj zdroje → 
AI Agent 4: Vytvoř daily digest:
  - 3 nejdůležitější články s shrnutím
  - Nové nástroje a trendy
  - Relevantní diskuze (Reddit threads)
→ Uložte jako denní poznámku → 
→ Pošli email/Slack: "Tvůj daily research digest je ready"
```

### Příklad 6: Automatické propojování znalostí
```
Nová poznámka v Obsidian/Notion → 
AI Agent 1: Analyzuj obsah a hlavní témata → 
AI Agent 2: Vyhledej podobné existující poznámky → 
AI Agent 3: Navrhni propojení (backlinks) → 
AI Agent 4: Identifikuj mezery ve znalostech → 
AI Agent 5: Navrhni, co prostudovat dále → 
→ Notifikace: "Nová poznámka propojená s 5 existujícími + 2 návrhy na další studium"
```

---

## Quick Action Guide

### Klíčové závěry
- **Agentské workflow ≠ plně autonomní agenti** (ty jsou pro pokročilé)
- Agent = AI dělá rozhodnutí v každém kroku workflow
- **3 úrovně:** Automatizace → Automatizace s AI → Agentské workflow
- Nástroje: Relay.app (start), Make, N8N, Copilot Studio, Lindy.ai
- Production-ready workflow = týdny až měsíce práce a iterací
- Vždycky měj human-in-the-loop pro kritická rozhodnutí

### Co se vyhnout (a co dělat místo toho)
- ❌ Očekávat plně autonomní agenty. ✅ Začni s agentskými workflow v no-code nástrojích.
- ❌ Automatizovat vše najednou. ✅ Začni jedním workflow, ověř funkčnost.
- ❌ Žádný error handling. ✅ Vždycky měj fallback na člověka když AI selže.
- ❌ 100% automatizace critical tasks. ✅ Human-in-the-loop pro důležitá rozhodnutí.
- ❌ Neměřit úspěšnost. ✅ Trackuj % úspěšných běhů, kde selhávají.

### Začněte tady

**Postupnost – začni jednoduše:**

**Krok 0: Vyber nástroj (30 minut):**
- **Pro rychlý start:** Relay.app (AI kroky vestavěné, nejjednodušší)
- **Pro flexibilitu:** Make.com (více kontrol, integrace)
- **Pro control:** N8N (self-hosted, open-source)
- **Pro Microsoft:** Copilot Studio (Teams, SharePoint)
- **Pro experiment:** Lindy.ai (natural language setup)

**Krok 1: Identifikuj proces** (1 den):
- Vyberte jednu pravidelnou činnost:
  - **Pro začátek:** Zpracování zákaznických zpráv (email/formulář)
  - **Pokročilé:** Knowledge chatbot (vyhledávání v dokumentech)
  - Třídění dokumentů
  - Meeting notes
  - Lead qualification
- Namapuj současný manuální proces (kolik to trvá?)
- Identifikujte rozhodovací body (kde děláte rozhodnutí?)

**Krok 2: Navrhni workflow** (2-3 dny):
- Nakresli diagram (trigger → AI kroky → podmínky → akce)
- Definujte AI kroky: co má AI analyzovat a rozhodnout
- Napiš prompty: jasně řekni AI, co má vrátit (ideálně JSON)
- Identifikujte podmínky a větve

**Krok 3: Implementace** (1 týden):
- Setup trigger (email, formulář, webhook)
- Přidej první AI krok (analýza)
- Testuj s 5 příklady
- Přidej podmíněné cesty
- Přidej další AI kroky
- Přidej finální akce
- **Tip:** Testuj po každém kroku!

**Krok 4: Error handling** (3-5 dní):
- Co se stane, když AI vrátí chybu?
- Confidence thresholds (pokud AI není si jistá → člověk schválí)
- Fallback mechanismus (AI selže → notifikace člověku)
- Logování pro debugging

**Krok 5: Testování** (2-3 týdny):
- 50-100 testovacích případů (reálná data)
- Měř úspěšnost (% správně zpracováno)
- Iteruj prompty a podmínky
- Testuj edge cases (neočekávané situace)

**Krok 6: Deploy a monitoring** (ongoing):
- Pusť na reálných datech
- **První týden:** Kontroluj denně
- **První měsíc:** Kontroluj 2-3x týdně
- Měsíčně review metriky
- Průběžně zlepšuj

---

### Jaký nástroj pro jakou situaci?

| **Situace** | **Nástroj** |
|-------------|-------------|
| Chci nejrychlejší start | **Relay.app** |
| Potřebuji volat vlastní API | **Make.com** |
| Chci full control nad daty | **N8N** |
| Microsoft 365 prostředí | **Copilot Studio** |
| Chci experimentovat s natural language | **Lindy.ai** |

---

### Co očekávat – realistický timeline

**První měsíc:**
- Úspěšnost: 40-60%
- Hodně iterací promptů a podmínek
- Objevování edge cases

**Po 3 měsících:**
- Úspěšnost: 70-85%
- Stabilnější běh
- Minimum manuálních zásahů

**Dlouhodobě:**
- Úspěšnost: 80-90%
- Občasné updating (když se změní procesy)

---

## Zdroje

**Tip:** Kompletní přehled nástrojů najdete na https://drimalka.com/aplikace-ne-druhy-mozek-nejen-s-ai/

---

**Důležité:** Production-ready agentské workflow není projekt na týden, ale na měsíce. První verze nebude dokonalá – to je normální!