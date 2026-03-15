# Hromadně konvertovat desítky souborů do jednotného formátu

## Obecné informace

Napsaný skript využívající API pro batch zpracování velkého množství souborů. Místo ruční konverze jednoho souboru po druhém — automatizace pro 10, 50 nebo 200 souborů najednou.

**Proč na tom záleží:** 50 PDF převést na text ručně = hodiny práce. Se skriptem využívajícím API = 30 minut běhu. Úspora stovek hodin.

**Základní princip:** Návrh postupu → AI napíše skript → Test na malém vzorku → Batch všechno.

## ⚠️ Realistická očekávání

První skript nebude fungovat dokonale. API limity, formátování, edge cases — vše se musí vyladit. Počítej s 2-3 hodinami ladění, než skript běží spolehlivě. **Vždy testuj na 3-5 souborech, než spustíš batch!**

**Důležité:** Během tohoto procesu se naučíš spoustu tipů a triků — například jaké AI modely použít pro různé účely, jak optimalizovat náklady, nebo, jak řešit specifické problémy.

## 🚀 Quick Win

1. Vyberte 3 PDF soubory
2. Požádej ChatGPT/Claude: „Napište Python skript s Anthropic API pro extrakci textu z PDF"
3. AI napíše skript
4. Spusťte ho na 3 testovacích PDF
5. Funguje? Hotovo — máte základ pro batch processing!

**Klíčové:** Získej API přístup k AI modelům (některé jsou zdarma za určitých podmínek, některé placené). Pak nechej AI napsat celý skript — stačí dát odkaz na API dokumentaci a říct, co potřebujete.

## API k použití

### 1. Text API (pro zpracování obsahu)

**Anthropic Claude:**
- claude-sonnet-4-20250514
- Výborné na strukturované zpracování
- Batch API mode = levnější

**OpenAI GPT:**
- gpt-4 nebo gpt-4-turbo
- Batch processing dostupný

**Google Gemini:**
- gemini-pro
- Dobré na různé formáty

**Mistral:**
- mistral-large
- Rychlé zpracování

### 2. Web Scraping API

**Exa:**
- AI-powered web search a scraping
- https://exa.ai

**Firecrawl:**
- Crawling a scraping optimalizovaný pro AI
- https://firecrawl.dev

### 3. OCR API (doporučené)

**Mistral OCR** (doporučeno)
- Vysoce přesné rozpoznávání textu integrované v Mistral AI modelech
- Pixtral model s OCR
- Zvládá i komplexní dokumenty a ručně psaný text
- **Web:** https://mistral.ai/news/mistral-ocr

**Azure OCR / Computer Vision** (doporučeno)
- Cloudové OCR API od Microsoftu s vysokou přesností
- Robustní a velmi přesné
- Podpora 100+ jazyků
- **Web:** https://azure.microsoft.com/products/ai-services/ai-vision

**DeepSeek OCR** (doporučeno)
- Pokročilé open source OCR řešení
- Podpora mnoha jazyků a typů dokumentů
- **Web:** https://www.deepseek.com

## Proces krok za krokem

### 1. Navrhni postup

**Extra důležité u automatizace:** Musíš napsat dobrý prompt pro AI. Nezačínej hned s velkým množstvím souborů — začni postupně, otestuj na malém vzorku a vylaď, jak prompt, tak zpracování.

```
Příklad promptu pro AI:
Potřebuji zpracovat 50 PDF souborů.
Z každého chci:
- Vytáhnout text
- Identifikovat klíčové sekce
- Extrahovat data do struktury

Navrhni postup:
1. Jaké API použít
2. Jak batch zpracovat
3. Jak uložit výsledky
4. Jak nejlíp nastavit prompt pro zpracování
```

### 2. Nechej AI napsat skript

**Hlavně:** Nechte si skript napsat AI! Stačí dát odkaz na API dokumentaci a říct, co potřebujete. AI vám napíše celý funkční skript.

**Příklad promptu:**
```
Napište Python skript který:
1. Přečte všechny PDF v složce
2. Pro každý PDF použije Claude API k extrakci textu
3. Strukturuje text podle šablony
4. Uloží výsledky do JSON

Zeptej se mě, jak to udělat nejlíp — optimalizace, vhodný model, rate limiting, atd.
```

### 3. Test na malém vzorku

**⚠️ KRITICKÉ: Vždy testuj první!**

1. Vyberte 3-5 reprezentativních souborů
2. Spusťte skript
3. Zkontrolujte výstupy:
   - Jsou data správně?
   - Funguje error handling?
   - Je struktura správná?

### 4. Batch zpracování

Když test funguje:
```bash
# Spusťte pro všechny soubory
python batch_process.py

# Monitoruj progress
# Nechte běžet (může trvat hodiny)
```

**Batch Mode API výhody:**
- 50% levnější, než standardní API
- Zpracování na pozadí
- Ideální pro velké množství dat

## 💡 Příklad z praxe

Legal assistant měl 200 skenovaných smluv v PDF. Použil Microsoft Azure OCR API + Claude pro extrakci klíčových údajů (strany, částky, termíny). 

První verze skriptu trvala 3 hodiny ladění:
- OCR kvalita nebyla dokonalá
- Nějaké PDF byly rozbitné
- Struktura dat se musela upravit

Po otestování na 10 smlouvách spustil batch. Za 2 hodiny měl Excel s extrahovanými daty ze všech smluv. Manuálně by to bylo 2 týdny práce.

## Konkrétní příklady použití

Co všechno se dá dělat s batch zpracováním:

- **Opravit formátování textů** stažených z LinkedInu (nebo jiných platforem)
- **Analyzovat emailovou komunikaci** — identifikovat vzory, témata, sentiment
- **Analyzovat konverzace s AI** — zjistit, co funguje, co ne, jak zlepšit prompty
- **Generovat personalizovanou komunikaci** podle předchozích zpráv a požadavků účastníků
- **Exportovat prezentace do obrázků** (1 slide = 1 obrázek), použít OCR a udělat popis každého slidu
- **Čistit a strukturovat adresáře** na počítači, stránky v Notionu, tabulky a další datové zdroje
- **Porovnávat dokumenty** — najít rozdíly, změny, nebo konzistenci napříč verzemi
- **Extrahovat data z faktur/smluv** do strukturovaných tabulek
- **Převádět rozsáhlé PDF knihy** na prohledávatelný text s kapitolami
- **Analyzovat zákaznické recenze** z různých zdrojů a vytvořit souhrnný report

## Quick Action Guide

### Klíčové závěry
- Nechej AI napsat skript
- **VŽDY test na malém vzorku** (3-5 souborů)
- Batch mode API = levnější
- Kombinuj API podle potřeby (OCR + Claude, Scraping + GPT)

### Co se vyhnout (a udělat místo toho)
- ❌ Nespouštěj batch bez testu. ✅ Vždy 3-5 testovacích souborů první.
- ❌ Nepoužívejte standardní API pro batch. ✅ Batch mode je 50% levnější.
- ❌ Neignoruj error handling. ✅ Jeden rozbitý soubor nesmí zastavit celý batch.

### Start zde
1. Identifikujte, co potřebujete zpracovat (PDF, obrázky, weby)
2. Požádej AI navrhnout postup + napsat skript
3. Test na 3-5 souborech
4. Vylaďte dokud funguje spolehlivě
5. Spusťte batch pro všechny soubory
