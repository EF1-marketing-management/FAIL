# Bezpečnost AI nástrojů ve firmě: Co potřebujete vědět v roce 2026

> ⚠️ **Upozornění:** Tento dokument má **informativní charakter** a nepředstavuje právní ani compliance poradenství. Nastavení AI platforem se rychle mění – informace odpovídají stavu k lednu 2026. Před jakýmkoliv rozhodnutím doporučujeme ověřit aktuální podmínky konkrétního nástroje a v případě potřeby konzultovat s právním nebo IT oddělením.

---

## Proč je tohle důležité právě teď

Rok 2026 je přelomový. AI přestává být experimentem a stává se běžnou součástí práce – v e-mailech, dokumentech, prezentacích, analýzách. S tím přicházejí nová rizika, která se týkají každého, kdo AI nástroje používá. V srpnu 2026 navíc začínají platit klíčové části EU AI Act. Rozumět základům bezpečnosti AI už není záležitost IT oddělení – je to kompetence každého profesionála.

---

## Co říká audit ve 30 sekundách

Tento dokument vychází z rozsáhlého bezpečnostního auditu čtyř hlavních AI platforem – Microsoft Copilot, Google Gemini, OpenAI ChatGPT a Anthropic Claude – zpracovaného v lednu 2026. Tady jsou klíčové závěry:

**Všechny čtyři platformy jsou v Enterprise verzích bezpečné.** Žádná z nich netrénuje na firemních datech, všechny nabízejí smlouvy o zpracování dat (DPA) a splňují základní požadavky GDPR.

**Bezplatné verze (Free) nejsou vhodné pro firemní data.** Ve výchozím nastavení trénují na vašich konverzacích a neposkytují žádné smluvní záruky. Placené spotřebitelské verze (Plus, Pro) lze pro pracovní účely použít, ale je nutné vypnout trénování na vlastních datech – návod najdete níže.

**Největší riziko není technologie, ale lidské chování.** Špatně nastavená oprávnění, používání soukromých účtů pro práci a bezmyšlenkovité vkládání citlivých dat do AI – to jsou reálné problémy roku 2026, ne sofistikované hackerské útoky.

**EU AI Act začíná reálně dopadat na firmy.** Od srpna 2026 platí přísná pravidla pro AI v HR, financích a dalších oblastech, kde se rozhoduje o lidech. Pokud AI používáte k hodnocení kandidátů nebo zaměstnanců, týká se to i vás.

**Lokalizace dat v EU se výrazně zlepšila.** OpenAI od ledna 2026 nově garantuje zpracování dat v EU. Google nabízí suverénní cloud přes T-Systems. Microsoft má EU Data Boundary, ale pozor na novou integraci modelů Anthropic, která z něj vypadává.

---

## Základ bezpečné práce s AI: tři třídy informací

Než se začnete zabývat nastavením konkrétních nástrojů, je klíčové pochopit, že ne každá informace představuje stejné riziko. Bezpečné používání AI je především o **risk managementu** – tedy o tom, která data do jakého nástroje patří a která ne.

### Třída 1: Veřejné informace

Data, která jsou volně dostupná nebo jejichž sdílení nepředstavuje žádné riziko. Patří sem obecné znalosti, veřejné dokumenty, vaše vlastní myšlenky bez citlivého kontextu.

**Přístup:** Můžete je vkládat do jakéhokoliv AI nástroje bez omezení.

### Třída 2: Firemní, ale necitlivé informace

Interní data, která nejsou veřejná, ale jejich případné sdílení nezpůsobí firmě škodu. Patří sem například interní texty bez citlivého obsahu, obecné procesy, šablony dokumentů.

**Přístup:** Lze použít ve správně nakonfigurovaných nástrojích. Minimálně je nutné mít vypnuté trénování modelů na vlastních datech.

### Třída 3: Citlivé informace

Data, jejichž únik by mohl způsobit reálnou škodu – firmě, klientům nebo zaměstnancům. Patří sem smlouvy, mzdy, osobní údaje, obchodní strategie, finanční výsledky před zveřejněním, údaje o klientech.

**Přístup:** Pouze Enterprise verze s DPA (smlouvou o zpracování dat), ideálně s garantovanou lokalizací dat v EU. V případě pochybností konzultujte s IT oddělením.

---

## Spotřebitelské vs. Enterprise verze: jaký je rozdíl

Problém tedy není v tom, *který* nástroj zvolíte, ale *jak* ho používáte – a jakou verzi.

| | Bezplatná verze (Free) | Placená spotřebitelská verze (Plus/Pro) | Enterprise verze |
|---|---|---|---|
| Trénování na vašich datech | ⚠️ Typicky ANO | ⚠️ ANO, ale lze vypnout | ✅ Garantovaně NE |
| Smlouva o zpracování dat (DPA) | ❌ | ❌ | ✅ |
| Vhodná pro firemní data | ❌ | ⚠️ Jen po správném nastavení | ✅ |
| Řízení přístupů (SSO/SCIM) | ❌ | ❌ | ✅ |
| Auditní logy | ❌ | ❌ | ✅ |
| Lokalizace dat v EU | ❌ | ❌ | ✅ (dle konfigurace) |

> 💡 **Poznámka:** Bezpečné nasazení AI dnes není výsadou technologických firem. I banky, pojišťovny a další subjekty z nejvíce regulovaných odvětví dnes úspěšně nasazují nástroje jako Claude, ChatGPT, Gemini nebo Cursor pro své zaměstnance – v souladu s bezpečnostními a regulatorními požadavky. Klíčem je správná volba verze a konfigurace, ne odmítnutí AI jako takového.

**Klíčový závěr:** Bezplatné verze nejsou vhodné pro práci s firemními daty. Placené spotřebitelské verze (Plus, Pro) lze pro méně citlivá data použít – ale je nutné nejprve vypnout trénování. Enterprise verze jsou vhodné pro všechny třídy dat, pokud jsou správně nakonfigurované.

---

## Jak vypnout trénování na vašich datech

I pokud používáte spotřebitelskou verzi (Free, Plus, Pro), můžete trénování na svých datech vypnout. U Enterprise verzí je trénování vypnuté automaticky – ale ověřte si to.

### ChatGPT (OpenAI)

1. Klikněte na ikonu profilu (vpravo nahoře)
2. Vyberte **Settings**
3. Přejděte na **Data Controls**
4. Vypněte přepínač **„Improve the model for everyone"**

Alternativa: Zapněte **Temporary Chat** (ikona vpravo nahoře v okně chatu) – tyto konverzace se neukládají ani nepoužívají k trénování.

> U verzí Enterprise, Team a Edu je trénování vypnuté ve výchozím nastavení. Ověřte u svého IT oddělení.

### Claude (Anthropic)

1. Klikněte na ikonu profilu / své iniciály
2. Přejděte na **Settings → Privacy**
3. Vypněte přepínač **„Help improve Claude"**

Důležité: Od října 2025 Anthropic ve výchozím stavu trénuje na datech spotřebitelských účtů (Free, Pro, Max). Pokud jste to při aktualizaci podmínek nezměnili, vaše konverzace se pravděpodobně používají k trénování. Pokud trénování povolíte, Anthropic si data uchovává až 5 let. Po vypnutí se retence zkrátí na 30 dní.

> Firemní účty (Claude for Work, Enterprise, API přes Bedrock/Vertex) jsou z trénování automaticky vyloučeny.

### Google Gemini

1. Otevřete Gemini a klikněte na ikonu aktivity (hodiny se šipkou) nebo přejděte do nastavení účtu
2. Najděte **Gemini Apps Activity** (nově přejmenováno na **„Keep Activity"**)
3. Klikněte na **Turn off** → zvolte **„Turn off and delete activity"** (smaže i historická data)

Volitelně: Zkontrolujte, zda nemáte zaškrtnuté **„Improve Google services with your audio and Gemini Live recordings"** – pokud ano, odškrtněte.

> U Google Workspace (firemních účtů) je trénování vypnuté ve výchozím nastavení. V EEA, Japonsku, Švýcarsku a UK jsou navíc vypnuté i Smart Features.

### Microsoft Copilot (M365)

U Copilotu pro Microsoft 365 (Enterprise) **není potřeba nic vypínat** – Microsoft smluvně garantuje, že data zákazníků nejsou používána k trénování modelů. Toto je součástí Enterprise Data Protection a je zakotveno v DPA.

> Pozor ale na bezplatnou verzi Copilotu (copilot.microsoft.com) – ta má jiné podmínky. Pro firemní použití vždy využívejte licencovaný Copilot pro M365.

### Shrnutí: výchozí nastavení trénování

| Nástroj | Spotřebitelská verze (Free/Plus/Pro) | Enterprise verze |
|---|---|---|
| ChatGPT | ⚠️ Zapnuté (opt-out) | ✅ Vypnuté |
| Claude | ⚠️ Zapnuté od 10/2025 (opt-out) | ✅ Vypnuté |
| Gemini | ⚠️ Zapnuté (opt-out) | ✅ Vypnuté |
| Copilot M365 | ⚠️ Závisí na verzi | ✅ Vypnuté |

**Zlaté pravidlo:** Vypněte trénování na všech osobních účtech, kde se přihlašujete. Pro práci s citlivými daty pak volte nástroj podle míry rizika – větší firmy s přísnými compliance požadavky zpravidla sáhnou po Enterprise verzi se smluvními zárukami, menší a střední firmy mohou v mnoha případech bezpečně vyjít i s placenou spotřebitelskou verzí při správném nastavení. Klíčová otázka není „mám Enterprise?", ale „vím, co do AI vkládám a jaké to nese riziko?"

---

## Srovnání 4 hlavních platforem (leden 2026)

### Microsoft Copilot pro M365

| Oblast | Hodnocení |
|---|---|
| Trénování na datech klienta | ✅ NE (garantováno v DPA) |
| Data v EU (uložení) | ✅ EU Data Boundary |
| Data v EU (zpracování) | ⚠️ ANO, ale pozor na plugin Anthropic |
| Suverénní cloud | ✅ M365 Local |
| Ochrana citlivých dat (DLP) | ✅ Vynikající (Purview) |
| Štítky citlivosti | ✅ Plná dědičnost |

**Silná stránka:** Nejhlubší integrace s pracovním prostředím. Copilot respektuje přístupová práva a štítky citlivosti – pokud je máte správně nastavené.

**Na co si dát pozor:** Od ledna 2026 je možné aktivovat modely Anthropic (Claude) jako doplněk. V EU je to ve výchozím stavu vypnuté. Pokud to zapnete, data mohou putovat mimo EU. Pro regulovaná odvětví doporučujeme ponechat vypnuté.

---

### Google Gemini pro Workspace

| Oblast | Hodnocení |
|---|---|
| Trénování na datech klienta | ✅ NE (garantováno v DPA) |
| Data v EU (uložení) | ✅ Data Regions |
| Data v EU (zpracování) | ✅ Pro vybrané modely |
| Suverénní cloud | ✅ T-Systems (zlatý standard) |
| Ochrana citlivých dat (DLP) | ⚠️ Vysoká, ale méně granulární |
| ISO 42001 certifikace | ✅ ANO |

**Silná stránka:** Partnerství s T-Systems nabízí v Evropě nejvyšší úroveň datové suverenity. Google nemá technickou možnost dešifrovat data bez součinnosti T-Systems.

**Na co si dát pozor:** Je nutné důsledně odlišit Gemini v rámci Workspace (chráněné) od spotřebitelské verze na gemini.google.com (nechráněné). Pokud administrátor nezakáže přístup ke spotřebitelské verzi, zaměstnanci mohou nevědomky souhlasit s použitím dat pro trénování.

---

### OpenAI ChatGPT Enterprise

| Oblast | Hodnocení |
|---|---|
| Trénování na datech klienta | ✅ NE (garantováno v DPA) |
| Data v EU (uložení) | ✅ ANO |
| Data v EU (zpracování) | ✅ ANO (novinka leden 2026) |
| Suverénní cloud | ❌ Pouze privátní instance |
| Ochrana citlivých dat (DLP) | ⚠️ Základní |
| ISO 42001 certifikace | ✅ ANO |

**Silná stránka:** Od ledna 2026 konečně plná datová rezidence v EU včetně zpracování. Model GPT-5.2 přináší výrazně lepší reasoning. Možnost nastavit Zero Data Retention.

**Na co si dát pozor:** ChatGPT Enterprise je izolovaný nástroj – stojí mimo váš hlavní pracovní ekosystém (na rozdíl od Copilotu a Gemini). Uživatelé do něj musí data aktivně kopírovat, což zvyšuje riziko lidské chyby.

---

### Anthropic Claude Enterprise

| Oblast | Hodnocení |
|---|---|
| Trénování na datech klienta | ✅ NE (garantováno v DPA) |
| Data v EU (uložení) | ⚠️ Přes AWS/GCP – závisí na konfiguraci |
| Data v EU (zpracování) | ⚠️ Částečně (závisí na hostingu) |
| Suverénní cloud | ❌ Závisí na partnerovi |
| Ochrana citlivých dat (DLP) | ⚠️ Základní (API) |
| ISO 42001 certifikace | ✅ ANO |

**Silná stránka:** Nejpokročilejší přístup k bezpečnosti modelu (Constitutional AI). Obrovské kontextové okno (až 1M tokenů) umožňuje analyzovat rozsáhlé dokumenty najednou. Nejvyšší transparentnost – zveřejňuje principy řízení modelu.

**Na co si dát pozor:** V SaaS verzi se data primárně zpracovávají v USA, pokud není dohodnuto jinak. Pro plnou kontrolu nad lokalizací je lepší využít Claude přes AWS Bedrock v evropském regionu (Frankfurt, Paříž).

---

## EU AI Act: Co vás čeká

### Už platí (od února 2025)

Zákaz AI praktik představujících nepřijatelné riziko – sociální skóring, biometrická kategorizace emocí na pracovišti, plošné stahování snímků obličejů. Žádný z hlavních nástrojů toto nenabízí, ale riziko vzniká, pokud byste si takový systém postavili sami přes API.

### Kritický termín: srpen 2026

Začínají platit povinnosti pro **vysoce rizikové AI systémy**. Pokud ve firmě používáte AI pro:

- **HR a nábor** – třídění životopisů, hodnocení kandidátů, hodnocení výkonnosti
- **Vzdělávání** – hodnocení studentů, přijímací řízení
- **Finance** – úvěrové skóringy, pojišťovnictví
- **Kritickou infrastrukturu** – řízení dodávek, doprava

...musíte do srpna 2026 zavést:

1. **Systém řízení rizik** – dokumentovaná analýza rizik konkrétního nasazení
2. **Lidský dohled** – AI nesmí rozhodovat plně automaticky
3. **Technickou dokumentaci** – jak systém funguje, na jakých datech
4. **Kontrolu kvality dat** – minimalizace diskriminace a zaujatosti (bias)

### Co to znamená prakticky

Využívat Copilot k sumarizaci e-mailů je v pořádku. Ale pokud ve své práci používáte AI k rozhodování o lidech – třeba k předvýběru kandidátů nebo hodnocení výkonnosti – měli byste vědět, že od srpna 2026 to bude podléhat přísným pravidlům. Výstup AI si vždy ověřte a rozhodněte sami.

---

## 4 hlavní rizika a jak se jim vyhnout

### 1. AI vidí víc, než byste čekali

**Co se děje:** AI nástroje (zejména Copilot a Gemini) prohledávají vše, k čemu máte ve firmě přístup. Pokud máte historicky přístup k širokému množství dokumentů (a to je v mnoha firmách běžné), AI vám na dotaz může vrátit i data, která jste nikdy aktivně nehledali. Totéž platí pro vaše kolegy – pokud mají přístup k vašim složkám, AI jim je může zpřístupnit.

**Co s tím můžete udělat:**
- Uvědomte si, že cokoliv je ve sdílených složkách, může AI „najít" a předložit komukoli s přístupem
- Zkontrolujte si sdílení svých dokumentů – nemáte něco sdílené na „Everyone" nebo „Celá firma"?
- Pokud narazíte na data, ke kterým byste neměli mít přístup, upozorněte na to IT oddělení

---

### 2. Osobní účet neznamená firemní ochrana

**Co se děje:** Když používáte svůj soukromý účet pro práci – zejména v bezplatné verzi – vaše firemní data nemají žádnou smluvní ochranu. Mohou být použita k trénování modelů a vy nad nimi ztrácíte kontrolu. U placených spotřebitelských verzí (Plus, Pro) lze trénování vypnout, ale ochrana je stále slabší než u Enterprise.

**Co s tím můžete udělat:**
- Pro práci s firemními daty vždy preferujte firemní AI účet (pokud ho máte)
- Pokud firemní účet nemáte, minimálně si vypněte trénování na osobním účtu (viz sekce výše)
- Nevkládejte do nechráněných nástrojů citlivá firemní data – smlouvy, mzdy, strategie, osobní údaje klientů
- Pokud si nejste jisti, jaké nástroje jsou ve vaší firmě schválené k použití, zeptejte se IT oddělení – v řadě firem probíhá nebo se plánuje whitelisting bezpečných AI nástrojů

---

### 3. Za AI stojí víc firem, než si myslíte

**Co se děje:** AI platformy začínají v pozadí využívat modely od jiných poskytovatelů. Například Microsoft Copilot nově umožňuje integraci modelů Anthropic. Vaše data tak mohou putovat k dalšímu poskytovateli – a potenciálně i mimo EU.

**Co s tím můžete udělat:**
- Zajímejte se o to, jaké nástroje vaše firma používá a jak jsou nakonfigurované
- Pokud pracujete s citlivými daty a nejste si jisti, zeptejte se svého IT oddělení na nastavení
- Obecně platí: čím méně nástrojů a integrací, tím menší riziko

---

### 4. AI v HR, financích nebo hodnocení? Pozor na zákon

**Co se děje:** Od srpna 2026 začínají platit přísné povinnosti pro AI v oblastech jako nábor, hodnocení zaměstnanců, úvěrové rozhodování nebo vzdělávání. Pokud ve své práci AI používáte k rozhodování o lidech, musíte vědět, že to bude regulované.

**Co s tím můžete udělat:**
- Pokud používáte AI k hodnocení kandidátů, zaměstnanců nebo klientů – vždy si výstup ověřte a rozhodněte sami
- Nenechávejte AI rozhodovat automaticky o lidech bez vaší kontroly
- Pokud si nejste jisti, zda vaše využití AI spadá do „vysoce rizikové" kategorie, promluvte si s nadřízeným nebo právním oddělením

---

> **Zapamatujte si:** Bezpečnost AI není jen o technologii – je o vašich návycích a schopnosti rozlišit, která data kam patří. Vypněte trénování na osobních účtech, používejte firemní účty pro citlivá data, konzultujte s IT oddělením a vždy si ověřujte výstupy AI. To je základ, na kterém můžete AI bezpečně využívat naplno.

---

*Zdroj: Audit bezpečnosti a compliance nástrojů GenAI, leden 2026*

*Tento dokument má výhradně informační charakter a nepředstavuje právní, compliance ani jiné odborné poradenství. Autor nepřebírá odpovědnost za rozhodnutí učiněná na základě zde uvedených informací. Nastavení platforem se průběžně mění – před jakýmkoliv rozhodnutím ověřte aktuální podmínky konkrétního nástroje.*
