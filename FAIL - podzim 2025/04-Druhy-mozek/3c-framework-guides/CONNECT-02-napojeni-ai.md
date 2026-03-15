# Jak napojit AI na firemní data pro odpovědi v kontextu

**Přehled:** AI nástroje se napojí přímo na vaše cloudové úložiště (Google Drive, OneDrive, Notion) a odpovídají podle aktuálních dat.

**Proč na tom záleží:** Nemusíte nic manuálně nahrávat ani kopírovat. AI má přímý přístup k vašim souborům a vždycky pracuje s nejnovější verzí.

**Základní princip:** Propojíte AI nástroj s cloudovým úložištěm, autorizujete přístup, a AI pak může prohledávat a číst vaše soubory.

---

## ⚠️ Realistická očekávání

Integrace AI s cloudovými úložišti se neustále zlepšují, ale **zatím to nemusí fungovat na 100 %**. Gemini s Google Drive funguje skvěle, ale ChatGPT s Notion vyžaduje dodatečné kroky. Copilot s SharePoint je solidní, ale občas „nevidí" nejnovější soubory. Co dnes funguje dobře, může být zítra ještě lepší – a naopak. **Proto vždy testujte na vlastních datech!**

---

## 🚀 Quick Win

**Zjisti, co máte k dispozici a vyzkoušej:**

1. **Pokud máte Google Workspace:** Otevřete Gemini a zkus: „Najděte v mých dokumentech informace o [projekt]"
2. **Pokud máte Microsoft 365:** Otevřete Copilot a zkus: „Najděte v SharePointu dokument o [téma]"
3. **Pokud máte Notion:** Aktivuj Notion AI a použij `/ai` příkaz
4. **Pokud máte ChatGPT (ne Custom GPT):** Můžete napojit přímo v chatu na Google Drive, OneDrive nebo Notion přes Connectors
5. **Pokud máte Claude:** Připojte Google Drive, Gmail nebo GitHub přes integrace v nastavení
6. Funguje? Super – máte napojení!
7. Nefunguje nebo nemáš tyto nástroje? Export dokumenty a použij Custom GPT/Claude Project

---

## AI nástroje a jejich napojení

### 1. Gemini + Google Drive (nejpřímější integrace - doporučeno)

**Co to je:** Gemini automaticky vidí váš Google Drive, Docs, Sheets.

**Jak to funguje:**
- Gemini má nativní přístup k Google Workspace
- Nemusíš nic nastavovat
- Jen se ptej a Gemini hledá

**Web:** https://gemini.google.com

**Příklad použití:**

```
„Najděte všechny dokumenty o Q4 rozpočtu"
„Shrň mi poslední prezentaci o produktu X"
„Které soubory zmiňují klienta ABC?"
```

**Kdy použít:** Máš Google Workspace a chcete zero-setup řešení.

**Důležité:** 
- Funguje jen pro soubory ve tvém Google Drive
- Respektuje oprávnění (vidí jen, co můžete ty)
- Pro týmové použití: každý má svůj Gemini s vlastním přístupem

---

### 2. ChatGPT + Cloudová úložiště (přímé napojení bez Custom GPT)

**Co to je:** ChatGPT (standardní chat) může být připojen přímo ke cloudovým úložištím přes funkci **Connectors** nebo **Apps & Connectors**.

**Podporované zdroje:**
- Google Drive
- Microsoft OneDrive / SharePoint  
- Notion (workspace)

**Jak nastavit připojení (příklad: Google Drive):**

1. V ChatGPT chatu klikněte na ikonu **📎 (připojit soubor)**
2. Vyberte možnost **"Connect app"** nebo **"Connectors"**
3. Najděte **Google Drive** a klikněte na **"Connect"**
4. Přihlaste se ke svému Google účtu (OAuth autorizace)
5. Povolte ChatGPT přístup k vybraným složkám
6. Po dokončení synchronizace můžete klást otázky typu: "Najdi v mých dokumentech informace o [téma]"

**Pro Notion:**
1. V nastavení ChatGPT najděte **"Connected apps"**
2. Vyberte **Notion** a klikněte **"Connect"**
3. Autorizujte přístup k workspace
4. ChatGPT pak může číst obsah z Notion

**Pro OneDrive/SharePoint (ChatGPT Enterprise):**
1. Administrátor musí povolit SharePoint konektor v nastavení
2. Uživatelé pak mohou připojit své účty přes OAuth
3. Funguje napříč celou organizací

**Důležité:**
- Není potřeba vytvářet Custom GPT – funguje přímo v běžném chatu
- Respektuje oprávnění (vidí jen, co máte právo vidět)
- Integrace se stále vyvíjejí – nemusí fungovat 100% spolehlivě

**Alternativa – Custom GPT (pro stabilnější řešení):**
1. Notion → Export workspace jako Markdown
2. ChatGPT → Create GPT → Nahrajte exportované soubory
3. Funguje offline, ale není automaticky aktuální

**Kdy použít:** Máš hlavní dokumentaci v cloudovém úložišti a chceš rychlý přístup bez vytváření Custom GPT.

---

### 3. Claude + Cloudová integrace & Projects

**Co to je:** Claude nabízí dva přístupy – přímé integrace přes Connectors nebo nahrání do Projects.

**Cesta A: Přímé integrace (Claude Connectors)**

Claude podporuje připojení k:
- **Google Drive**
- **Gmail** 
- **GitHub**
- **Google Calendar**

**Jak nastavit (příklad: Google Drive):**
1. V Claude chatu klikněte na **"Connect sources"** nebo ikonu integrace
2. Vyberte **Google Drive**
3. Přihlaste se a autorizujte přístup
4. Claude pak může prohledávat vaše soubory na Drive

**Důležité:** 
- Funguje přímo v chatu, nemusíš vytvářet Project
- Respektuje Google Drive oprávnění
- Stále ve vývoji – může mít občasné limity

**Cesta B: Claude Projects (upload souborů)**

1. Claude → New Project → pojmenuj
2. Upload dokumenty do „Project Knowledge"
3. Konverzuj v rámci projektu – Claude vidí dokumenty

**Limity:**
- Není to „live" připojení – musíš soubory nahrát
- Ale: obrovské context okno (200K tokenů)
- Dobré pro stabilní dokumentaci

**Kdy použít:** 
- Přímé integrace: Máš data v Google Drive/Gmail a chceš živé připojení
- Projects: Máš sadu dokumentů, která se často nemění, nebo chcete plnou kontrolu nad tím, co AI vidí

---

### 4. Microsoft Copilot + OneDrive/SharePoint (enterprise - doporučeno)

**Co to je:** Automatické propojení v Microsoft 365 ekosystému s enterprise bezpečností.

**Jak to funguje:**
- Copilot automaticky vidí OneDrive, SharePoint, Teams
- Funguje přes celou M365 organizaci
- Enterprise security a compliance

**Web:** https://www.microsoft.com/microsoft-copilot

**Příklad dotazů:**

```
„Najděte poslední rozpočet z našeho SharePoint týmu"
„Kdo pracoval na dokumentu X?"
„Shrň mi emaily o projektu Y z posledního týdne"
```

**Kdy použít:** Jste větší firma s Microsoft 365 a potřebujete enterprise řešení.

**Důležité:**
- Vyžaduje Microsoft 365 Copilot licenci
- Admin může řídit, co Copilot vidí
- Respektuje všechna SharePoint oprávnění

---

### 5. Poznámkové aplikace s AI

**OneNote + Copilot:**
- Copilot vidí vaše OneNote poznámky
- Funguje v rámci Microsoft ekosystému

**Notion + Notion AI:**
- AI přímo integrované v Notion
- Vidí celý workspace automaticky

**Google Keep + Gemini:**
- Základní integrace
- Gemini může hledat v Keep poznámkách

---

## 💡 Příklad z praxe

**Obchodní tým** používá Microsoft 365. Copilot má přístup k SharePointu s dokumentací produktů, ceníky a případovými studiemi. Obchodník se před schůzkou zeptá Copilot: „Co je nejnovější ceník pro Enterprise plán?" Copilot vytáhne aktuální informace z SharePointu. Obchodník má správné číslo za 5 sekund místo 10 minut hledání.

**Další příklady:**
- Marketingový tým + Gemini + Google Drive: „Najděte všechny kampaně z Q3"
- Produktový tým + Notion AI: „Jaké jsou otevřené požadavky na funkce?"
- Podpora + Copilot + SharePoint: „Kde je návod na řešení problémů s produktem X?"

---

## Proces napojení

### 1. Identifikujte, co používáte

**Jakou AI?**
- ChatGPT, Claude, Gemini, Copilot

**Kde máte data?**
- Google Drive, Notion, OneDrive, SharePoint, OneNote

### 2. Zjisti možnosti propojení

Google: „[AI nástroj] + [úložiště] integration 2025"

**Příklad výsledků:**
- Gemini ✓ nativně vidí Google Drive
- ChatGPT ⚠️ potřebuje Custom GPT nebo export
- Claude ⚠️ vyžaduje upload do Project
- Copilot ✓ nativně vidí Microsoft 365

### 3. Vyzkoušejte dostupné možnosti

- Ne enterprise – začni s dostupným
- Testujte na reálných datech
- Ověř že vidí, co má

### 4. Otestuj

- Nahrajte testovací data nebo se připoj
- Zkuste se zeptat AI
- Ověř že odpovídá ze správných zdrojů

---

## Quick Action Guide

### Klíčové závěry
- Každý má jiné nástroje – proces je: zjistit + vyzkoušet
- Začněte s dostupným, ne s ideálním
- Nativní integrace (Gemini+Drive, Copilot+M365) jsou nejjednodušší

### Co se vyhnout (a, co dělat místo toho)
- ❌ Předpokládat že všechny integrace fungují stejně. ✅ Testujte na vlastních datech nejdřív.
- ❌ Dávat AI přístup ke všemu najednou. ✅ Začněte s jednou složkou nebo workspace.
- ❌ Spoléhat se na AI že najde vše. ✅ Ověř výsledky, zvlášť zpočátku.
- ❌ Zapomenout na oprávnění. ✅ Zkontrolujte kdo má přístup k čemu.

### Začněte tady

**Postupnost - začni jednoduše:**

1. Zjistěte jakou AI a úložiště používáte (ChatGPT + Notion? Gemini + Drive?)
2. Google: „[vaše AI] + [vaše úložiště] integration"
3. **Začněte s nejjednodušší dostupnou možností:**
   - Gemini + Google Drive = žádné nastavování
   - Copilot + Microsoft 365 = žádné nastavování
   - Custom GPT/Claude Project = musíš nahrát dokumenty
4. Připoj se nebo nahraj **testovací data** (ne všechno najednou!)
5. Testujte: „Najděte dokument o [něco konkrétního]"
6. Funguje? Postupně přidávej více dat
7. Nefunguje? Zkuste jinou kombinaci AI + úložiště

**Kdy přejít na pokročilé:**
- Nativní integrace (Gemini/Copilot) fungují → zůstaň u toho
- Potřebuješ specifické napojení → custom API/MCP integrace
- Potřebuješ plnou kontrolu → custom RAG systém

---

## Zdroje

**Tip:** Kompletní přehled nástrojů najdete na https://drimalka.com/aplikace-ne-druhy-mozek-nejen-s-ai/

---

**Důležité:** Začněte s malým testovacím datastem, než propojíš všechno.