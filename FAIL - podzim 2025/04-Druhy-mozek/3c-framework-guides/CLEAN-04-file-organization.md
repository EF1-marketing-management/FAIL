# Analyzovat vaše úložiště (soubory, poznámky, data) a navrhnout logičtější organizaci

## Obecné informace

AI analyzuje cokoliv, navrhne přehlednou strukturu a, co je **kritické** — vytvoří popis/dokumentaci pro každou složku - pro lidi i pro AI agenty.

**Proč na tom záleží:** Špatně organizované soubory = ztracený čas hledáním. Dobrá struktura + README v každé složce = kdokoliv (člověk i AI) najde všechno velmi rychle.

**Základní princip:** Export struktury nebo napojení AI nástroje na váš zdroj informací → AI analyzuje → Navrhne logiku → Vytvoří README pro každou složku → Implementujte.

## ⚠️ Realistická očekávání

První návrh organizace bude vypadat úžasně, ale když začnete přesouvat soubory, zjistíte že to není ideální. Budete muset párkrát upravit strukturu, než vám bude vyhovovat. **DŮLEŽITÉ: Vždy si udělejte zálohu před reorganizací!**

## 🚀 Quick Win

1. Export strukturu jedné složky
2. Vložte do ChatGPT: „Navrhni lepší organizaci této složky"
3. Prohlédni si návrh
4. Implementujte na malé testovací složce
5. Hotovo — vidíte jestli to funguje!

## Jak exportovat strukturu

**Nejjednodušší způsob:**
- Udělejte **screenshot** souborů a složek
- Nahrajte screenshot do AI
- Požádej AI: „Popiš tuto strukturu a navrhni lepší organizaci"

**Pokud chcete textový export:**

**macOS/Linux:**
```bash
# Nainstalujte tree pokud nemáš
brew install tree

# Export struktury
tree -L 3 > struktura.txt
```

**Windows PowerShell:**
```powershell
# Export struktury
Get-ChildItem -Recurse -Depth 3 | Out-File struktura.txt
```

**Notion:**
- Export workspace do markdown
- Automaticky dostanete strukturu

**Nebo přímo:**
- **Claude Desktop** — může se připojit k lokální složce
- **Cursor** — pracuje přímo se soubory

## Proces krok za krokem

### 1. Export nebo připoj strukturu do AI

**Příklad promptu:**
```
Analyzuj tuto strukturu souborů a navrhni lepší organizaci.

Identifikujte:
1. Co je chaotické
2. Jaké jsou duplicity
3. Špatné názvy
4. Logické kategorie

Navrhni:
- Novou strukturu složek
- Systém pojmenovávání
- README/popis pro každou hlavní složku

[Vložte strukturu]
```

### 2. AI analyzuje a navrhne

AI identifikuje problémy:
- Chaos v pojmenovávání
- Duplicitní soubory
- Špatné kategorizace
- Chybějící logika

### 3. AI vytvoří návrh s README

**Příklad návrhu:**

```
📁 Clients
  📄 README.md — „Klientské projekty. Struktura: [client-name]-[year]"
  📁 acme-2025
  📁 techcorp-2024

📁 Projects
  📄 README.md — „Interní projekty. Aktivní projekty zde, archivované v /Archive"
  📁 website-redesign
  📁 crm-migration

📁 Templates
  📄 README.md — „Šablony pro opakované použití. Copyovat, ne editovat originál"
  📁 emails
  📁 presentations
  📁 contracts

📁 Resources
  📄 README.md — „Reference materiály, brand assets, guidelines"
  📁 brand-assets
  📁 guidelines

📁 Archive
  📄 README.md — „Dokončené/neaktivní projekty. Naming: [name]-ARCHIVED-[year]"
```

### 4. DŮLEŽITÉ: Vytvořte README pro každou složku

**Příklad README.md:**

```markdown
# Clients

Tato složka obsahuje všechny klientské projekty.

## Struktura
- Každý klient má vlastní složku
- Naming: `[client-name]-[year]`
- Příklad: `acme-2025`

## Co patří sem
- Klientské dokumenty
- Smlouvy
- Deliverables
- Komunikace

## Co sem NEPATŘÍ
- Interní diskuze → /Internal
- Šablony → /Templates
- Dokončené projekty starší 2 roky → /Archive

## Proces
1. Nový klient → Vytvořte složku podle naming convention
2. Během projektu → Všechno do klientské složky
3. Po dokončení (2+ roky) → Přesuň do /Archive
```

**Proč README?**
- Pro lidi: Orientace kam, co patří
- Pro AI agenty: Kontext pro zpracování
- Pro tým: Konzistence

### 5. Implementujte postupně

**⚠️ KRITICKÉ: UDĚLEJ ZÁLOHU!**

```bash
# Duplikuj celou strukturu před změnami
cp -r original backup-2025-01-15
```

Pak postupně:
1. Vytvořte novou strukturu složek
2. Přidejte README do každé složky
3. Postupně přesouvej soubory
4. Testujte — všichni najdou, co potřebují?

## Dokumentace — Matt Palmer's 8 pravidel

Použijte pro psaní README souborů:
https://mattpalmer.io/posts/8-rules-for-better-docs/

Klíčové principy:
- Začněte s „proč" ne s „jak"
- Krátké odstavce
- Příklady > teorie
- Konzistentní struktura

## 💡 Příklad z praxe

Consultant měl na Google Drive 1200 souborů v 50 složkách bez logiky. Exportoval strukturu, Claude navrhl reorganizaci do 5 hlavních kategorií: Clients / Projects / Templates / Resources / Archive. 

**Důležitější:** Claude vytvořil README.md pro každou složku s popisem:
- „Co patří sem"
- „Naming convention" 
- „Co dělat když..."

Po měsíci používání tým oceňuje že najdou cokoliv za 10 sekund. Nový člověk se zorientuje za 5 minut.

## Quick Action Guide

### Klíčové závěry
- **KRITICKÉ: Popis struktury** (README) pro lidi i AI
- **ZÁLOHA** před reorganizací!
- Implementujte postupně
- README jsou investice do budoucna

### Co se vyhnout (a udělat místo toho)
- ❌ Nepřeskakuj README. ✅ Každá hlavní složka musí mít popis.
- ❌ Nereorganizuj bez zálohy. ✅ Vždy duplikuj před změnami.
- ❌ Nevytvářejte strukturu bez testování. ✅ Testujte na malé složce první.

### Start zde
1. Export strukturu jedné chaotické složky
2. Nechej AI navrhnout lepší organizaci + README
3. **Udělaj zálohu!**
4. Implementujte na testovací složce
5. Pokud funguje → rozšiř na zbytek
