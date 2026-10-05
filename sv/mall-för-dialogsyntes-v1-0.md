# Mall för Dialogsyntes

**Version:** 1.0 — ingår i Dialogsyntes-paketet v1.0
**Kompatibel med:** Användarguide v1.0, Inläsningsprompt v1.0
**Huvudsaklig målgrupp:** Personer och AI-agenter som behöver bevara och återanvända viktiga beslut, resonemang och lärdomar från projekt, arbetsprocesser och utforskande dialoger.

---

## 1. Syfte

En Dialogsyntes bevarar de **viktigaste besluten, resonemangen och lärdomarna** från en dialog, ett projekt eller en arbetsprocess.

**Varför?**
När en session stängs eller en ny person/AI-agent tar över, går ofta **varför** och **hur** förlorat. Dialogsyntesen löser detta genom att dokumentera:
- Vilket problem som lösts
- Vilka alternativ som övervägdes (och varför vissa valdes bort)
- Vilka antaganden och osäkerheter som återstår
- Vilka lärdomar som kan återanvändas i framtida arbete

**Resultat:**
Nästa person eller AI-agent kan **omedelbart förstå sammanhanget** och bygga vidare på tidigare arbete — utan att börja om från noll och utan den svällande, generiska "forminflation" som lätt uppstår när en ny chatt saknar både substans och metakontext.

---

## 2. Ramverk: Kontext-stacken

Dialogsyntesen är en av fyra komponenter i ett **hållbart AI-samarbete**:

| Komponent             | Roll          | Beskrivning                                                       | Exempel på fil                          |
|-----------------------|---------------|-------------------------------------------------------------------|------------------------------------------|
| **Arbetsresultatet**  | Substansen    | Den färdiga produkten, koden, rapporten eller specifikationen.     | `Arkitektur_Routing_v1.0.pdf`            |
| **Dialogsyntesen**    | Kontexten     | Varför resultatet ser ut som det gör.                             | `Dialogsyntes_v1.md`                     |
| **Inläsningsprompten**| Styrningen    | Hur historiken aktiveras i en ny chatt.                           | `dialogsyntes-prompt-svenska-v1-0.md`     |
| **Mallen & Guiden**   | Ramverket     | Hur syntesen skapas, tolkas och förvaltas.                        | Mallen + Användarguiden                  |

**Substansen och metakontexten måste alltid resa tillsammans.** Skickar du bara Dialogsyntesen tvingas agenten gissa detaljnivå och upplösning — det är då svaren sväller.

---

## 3. Två dimensioner: Klassificering och Status

### 3.1 Klassificering — vad posten *är*

| Klass                     | Definition                                                             |
|---------------------------|------------------------------------------------------------------------|
| **Beslut**                | Fattat och gällande vägval.                                            |
| **Förslag**               | Idé som diskuterats men ej beslutat.                                   |
| **Antagande**             | Obekräftad hypotes som beslutet vilar på.                              |
| **Avvisat alternativ**    | Övervägd men bortvald väg (dokumenteras med skäl).                     |
| **Öppen fråga**           | Viktig osäkerhet som saknar svar.                                      |
| **Återanvändbar lärdom**  | Generell princip, mönster eller varning med giltighet utöver beslutet. |

### 3.2 Status — beslutets livscykel (endast för klassen Beslut)

| Status         | Definition                                                                                 |
|----------------|--------------------------------------------------------------------------------------------|
| **Föreslaget** | Rekommenderat vägval som ännu inte är beslutat.                                             |
| **Aktivt**     | Beslutet gäller och används.                                                                |
| **Ersatt**     | Beslutet har ersatts av ett senare beslut. Kedjas med *Ersätts av*.                         |
| **Avvisat**    | Vägvalet har övervägts men aktivt valts bort. Behålls för att inte samma analys ska göras om. |
| **Pausat**     | Beslutet eller genomförandet har tillfälligt lagts åt sidan.                                |

### 3.3 Kedjning och ID:n

- Stabila ID:n per post: `BL-NNN` (beslut), `A-NNN` (antagande), `F-NNN` (öppen fråga), `L-NNN` (lärdom).
- När ett beslut ändras: skapa en **ny post**, markera den gamla som `Ersatt` och länka dem via **Ersätter / Ersätts av**.
- Ändra aldrig en äldre beslutspost i efterhand — historiken är en del av kunskapen.

---

## 4. Instruktion till AI-agenten

När du ombeds skapa eller uppdatera en Dialogsyntes:

**1. Identifiera reella vägval.** Fokusera på beslut som påverkar mål eller avgränsning, modell/struktur/metod, definitioner och begrepp, val mellan handlingsalternativ, prioriteringar, ansvar eller ägarskap, mätning och framgångskriterier, förvaltning/dokumentation/återanvändning samt framtida arbete eller beroenden.

*Dokumentera beslutet om minst ett påstående stämmer:*
- Beslutet förändrar arbetets mål, omfattning eller avgränsning.
- Beslutet väljer mellan verkliga alternativ.
- Beslutet påverkar metod, struktur, ansvar eller mätning.
- Beslutet leder till följder som andra behöver känna till.
- Beslutet kan behöva försvaras eller omprövas senare.
- Beslutet bygger på antaganden som behöver valideras.
- En framtida deltagare riskerar att göra om samma analys utan loggen.

*Dokumentera normalt inte:* enstaka formuleringar, typografiska ändringar, mindre korrektur, idéer som bara nämndes i förbigående, förslag som aldrig diskuterades vidare, eller operativa detaljer som lätt utläsas ur slutprodukten.

**2. Länka till arbetsresultatet.** Koppla varje beslut till det **konkreta material** (kod, användarresa, dokument) som skapades i dialogen.

**3. Klassificera med precision.** Ge varje post en klass (se 3.1) och varje beslut dessutom en status (se 3.2). Blanda inte ihop klassificering och status — klassen *Avvisat alternativ* dokumenteras under postens alternativ, medan statusen *Avvisat* gäller ett beslut som aktivt valts bort.

**4. Referera, återskapa inte.** Dokumentera beslutet, motiveringen och konsekvenserna i posten. Kopiera inte längre sammanhängande innehåll från underliggande dokument (specifikationer, principer, definitioner, dialoger) — hänvisa i stället under **Källunderlag** med identifierare, version eller länk. Undantag: det som krävs för att beslutet ska kunna förstås och omprövas utan tillgång till källunderlaget ska stå kvar i posten. Tumregel: *så mycket att beslutet kan förstås, så lite att det inte blir en kopia.*

**5. Sanera känslig data.** Ta inte med lösenord, API-nycklar, åtkomsttoken eller personuppgifter i loggen. Dialogsyntesen är till för att resa mellan chattar, agenter och personer.

**6. Bevara stringens.** Gissa inte. Om information saknas, markera det tydligt som en **öppen fråga** eller ett **antagande**. Saknade uppgifter markeras som okända — de fylls aldrig in med gissningar. Det gäller även beslutsdatum: ange exakt dag endast om den framgår av dialogen, i annat fall månad (ÅÅÅÅ-MM), i sista hand **Ej dokumenterat**. Dokumentets *Senast uppdaterad* är alltid exakt och är det primära datumet. Använd konkret språk och undvik spekulationer.

---

## 5. Dokumentets stomme

Varje Dialogsyntes inleds med:

```markdown
# Dialogsyntes: [Projekt / dialog / process]

**Kopplat Arbetsresultat:** [filnamn + version]
**Omfattning:** [vilket arbete, vilken tidsperiod eller vilken dialog]
**Syfte med arbetet:** [övergripande problem eller mål]
**Senast uppdaterad:** [ÅÅÅÅ-MM-DD]
**Ansvarig:** [namn/roll — eller lämnas tom]
**Källunderlag:** [dialog-ID:n, dokument, möten — med version där sådan finns]
```

Följt av en **beslutsöversikt**:

| Beslut-ID | Titel | Status | Datum | Ersätter / relaterar till |
|-----------|-------|--------|-------|----------------------------|
| BL-001    | [titel] | [status] | [datum] | [ID eller —] |

---

## 6. Snabbversion — beslutspost

Används för enklare vägval som ändå behöver kunna förstås eller återanvändas senare.

```markdown
## BL-NNN: [Kort titel]

**Status:** [Föreslaget / Aktivt / Ersatt / Avvisat / Pausat]
**Datum:** [ÅÅÅÅ-MM-DD, ÅÅÅÅ-MM eller Ej dokumenterat]
**Beslutstyp:** [Strategi / Metod / Avgränsning / Teknik / Design / Data / Innehåll / Organisation / Förvaltning — valfritt]
**Taggar:** [valfritt]

### Bakgrund
[Vilken fråga eller vilket problem behandlades?]

### Beslut
[Vad valdes?]

### Motivering
[Varför valdes detta?]

### Återanvändbar lärdom
[Generell princip — eller "Ingen återanvändbar lärdom identifierad"]

### Antaganden och osäkerheter
- A-NNN: [antagande]. Valideras genom [metod].

### Konsekvenser och nästa steg
[Vilka följder får beslutet? Vad görs härnäst?]

### Källunderlag
- [Dialog-ID, dokument + version, länk]
```

---

## 7. Fullständig version — beslutspost

Används när beslutet påverkar modell, metod eller strategi, kräver dokumenterade alternativ, kan behöva omprövas, får konsekvenser för flera personer, processer eller system, eller bygger på betydelsefulla antaganden.

```markdown
## BL-NNN: [Kort och tydlig titel]

**Status / Datum / Beslutstyp / Taggar:** [som i snabbversionen]

### Bakgrund
[Problemet, behovet eller frågan som ledde fram till beslutet.]

### Observationer och underlag
[Verifierade fakta, erfarenhetsbaserade observationer, exempel — skilj dem åt. Ange om underlaget är otillräckligt.]

### Beslutskriterier
[Vilka kriterier användes för att bedöma alternativen? Exempel: användarvärde, verksamhetsvärde, risk, enkelhet, genomförbarhet, kostnad, mätbarhet, förvaltningsbarhet.]

### Alternativ som övervägdes

#### Alternativ A: [Namn]
- **Fördelar:** [...]
- **Nackdelar och risker:** [...]

#### Alternativ B: [Namn]
- **Fördelar:** [...]
- **Nackdelar och risker:** [...]

[Skapa inga alternativ som inte faktiskt diskuterades.]

### Beslut
[Kort, konkret och självständigt — begripligt utan originaldialogen.]

### Motivering
[Varför det valda alternativet bedömdes bäst — och varför de viktigaste alternativen valdes bort.]

### Återanvändbar lärdom
[Princip, mönster eller varning — eller "Ingen återanvändbar lärdom identifierad"]

### Antaganden
- A-NNN: [antagande]. Valideras genom [metod].

### Konsekvenser
- **Positiva:** [...]
- **Negativa eller kostnader:** [...]
- **Risker:** [...]

### Beroenden
[Beslut, system, personer, data eller externa faktorer — eller "Inga kända beroenden".]

### Källunderlag
- [Dialog-ID, dokument + version, länk]

### Validering och uppföljning
- **Indikator:** [vad visar att beslutet fungerar?]
- **Datakälla:** [hur följs det upp? Exempel: användartest, sakkunniggranskning, pilot, dataanalys, dokumenterad erfarenhet]
- **Ansvarig:** [om känd] — **Tidpunkt:** [om bestämd]

### Relaterade beslut
[BL-NNN — eller "Ej tillämpligt"]

**Ersätter:** [BL-NNN eller Ej tillämpligt]
**Ersätts av:** [BL-NNN eller Ej tillämpligt]
```

---

## 8. Sammanställningar

I slutet av dokumentet samlas återkommande information:

**Antaganden**

| ID    | Antagande | Påverkade beslut | Status       | Validering |
|-------|-----------|------------------|--------------|------------|
| A-001 | [...]     | [BL-001]         | Ej validerat | [metod]    |

**Öppna frågor**

| ID    | Öppen fråga | Varför viktig | Berörda beslut | Nästa steg |
|-------|-------------|----------------|----------------|------------|
| F-001 | [...]       | [...]          | [BL-001]       | [åtgärd]   |

**Återanvändbara lärdomar**

| ID    | Lärdom | Ursprungliga beslut | Relevanta sammanhang |
|-------|--------|---------------------|----------------------|
| L-001 | [...]  | [BL-001]            | [...]                |

Återkommande lärdomar samlas vid behov i ett **centralt Lärdomsregister** (se Användarguiden, avsnitt 6).

---

## 9. Förvaltningsprinciper

1. Behåll historiken även när ett beslut ersätts.
2. Ändra aldrig en äldre beslutspost i efterhand — skapa en ny post och kedja dem.
3. Använd stabila ID:n och länka beslut till relevanta dokument, modeller och exempel.
4. Uppdatera antaganden och öppna frågor när de valideras eller besvaras.
5. Förvara Dialogsyntesen tillsammans med sitt Arbetsresultat.
6. **AI föreslår — en människa granskar och godkänner.**

---

## 10. Kvalitetskontroll (före leverans)

- [ ] Är det tydligt vad som faktiskt beslutades?
- [ ] Har förslag, beslut, antaganden och öppna frågor hållits isär?
- [ ] Har osäkerheter och antaganden bevarats?
- [ ] Har alternativen dokumenterats neutralt — utan påhittade alternativ?
- [ ] Har saknade uppgifter markerats som okända i stället för att fyllas med gissningar?
- [ ] Är varje beslutstext begriplig utan originaldialogen?
- [ ] Hänvisas källunderlag med version eller identifierare i stället för att kopieras?
- [ ] Innehåller loggen inga lösenord, API-nycklar eller personuppgifter?
- [ ] Är detaljnivån tillräcklig för framtida omprövning — men kortare än dialogen?

---

## 11. Exempel på klassificering

### Beslut
- **Beslut:** "Vi använder Python 3.10 för projektet."
  **Motivering:** Kompatibilitet med befintliga bibliotek och teamets expertis.
  **Källunderlag:** Kravspec v1.2; dialog #12.
  **Status:** Aktivt

### Förslag
- **Förslag:** "Kan vi använda Rust istället för Python för prestandakritiska delar?"
  *(Förslag har ingen livscykelstatus. Lyfter frågan kvar efter dialogen dokumenteras den som öppen fråga.)*

### Antagande
- **Antagande (A-001):** "Användarna kommer att föredra en mobilapp framför en webbapp."
  **Validering:** Kräver användartestning.

### Avvisat alternativ
- **Alternativ:** "Rust för prestandakritiska delar."
  **Skäl:** Kodbasen är Python; vinsten bedömdes mindre än underhållskostnaden.

### Öppen fråga
- **F-001:** "Vilka delar av flödet är faktiskt prestandakritiska?"
  **Nästa steg:** Profilering innan eventuell optimering.

### Återanvändbar lärdom
- **Lärdom (L-001):** "Involvera användare tidigt i designprocessen för att undvika dyra omdesigns senare."
  **Typ:** Generell princip.

Kompletta exempel på snabb- och fullständiga beslutsposter finns i Användarguiden, avsnitt 4.

---

## 12. Maskinläsbar sammanfattning

```yaml
model:
  name: Dialogsyntes
  version: "1.0"
  package_version: "1.0"
  purpose: "Bevara och återanvända kunskap från dialoger, projekt och arbetsprocesser."
  components:
    - Arbetsresultatet   # Substansen
    - Dialogsyntesen      # Kontexten
    - Inläsningsprompten  # Styrningen
    - Mallen & Guiden     # Ramverket
  classifications: [Beslut, Förslag, Antagande, Avvisat alternativ, Öppen fråga, Återanvändbar lärdom]
  decision_statuses: [Föreslaget, Aktivt, Ersatt, Avvisat, Pausat]
  post_levels: [Snabb, Fullständig]
  rules:
    - "Referera, återskapa inte (hänvisa med version i stället för att kopiera)."
    - "Ingen känslig data (lösenord, API-nycklar, personuppgifter)."
    - "AI föreslår, människa granskar."
    - "Kedja ersatta beslut; ändra aldrig äldre poster."
    - "Saknad information markeras som okänd — fylls aldrig in med gissningar."
    - "Beslutsdatum: exakt dag om känd, annars månad (ÅÅÅÅ-MM), annars Ej dokumenterat."
```