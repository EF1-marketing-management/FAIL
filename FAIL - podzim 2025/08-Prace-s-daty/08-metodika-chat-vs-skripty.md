# Metodika: Kdy použít chat vs. skripty/pokročilé nástroje

Tento dokument slouží jako praktický průvodce pro rozhodování, který nástroj zvolit při práci s daty a dokumenty pomocí AI. Je určen jak pro lidi, tak pro AI agenty.

---

## 1. Práce s daty (tabulky, datasety, databáze)

### Kdy stačí chat (ChatGPT, Claude, Gemini, Copilot)

**Ideální scénáře:**
- Máš 1–2 malé tabulky (do cca 1000 řádků)
- Potřebuješ jednorázovou analýzu
- Data jsou již čistá a strukturovaná
- Stačí ti základní operace: součty, průměry, jednoduché vizualizace

**Postup:**
1. Nahraj soubor (CSV, Excel) přímo do chatu
2. Popiš, co chceš zjistit
3. Nech AI provést analýzu a interpretovat výsledky

**Omezení:**
- Velikost souboru je limitována (typicky do 50–100 MB)
- Nelze spojovat data z více zdrojů automaticky
- Každá nová analýza vyžaduje ruční nahrání

---

### Kdy použít skripty/pokročilé nástroje

**Ideální scénáře:**
- Máš 5+ tabulek nebo složek s daty
- Data vyžadují čištění, normalizaci nebo transformaci
- Potřebuješ analýzu opakovat pravidelně (denně, týdně, měsíčně)
- Pracuješ s tisíci až miliony řádků
- Potřebuješ real-time aktualizace nebo propojení s databází

**Doporučené nástroje:**
- **Claude Code / Cursor / GitHub Copilot** – pro psaní skriptů s AI asistencí
- **Google Apps Script** – pro automatizaci v Google Workspace
- **Python** (pandas, polars) – pro transformace a analýzy
- **SQL** – pro práci s databázemi
- **dbt** – pro transformace v datovém skladu

**Postup:**
1. Navrhni datový pipeline (zdroje → transformace → výstup)
2. Napiš skripty pro ETL (Extract, Transform, Load)
3. Nastav automatizaci (cron, scheduler, webhook)
4. Připoj vizualizační nástroj pro reporting

---

### Rozhodovací matice: Data

| Kritérium | Chat | Skripty |
|-----------|------|---------|
| Počet tabulek | 1–2 | 3+ |
| Počet řádků | < 1 000 | > 1 000 |
| Frekvence analýzy | Jednorázově | Opakovaně |
| Čistota dat | Již čistá | Vyžadují úpravu |
| Propojení zdrojů | Ne | Ano |
| Real-time | Ne | Ano |

---

## 2. Práce s dokumenty (texty, PDF, znalostní báze)

### Kdy stačí chat (ChatGPT, Claude, Gemini, Copilot)

**Ideální scénáře:**
- Máš 1–2 krátké dokumenty (do cca 50 stran celkem)
- Potřebuješ jednorázovou sumarizaci nebo extrakci
- Dokument je v podporovaném formátu (PDF, Word, TXT)
- Nepotřebuješ prohledávat více dokumentů najednou

**Postup:**
1. Nahraj dokument do chatu
2. Polož konkrétní otázky nebo požádej o sumarizaci
3. Iteruj – upřesňuj dotazy podle odpovědí

**Omezení:**
- Kontextové okno je omezené (i u dlouhých kontextů max. cca 200 stran)
- Nelze efektivně prohledávat stovky dokumentů
- Při každé konverzaci začínáš znovu

---

### Kdy použít skripty/pokročilé nástroje

**Ideální scénáře:**
- Máš desítky až stovky dokumentů
- Potřebuješ prohledávat celou znalostní bázi
- Dokumenty jsou v různých formátech (PDF, Word, HTML, e-maily)
- Potřebuješ porovnávat verze nebo sledovat změny
- Znalostní báze se průběžně aktualizuje

**Doporučené nástroje:**
- **Claude Code / Cursor / GitHub Copilot** – pro psaní skriptů s AI asistencí
- **Google Apps Script** – pro automatizaci v Google Workspace
- **RAG (Retrieval-Augmented Generation)** – pro prohledávání dokumentů
- **Vektorové databáze** (Pinecone, Weaviate, Chroma, Qdrant) – pro sémantické vyhledávání
- **LangChain / LlamaIndex** – pro orchestraci RAG pipeline

**Postup:**
1. Extrahuj text ze všech dokumentů (parsing)
2. Rozděl na chunky (typicky 500–1000 tokenů)
3. Vytvoř embeddingy a ulož do vektorové databáze
4. Nastav retrieval pipeline pro dotazování
5. Automatizuj indexaci nových dokumentů

---

### Rozhodovací matice: Dokumenty

| Kritérium | Chat | Skripty |
|-----------|------|---------|
| Počet dokumentů | 1–2 | 10+ |
| Celkový rozsah | < 50 stran | > 50 stran |
| Počet formátů | 1–2 | 3+ |
| Aktualizace | Jednorázově | Průběžně |
| Prohledávání | Jeden dokument | Celá báze |
| Verzování | Ne | Ano |

---

## 3. Rozhodovací strom

```
START: Jaký je tvůj úkol?
│
├─► Práce s DATY (tabulky, čísla)
│   │
│   ├─► Máš max. 2 malé tabulky a jde o jednorázovou analýzu?
│   │   ├─► ANO → Použij CHAT
│   │   └─► NE → Pokračuj ↓
│   │
│   ├─► Potřebuješ spojovat více zdrojů nebo čistit data?
│   │   ├─► ANO → Použij SKRIPTY
│   │   └─► NE → Pokračuj ↓
│   │
│   └─► Potřebuješ analýzu opakovat nebo mít live data?
│       ├─► ANO → Použij SKRIPTY + AUTOMATIZACI
│       └─► NE → Použij CHAT
│
└─► Práce s DOKUMENTY (texty, PDF)
    │
    ├─► Máš max. 2 krátké dokumenty?
    │   ├─► ANO → Použij CHAT
    │   └─► NE → Pokračuj ↓
    │
    ├─► Potřebuješ prohledávat desítky/stovky dokumentů?
    │   ├─► ANO → Použij RAG + VEKTOROVOU DB
    │   └─► NE → Pokračuj ↓
    │
    └─► Potřebuješ průběžně aktualizovat znalostní bázi?
        ├─► ANO → Použij SKRIPTY + AUTOMATICKOU INDEXACI
        └─► NE → Použij CHAT
```

---

## 4. Praktické příklady

### Příklad 1: Analýza prodejních dat za měsíc
- **Vstup:** 1 Excel tabulka, 500 řádků
- **Úkol:** Zjistit top produkty a trendy
- **Řešení:** ✅ Chat – stačí nahrát a ptát se

### Příklad 2: Konsolidace dat z 10 poboček
- **Vstup:** 10 Excel souborů, různé formáty sloupců
- **Úkol:** Sjednotit a vytvořit měsíční report
- **Řešení:** ✅ Skripty – nutná normalizace a automatizace

### Příklad 3: Sumarizace smlouvy
- **Vstup:** 1 PDF, 30 stran
- **Úkol:** Vytáhnout klíčové body a rizika
- **Řešení:** ✅ Chat – dokument se vejde do kontextu

### Příklad 4: Firemní znalostní báze
- **Vstup:** 500 interních dokumentů (směrnice, manuály, zápisy)
- **Úkol:** Umožnit zaměstnancům ptát se na cokoliv
- **Řešení:** ✅ RAG + vektorová databáze

### Příklad 5: Porovnání verzí právního dokumentu
- **Vstup:** 3 verze stejné smlouvy
- **Úkol:** Najít všechny změny mezi verzemi
- **Řešení:** ✅ Skripty – automatické diffování

---

## 5. Instrukce pro AI agenty

Při rozhodování, který nástroj doporučit uživateli, postupuj takto:

1. **Zjisti rozsah:**
   - Kolik souborů/dokumentů má uživatel?
   - Jak jsou velké?
   - V jakých formátech?

2. **Zjisti frekvenci:**
   - Jde o jednorázový úkol nebo opakující se proces?
   - Potřebuje uživatel live/aktuální data?

3. **Zjisti komplexitu:**
   - Jsou data čistá nebo vyžadují transformaci?
   - Potřebuje spojovat více zdrojů?

4. **Doporuč řešení:**
   - Pokud rozsah malý + jednorázově → Chat
   - Pokud rozsah velký NEBO opakovaně NEBO komplexní transformace → Skripty

5. **Nabídni konkrétní nástroje:**
   - Pro chat: ChatGPT, Claude, Gemini, Copilot
   - Pro skripty: Claude Code, Cursor, GitHub Copilot, Google Apps Script
   - Pro data: Python/pandas, SQL, dbt
   - Pro dokumenty: RAG, LangChain, vektorová DB

6. **Upozorni na omezení:**
   - Chat má limity na velikost souborů a kontextu
   - Skripty vyžadují technické znalosti nebo pomoc vývojáře

---

## 6. Shrnutí

| Situace | Doporučení |
|---------|------------|
| Malý rozsah, jednorázově, čistá data | **Chat** |
| Velký rozsah, opakovaně, komplexní data | **Skripty** |
| Něco mezi | Začni chatem, při limitech přejdi na skripty |

**Zlaté pravidlo:** Pokud něco děláš víc než 3× ručně, automatizuj to.

---

*Verze dokumentu: 1.0*
