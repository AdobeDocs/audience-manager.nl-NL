---
description: Dit rapport retourneert een lijst met kenmerken die ten minste 10.000 keer zijn gerealiseerd in de 30 dagen voorafgaand aan de geselecteerde datum of data en die een standaardafwijking van 1,7 of meer hebben in dezelfde tijdsinterval. Het rapport helpt u evalueren hoe het aantal indrukken van unieke gebruikers in een kenmerk in de loop der tijd fluctueert.
seo-description: This report returns a list of traits that have been realized at least 10,000 times in the 30 days prior to the selected date(s) and have a standard deviation greater or equal to 1.7 in either direction over the same time interval. The report helps you evaluate how the number of impressions from unique users in a trait fluctuate over time.
seo-title: Daily Trait Variation Report
solution: Audience Manager
title: Dagelijks verslag over de variatie van het reisdoel
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: Audience Optimization Reports
exl-id: c84a3f13-70fb-4167-b05b-de5cf518ec03
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 0%

---

# Dagelijks verslag over de variatie van het reisdoel {#daily-trait-variation-report}

Dit rapport retourneert een lijst met kenmerken die ten minste 10.000 keer zijn gerealiseerd in de 30 dagen voorafgaand aan de geselecteerde datum of data en die een standaardafwijking van 1,7 of meer hebben in dezelfde tijdsinterval. Het rapport helpt u evalueren hoe het aantal indrukken van unieke gebruikers in een kenmerk in de loop der tijd fluctueert.

>[!NOTE]
>
>In het Daily Trait Variation Report in Audience Manager worden de RBAC-beginselen in acht genomen. U kunt slechts sporen van gegevensbronnen zien die u toegang tot hebt gebaseerd op de [ RBAC Gebruikersgroep ](/help/using/features/administration/administration-overview.md) die u tot behoort.

Standaardafwijking meet de mate van variatie of spreiding ten opzichte van het gemiddelde (of de gemiddelde/verwachte waarde). Een lage standaardafwijking geeft aan dat de gegevenspunten zeer dicht bij het gemiddelde liggen. Een hoge standaardafwijking geeft aan dat de gegevenspunten worden uitgespreid over een groot waardebereik.

![](assets/daily_trait_variation.png)

Gebruik de lijst [!UICONTROL Date] om een of meer datums voor uw rapport te selecteren. Onder aan de lijst wordt een kleurenstreepjesdiagram weergegeven dat een visuele weergave biedt van het bereik van de standaardafwijking voor alle kenmerken op alle geselecteerde datums. De zwarte verticale lijn geeft het gemiddelde aan.

De middelste kolom bevat een lijst met kenmerken die worden aangegeven door [!UICONTROL Trait ID] en [!UICONTROL Trait Name] . Klik op een kenmerk om een pop-updialoogvenster te openen waarin u de volgende opties kunt selecteren:

* **houdt slechts:** verwijdert alle andere eigenschappen uit het rapport en toont gegevens voor dit slechts bezit.
* **uitsluiten:** verwijdert deze eigenschap uit het rapport en toont gegevens voor alle andere eigenschappen. U kunt meerdere kenmerken uitsluiten.
* **Gegevens van de Mening:** laat u gegevens voor die rij tonen. U kunt ook alle rijen als een tekstbestand downloaden.

In de kolom [!UICONTROL Standard Deviation] worden staafdiagrammen met kleurcodes weergegeven die de standaardafwijking voor elk kenmerk gedurende het geselecteerde interval weergeven. Rode balken geven kenmerken aan met een negatieve standaardafwijking (gegevenspunten zijn meestal onder het gemiddelde). Groene balken geven kenmerken aan met een positieve standaardafwijking (gegevenspunten liggen meestal boven het gemiddelde). Plaats de muisaanwijzer op een willekeurige balk om een pop-upvenster weer te geven met meer informatie en opties voor het behouden of uitsluiten van de betreffende status en voor het weergeven van meer informatie.

De vertoningen van pictogrammen bij de bodem van het rapport dat u gegevens in diverse formaten laat uitvoeren, om het even welke veranderingen terugkeren u aan het rapport (zoals het uitsluiten van eigenschappen) had kunnen aanbrengen, toelaten of onbruikbaar maken automatische updates, en verfrist de gegevens van het rapport. Zie [ Verklaarde de Pictogrammen en Hulpmiddelen van het Rapport ](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Gevallen gebruiken {#use-cases}

**Voorbeeld #1**: dit rapport kan zeer nuttig in situaties zijn waar u eigenschappen met een hoog seizoonaliteitsniveau hebt. Stel dat uw online winkel seizoensgebonden promoties van verschillende typen en prijzen test. De volgende kenmerken zijn gedefinieerd in [!DNL Audience Manager] :

* `productPage == "December Promotion"`
* `price > "500"`

Stel dat u het [!UICONTROL Daily Trait Variation] -rapport uitvoert op 20 december en dat u de afgelopen 30 dagen een sterke positieve afwijking ziet van de bovengenoemde kenmerken. Dit kan erop wijzen dat uw bezoekers op zoek zijn naar de producten die in uw seizoensbevorderende actie worden vermeld. Om van deze trend te profiteren, kunt u dan meer inspanning investeren in het richten van creatieve mensen voor die specifieke productcategorie op bezoekers die in hen geïnteresseerd zijn.

**Voorbeeld #2**: dit rapport kan u helpen het richten anomalieën met betrekking tot het etiketteren van kwesties of het trekken misconfiguraties identificeren. Stel dat u de volgende eigenschap hebt gedefinieerd op basis van de categorieën van uw online winkel:

* `productPage == "smartphones"`

Als gevolg van een herconfiguratie van je winkel, splitst u de smartphones pagina in meerdere pagina&#39;s, op basis van merknamen. U bent echter vergeten de kenmerken bij te werken die zijn gedefinieerd in [!DNL Audience Manager] .

Een maand later voert u het [!UICONTROL Daily Trait Variation] -rapport uit en ziet u een grote negatieve afwijking van de `productPage == "smartphones"` -eigenschap, hoewel het bezoekersaantal is gestegen, volgens de analyse van uw site. Op basis van deze informatie realiseert u zich dat u de kenmerken in [!DNL Audience Manager] voor uw nieuwe productpagina&#39;s niet hebt bijgewerkt, zodat u weet dat u de volgende eigenschappen moet creëren:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Zodra u dit doet, zult u uw publiek zien kwalificeren voor de pas gecreëerde eigenschappen.
