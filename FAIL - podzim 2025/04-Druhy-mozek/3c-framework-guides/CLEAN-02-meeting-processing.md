# Transformovat informace z konverzací (schůzky, porady) do znalostí

## Obecné informace

Zpracování záznamů konverzací do použitelné podoby — klíčem je dobrý prompt, který definuje strukturu výstupu. Automatický přepis + AI strukturování = 30 minut práce hotové za 2 minuty.

**Proč na tom záleží:** Nejde jen o meetingy — může jít například o cílené schůzky, na kterých probíráme nějaký projekt (abychom měli vytvořený základ pro znalostní bázi) nebo proces (abychom ho pak jednoduše popsali a udělali základ automatizace). Manuální zápisy jsou nekonzistentní a časově náročné. Automatizované zpracování dává stejnou strukturu pokaždé a zachytí vše, co bylo řečeno.

**Základní princip:** Prompt je klíčový — musíš definovat přesnou strukturu výstupu. Stejný prompt použij pro všechny schůzky stejného typu.

## ⚠️ Realistická očekávání

Některé automatické přepisy budou dělat chyby (jména, termíny). AI strukturování bude muset být upraveno, než najdete prompt, který vám vyhovuje. To je normální — každý tým má jiný styl dokumentace. 

**Důležité:** Musíš vyladit prompt, například, aby si AI nevymýšlel informace, nebo, aby upozornil na nejasnosti, u kterých si není jistý. Iterativní vylepšování promptu je klíčové pro spolehlivé výsledky.

## 🚀 Quick Win

1. Nahrajte si poslední meeting nahrávku do TurboScribe (nebo jiný nástroj)
2. Vezmi přepis a vlož do ChatGPT s promptem: „Udělejte z toho zápis: Rozhodnutí / Akce / Otázky"
3. Zkontrolujte výstup
4. Hotovo — máte strukturovaný zápis!

## Konkrétní nástroje

### Automatické přepisy meetingů

**TLDV** (doporučeno)
- Specializovaný nástroj pro nahrávání a přepisování schůzek na Google Meet a Zoom
- Automaticky nahrává a přepisuje s časovými značkami
- 30+ jazyků, AI souhrny
- Free plán: neomezené nahrávání
- **Web:** https://tldv.io

**Fireflies.ai** (doporučeno)
- AI asistent pro automatické přepisování a analýzu schůzek
- Podporuje Zoom, Google Meet, Microsoft Teams a další
- Automatický přepis v 70+ jazycích, identifikace mluvčích
- Integrace do CRM a project management nástrojů
- Free plán: 3 kredity měsíčně
- **Web:** https://fireflies.ai

**Microsoft Teams Copilot** (doporučeno pro Microsoft 365)
- Integrovaný AI asistent v Teams
- Vestavěný přepis a poznámky
- Přepisuje, sumarizuje a vytváří akční body ze schůzek
- Funguje automaticky pokud máte Copilot licenci
- **Web:** https://www.microsoft.com/microsoft-teams/

### AI zpracování přepisů

**ChatGPT / Claude / Gemini:**
Po získání přepisu ho zpracuj s dobrým promptem.

## Důležité: Dobrý prompt je základ

**Příklad promptu pro meeting zápis:**

```
Z tohoto přepisu vytvoř strukturovaný zápis s těmito sekcemi:

## Klíčová rozhodnutí
[Co jsme se rozhodli — konkrétní rozhodnutí]

## Akční body
[Kdo | Co přesně udělá | Do kdy]

## Důležité insights
[Co jsme se naučili nebo zjistili]

## Otevřené otázky
[Co zbývá vyřešit příště]

Formát: Bullet points, stručně, bez zbytečných slov.
```

**Uložte prompt jako šablonu:**
Když najdete prompt, co funguje, ulož si ho a použij pro všechny podobné schůzky.

## Proces krok za krokem

1. **Automatický přepis:** TLDV, Fireflies, nebo Teams Copilot
2. **AI zpracování s promptem:**
   - Zkopírujte přepis do ChatGPT/Claude
   - Vložte svůj ulož promt pro strukturování
   - Získej strukturovaný zápis
3. **Uložte a sdílej:**
   - Propoj s projektovou dokumentací
   - Sdílejte s týmem
   - Archivuj pro budoucí referenci

## 💡 Příklady z praxe

**Product owner:** Nahrává každou sprint planning schůzku přes Teams (automatický přepis). Po schůzce zkopíruje přepis do Claude s uloženým promptem, který extrahuje: User Stories + Akceptační kritéria + Blockers + Action Items s assignees. Výstup rovnou vloží do Jira. Ušetří 30 minut týdně.

**Popis procesu:** Vedoucí oddělení nahrává rozhovor s týmem o procesu schvalování faktur. AI vytvoří strukturovaný popis procesu včetně kroků, odpovědností a časových limitů. Základ pro automatizaci nebo onboarding.

**Onboarding školení:** HR nahrává onboarding školení nových zaměstnanců. AI z toho vytvoří znalostní bázi s FAQ, klíčovými procedurami a kontakty. Nový zaměstnanec má vše na jednom místě.

**Analýza porad:** Manažer nechá AI zpětně analyzovat přepisy posledních 10 porad. AI identifikuje opakující se témata, efektivitu diskuzí a navrhne, jak porady zlepšit (kratší, strukturovanější, méně opakování).

## Konkrétní příklad promptu pro různé typy schůzek

**Sprint Planning:**
```
Vytvořte z přepisu strukturovaný zápis:

## User Stories diskutované
[Story | Priority | Story Points]

## Akceptační kritéria
[Pro každou story - co musí být splněno]

## Blockers identifikované
[Co brání pokroku]

## Action Items
[Kdo | Co | Do kdy]
```

**Client Call:**
```
Strukturuj tento client call:

## Klíčové požadavky klienta
[Co klient chce — specificky]

## Naše závazky
[Co jsme slíbili dodat]

## Next Steps
[Kdo | Co | Termín]

## Otevřené otázky pro příště
```

**1-on-1 Meeting:**
```
Udělejte zápis z 1-on-1:

## Diskutovaná témata
[Hlavní body, co jsme probírali]

## Action Items
[Kdo | Co | Do kdy]

## Follow-up potřebný
[Co vyřešit příště]
```

## Quick Action Guide

### Klíčové závěry
- **Prompt je základ** — definuj přesnou strukturu výstupu
- Automatický přepis ušetří čas
- Používej konzistentní prompt/šablonu pro všechny schůzky stejného typu
- Propoj s existující dokumentací

### Co se vyhnout (a udělat místo toho)
- ❌ Nemanuálně přepisuj. ✅ Použijte automatické nástroje (TLDV, Fireflies).
- ❌ Nežádej AI „udělej poznámky". ✅ Definujte přesnou strukturu v promptu.
- ❌ Nepiš prompt každou schůzku. ✅ Uložte prompt a používej konzistentně.

### Start zde
1. Nastavte si automatický přepis (TLDV nebo Fireflies)
2. Po první schůzce zkopíruj přepis do AI s promptem
3. Vylaďte prompt dokud neodpovídá vaše potřebě
4. Uložte prompt a používej pro všechny podobné schůzky
