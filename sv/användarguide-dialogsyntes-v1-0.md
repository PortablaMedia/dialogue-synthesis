# Användarguide: Dialogsyntes

**Version:** 1.0 — ingår i Dialogsyntes-paketet v1.0
**Kompatibel med:** Mall för Dialogsyntes v1.0, Inläsningsprompt v1.0
**Syfte:** En praktisk handbok för att bevara och återanvända kunskap, resonemang och stringens i iterativt arbete med AI-agenter och i mänskliga projekt.

---

## 1. Introduktion

### Syfte med guiden
Denna guide hjälper dig att dokumentera viktiga vägval från dialoger mellan människor, mellan människor och AI-agenter eller mellan AI-agenter på ett strukturerat sätt.

Målet är att bevara kunskap så att du, kollegor eller framtida AI-agenter kan förstå:
- vilka problem som har behandlats
- vilka beslut som har fattats
- varför vissa vägval gjordes
- vilka antaganden och osäkerheter som återstår
- vilka återanvändbara lärdomar som kan tas vidare till andra sammanhang

### Grundkonceptet: Kontext-stacken
När man arbetar i långa eller uppdelade AI-sessioner uppstår ofta två problem:
1. **Minnesförlust:** AI-agenten tappar tråden eller sammanfattar bort viktiga detaljer.
2. **Forminflation & Precisionstapp:** När en ny chatt startas om utan rätt underlag tenderar AI-agenten att generera svällande, generiska och mindre användbara svar i stället för att hålla samma skarpa stringens som i förra chatten.

För att lösa detta bygger metoden på en **fyrdelad kontext-stack**:

```text
  [ 1. ARBETSRESULTATET ] --> "Substansen" (Koden, användarresorna, rapporten från förra steget)
  [ 2. DIALOGSYNTESEN   ] --> "Metakontexten" (Besluten, motiveringarna, lärdomarna)
  [ 3. INLÄSNINGSPROMPT  ] --> "Styrningen" (Låsta ramar, stringenskrav, dagens mål)
  [ 4. RAMVERK / MALL   ] --> "Standarder" (Instruktioner för att förvalta och uppdatera)
```

> **Varför räcker det inte med bara Dialogsyntesen?**  
> Dialogsyntesen bevarar *resonemanget* (metakontexten). Men om AI-agenten inte också får se det faktiska *arbetsresultatet* (substansen) tvingas den gissa sig till detaljnivån och upplösningen. Det är då svarstexten lätt sväller från 6 konsekventa punkter till 25 generiska idéer. **Substansen och Metakontexten måste alltid resa tillsammans.**

### Fyra delar i en beslutspost
För varje vägval hålls fyra begrepp strikt åtskilda:

- **Beslut:** Beskriver **vad som valdes**.
- **Motivering:** Beskriver **varför det valda alternativet bedömdes vara bäst**.
- **Konsekvenser:** Beskriver **vad beslutet leder till i det aktuella arbetet**.
- **Återanvändbar lärdom:** Beskriver **vad andra projekt, team eller framtida AI-dialoger kan lära av beslutet**.

En återanvändbar lärdom ska uttrycka en princip, ett mönster, en varning eller en praktisk tumregel. Den ska inte bara upprepa beslutet.

Exempel:
- **Beslut:** Praktiska guider prioriteras i bloggen under kvartalet.
- **Motivering:** Tidigare guider har skapat högre engagemang än nyhetsinlägg.
- **Konsekvens:** Den redaktionella kalendern behöver ändras.
- **Återanvändbar lärdom:** När tidigare innehåll visar tydliga skillnader i användarbeteende bör innehållsformat prioriteras utifrån dokumenterad effekt, men slutsatsen behöver omprövas när målgrupp eller distributionskanal förändras.

### Klassificering och status — två olika saker
Varje post i en Dialogsyntes har en **klass** (vad posten är): Beslut, Förslag, Antagande, Avvisat alternativ, Öppen fråga eller Återanvändbar lärdom.

Utöver klassen har varje **beslut** en **status** som beskriver dess livscykel: `Föreslaget`, `Aktivt`, `Ersatt`, `Avvisat` eller `Pausat`. Definitionerna finns i mallen (avsnitt 3) — guiden använder samma värden.

### Vem är guiden för?
- **Projektledare** som vill dokumentera nyckelbeslut.
- **Innehållsskapare** som utvecklar strategier eller riktlinjer.
- **Utvecklare & Arkitekter** som fattar tekniska vägval.
- **AI-användare** som vill bevara kunskap och stringens mellan långa dialoger med AI-agenter.

---

## 2. När ska du använda Dialogsyntesen?

### Utlösarpunkter: när bör du skapa en syntes?
Skapa eller uppdatera en Dialogsyntes när något av följande inträffar:
- Dialogen har blivit **värdefull att förlora** — du skulle bli ledsen om tråden försvann.
- Kontextfönstret närmar sig **kapacitet** eller chatten börjar kännas mättad.
- En **session eller fas avslutas** och nästa steg kräver en ny chatt.
- En **milstolpe** har nåtts och du vill låsa de fattade besluten.
- Du behöver **byta agent, verktyg eller person** i arbetet.
- Ett tidigare antagande har **omprövats** eller en avgränsning har blivit viktig.

### Använd snabbversionen när:
- Dialogen är kort eller enkel och innehåller några få vägval.
- Beslutet inte kräver dokumenterade alternativ, riskanalys eller beroenden.
- Du snabbt vill fånga de viktigaste punkterna.
- Beslutet är avgränsat men ändå kan behöva förstås eller återanvändas senare.

*Exempel:*
- Blogginläggen ska normalt vara högst 500 ord.
- En viss visuell princip ska användas konsekvent i en kampanj.
- Nyhetsbrevet ska publiceras på torsdagar.

### Använd den fullständiga versionen när:
- Beslutet påverkar en modell, metod, arkitektur eller strategi.
- Dokumenterade alternativ och jämförelser behövs.
- Beslutet kan behöva omprövas senare.
- Beslutet får konsekvenser för flera personer, processer, system eller AI-agenter.
- Beslutet bygger på betydelsefulla antaganden som behöver valideras.
- En framtida deltagare riskerar att behöva göra om samma analys utan loggen.

*Exempel:*
- En viss AI-modell väljs för en tjänst.
- Projektet avgränsas till en särskild målgrupp eller marknad.
- Användarupplevelse prioriteras framför kortsiktiga kostnadsbesparingar.

### Dokumentera inte
Enkelt test: dokumentera bara vägval som en framtida deltagare kan behöva ompröva. Enstaka formuleringar, mindre korrektur och idéer som aldrig diskuterades vidare hör inte hemma i loggen — mallens granularitetstest (avsnitt 4) äger de fullständiga reglerna.

### När bör en återanvändbar lärdom dokumenteras?
Dokumentera en lärdom när minst ett av följande gäller:
- samma insikt kan hjälpa ett annat projekt
- ett tydligt mönster har identifierats
- ett vanligt misstag eller en risk har blivit synlig
- ett gränsfall har lett till en viktig princip
- ett tidigare antagande har visat sig vara otillräckligt
- lärdomen kan hjälpa en framtida deltagare/AI-agent att undvika samma analys

Alla beslut behöver inte ge en generell lärdom. Skriv **Ingen återanvändbar lärdom identifierad** när beslutet är specifikt för det aktuella fallet.

---

## 3. Hur använder du Dialogsyntesen?

### Steg 1: Välj version
Använd kriterierna i avsnitt 2 för att välja snabb eller fullständig version. Strukturerna för båda finns i mallen (avsnitt 6–7).

### Steg 2: Fyll i Dialogsyntesen (Avsluta Chatt 1)
- Be AI-agenten sammanfatta dialogen med **Prompt 1** (se avsnitt 8).
- Koppla besluten direkt till ditt framtagna Arbetsresultat.
- **Hänvisa till källunderlag med filnamn och version — klistra inte in längre textutdrag** ur specifikationer, principer eller dialoger. Det som krävs för att beslutet ska förstås står i posten; resten lämnas åt källan.
- **Ta aldrig med lösenord, API-nycklar eller personuppgifter** i loggen — den är till för att resa mellan chattar, agenter och personer.
- **Snabbversion:** Fyll i bakgrund, beslut, motivering, återanvändbar lärdom, antaganden, konsekvenser och källunderlag.
- **Fullständig version:** Fyll även i observationer, beslutskriterier, alternativ, beroenden, risker och uppföljning.

### Steg 3: Granska och godkänn
Om en AI-agent har skapat loggen gäller principen: **AI föreslår, människa granskar**.

Kontrollera att:
- beslutstexten är begriplig utan originaldialogen
- kopplingen till det konkreta Arbetsresultatet är tydlig
- antaganden och osäkerheter är separerade från beslutet
- statusen är korrekt (`Aktivt`, `Föreslaget`, `Ersatt`, `Avvisat`, `Pausat` — definitioner i mallen)
- den återanvändbara lärdomen inte bara upprepar beslutet
- källunderlag hänvisas **med version eller identifierare** i stället för att kopieras
- loggen inte innehåller lösenord, API-nycklar eller personuppgifter

### Steg 4: Spara och versionera
- Spara loggen som Markdown, exempelvis `Dialogsyntes_v1.md` tillsammans med ditt resultat `Arbetsresultat_v1.md`.
- Skapa en ny version när loggen eller arbetsresultatet uppdateras.
- Behåll äldre beslut när de ersätts och markera dem som `Ersatt` — länka dem till de nya besluten (se mallens kedjningsregler).

### Steg 5: Starta nästa session (Läs in i Chatt 2)
När du startar nästa chatt i samma projekt:
1. Ladda upp **både** `Arbetsresultat_v1.md` och `Dialogsyntes_v1.md`.
2. Klistra in **Inläsningsprompten** (filen `dialogsyntes-prompt-svenska-v1-0.md`) med dagens nya mål.
3. AI-agenten låser de fattade besluten, tar hänsyn till öppna frågor och behåller samma detaljnivå och stringens.

---

## 4. Praktiska exempel

### Exempel 1: Snabbversion

```markdown
# Dialogsyntes: Blogginnehåll Q4 2026

**Kopplat Arbetsresultat:** Redaktionell_Kalender_Q4.md

## BL-001: Fokus på praktiska guider

**Status:** Aktivt  
**Datum:** 2026-09-02  
**Beslutstyp:** Innehåll  
**Taggar:** blogg, strategi, användarupplevelse

### Bakgrund
Vi ville öka trafik och engagemang på bloggen. Analys av tidigare inlägg visade att praktiska guider hade väsentligt högre delning än nyhetsinlägg.

### Beslut
Vi prioriterar praktiska guider och steg-för-steg-artiklar under Q4 2026 (se modul 2 i Redaktionell_Kalender_Q4.md).

### Motivering
Tidigare resultat tyder på högre engagemang och bättre sökresultat för praktiskt innehåll.

### Återanvändbar lärdom
När tidigare innehåll visar tydliga skillnader i användarbeteende bör den redaktionella planeringen bygga på dokumenterad effekt. Slutsatsen behöver omprövas om målgrupp, ämne eller distributionskanal förändras.

### Antaganden och osäkerheter
- A-001: Läsarna föredrar praktiskt innehåll framför nyheter. Valideras genom analys av trafikdata efter tre månader.

### Konsekvenser och nästa steg
- Skriv två guider per månad.
- Uppdatera den redaktionella kalendern.
- Följ upp tid på sida och delningar.

### Källunderlag
- Dialog #45, analys av bloggstatistik.
```

---

### Exempel 2: Fullständig version

```markdown
# Dialogsyntes: AI-chatbot för kundtjänst

**Kopplat Arbetsresultat:** Arkitektur_Routing_v1.0.pdf

## BL-001: Val av AI-modell och routinglogik

**Status:** Aktivt  
**Datum:** 2026-08-15  
**Beslutstyp:** Teknik  
**Taggar:** AI, modellval, prestanda, kostnad

### Bakgrund
En AI-modell behövdes för att hantera svenska kundfrågor om returer. Kraven omfattade noggrannhet, svarstid och kostnad.

### Observationer och underlag
- Modell A gav lägre kostnad och kortare svarstid men lägre noggrannhet.
- Modell B gav högre noggrannhet men högre kostnad och längre svarstid.
- Lokala modeller krävde mer infrastruktur och anpassning.

### Beslutskriterier
- noggrannhet, kostnad, svarstid, stöd för svenska.

### Alternativ som övervägdes

#### Alternativ A: Primär kostnadseffektiv modell med reservmodell
- **Fördelar:** Lägre genomsnittlig kostnad och kort svarstid.
- **Nackdelar och risker:** Kräver logik för att identifiera komplexa frågor.

#### Alternativ B: En mer kapabel modell för alla frågor
- **Fördelar:** Enklare teknisk lösning och högre genomsnittlig noggrannhet.
- **Nackdelar och risker:** Högre kostnad och längre svarstid.

### Beslut
Använd en kostnadseffektiv modell som primär modell och en mer kapabel modell som reserv för komplexa frågor (implementeras enligt specifikationen i Arkitektur_Routing_v1.0.pdf).

### Motivering
Lösningen bedömdes ge bäst balans mellan kostnad, prestanda och språkstöd, under förutsättning att reservlogiken fungerar tillförlitligt.

### Återanvändbar lärdom
Val av AI-modell behöver inte vara ett binärt val mellan kvalitet och kostnad. En kombination av modeller kan vara lämplig när uppgifterna varierar i komplexitet, men nyttan beror på att klassificering och reservlogik kan valideras.

### Antaganden
- A-001: Den primära modellen klarar merparten av frågorna tillräckligt väl.
- A-002: Komplexa frågor kan identifieras och skickas vidare till reservmodellen.

### Konsekvenser
- **Positiva:** Lägre kostnader och kortare svarstid för de flesta frågor.
- **Negativa:** Ökad teknisk komplexitet.
- **Risker:** Felklassificering kan påverka kundupplevelsen.

### Beroenden
- Tillgång till båda modellerna.
- En fungerande router-komponent för osäkra frågor.

### Källunderlag
- Testdialoger och kravdokument.
```

---

## 5. Vanliga frågor & Problemlösning

### Varför blev svaret i Chatt 2 svällande och osammanhängande?
Detta beror nästan alltid på **"Forminflation"** som uppstår när AI-agenten saknar det faktiska Arbetsresultatet. Om AI:n bara får beslutstexten utan det konkreta utkastet/koden måste den gissa sig till detaljnivån.
- **Lösning:** Ladda upp *både* Arbetsresultat och Dialogsyntes i Chatt 2 — och använd Inläsningsprompten, som innehåller ett explicit stringenskrav.

### Vad är skillnaden mellan beslut, förslag, antagande och lärdom?
- **Beslut:** Ett val som har gjorts och gäller.
- **Förslag:** En idé som diskuterats men inte spikats.
- **Antagande:** En obekräftad hypotes som beslutet vilar på.
- **Återanvändbar lärdom:** En generell princip, ett mönster eller en varning som kan tillämpas även i helt andra sammanhang.

### Vad är skillnaden mellan klassificering och status?
**Klassificeringen** beskriver vad posten *är* (beslut, förslag, antagande, avvisat alternativ, öppen fråga eller lärdom). **Statusen** beskriver ett besluts *livscykel* (föreslaget, aktivt, ersatt, avvisat eller pausat). Ett förslag kan alltså inte ha statusen `Aktivt` — det är bara beslut som har livscykelstatus.

### Måste varje beslut ha en återanvändbar lärdom?
Nej. Vissa beslut är helt specifika för stunden. Skriv då **Ingen återanvändbar lärdom identifierad**.

### Får jag klistra in text från källdokumenten i loggen?
Nej, i princip inte. **Referera, återskapa inte.** Klistrar du in längre textutdrag skapas en dubblett som kan bli inaktuell när källan uppdateras — och då vet ingen vilken som gäller. Hänvisa i stället med filnamn och version under Källunderlag (t.ex. "Kravspec v1.2, avsnitt 4.2").
- **Undantag:** Det som krävs för att beslutet ska kunna förstås och omprövas utan källan ska stå kvar i posten. Tumregel: *så mycket att beslutet kan förstås, så lite att det inte blir en kopia.*

### Vad händer med känsliga uppgifter?
De hör aldrig hemma i en Dialogsyntes. Loggen är designad för att resa mellan chattar, agenter och personer — därför ska den inte innehålla lösenord, API-nycklar, åtkomsttoken eller personuppgifter. Ta bort sådant innan loggen sparas; behovet av känslig data i dialogen hanteras i dialogen, inte i minnet.

### Varför står det "Ej dokumenterat" som beslutsdatum?
Beslut i dialoger fattas sällan i ett exakt ögonblick — de mognar ofta över flera meddelanden. Ett gissat exakt datum ger falsk precision och falsk auktoritet; "Ej dokumenterat" är ärligare. Därför gäller:
- Ange exakt dag endast om den framgår av dialogen.
- Annars räcker månadsprecision (ÅÅÅÅ-MM) — agenten kan ofta utläsa månaden.
- Dokumentets *Senast uppdaterad* (i stommen) är alltid exakt och är det primära datumet.
- Kronologin framgår ofta bättre av kedjningen (ersätter/ersätts av) än av datum.

*Tips för bättre precision — helt frivilligt:* skriv dagens datum i chatten när en session börjar, och kolla plattformens tidsstämplar när syntesen skapas. Ingen av delarna är ett krav.

### Vad händer om ett beslut ändras i en framtida chatt?
1. Ändra inte den ursprungliga texten i historiken.
2. Skapa en ny beslutspost (t.ex. `BL-005`).
3. Markera det gamla beslutet som `Ersatt` och länk till det nya via **Ersätts av / Ersätter**.

---

## 6. Tips för avancerade användare

### Använd taggar för bättre sökbarhet
Använd konsekventa taggar (t.ex. `taggar: AI, arkitektur, kostnad`) i header-sektionen för att enkelt kunna filtrera beslut i större repositories.

### Sammanställ ett centralt Lärdomsregister
När flera projekt genererar liknande lärdomar samlas dessa i ett gemensamt register.

| Lärdom-ID | Återanvändbar lärdom | Ursprungliga beslut | Relevanta sammanhang | Status |
|---|---|---|---|---|
| L-001 | [Lärdom] | [BL-001, BL-003] | [Projekt/Sammanhang] | [Etablerad / Preliminär] |

Återkommande lärdomar kan senare utvecklas till:
- Företagsspecifika System Prompts
- Metodregler och kvalitetskriterier
- `.cursorrules`-filer eller instruktioner till kodagenter

---

## 7. Checklistor

### Checklista för granskning (AI föreslår, människa godkänner)
- [ ] Beslutstexten är begriplig helt utan tillgång till ursprungschatten.
- [ ] Det framgår tydligt vilket Arbetsresultat besluten är kopplade till.
- [ ] Statusen är korrekt angiven (enligt mallens statusvärden).
- [ ] Antaganden och osäkerheter är separerade från beslutet.
- [ ] Återanvändbara lärdomar upprepar inte bara beslutet, utan ger en generell princip.
- [ ] Källunderlag hänvisas med version eller identifierare — inte kopieras.
- [ ] Loggen innehåller inga lösenord, API-nycklar eller personuppgifter.

---

## 8. Mallar & Prompter

### Standardprompt 1: Skapa/Uppdatera Dialogsyntes (Chatt 1)
> *"Analysera vår dialog och skapa en Dialogsyntes utifrån Mallen för Dialogsyntes (v1.0). Identifiera betydelsefulla vägval och koppla dem tydligt till vårt framtagna arbetsresultat. Skilj strikt mellan beslut, förslag, antaganden, avvisade alternativ, öppna frågor och återanvändbara lärdomar, och ge varje beslut en status (Föreslaget, Aktivt, Ersatt, Avvisat eller Pausat). Hänvisa till underlag med filnamn och version i stället för att kopiera in dem, och ta inte med lösenord, API-nycklar eller personuppgifter. Gissa inte sådant som inte framgår. Formulera varje beslut så att det kan förstås utan tillgång till originaldialogen."*

### Inläsningsprompten (Chatt 2) — se separat fil
Prompten för att läsa in kontexten i en ny chatt finns som **egen, kanonisk fil i paketet**: `dialogsyntes-prompt-svenska-v1-0.md` (version 1.0). Klistra in den i Chatt 2 tillsammans med dagens mål, samtidigt som Arbetsresultatet och Dialogsyntesen laddas upp.

Texten visas inte här — enligt modellens egen regel: **referera, återskapa inte**. Följ alltid filen om den uppdateras; den är källan.

---

## 9. Sammanfattning: Nyckelprinciper

1. **Dokumentera vägval, inte hela dialogen.**
2. **Låt alltid Arbetsresultatet och Dialogsyntesen resa tillsammans.**
3. **Håll beslutsposten självständig och begriplig utan chattloggen.**
4. **Skilj beslut från förslag, antaganden och öppna frågor — och klassificering från status.**
5. **Låt AI föreslå och en människa granska.**
6. **Skilj återanvändbar lärdom från det specifika beslutet.**
7. **Generalisera lärdomar försiktigt.**
8. **Referera, återskapa inte — hänvisa till källunderlag med version.**
9. **Lämna känsliga uppgifter utanför loggen.**

---

## 10. Nästa steg

- Välj en avslutad dialog och skapa din första Dialogsyntes.
- Testa att starta Chatt 2 genom att ladda upp *både* ditt arbetsresultat och syntesen, och klistra in Inläsningsprompten.
- Utvärdera om den nya AI-agenten behåller stringensen och respekterar dina beslut.

**Lycka till!**