# Jak vytvořit chatbota, který odpovídá na opakující se otázky

**Přehled:** Tento návod je pro scénáře, kdy nemáte k dispozici korporátní nástroje, nebo se chcete naučit, jak chatbot funguje a jak připravit data. Používáme uživatelsky jednoduché aplikace, které zvládne každý.

**Proč na tom záleží:** Ušetříte desítky hodin týdně tím, že opakující se otázky zodpoví chatbot místo vás. 24/7 dostupnost pro zákazníky i interní týmy.

**Základní princip:** Připravíte znalostní bázi, nahrajete do nástroje, nastavíte instrukce a chování, otestujete a embedujete na web, do Slacku nebo jako hlasového asistenta.

---

## ⚠️ Realistická očekávání

První verze chatbota nebude na všechno odpovídat 100% správně. **To je normální a očekávané.** Musíte průběžně přidávat znalosti podle toho, na, co se lidi ptají. Prvních pár týdnů aktivní údržba (učíte chatbota), pak stabilizace. Každá iterace (promptu i znalostní báze) zlepší výsledky.

---

## 🚀 Quick Win

1. Vyberte nástroj (pro začátek **Chatbase** — nejjednodušší)
2. Připrav 3-5 dokumentů s nejčastějšími FAQ (vyčištěné a strukturované!)
3. Vytvořte chatbota a nahraj dokumenty
4. Otestuj 10-20 různých otázek (včetně těch složitých)
5. Oprav odpovědi kde bot selhává
6. Funguje dobře? Můžeš embedovat na web!
7. Hotovo – máte první chatbota!

---

## DŮLEŽITÉ: Dobrě zpracovaná znalost

**Kvalita chatbota = kvalita dat.**

### Příprava znalostí

**1. Shromáždi FAQ:**
- Nejčastější otázky z podpory/HR/IT
- Historické odpovědi z emailů/Slacku
- Dokumentace, návody, procesy

**2. Vyčisti a strukturuj:**
- Ne chaotické poznámky → jasné Q&A páry
- Jednotný formát
- Přehledné sekce s nadpisy

**Příklad špatné znalosti:**
```
neco o dovolené
lidi se ptaji, jak si brat dovolene
myslim ze to je v tom pdf někde
```

**Příklad dobré znalosti:**
```
# Dovolená

## Jak si vzít dovolenou?
1. Otevřete HR systém na [odkaz]
2. Vyplň formulář s daty
3. Odešli ke schválení manažerovi
4. Dostaneš potvrzení do 48h

## Kolik mám nárok?
- 20 dnů základní nárok
- +5 dnů po 5 letech ve firmě
- Viz kompletní politika: [odkaz]
```

**3. Otestuj kompletnost:**
- Máš odpovědi na 80% dotazů?
- Chybí něco důležitého?

---

## 🎯 Základní principy tvorby chatbota

**Každý chatbot má 4 klíčové komponenty:**

### 1. Znalostní báze (Knowledge Base)
- **Co to je:** Dokumenty, FAQ, návody, ze kterých chatbot čerpá odpovědi
- **Jak na to:** Nahrajete PDF, Word, text, URL webu nebo propojíte Notion/Google Docs
- **Klíč:** Čím kvalitnější a strukturovanější data, tím lepší odpovědi

### 2. Instrukce (System Prompt)
- **Co to je:** Pravidla, jak se má chatbot chovat
- **Jak nastavit:**
  - Tón hlasu: „Buď profesionální a přátelský"
  - Jazyk: „Odpovídej vždy česky"
  - Omezení: „Odpovídej pouze na základě znalostní báze, pokud nevíš, řekni to"
  - Role: „Jsi zákaznický asistent e-shopu"
- **Příklad instrukcí:**
  ```
  Jsi AI asistent pro zákaznickou podporu e-shopu s elektronikou.
  Odpovídej přátelsky, stručně a vždy v češtině.
  Používej pouze informace ze znalostní báze.
  Pokud nevíš odpověď, řekni: "Na tuto otázku nemám informace, kontaktujte prosím podporu na podpora@eshop.cz"
  Vždy uveď zdroj informace nebo odkaz, pokud je k dispozici.
  ```

### 3. AI Model
- **Výběr modelu:** GPT-4, Claude 3.5, Gemini 2.0
- **Kdy jaký:**
  - GPT-4: Nejlepší kvalita, nejdražší
  - Claude 3.5: Dlouhé kontexty, bezpečný
  - Gemini 2.0: Rychlý a levný
- **Tip:** Pro začátek GPT-4 nebo Claude 3.5

### 4. Integrace a kanály
- **Web embed:** Chat widget na stránkách
- **Messaging:** WhatsApp, Messenger, Instagram
- **Workplace:** Slack, Microsoft Teams
- **Hlas:** Voiceflow + Elevenlabs pro hlasové rozhraní

### 5. Monitoring a zlepšování
- **Sleduj konverzace:** Co lidé skutečně chtějí?
- **Identifikuj mezery:** Na co bot neumí odpovědět?
- **Iteruj:** Doplňuj znalosti, upravuj instrukce
- **Měř úspěšnost:** % vyřešených dotazů bez eskalace

---

## Nástroje – no-code chatbot buildery

**Přehled podle použití:**
- **Pro rychlý start:** Chatbase (nejjednodušší)
- **Pro pokročilé flow:** Botpress
- **Pro Microsoft prostředí:** Copilot Studio
- **Pro hlasové rozhraní:** Voiceflow + Elevenlabs
- **Pro automatizaci a integraci:** N8N

### 1. Chatbase (nejjednodušší - doporučeno)

**Co to je:** Jednoduchý nástroj pro vytvoření chatbota z vašich dokumentů a webových stránek během několika minut.

**Klíčové funkce:**
- Upload PDF, Word, web stránek, Notion
- Výběr AI modelu (GPT-4, Claude, Gemini)
- Embed na web, WhatsApp, Messenger, Instagram, Slack
- „Revise answer" – opravíš konkrétní odpověď snadno
- Sbírání leadů (email, telefon)

**Web:** https://www.chatbase.co

**Krok za krokem:**

1. **Registrace:** chatbase.co → Try for Free
2. **Vytvořte chatbota:** New Chatbot → pojmenuj
3. **Nahrajte data:**
   - Upload souborů (PDF, Doc, TXT)
   - Nebo zadej URL webu (Chatbase to načte)
   - Nebo propoj Notion
4. **Nastavte chování:**
   - Model: GPT-4, Claude 3.5, Gemini 2.0
   - Tón: profesionální / přátelský
   - Jazyk: čeština
   - Custom instructions: „Odpovídej stručně s odkazy na zdroj"
5. **Testujte v Playground:**
   - Zkuste 10 různých otázek
   - Sledujte odpovědi
6. **Oprav odpovědi:**
   - V Chat Logs klikni „Revise answer"
   - Dejte správnou odpověď
   - Chatbase si to zapamatuje
7. **Embed:**
   - Connect → Website → Copy code
   - Vložte na web

**Cena:** Free plan (omezené), od $40/měsíc

**Kdy použít:** Chceš nejrychlejší cestu k funkčnímu chatbotovi.

---

### 2. Botpress (pokročilé workflow)

**Co to je:** Open-source platforma pro tvorbu pokročilých AI chatbotů s vizuálním workflow builderem.

**Principy práce:**
- **Knowledge base:** Nahrajete dokumenty stejně jako v Chatbase
- **Instrukce:** Nastavíte v „AI Task" – tón, jazyk, pravidla
- **Flow builder:** Vytvoříte vlastní konverzační flow s podmínkami
- **Integrace:** WhatsApp, Messenger, Telegram, web, Slack

**Jak na to:**
1. Botpress.com → Sign up → Create Bot
2. Nahrajte knowledge base (PDF, text, URL)
3. Nastavte AI Task (instrukce, model)
4. Vytvořte flow (pokud potřebujete víc než jen Q&A)
5. Testujte v Emulator
6. Publikujte na kanály

**Web:** https://botpress.com

**Kdy použít:** Potřebujete složitější konverzační flow s podmínkami a vlastní logikou.

---

### 3. Voiceflow + Elevenlabs (hlasové rozhraní)

**Co to je:** Kombinace Voiceflow (konverzační design) + Elevenlabs (realistický hlas AI)

**Principy práce:**
- **Voiceflow:** Vytvoříte chatbot s textem i hlasem
- **Elevenlabs:** Vygenerujete vlastní AI hlas (můžete nahrát svůj vlastní)
- **Integrace:** Telefonní linka, web, aplikace

**Jak nastavit:**
1. **Elevenlabs (hlas):**
   - Elevenlabs.io → vyber hlas nebo nahraj vlastní
   - Vygeneruj API klíč
2. **Voiceflow (chatbot):**
   - Voiceflow.com → Create Assistant
   - Nahraj knowledge base
   - Nastav instrukce (jak v Chatbase)
   - Integrace → Elevenlabs → API klíč
3. Testuj hlasové konverzace
4. Publikuj (telefonní číslo, web embed)

**Web:** https://voiceflow.com + https://elevenlabs.io

**Kdy použít:** Chcete hlasového asistenta (telefonní linka, audio na webu).

---

### 4. Microsoft Copilot Studio (enterprise)

**Co to je:** Microsoft platforma pro tvorbu vlastních AI asistentů integrovaných do Microsoft 365.

**Principy práce:**
- **Knowledge:** Propojení se SharePoint, OneDrive, Microsoft Graph
- **Instrukce:** Nastavení v „Topics" – jak má bot reagovat
- **Integrace:** Teams, Power Platform, Dynamics 365
- **Bezpečnost:** Enterprise-grade bezpečnost a compliance

**Jak na to:**
1. Copilot Studio → Create → AI Assistant
2. Připoj znalostní zdroje (SharePoint, dokumenty)
3. Nastav Topics a instrukce
4. Testuj v Teams
5. Publikuj pro organizaci

**Web:** https://www.microsoft.com/en-us/microsoft-copilot/microsoft-copilot-studio

**Kdy použít:** Pracujete v Microsoft 365 prostředí a potřebujete enterprise řešení.

---

### 5. N8N (automatizace a pokročilá integrace)

**Co to je:** Open-source automatizační platforma pro propojení chatbota s vašimi systémy.

**Principy práce:**
- **Workflow automatizace:** Chatbot → N8N → CRM/Database/Email/API
- **Integrace:** Propojení s 400+ aplikacemi
- **Vlastní logika:** Podmínky, transformace dat, pokročilé zpracování

**Jak použít s chatbotem:**
1. Vytvoř chatbot v Chatbase/Botpress
2. V N8N vytvoř workflow: Webhook → zpracování → akce
3. Propoj chatbot s N8N webhook
4. Příklad: Dotaz zákazníka → N8N → kontrola v CRM → odpověď s daty

**Web:** https://n8n.io

**Kdy použít:** Potřebujete propojit chatbot s interními systémy (CRM, databáze, API).

---

### 6. Další nástroje (stručně)

**Delphi** (doporučeno)
- Digitální dvojník založený na vašich znalostech
- **Principy:** Nahrajete data, nastavíte personalitu, embedujete
- **Web:** https://www.delphi.ai

**RunBear** (doporučeno)
- Jednoduchý no-code AI assistant builder
- **Principy:** Upload dat, nastavení instrukcí, integrace s nástroji
- **Web:** https://runbear.io

**Tip:** Kompletní přehled nástrojů najdete na https://drimalka.com/aplikace-ne-druhy-mozek-nejen-s-ai/

---

## Proces vytvoření chatbota

### 1. Připrav znalosti (nejdůležitější!)

- Sesbírej FAQ a dokumentaci
- Vyčisti: strukturuj do sekcí
- Formát: Q&A páry s jasným kontextem

### 2. Vyberte nástroj

- **Pro start:** Chatbase
- **Pro pokročilé:** Botpress
- **Pro Microsoft stack:** Copilot Studio

### 3. Upload a nastavení

- Nahrajte dokumenty nebo URL
- Nastavte jazyk, tón, jméno bota
- Custom instructions: „Odpovídej podle dokumentů, pokud nevíš řekni to"

### 4. Testování (kritické!)

- Zkuste 20-30 různých otázek:
  - Běžné otázky
  - Edge cases (nejasné, mimo téma)
  - Kombinace dotazů
- Sledujte, co bot neví

### 5. Doplň chybějící info

- Najděte mezery v odpovědích
- Doplň dokumentaci
- Znovu testuj

### 6. Nasazení

- Embed na web (snippet kódu)
- Nebo do Slack/Teams
- Nebo jako WhatsApp bot

### 7. Průběžné zlepšování

- **Monitoruj konverzace:** Co lidi reálně chtějí?
- **Identifikujte, co bot neví:** Které otázky nezodpoví?
- **Doplňuj znalosti:** Přidejte chybějící info
- **Měsíčně:** Review top dotazů a upravuj

---

## 💡 Příklady z praxe

### Příklad 1: Chatbot pro e-shop s elektronikou

**Situace:** E-shop s 500+ produkty měl 150+ zákaznických dotazů týdně (dostupnost, doprava, parametry produktů, reklamace).

**Řešení: Zákaznický chatbot v Chatbase**

**Příprava znalostní báze:**
1. **Produktová dokumentace:**
   - Export katalogu produktů (názvy, parametry, ceny, dostupnost)
   - Nejčastější otázky k produktům (kompatibilita, technické detaily)
2. **Obchodní podmínky:**
   - Dodací lhůty a možnosti dopravy
   - Platební metody
   - Reklamační proces a vrácení zboží
3. **FAQ:**
   - 30 nejčastějších dotazů ze zákaznické podpory
   - Průvodce výběrem produktů

**Nastavení v Chatbase:**
```
Instrukce:
"Jsi AI asistent pro zákaznickou podporu e-shopu TechShop.cz s elektronikou.

ROLE: Pomáháš zákazníkům s dotazy k produktům, objednávkám a reklamacím.

TÓN: Přátelský, profesionální, trpělivý.

PRAVIDLA:
- Odpovídej POUZE na základě znalostní báze
- Buď konkrétní – uveď ceny, dostupnost, parametry
- Vždy odkaž na konkrétní produkt nebo stránku
- Pokud nevíš, řekni: 'Na tuto otázku nemám informace. Kontaktujte prosím podporu na podpora@techshop.cz nebo +420 123 456 789'
- NIKDY nevymýšlej informace o produktech nebo cenách

JAZYK: Vždy česky.
"
```

**Výsledky:**
- **První měsíc:** 45% dotazů vyřešeno chatbotem bez eskalace
- **Po 3 měsících:** 70% dotazů vyřešeno automaticky
- **Úspora času:** 15 hodin týdně zákaznické podpory
- **Benefit:** Zákazníci mají odpovědi 24/7, i o víkendech
- **Investice:** 1 den setup, 2 hodiny/měsíc údržba

**Typické dotazy, které bot zvládá:**
- „Máte na skladě iPhone 15 Pro?"
- „Jaká je dodací lhůta do Brna?"
- „Jak probíhá reklamace?"
- „Jaký je rozdíl mezi modelem X a Y?"
- „Můžu platit na splátky?"

---

### Příklad 2: Interní chatbot pro onboarding a znalost produktů

**Situace:** Firma s 50+ obchodníky měla problém s onboardingem nových lidí a aktuální znalostí produktového portfolia (150+ produktů, měnící se ceníky).

**Řešení: Interní knowledge bot v Botpress s integrací do Slacku**

**Příprava znalostní báze:**
1. **Onboarding dokumentace:**
   - Přehled firmy, hodnoty, procesy
   - Jak funguje CRM (HubSpot)
   - Prodejní proces krok za krokem
   - Kontakty na klíčové lidi v týmu
2. **Produktové znalosti:**
   - Katalog všech produktů a služeb
   - Ceníky (aktualizované měsíčně)
   - Use cases a case studies
   - Konkurenční srovnání
   - Argumentační mapa (námitky a odpovědi)
3. **Procesy a nástroje:**
   - Jak vytvořit nabídku
   - Schvalovací proces slev
   - FAQ pro interní tým

**Nastavení v Botpress:**
```
Instrukce:
"Jsi AI asistent 'SalesBot' pro interní tým obchodníků společnosti XYZ.

ROLE: Pomáháš obchodníkům s produktovými znalostmi, procesy a onboardingem.

TÓN: Přátelský kolega, který vždy pomůže.

PRAVIDLA:
- Odpovídej konkrétně s odkazy na dokumenty nebo nástroje
- Pro ceníky VŽDY uveď aktuální datum platnosti
- Pokud jde o složitý proces, rozděl do kroků
- Pokud nevíš, přesměruj na konkrétního člověka (např. 'Kontaktuj Janu z produktového týmu @jana')
- Používej interní terminologii a názvy nástrojů (HubSpot, Slack, Miro)

FORMÁT ODPOVĚDÍ:
- Stručné, praktické, s odkazy
- Pokud je víc možností, uveď seznam

JAZYK: Česky, občas anglické termíny (CRM, pipeline).
"
```

**Integrace:**
- **Slack bot:** Příkaz `/salesbot [dotaz]` v jakémkoliv kanálu
- **Web dashboard:** Interní portál s embedovaným chatbotem
- **Mobilní:** Přístup přes Slack mobil

**Výsledky:**
- **Onboarding:** Nový obchodník samostatný za 2 týdny (dřív 4-6 týdnů)
- **Produktové znalosti:** 80% dotazů na produkty vyřešeno okamžitě botem
- **Úspora času:** Produktový tým ušetří 20+ hodin měsíčně (nemusí odpovídat stále dokola)
- **Aktuálnost:** Bot má vždy aktuální ceníky (manuálně se to ztrácelo v emailech)
- **Investice:** 3 dny setup, 3 hodiny/měsíc update dat

**Typické dotazy, které bot zvládá:**
- „Jak vytvořím nabídku v HubSpotu?"
- „Jaká je cena produktu Premium a jaké má funkce?"
- „Kdo schvaluje slevy nad 20%?"
- „Jak argumentovat proti konkurenci Z?"
- „Koho mám kontaktovat ohledně technické implementace?"
- „Jaké jsou case studies z automotive sektoru?"

**Bonus – hlasový asistent (Voiceflow + Elevenlabs):**
Pro obchodníky na cestě přidali hlasovou verzi bota:
- Dotaz hlasem: „Salesbot, jaká je cena produktu X?"
- Odpověď hlasem: „Produkt X stojí 15 000 Kč měsíčně..."
- Použití: V autě cestou na meeting, rychlá kontrola informací

---

## Quick Action Guide

### Klíčové závěry
- **KRITICKÉ: Dobrá znalost + správné instrukce** = kvalitní bot
- Začněte jednoduše: 20-30 nejčastějších otázek
- Bot nemůže odpovědět na vše → vždy fallback na člověka
- Průběžně monitoruj a iteruj (první 2 měsíce aktivní učení)

### Co se vyhnout (a co dělat místo toho)
- ❌ Nahrát chaotické dokumenty. ✅ Nejdřív vyčisti a strukturuj data.
- ❌ Vágní instrukce. ✅ Jasná role, tón, pravidla (viz příklady).
- ❌ Očekávat 100% úspěšnost. ✅ Začni s 60%, iteruj na 80%.
- ❌ „Set and forget". ✅ První 2 měsíce aktivně doplňuj znalosti.
- ❌ Testovat jen jednoduché otázky. ✅ Zkus edge cases a nejasné dotazy.

### Začněte tady – krok za krokem

**1. Definuj use case (5 minut):**
- **Externě (zákazníci):** E-shop FAQ, podpora produktu, reklamace?
- **Interně (tým):** Onboarding, produktové znalosti, HR/IT helpdesk?

**2. Sesbírej znalosti (2-4 hodiny):**
- 20-30 nejčastějších otázek
- Odpovědi strukturované, s odkazy
- Dokumentace, procesy, kontakty

**3. Vyber nástroj (10 minut):**
- **Pro rychlý start:** Chatbase
- **Pro hlasové rozhraní:** Voiceflow + Elevenlabs
- **Pro pokročilé workflow:** Botpress
- **Pro Microsoft prostředí:** Copilot Studio
- **Pro automatizaci:** N8N (propojení s CRM/API)

**4. Nahraj data a nastav instrukce (30 minut):**
- Upload dokumentů
- Napiš jasné instrukce (viz příklady výše):
  - Role bota
  - Tón komunikace
  - Pravidla odpovědí
  - Co dělat, když neví
- Vyber AI model (GPT-4 nebo Claude 3.5)

**5. Testuj (1-2 hodiny):**
- 30+ různých otázek (včetně edge cases)
- Sleduj, co bot neví
- Oprav odpovědi / doplň znalosti
- Znovu testuj (iterace!)

**6. Nasaď (15 minut):**
- **Web:** Embed code na stránky
- **Slack/Teams:** Propoj bot s workspace
- **Hlas:** Telefonní linka (Voiceflow)

**7. Monitoruj a zlepšuj (průběžně):**
- **Týdně:** Check konverzace, doplň chybějící info
- **Měsíčně:** Review top dotazů, uprav instrukce
- **Cíl:** Po 2-3 měsících 70-80% úspěšnost

---

### Kdy použít jaký nástroj?

| **Potřeba** | **Nástroj** | **Důvod** |
|-------------|-------------|-----------|
| Rychlý start, jednoduché FAQ | **Chatbase** | Nejjednodušší setup |
| Hlasový asistent (telefonní linka) | **Voiceflow + Elevenlabs** | Realistický hlas |
| Pokročilé flow s podmínkami | **Botpress** | Visual workflow builder |
| Enterprise, Microsoft 365 | **Copilot Studio** | Integrace s Teams, SharePoint |
| Propojení s CRM/API/databází | **N8N + Chatbase** | Automatizace workflow |

---

### Co očekávat – realistický timeline

**První týden:**
- Setup a základní knowledge base: 4-6 hodin
- Úspěšnost: 40-50% dotazů

**První měsíc:**
- Aktivní učení (2 hod/týden doplňování znalostí)
- Úspěšnost: 60-70% dotazů

**Po 3 měsících:**
- Stabilizace, minimální údržba (2 hod/měsíc)
- Úspěšnost: 75-85% dotazů

**Dlouhodobě:**
- Bot šetří desítky hodin měsíčně
- Aktualizace při změně procesů/produktů