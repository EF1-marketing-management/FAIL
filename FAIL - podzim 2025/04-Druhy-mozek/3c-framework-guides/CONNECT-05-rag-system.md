# Jak nastavit RAG systém pro přesné odpovědi z firemních znalostí

**Přehled:** Pokročilý systém, který dynamicky vyhledává relevantní informace ve vašich dokumentech před generováním odpovědi.

**Proč na tom záleží:** Místo nahrání všech dokumentů najednou (limit context window), RAG najde jen relevantní části a použije je pro odpověď. To znamená: práce s tisíci dokumentů, přesné citace, méně halucinací.

**Základní princip:** RAG = Retrieval (vyhledání) + Augmented (obohacení) + Generation (generování). AI nejdřív najde relevantní části dokumentů, pak je použije jako kontext pro odpověď.

---

## ⚠️ Realistická očekávání

RAG je pokročilá technologie – první implementace **nemusí fungovat napoprvé a nebude perfektní**. To je normální. Chunking strategie (jak rozdělit dokumenty), embedding kvalita, retrieval přesnost (jak dobře najde relevantní části) – vše vyžaduje experimentování a iterace. Očekávejte dny až týdny iterací, než systém běží uspokojivě. Každý experiment vás ale posune blíž k fungujícímu řešení.

---

## 🚀 Quick Win

**DŮLEŽITÉ: RAG není „quick win" projekt.** Je to pokročilá implementace. 

**Nejjednodušší cesta k RAG funkcionalitě:**
1. Začněte s **Notion AI** nebo **Microsoft Copilot** (mají RAG vestavěný)
2. Nahrajte dokumenty
3. Testujte odpovědi
4. To je nejrychlejší cesta k RAG funkcionalitě — funguje hned

**Vlastní RAG:** Počítej s týdny práce a technickými znalostmi.

---

## Co je RAG?

**RAG lidsky vysvětleno:** Systém, který funguje jako knihovník. Místo přečtení všech knih (dokumentů) najednou, knihovník (RAG) nejdřív najde relevantní kapitoly z různých knih a pak vám z nich odpoví. To umožňuje pracovat s tisíci dokumentů efektivně.

### Rozdíl: Simple chatbot vs. RAG

**Simple chatbot (Custom GPT, základní Claude Project):**
1. Nahraji dokumenty
2. AI je má všechny v context window (kontextové okno - paměť AI)
3. AI odpoví podle všeho
4. **Limit:** Context window (~200K tokenů = ~500 stran)

**RAG systém:**
1. Nahraji tisíce dokumentů
2. Dokumenty se rozdělí na kousky (**chunks - části dokumentu**) a převedou na **embeddings (vektorové reprezentace textu)**
3. Když se ptám → systém **nejdřív vyhledá** 5-10 nejrelevantnějších chunks
4. Jen ty pošle AI jako kontext
5. AI odpoví na základě vybraných chunks
6. **Výhoda:** Funguje s obrovskými databázemi (1000+ dokumentů)

**Embedding (embedding):** Převod textu na čísla (vektory), které zachycují význam. Podobné texty mají podobné vektory.

**Vector database (vektorová databáze):** Specializovaná databáze pro ukládání a vyhledávání embeddings.

---

### Jak RAG funguje (technicky)

**1. Příprava (jednou):**
```
Dokument → rozděl na chunks (např. 500 slov) → 
vytvoř embedding (vektorová reprezentace) → 
ulož do vector database
```

**2. Query (když se ptáš):**
```
Otázka → vytvoř embedding otázky → 
najdi podobné chunks ve vector DB → 
vezmi top 5-10 chunks → 
pošli je + otázku do LLM → 
LLM odpoví s citacemi
```

**Výsledek:** Přesné odpovědi s citacemi konkrétních dokumentů, škáluje na tisíce dokumentů.

---

## Nástroje

### No-code: Použijte vestavěný RAG

Tyto nástroje mají RAG už implementovaný:

**1. Notion AI** (doporučeno)
- Automaticky RAG nad celým Notion workspace
- Zero setup, žádné manuální nahrávání
- Cena: $10/uživatel/měsíc
- **Web:** https://www.notion.com

**2. Microsoft Copilot (M365)** (doporučeno)
- RAG nad SharePoint, OneDrive, Teams
- Enterprise security a compliance
- Integrace s celým Microsoft 365 ekosystémem
- Cena: $30/uživatel/měsíc (vyžaduje M365)
- **Web:** https://www.microsoft.com/microsoft-copilot

**3. ChatGPT Enterprise** (doporučeno)
- RAG nad nahranými dokumenty
- Custom GPTs s velkými knowledge bases
- Enterprise-grade bezpečnost
- Cena: Enterprise pricing
- **Web:** https://openai.com/chatgpt/enterprise

**Kdy použít no-code:** Chceš funkční RAG rychle a nemáš speciální požadavky.

---

### Custom RAG: Když potřebujete kontrolu

**Nástroje potřebné:**

**1. Vector Database (ukládání embeddings):**
- **Pinecone:** Managed service, snadný start (https://www.pinecone.io)
- **Weaviate:** Open-source, self-hosted (https://weaviate.io)
- **Chroma:** Lightweight, pro development (https://www.trychroma.com)
- **Qdrant:** Fast, open-source (https://qdrant.tech)

**2. Embedding Models (převod textu na vektory):**
- **OpenAI Embeddings:** text-embedding-3-large (https://platform.openai.com)
- **Voyage AI:** Specialized embeddings (https://www.voyageai.com)
- **Open-source:** sentence-transformers

**3. Orchestration (spojení všeho - doporučeno):**
- **LlamaIndex:** Framework pro propojení LLM s externími daty, ideální pro stavbu vlastních znalostních bází a Q&A systémů (https://www.llamaindex.ai)
- **LangChain:** Populární framework pro tvorbu AI aplikací s workflow, agenty a integrací mnoha nástrojů (https://www.langchain.com)
- **Haystack:** Open-source RAG framework (https://haystack.deepset.ai)

---

## Proces: Postavit vlastní RAG

### Fáze 1: Příprava dokumentů

**1. Sesbírej dokumenty**
- Všechny relevantní dokumenty (PDF, Word, markdown, HTML)
- Vyčisti: odstraň nepotřebné části

**2. Chunking (rozdělení na kousky)**

Strategie závisí na obsahu:
- **Firemní dokumenty:** 300-500 slov per chunk
- **Technická dokumentace:** podle sekcí/nadpisů
- **FAQ:** jedna otázka+odpověď = jeden chunk

**Příklad chunking:**
```python
# Jednoduchý příklad (ve skutečnosti používej LlamaIndex/LangChain)
def chunk_text(text, chunk_size=500):
    words = text.split()
    chunks = []
    for i in range(0, len(words), chunk_size):
        chunk = ' '.join(words[i:i+chunk_size])
        chunks.append(chunk)
    return chunks
```

**3. Vytvořte embeddings**

**Nechte AI napsat kód:**
```
Požádej ChatGPT/Claude: „Napište Python script který vytvoří embeddings 
z textových chunks pomocí OpenAI API a uloží je do Pinecone."
```

AI vám napíše celý funkční kód.

**4. Uložte do vector database**

Opět nechte AI napsat kód — dejte mu dokumentaci Pinecone/Weaviate/Chroma a popis, co potřebujete.

---

### Fáze 2: Query (hledání a odpověď)

**1. User se zeptá**

**2-4. Vytvořte embedding, vyhledej, pošli do LLM**

**Nechte AI napsat celý query pipeline:**
```
Požádej ChatGPT/Claude: „Napište Python script pro RAG query který:
1. Vezme otázku uživatele
2. Vytvoří embedding otázky pomocí OpenAI
3. Vyhledá top 5 podobných chunks v Pinecone
4. Pošle je jako kontext do GPT-4
5. Vrátí odpověď s citacemi

Použijte best practices pro error handling a strukturované výstupy."
```

AI vám napíše celý funkční kód. Nemusíte psát ručně.

---

## 💡 Příklad z praxe

**Legal tech startup** postavil RAG systém nad 5000 soudních rozhodnutí. Advokáti se ptají: „Precedens pro nezaplacené faktury nad 50k?" 

**Proces:**
1. RAG najde 5-10 nejpodobnějších případů (podle embedding similarity)
2. Pošle je GPT-4 jako kontext
3. GPT vygeneruje odpověď s citacemi konkrétních případů

**Výsledky:**
- Přesnost 95%
- Manuální hledání: hodiny → RAG: 10 sekund
- Investice: 4 týdny development

**Další příklady:**
- Customer support nad produktovou dokumentací (1000+ stránek)
- HR assistant nad firemními policies (500+ dokumentů)
- Technical support nad API dokumentací
- Research assistant nad vědeckými papery

---

## Kdy potřebujete RAG?

### Potřebuješ RAG když:
- ✅ Máš 100+ dokumentů
- ✅ Dokumenty dohromady překračují context window (500+ stran)
- ✅ Potřebuješ přesné citace zdrojů
- ✅ Chceš minimalizovat halucinace
- ✅ Dokumenty se často mění (RAG snadno aktualizuješ)

### NEPOTŘEBUJEŠ RAG když:
- ❌ Máš 10-20 dokumentů → stačí Custom GPT nebo Claude Project
- ❌ Dokumenty jsou malé (celkem < 200 stran)
- ❌ Nemáš technické znalosti a budget pro custom řešení
- ❌ Potřebuješ to rychle → použij Notion AI nebo Copilot

---

## Quick Action Guide

### Klíčové závěry
- RAG je nutný pro velké knowledge bases (100+ dokumentů)
- Kvalita závisí na chunking strategii a embeddings
- No-code cesta: Notion AI nebo Copilot pokud nemáš speciální požadavek
- Custom RAG = týdny práce, ale větší kontrola

### Co se vyhnout (a, co dělat místo toho)
- ❌ Začít s custom RAG když stačí no-code. ✅ Nejdřív zkus Notion AI nebo Copilot.
- ❌ Špatný chunking (příliš velké nebo malé). ✅ Testujte různé velikosti chunks na vzorku dokumentů.
- ❌ Zapomenout na metadata. ✅ Přidejte k chunks metadata (zdroj, datum, kategorie) pro lepší filtrování.
- ❌ Neotestovat retrieval kvalitu. ✅ Změř kolik % dotazů najde správné chunks.

### Začněte tady

**Cesta 1: No-code (1 den)**
1. Pokud máte Notion: aktivuj Notion AI
2. Pokud máte M365: aktivuj Copilot
3. Testujte s reálnými dotazy
4. Funguje dost dobře? Hotovo!

**Cesta 2: Custom RAG (4-6 týdnů)**
1. Sesbírej a vyčisti dokumenty (1 týden)
2. Zvolte vector database (Pinecone pro start)
3. Experimentuj s chunking strategií (1 týden):
   - Zkuste 300, 500, 1000 slov per chunk
   - Změř které funguje nejlép
4. Implementujte základní RAG pipeline (1 týden):
   - Chunking → Embeddings → Vector DB → Query → LLM
   - Použijte LlamaIndex nebo LangChain
5. Testujte a iteruj (2 týdny):
   - 100+ testovacích dotazů
   - Měř přesnost odpovědí
   - Ladění chunking, retrieval, prompts
6. Deploy a monitoring

---

## Zdroje

**Tip:** Kompletní přehled nástrojů najdete na https://drimalka.com/aplikace-ne-druhy-mozek-nejen-s-ai/

---

**Důležité:** Custom RAG je project na týdny až měsíce, ne dny. Pokud nemáš tech tým nebo čas, použij no-code řešení.