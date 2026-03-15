# Vytvářet univerzální šablony ze vzorového obsahu (konkrétních příkladů)

## Obecné informace

Z již vytvořených materiálů udělat obecné zadání/šablonu pro AI — použitelné opakovaně. Vezmi 1-x konkrétních příkladů, AI z nich vytvoří univerzální šablonu.

**Proč na tom záleží:** Cokoliv děláte opakovaně můžete šablonovat. Místo psát stejný typ emailu/dokumentu/postu znovu, vytvořte šablonu jednou a AI vám vygeneruje varianty.

**Základní princip:** Vzorový materiál → AI identifikuje strukturu → Nahradí specifika placeholdery → Univerzální šablona.

**Co je placeholder?** Placeholder je zástupný symbol (např. [JMÉNO], [DATUM], [PROJEKT]), který označuje místo v šabloně, kde se bude měnit konkrétní informace. Místo opakování celého textu jen vyměníš hodnoty v placeholderech.

## ⚠️ Realistická očekávání

První šablona nebude univerzální — bude moc specifická nebo moc obecná. Potřebuješ ji otestovat na 3-5 různých případech a postupně vyladit, než bude fungovat dobře.

**Bonus:** Toto je super příležitost ty příklady vyladit a vylepšit. Když vytvoříš ideální příklad (nebo necháš AI ho vytvořit), AI pak bude pracovat přesně podle tohoto vzoru. Kvalita tvých příkladů = kvalita budoucích výstupů.

## 🚀 Quick Win

1. Vyberte 2-3 emaily stejného typu (třeba odpovědi zákazníkům)
2. Vložte je do AI: „Vytvořte z těchto příkladů univerzální šablonu"
3. AI vám dá šablonu s [PLACEHOLDERY]
4. Vyzkoušejte ji na novém případu
5. Hotovo — máte svou první šablonu!

## Konkrétní nástroje

**AI pro vytvoření šablon:**
- ChatGPT, Claude, Gemini, Microsoft Copilot
- Všechny umí identifikovat vzory a vytvořit šablony

**Uložení šablon:**
- **OneNote / Notion** — pro manuální použití
- **Custom GPT / Claude Projects** — ideální, šablona přímo v AI asistentu
- **Snipety v emailu** — pro email šablony

## Proces krok za krokem

### 1. Vyberte vzorový materiál

Něco, co děláte pravidelně:
- Emaily podobného typu
- LinkedIn posty
- Meeting zápisy
- Nabídky pro klienty
- YouTube popisy

### 2. Nechej AI vytvořit šablonu

**Příklad promptu:**
```
Z těchto 3 příkladů vytvoř obecnou šablonu, kterou můžu použít opakovaně.

Identifikujte:
1. Strukturu (jak je obsah uspořádaný)
2. Opakující se vzory
3. Co se mění mezi příklady

Vytvořte šablonu s [PLACEHOLDERY] pro části, co se mění.

[Vložte své 3 příklady]
```

### 3. AI vytvoří šablonu

AI vám vrátí šablonu s placeholdery:

**Příklad výstupu — Email šablona:**
```
Předmět: [TÉMA] — Další kroky

Ahoj [JMÉNO],

Děkuji za schůzku ohledně [PROJEKT]. 

Jak jsme se dohodli, hlavní next steps jsou:
- [ACTION_1] — do [DATUM_1]
- [ACTION_2] — do [DATUM_2]
- [ACTION_3] — do [DATUM_3]

V případě otázek mi napiš.
Příští call máme [DATUM_CALL].

[TVOJE_JMÉNO]
```

### 4. Otestuj na nových případech

Vyzkoušejte šablonu na 2-3 reálných situacích:
- Funguje?
- Chybí něco?
- Je dost flexibilní?

### 5. Uložte pro opakované použití

**Nejlepší způsob:** Vytvořte Custom GPT nebo Claude Project
- Nahrajte šablonu do AI asistenta
- Když potřebujete nový obsah: „Vygeneruj email podle šablony pro klienta [jméno], projekt [X], deadline [datum]"
- AI vyplní placeholdery

## 💡 Příklad z praxe

HR specialista měl 15 různých nabídkových emailů pro kandidáty. Nahrál je do Custom GPT a požádal o vytvoření univerzální šablony. GPT vytvořil šablonu s placeholdery [POZICE], [PLAT], [BENEFITS], [START_DATE]. Teď při každé nové nabídce jen vyplní hodnoty a GPT vygeneruje profesionální email. Ušetří 20 minut na každé nabídce.

## Praktické příklady šablon

### YouTube Video popis

**Vzorový prompt pro vytvoření šablony:**
```
Vytvořte šablonu pro YouTube popisy na základě těchto 3-5 příkladů.
Struktura: Hook / Hlavní obsah / Odkazy / CTA

[Vložte 3-5 svých existujících popisů]
```

**Výsledná šablona:**
```
[HOOK — 1-2 věty, co video nabízí]

V tomto videu se dozvíte:
- [BOD_1]
- [BOD_2]
- [BOD_3]

Časové značky:
00:00 — [SEKCE_1]
[ČAS] — [SEKCE_2]
[ČAS] — [SEKCE_3]

📚 Zdroje zmíněné ve videu:
- [ODKAZ_1]
- [ODKAZ_2]

🔔 Nezapomeňte se přihlásit k odběru!

#[HASHTAG_1] #[HASHTAG_2] #[HASHTAG_3]
```

### Meeting zápis šablona

**Po vytvoření šablony z vzorů:**
```
# Meeting: [NÁZEV]
Datum: [DATUM]
Účastníci: [JMÉNA]

## Rozhodnutí
- [ROZHODNUTÍ_1]
- [ROZHODNUTÍ_2]

## Akční body
| Kdo | Co | Do kdy |
|-----|-----|--------|
| [OSOBA_1] | [ÚKOL_1] | [DATUM_1] |
| [OSOBA_2] | [ÚKOL_2] | [DATUM_2] |

## Důležité insights
- [INSIGHT_1]
- [INSIGHT_2]

## Next meeting
[DATUM] — [AGENDA]
```

### Email po akci

```
Předmět: Díky za účast na [NÁZEV_AKCE]

Ahoj [JMÉNO],

děkuji za účast na [NÁZEV_AKCE], které se konalo [DATUM].

Jak jsme slíbili, posílám:
- [MATERIÁL_1]
- [MATERIÁL_2]
- [MATERIÁL_3]

Pokud máte dotazy k [TÉMA], neváhej napsat.

Další akce: [DATUM_DALŠÍ_AKCE]

Těším se na viděnou,
[TVOJE_JMÉNO]
```

## Quick Action Guide

### Klíčové závěry
- Z konkrétních příkladů → univerzální zadání
- Testujte šablonu na více případech, než finalizuješ
- Ideálně používej v AI asistentech (Custom GPT, Claude Projects)
- Jakýkoliv opakující se obsah může být šablonován

### Co se vyhnout (a udělat místo toho)
- ❌ Nevytvářejte šablonu z 1 příkladu. ✅ Potřebuješ 2-3 příklady minimum.
- ❌ Neulož šablonu a zapomeň. ✅ Otestuj na reálných případech.
- ❌ Nepiš šablonu ručně. ✅ Nechej AI identifikovat strukturu z příkladů.

### Start zde
1. Identifikujte opakující se typ obsahu (emaily, posty, dokumenty)
2. Vyberte 2-3 dobré příklady
3. Nechej AI vytvořit šablonu s placeholdery
4. Otestuj na 2-3 nových případech
5. Uložte do AI asistentů nebo automatizací pro snadné použití
