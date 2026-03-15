# Převádět různé formáty (audio, screenshoty, PDF) do textu čitelného pro AI

## Obecné informace

Transformace různých formátů do textu otevírá možnost pracovat s informacemi v AI nástrojích. OCR, audio přepisy a PDF zpracování — všechno přes manuální použití chat nástrojů s dobrým promptem.

**Proč na tom záleží:** AI si nejlépe poradí s jednoduchými textovými formáty (a pokud nemáme textový, musí aplikovat pokročilejší technologie jako OCR). Nicméně pro většinu jednodušších use casů jsou právě jednoduché formáty jako text/markdown nejlepší. Klíčový rozdíl je v kvalitě promptu — dobrý prompt určí, jestli dostanete chaos nebo strukturované poznámky.

**Základní princip:** Prompt je základ. Definujte přesně, co chcete, iteruj dokud nedostaneš správný výstup, a ulož si prompt pro příště.

## ⚠️ Realistická očekávání

První prompt nedá dokonalý výsledek. OCR z rozmazaných fotek může být špatné. Přepis s akcentem může mít chyby. Iterujte prompt 2-3× než dostanete to, co chcete.

## 🚀 Quick Win

1. Udělejte screenshot nějaké tabulky/textu
2. Nahrajte do ChatGPT
3. Napište: „Převeď tento obrázek do tabulky/markdown textu"
4. Zkopírujte výsledek
5. Hotovo — máte funkční OCR!

## Konkrétní nástroje

### 1. OCR (Obrázky, Screenshoty, Skenované dokumenty)

**ChatGPT (GPT-4 Vision):**
- Nahrajte obrázek přímo do chatu
- GPT-4 umí číst text, tabulky, diagramy, dokonce i rukopis
- Funguje s PDF, PNG, JPG

**Claude:**
- Upload obrázku nebo PDF (až 100 stran)
- Velmi silný na komplexní dokumenty a layouty
- Dokáže zpracovat i handwriting

**Gemini:**
- Podobné schopnosti jako ChatGPT
- Dobré na vizuální analýzu a OCR
- Má největší kontextové okno ze všech AI nástrojů

**NotebookLM:**
- Umí zpracovat až stovky stránek najednou
- Dokáže převádět text z videa
- Ideální pro analýzu rozsáhlých dokumentů

**Jak použít:**
```
Příklad promptu pro OCR:
Převeď tento obrázek do strukturovaných poznámek. 
Použijte:
- Nadpisy pro hlavní sekce
- Bullet points pro položky
- Tabulky kde je to relevantní
- Shrnutí na konci
```

**Kdy použít:** Máš screenshot, foto whiteboard, nebo skenovaný dokument a potřebujete text vytáhnout rychle bez specializovaných nástrojů.

### 2. PDF zpracování

**Všechny hlavní AI (ChatGPT, Claude, Gemini):**
- Nahrajte PDF přímo
- AI vidí text i obrázky v PDF
- Dokáže extrahovat, shrnout, strukturovat

**Jak použít:**
```
Příklad promptu pro PDF:
Přečti tento PDF a vytvoř strukturované poznámky:
1. Hlavní témata (3-5 bullet points)
2. Klíčové insights pro každé téma
3. Action items pokud nějaké jsou
4. Shrnutí do 2 vět
```

**Kdy použít:** Máš PDF prezentaci, report nebo dokument a chcete rychlé shrnutí nebo extrakci klíčových informací místo ručního čtení.

### 3. Audio transkripce

**TurboScribe:** (doporučeno pro jednotlivé soubory)
- AI-powered transkripce (používá Whisper)
- 99.8% přesnost, 98+ jazyků
- Až 10 hodin dlouhé soubory
- Free: 3 transkripce denně (30 min/soubor)
- Paid: neomezené za $10/měsíc
- **Web:** https://turboscribe.ai

**Meeting přepisy — automatické nástroje (doporučeno):**
- **TLDV** — Specializovaný nástroj pro nahrávání a přepisování schůzek na Google Meet a Zoom (https://tldv.io)
- **Fireflies.ai** — AI asistent pro automatické přepisování, podporuje víc platforem (Teams, Zoom, Meet) (https://fireflies.ai)
- **Microsoft Teams Copilot** — Integrovaný AI asistent v Teams pro přepisy a souhrny (https://www.microsoft.com/microsoft-teams/)
- Všechny automaticky nahrávají a přepisují schůzky
- **Tyto nástroje umí zpracovat jakékoliv video** (nejen živé schůzky)

**Word Online:**
- Umí přepisy z audio souborů
- Můžete buď diktovat přímo, nebo nahrát záznam

**Jak použít s AI zpracováním:**

1. Nahrajte audio do TurboScribe → získej přepis
2. Zkopírujte přepis do ChatGPT/Claude s promptem:

```
Z tohoto audio přepisu vytvoř strukturovaný zápis:

## Klíčová rozhodnutí
[co jsme se rozhodli]

## Akční body
[kdo | co | do kdy]

## Důležité insights
[co jsme se naučili/zjistili]

## Otevřené otázky
[co zbývá vyřešit]
```

**Kdy použít:** Máš nahrávku meetingu, podcastu nebo rozhovoru a chcete rychlý přepis místo ručního přepisování. 

## Důležité: Pracuj s promptem

**Vzorový přístup:**
1. Nahrajte soubor/obrázek
2. Definujte, jak to chcete zpracovat
3. Iterujte prompt dokud nedostaneš správný výstup
4. **Uložte si prompt** jako šablonu pro příště

**Vytvořte asistenta nebo ulož prompt:**
- Když najdete funkční prompt → ulož si ho
- Klidně vytvoř AI asistenta (Custom GPT, Claude Project) specializovaného na tento typ zpracování
- Dělej něco vzorově → najdi pattern → opakuj

## 💡 Příklad z praxe

Projektový manager nahrává screenshoty z whiteboard sessions do Claude. Používá prompt: „Převeď tento whiteboard do strukturovaného action planu: 1) Hlavní cíle, 2) Akční kroky s odpovědnými osobami, 3) Timeline". Ušetří 30 minut po každém brainstormingu.

## Quick Action Guide

### Klíčové závěry
- Prompt je základ — definuj přesně, co chcete
- Chat nástroje (ChatGPT, Claude, Gemini) zvládnou většinu OCR/PDF úkolů
- Pro audio použij TurboScribe nebo meeting nástroje (TLDV, Fireflies)

### Co se vyhnout (a udělat místo toho)
- ❌ Nenahrávej soubor bez promptu. ✅ Vždy řekni AI, jak má výstup strukturovat.
- ❌ Neakceptuj první výsledek pokud není dobrý. ✅ Iterujte prompt 2-3×.
- ❌ Nezapomeňte si ulož funkční prompty. ✅ Vytvořte si knihovnu šablon.

### Start zde
1. Udělejte test na jednom obrázku/PDF/audio se svým promptem
2. Vylaďte prompt dokud nevyhovuje
3. Uložte prompt do poznámek nebo vytvoř Custom GPT/Claude Project
4. Použijte stejný prompt pro další podobné úkoly
