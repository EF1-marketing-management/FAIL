# Jak postavit vlastního AI asistenta s přístupem k vašim dokumentům

**Přehled:** Vytvoříte si specializovaného AI asistenta, který zná vaše dokumenty a odpovídá podle nich – bez programování.

**Proč na tom záleží:** Místo nekonečného vysvětlování kontextu AI při každém dotazu máte asistenta, který už vaše podklady zná. To znamená přesnější odpovědi za zlomek času.

**Základní princip:** Nahrajete dokumenty do AI nástroje, nastavíte instrukce, jak má odpovídat, a máte specialistu na vaše téma.

---

## ⚠️ Realistická očekávání

První asistent **nebude fungovat napoprvé** – bude si vymýšlet, nebo ignorovat vaše dokumenty. To je normální. Musíte iterovat instrukce a možná i upravit dokumenty. Počítejte s 3-5 verzemi, než funguje, jak chcete. Každá iterace vás ale naučí, jak asistenta lépe nastavit.

---

## 🚀 Quick Win

**Cíl:** Vytvořit asistenta, který funguje jako "druhý mozek" s přístupem k vaší znalostní bázi.

1. Vyberte AI nástroj (pro začátek **ChatGPT Custom GPTs** nebo **Claude Projects** — nejjednodušší)
2. **Připravte dokumenty pro nahrání:**
   - Menší soubory (do 50 stran): PDF, Word, markdown fungují dobře
   - **Velké soubory (100+ stran): převeďte PDF do Markdown** 
     - Proč? Velké PDF soubory mohou způsobit, že asistent nedává přesné odpovědi nebo „nevidí" části dokumentu. Markdown je pro AI lépe čitelný a umožňuje efektivnější zpracování informací.
     - Jak? Použijte nástroje jako [OpenL Translate PDF to Markdown](https://openl.io/cs/pdf-to-markdown) nebo podobné online konvertory
3. Nahrajte připravené dokumenty do nástroje
4. **✨ Napište instrukce – tento krok je klíčový:**
   
   ```
   Jsi expert na [téma]. Odpovídej POUZE na základě nahraných dokumentů.
   Pokud informace není v dokumentech, řekni jasně: "Tuto informaci nemám v nahraných dokumentech."
   Vždy uveď, ze které části dokumentu informace čerpáš.
   ```

5. **Jak odkazovat na znalostní bázi v promptu:**
   - **ChatGPT (Custom GPT):** Stačí se zeptat normálně – GPT automaticky prohledá nahrané soubory
   - **Claude (Projects):** V rámci projektu se zeptej přímo – Claude vidí všechny dokumenty v "Project Knowledge"
   - **Gemini (Gems):** Použij: "Podle nahraných dokumentů, [tvůj dotaz]"
   - **Microsoft Copilot (Agent v chatu, ne Studio):** "Na základě firemních dokumentů, [tvůj dotaz]"
   
   **Tip:** Pro jistotu začni otázky slovy: "Podle nahraných dokumentů..." nebo "V naší dokumentaci..."

6. Otestuj 5-10 různých otázek (jednoduché i složité)
7. Upravte instrukce podle toho, jak odpovídá
8. Hotovo – máte základního asistenta!

---

## Nástroje a, jak je použít

### 1. ChatGPT Custom GPTs (nejjednodušší start - doporučeno)

**Co to je:** Vlastní verze ChatGPT natrénovaná na vašich dokumentech.

**Klíčové funkce:**
- Nahrání až 20 souborů (PDF, Word, markdown, text)
- Vlastní instrukce pro chování asistenta
- Sdílení s týmem nebo veřejně
- Integrace s dalšími nástroji přes Actions

**Web:** https://chatgpt.com

**Krok za krokem:**

1. Jdi na chatgpt.com → Explore GPTs → Create
2. Nahrajte dokumenty přes „Configure" záložku
3. Napište instrukce v „Instructions":

```
Jsi expert na [téma]. Odpovídej pouze podle nahraných dokumentů.
Pokud informace není v dokumentech, řekni to jasně.
Používej [formální/neformální] tón.
```

4. Testujte: zkuste různé dotazy a sledujte odpovědi
5. Iterujte: upravte instrukce podle výsledků
6. Sdílejte: nastav „Anyone with a link" nebo „Only me"

**Kdy použít:** Chceš nejrychlejší cestu k funkčnímu asistentovi a máte ChatGPT Plus ($20/měsíc).

---

### 2. Claude Projects (lepší pro dlouhý kontext - doporučeno)

**Co to je:** Specializované workspace v Claude s vlastní knowledge base.

**Klíčové funkce:**
- Obrovské context okno (200K tokenů = ~500 stran)
- Custom instrukce pro každý projekt
- Lepší pro technické dokumenty
- Sdílení s týmem (na Team/Enterprise plánu)

**Web:** https://claude.ai

**Krok za krokem:**

1. Otevřete Claude → Projects → New Project
2. Pojmenuj projekt (např. „Marketing dokumentace")
3. V „Project Knowledge" nahrajte dokumenty
4. Nastavte „Custom Instructions":

```
Účel: Pomáhat marketingovému týmu s kampaněmi
Jak odpovídat: Konkrétně, s příklady z nahraných dokumentů
Tón: Praktický a akční
```

5. Testujte v konverzacích v rámci projektu
6. Přidávejte dokumenty podle potřeby

**Kdy použít:** Máte hodně technických dokumentů nebo potřebujete zpracovat dlouhé texty najednou.

---

### 3. Microsoft Copilot Studio (pro firemní použití - doporučeno)

**Co to je:** Microsoft platforma pro tvorbu vlastních AI asistentů integrovaných do Microsoft 365 ekosystému.

**Klíčové funkce:**
- Propojení s SharePoint, OneDrive
- Enterprise bezpečnost a compliance
- Integrace s Microsoft 365 ekosystémem

**Web:** https://www.microsoft.com/en-us/microsoft-copilot/microsoft-copilot-studio

**Základní postup:**
1. Přístup přes Microsoft 365 admin
2. Vytvořte nového copilota v Copilot Studio
3. Propoj s SharePoint knihovnami nebo OneDrive
4. Nastavte odpovědi a chování

**Kdy použít:** Jste ve větší firmě s Microsoft 365 a potřebujete enterprise-grade řešení.

---

### 4. Notion AI (nad Notion workspace - doporučeno)

**Co to je:** AI přímo integrované do Notion, zná vše z vašeho workspace.

**Klíčové funkce:**
- Automaticky vidí celý Notion workspace
- Žádné manuální nahrávání dokumentů
- AI příkazy přímo v poznámkách

**Web:** https://www.notion.com

**Jak použít:**
1. Aktivuj Notion AI v nastavení
2. Používej `/ai` příkazy kdekoliv v Notion
3. AI automaticky čerpá z celého workspace

**Kdy použít:** Už máte vše v Notion a nechcete to exportovat jinam.

---

## 💡 Příklad z praxe

**Onboarding manager** vytvořil Custom GPT s 15 firemními dokumenty (handbook, IT setup, benefits, procesy). Nový zaměstnanec se ptá GPT místo HR. GPT odpovídá přesně podle dokumentů, s odkazy na konkrétní sekce. Šetří HR týmu 5+ hodin týdně na opakující se otázky.

**Další příklady použití:**
- Firemní dokumentace → asistent pro onboarding
- Knihy a články → personal knowledge assistant  
- Projektové poznámky → project-specific helper
- FAQ a procesy → self-service support

---

## Quick Action Guide

### Klíčové závěry
- Kvalita asistenta = kvalita dokumentů a instrukcí
- Testujte s edge cases, ne jen očekávanými dotazy
- Iterujte dokud nefunguje spolehlivě (3-5 verzí je normální)

### Co se vyhnout (a, co dělat místo toho)
- ❌ Nenahrávat chaotické, nestrukturované dokumenty. ✅ Nejdřív dokumenty vyčisti a strukturuj.
- ❌ Vágní instrukce typu „buď užitečný". ✅ Konkrétní: „Odpovídej v bodech, s citacemi ze sekcí."
- ❌ Testovat jen jedním typem otázky. ✅ Zkuste edge cases: nejasné dotazy, mimo téma, složité dotazy.
- ❌ Použít skenované PDF bez OCR. ✅ Použijte čisté textové soubory nebo PDF s textem.

### Začněte tady
1. Vyberte 2-3 nejdůležitější dokumenty pro jeden konkrétní účel
2. **Zvolte nástroj podle potřeb:**
   - **ChatGPT** — pro začátek, jednoduché nastavení
   - **Claude Projects** — pro velké technické dokumenty
   - **Notion AI** — pokud máte už vše v Notion
   - **Microsoft Copilot** — pokud pracujete s Microsoft 365
3. Nahrajte dokumenty a napiš jasné instrukce
4. Testujte 10 různých otázek a sleduj odpovědi
5. Upravte instrukce nebo dokumenty podle výsledků
6. Opakuj kroky 4-5 dokud nejsi spokojený (3-5 iterací je normální)
7. Teprve pak sdílej s ostatními

---

## Zdroje

**Tip:** Kompletní přehled nástrojů najdete na https://drimalka.com/aplikace-ne-druhy-mozek-nejen-s-ai/

---

**Důležité:** Asistent je jen tak dobrý jako dokumenty a instrukce, které mu dáte. Věnujte čas přípravě.