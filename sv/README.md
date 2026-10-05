# Readme: Dialogsyntes-paketet

**Paketversion:** 1.0

*Detta är readme-filen för den svenska språkmappen (`/sv/`) — den auktoritativa versionen. Språkväljare, repository-struktur och kanondeklaration finns i rot-readmen: [`../README.md`](../README.md).*

## Paketets filer

| Fil                                   | Roll                                                          | Version |
|---------------------------------------|---------------------------------------------------------------|---------|
| `dialogsyntes-mall-v1-0.md`           | **Modellen** — hur syntesen byggs, klassificeras och förvaltas | 1.0     |
| `dialogsyntes_anvandarguide_v1_0.md`  | **Manualen** — för människor                                  | 1.0     |
| `dialogsyntes-prompt-svenska-v1-0.md` | **Inläsningsprompten** — klistras in i ny chatt               | 1.0     |
| `Readme.md`                           | **Paketöversikt** och läsordning                              | 1.0     |

*Dialogsyntes-loggarna (t.ex. `Dialogsyntes_v1.md`) och ett eventuellt Lärdomsregister skapas per projekt och ingår inte i paketet.*

---

## Vanliga frågor

**Vilken fil är modellen Dialogsyntes?**

> Mall för Dialogsyntes.

**Vilka filer ska en ny AI-agent få?**

*När agenten ska **fortsätta ett påbörjat arbete** (Chatt 2):*
1. Arbetsresultatet (substansen)
2. Dialogsyntes-loggarna (metakontexten)
3. Inläsningsprompten (klistras in som text i chatten)
4. Eventuellt lärdomsregister
5. Mallen — om agenten behöver tolka klasser och statusvärden på djupet, eller om osäkerhet uppstår

*När agenten ska **skapa eller uppdatera en Dialogsyntes:***
1. Mallen
2. Dialogen eller arbetsresultatet som syntesen ska byggas från

**Varför ska alltid båda dokumenten med vid fortsättning?**

> För modellen och besluten innehåller det faktiska tänkandet. Men utan Arbetsresultatet tvingas agenten gissa sig till detaljnivå och upplösning — och svaren sväller. **Substansen och metakontexten reser alltid tillsammans.**

**Vad är manualen för?**

> Manualen hjälper främst människor att använda modellen på rätt sätt.

---

## Ändringslogg

**Paket 1.0** — första publika versionen av Dialogsyntes-paketet: Mall, Användarguide, Inläsningsprompt och Readme med gemensam version.

*Intern utvecklingshistoria (beslutslogg v1 → Dialogsyntes-iterationerna fram till 1.0) förvaras separat och publiceras inte.*