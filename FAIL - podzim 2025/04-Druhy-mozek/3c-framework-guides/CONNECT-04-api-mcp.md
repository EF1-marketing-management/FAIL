# Jak pochopit a nastavit API a MCP pro propojení AI s externími nástroji

**Přehled:** Nastavíš Model Context Protocol (MCP) nebo API integrace, aby AI mohla pracovat s databázemi, soubory a nástroji.

**Proč na tom záleží:** AI přestane být jen chatbot a stane se nástrojem, který může číst vaše soubory, prohledávat databáze, nebo spouštět akce v jiných aplikacích.

**Základní princip:** Propojíš AI s externími zdroji dat nebo nástroji přes standardizované protokoly – buď přes MCP (nový standard) nebo klasické API.

---

## ⚠️ Realistická očekávání

MCP je nová technologie – dokumentace se mění, ne všechno funguje, jak má. První setup **nemusí fungovat napoprvé** — to je normální. První setup vám může trvat 2-3 hodiny a půlku času budete debugovat JSON konfigurace. Ale když to funguje, je to magie! Každá chyba vás naučí, jak systém funguje.

---

## 🚀 Quick Win

**Poznámka:** API a MCP není „quick win" — vyžaduje technické znalosti.

**Nejjednodušší cesta:**
1. Stáhněte **Claude Desktop** (má vestavěnou MCP podporu)
2. Najděte MCP server pro filesystem (🔗 https://smithery.ai/ nebo GitHub)
3. **Pomoz si AI:** Řekni Claude "Pomoz mi nastavit MCP config pro filesystem"
4. Přidejte do Claude Desktop config (JSON soubor) – AI ti pomůže s formátem
5. Restartuj Claude Desktop
6. Zkuste: "Analyzuj soubory v této složce"
7. **Nefunguje napoprvé?** To je normální — debuguj JSON config, kontroluj chybové hlášky

---

## Co je API a MCP?

### API (Application Programming Interface)

**Co je API:** Rozhraní, které umožňuje aplikacím komunikovat mezi sebou přes internet (☁️ cloud).

**Jak funguje:**
```
Vaše aplikace → posílá požadavek přes internet → API server (někde v cloudu)
→ zpracuje → vrátí odpověď
```

**Příklad:**
- Custom GPT volá OpenAI API → server zpracuje → vrátí odpověď
- Make.com volá AI API → AI analyzuje text → vrátí výsledek
- Váš chatbot volá API pro počasí → získá aktuální data

**API klíč (API key):** „Heslo" pro přístup k API. Nikdy ho nesdílejte! Kdokoliv s vaším API klíčem může volat službu na váš účet a generovat náklady.

**Použití:** Propojení vzdálených služeb, automatizace, volání AI z jiných aplikací.

---

### MCP (Model Context Protocol)

**Co je MCP:** MCP is an open protocol that enables AI models to securely interact with local and remote resources through standardized server implementations. This protocol extends AI capabilities through file access, database connections, API integrations, and other contextual services.

**Lidsky řečeno:** Nový standard pro propojení AI s nástroji a daty – jeden univerzální způsob, jak AI komunikuje s externími zdroji.

**Co MCP umožňuje (příklady externích nástrojů):**
- 📁 **Soubory:** Číst a analyzovat lokální soubory
- 🗄️ **Databáze:** Dotazovat SQLite, PostgreSQL
- 🌐 **Web scraping:** Firecrawl pro stahování webů
- 🔧 **Automatizace:** N8N pro workflow
- 🐙 **Git:** Práce s repository
- 🔍 **Vyhledávání:** Brave Search, Google
- 📊 **Google Sheets:** Číst a editovat tabulky
- 📧 **Email:** Gmail integrace
- A mnoho dalších (300+ serverů)

**Jak to funguje:**
1. **MCP server** = poskytuje přístup k datům/nástrojům (lokálně 🏠 nebo cloud ☁️)
2. **AI client** = Claude Desktop, ChatGPT, Cursor a další
3. AI se ptá → MCP server zpracuje → vrátí data → AI odpoví

---

### 🏠 Local vs ☁️ Cloud – co to znamená?

**Confused about Local 🏠 vs Cloud ☁️?**

**Local 🏠 (lokální):**
- MCP server komunikuje s **lokálně nainstalovaným softwarem** na vašem počítači
- **Příklady:**
  - Filesystem: čtení souborů na vašem disku
  - Chrome browser: ovládání prohlížeče
  - SQLite databáze na disku
  - Git repository na počítači

**Cloud ☁️ (vzdálené):**
- MCP server komunikuje s **vzdálenými API** přes internet
- **Příklady:**
  - Weather API: aktuální počasí
  - Brave Search: webové vyhledávání
  - GitHub API: vzdálené repository
  - Google Drive: soubory v cloudu

**Prakticky:** Local = běží na vašem počítači, Cloud = volá služby přes internet

---

### Rozdíl mezi API a MCP

| **Aspekt** | **API** | **MCP** |
|------------|---------|---------|
| **Co to je** | Rozhraní pro vzdálené služby | Protokol pro lokální i vzdálené zdroje |
| **Kde běží** | ☁️ Cloud (vzdálené servery) | 🏠 Local nebo ☁️ Cloud |
| **Použití** | Volání vzdálených služeb (počasí, AI) | Přístup k souborům, databázím, nástrojům |
| **Standardizace** | Každé API je jiné | Jeden standardní protokol |
| **Příklad** | OpenAI API, Weather API | Filesystem, Firecrawl, N8N |
| **Bezpečnost** | API key přes internet | Může běžet jen lokálně (bezpečnější) |

**Kdy použít co:**
- **API:** Potřebuji volat vzdálenou službu (AI, počasí, platby)
- **MCP:** Chci, aby AI pracovala s mými daty/nástroji (soubory, databáze)

---

## Nástroje a, jak je nastavit

### 1. Claude Desktop + MCP (nejlepší podpora!)

**Co to je:** Claude Desktop má vestavěnou plnou podporu MCP serverů.

**Další nástroje s MCP podporou:**
- **ChatGPT (developer version):** Experimentální MCP podpora
- **Cursor:** Pro AI coding
- **Zed:** Code editor s MCP
- **Continue:** VS Code extension

**Tip:** Claude Desktop má aktuálně nejstabilnější MCP implementaci.

**Dostupné MCP servery (300+ a roste):**
- 📁 **Filesystem:** čtení a práce se soubory
- 🌐 **Firecrawl:** web scraping a extrakce obsahu
- 🔧 **N8N:** automatizace workflow
- 🗄️ **SQLite:** lokální databáze
- 🐙 **Git/GitHub:** práce s repository
- 🔍 **Brave Search:** webové vyhledávání
- A mnoho dalších...

**Přehledy MCP serverů:**
- 🔗 https://smithery.ai/ (kurátorovaný seznam)
- 🔗 https://github.com/punkpeye/awesome-mcp-servers (community seznam)
- 🔗 https://cursor.directory/mcp (Cursor specifické)

**Setup krok za krokem:**

**Krok 1: Instalace Claude Desktop**
- Stáhněte z claude.ai/download
- Přihlas se

**Krok 2: Najděte config soubor**

Lokace podle OS:
- **macOS:** `~/Library/Application Support/Claude/claude_desktop_config.json`
- **Windows:** `%APPDATA%\Claude\claude_desktop_config.json`
- **Linux:** `~/.config/Claude/claude_desktop_config.json`

**Krok 3: Vytvořte nebo upravte config**

**💡 Tip:** Můžete si pomoct AI! Řekněte Claude nebo ChatGPT: *"Pomoz mi nastavit MCP config pro Claude Desktop - chci používat filesystem server pro složku Documents"* a AI vám config vygeneruje.

Otevřete soubor v editoru (VS Code, Notepad++):

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/Users/vase-jmeno/Documents"]
    }
  }
}
```

**Vysvětlení:**
- `"filesystem"` = název serveru (jakýkoliv)
- `"command": "npx"` = spustí Node.js balíček
- `"args"` = parametry (který server + cesta ke složce)

**Krok 4: Restartuj Claude Desktop**

- Zavři a znovu otevři Claude Desktop
- Měly by se objevit ikony 🔨 (tools available)

**Krok 5: Testujte**

```
"Analyzuj soubory v mé Documents složce"
"Najděte všechny Python soubory"
"Přečti obsah README.md"
```

Claude použije MCP filesystem server.

---

### Další příklady MCP serverů (stručně)

**Příklad 1: Firecrawl 🌐 (web scraping) – Cloud ☁️**

```json
{
  "mcpServers": {
    "firecrawl": {
      "command": "npx",
      "args": ["-y", "@mendable/firecrawl-mcp"],
      "env": {
        "FIRECRAWL_API_KEY": "tvuj_api_klic"
      }
    }
  }
}
```

**Co můžete:** "Stáhni obsah z example.com a vytvoř mi z toho markdown"

---

**Příklad 2: N8N 🔧 (automatizace) – Local 🏠**

```json
{
  "mcpServers": {
    "n8n": {
      "command": "npx",
      "args": ["-y", "@n8n/mcp-server"],
      "env": {
        "N8N_API_URL": "http://localhost:5678",
        "N8N_API_KEY": "tvuj_n8n_klic"
      }
    }
  }
}
```

**Co můžete:** "Spusť workflow 'Email notification' v N8N"

---

**Příklad 3: Filesystem 📁 (více složek) – Local 🏠**

```json
{
  "mcpServers": {
    "work-files": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/Users/vase-jmeno/Work"]
    },
    "projects": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/Users/vase-jmeno/Projects"]
    }
  }
}
```

**Co můžete:** "Porovnej soubory ve Work a Projects složkách"

---

### 2. ChatGPT + API integrace (přes Actions)

**Co to je:** Custom GPTs mohou volat externí API přes „Actions".

**Setup:**
1. Vytvořte Custom GPT
2. Configure → Actions → Add Action
3. Definujte API endpoint (URL, method, parameters)
4. Může vyžadovat OAuth autentizaci

**Kdy použít:** Chcete, aby ChatGPT mohl volat vaše vlastní API nebo třetí strany.

---

### 3. Cursor + MCP

**Co to je:** Cursor (AI code editor) má vestavěnou MCP podporu.

**Setup:**
- Podobně jako Claude Desktop
- Cursor Settings → MCP
- Přidejte MCP servery

**Použití:** AI coding asistent s přístupem k filesystému, databázím, Git.

---

### 4. Automatizace (Make, Relay) + AI API

**Co to je:** Automatizační nástroje volají AI API jako součást workflow.

**Příklad workflow:**
1. Trigger: Nový email
2. HTTP Request → OpenAI API (analyzuj email)
3. AI vrátí: kategorie, sentiment, draft odpovědi
4. Uložte do CRM + pošli draft

**Setup v Make.com:**
- HTTP module → POST request
- URL: `https://api.openai.com/v1/chat/completions`
- Headers: `Authorization: Bearer YOUR_API_KEY`
- Body: JSON s prompt a parametry

**Kdy použít:** Chcete automatizovat opakující se AI úkoly bez manuálního spouštění.

---

## 💡 Příklady z praxe

### Příklad 1: Content researcher s Firecrawl

**Situace:** Marketér potřebuje analyzovat konkurenční weby a vytvářet content briefy.

**Řešení:** Claude Desktop + Firecrawl MCP (☁️ cloud)

**Co dělá:**
- "Stáhni obsah z konkurence.com/blog a udělej mi přehled témat, která pokrývají"
- "Analyzuj SEO strukturu jejich článků"
- Claude přes Firecrawl stáhne web → vyextrahuje text → analyzuje

**Úspora:** 2-3 hodiny týdně manuálního kopírování obsahu.

---

### Příklad 2: Automatizace workflow s N8N

**Situace:** Firma používá N8N pro automatizace a chce je ovládat přirozenou řečí.

**Řešení:** Claude Desktop + N8N MCP (🏠 local)

**Co dělá:**
- "Spusť workflow pro odeslání weekly reportu"
- "Zkontroluj status posledního importu dat"
- Claude ovládá N8N přes MCP → spouští workflow

**Benefit:** Nemusíte hledat a klikat v N8N interface.

---

### Příklad 3: Analýza projektových souborů

**Situace:** Developer chce rychle pochopit strukturu projektu.

**Řešení:** Claude Desktop + Filesystem MCP (🏠 local)

**Co dělá:**
- "Analyzuj všechny Python soubory v této složce a vytvoř mi přehled funkcí"
- "Najdi všechny TODO komentáře v projektu"
- "Porovnej verze config souborů ve Work a Projects"

**Úspora:** 30+ minut denně procházení souborů.

---

### Další příklady:
- **Cursor + Git MCP:** "Udělej commit s popisem změn" (🏠 local)
- **Make + OpenAI API:** Automatické kategorizování emailů (☁️ cloud)
- **Claude + Brave Search MCP:** "Najdi aktuální info o AI regulacích v EU" (☁️ cloud)

---

## Bezpečnost

### NIKDY nesdílej API keys!

- API keys = heslo k tvým datům
- Někdo ho získá → může volat API na váš účet = náklady a riziko

### Bezpečné uložení:
- **Environment variables:** Ne přímo v kódu
- **Secret management:** 1Password, Bitwarden, AWS Secrets
- **Rotace keys:** Pravidelně měň

### Oprávnění:
- **Read-only:** Pokud možno začni s read-only přístupem
- **Minimum privilege:** Jen, co je potřeba
- **Monitoring:** Sledujte API volání

---

## Quick Action Guide

### Klíčové závěry
- MCP je nový standard (2024) – rychle se vyvíjí
- Claude Desktop má aktuálně nejstabilnější MCP podporu (ChatGPT developer version má experimentální)
- Local 🏠 vs Cloud ☁️: Local = váš počítač, Cloud = vzdálené API
- Bezpečnost: nikdy nesdílej API keys
- AI vám může pomoct s konfigurací!
- Začněte s read-only přístupem (bezpečnější)

### Co se vyhnout (a, co dělat místo toho)
- ❌ Dát API do veřejného Git repository. ✅ Použijte environment variables nebo .env soubor (v .gitignore).
- ❌ Dát AI full write access hned. ✅ Začněte read-only, pak postupně přidávej oprávnění.
- ❌ Zapomenout na rate limits. ✅ Sledujte kolik volání děláte, API má limity.
- ❌ Kopírovat JSON config s chybami. ✅ Používej JSON validator (jsonlint.com) před restartováním.

### Začněte tady

**Postupnost - začni jednoduše:**

**Pro MCP:**
1. Stáhněte **Claude Desktop** (má nejstabilnější MCP podporu)
2. Začněte s nejjednodušším MCP serverem (**filesystem** 📁 🏠 local)
3. Najděte config soubor podle OS
4. **Pomoz si AI:** Řekněte Claude "Pomoz mi nastavit MCP config pro filesystem"
5. Přidejte server do JSON config (nebo nechte AI vygenerovat)
6. Restartuj Claude Desktop
7. Testujte s jednoduchými dotazy
8. **Nefunguje?** Validuj JSON (jsonlint.com), kontroluj chybové hlášky
9. Funguje? Postupně přidávej další servery (Firecrawl ☁️, N8N 🏠)

**Kdy použít pokročilé:**
- Filesystem MCP funguje → můžete přidat další servery
- Potřebuješ custom integrace → piš vlastní MCP server

**Pro API:**
1. Zjisti jaké API potřebujete (OpenAI, Anthropic, Google)
2. Získej API key (v account settings)
3. Uložte key **bezpečně** (environment variable, NIKDY ne v kódu!)
4. **Nechte AI napsat kód** — dej mu API dokumentaci a řekni, co potřebujete
5. Zkuste základní volání
6. Integruj do svého workflow (Make, vlastní kód)

**Důležité:** První setup zabere čas a **nebude fungovat napoprvé**. Buďte trpěliví, debugujte krok za krokem, sledujte error messages. To je normální a každý tudy prochází.

---

## Zdroje (doporučeno)

### MCP
- **MCP Oficiální dokumentace:** https://docs.claude.com/en/docs/mcp
- **MCP servery (oficiální):** https://github.com/modelcontextprotocol/servers
- **MCP přehledy (community):**
  - 🔗 **Smithery** (kurátorovaný seznam): https://smithery.ai/
  - 🔗 **Awesome MCP Servers** (GitHub): https://github.com/punkpeye/awesome-mcp-servers
  - 🔗 **Cursor Directory MCP**: https://cursor.directory/mcp
- **Claude Desktop:** https://claude.ai/download

### API dokumentace
- **OpenAI:** https://platform.openai.com/docs
- **Anthropic (Claude):** https://docs.anthropic.com
- **Google Gemini:** https://ai.google.dev/docs
- **Mistral:** https://docs.mistral.ai

### Další nástroje
**Tip:** Kompletní přehled nástrojů najdete na https://drimalka.com/aplikace-ne-druhy-mozek-nejen-s-ai/