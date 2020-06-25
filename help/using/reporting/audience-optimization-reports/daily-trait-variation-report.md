---
description: Dit rapport retourneert een lijst met kenmerken die ten minste 10.000 keer zijn gerealiseerd in de 30 dagen voorafgaand aan de geselecteerde datum of data en die een standaardafwijking van 1,7 of meer hebben in dezelfde tijdsinterval. Het rapport helpt u evalueren hoe het aantal indrukken van unieke gebruikers in een kenmerk in de loop der tijd fluctueert.
seo-description: Dit rapport retourneert een lijst met kenmerken die ten minste 10.000 keer zijn gerealiseerd in de 30 dagen voorafgaand aan de geselecteerde datum of data en die een standaardafwijking van 1,7 of meer hebben in dezelfde tijdsinterval. Het rapport helpt u evalueren hoe het aantal indrukken van unieke gebruikers in een kenmerk in de loop der tijd fluctueert.
seo-title: Dagelijks verslag over de variatie van het reisdoel
solution: Audience Manager
title: Dagelijks verslag over de variatie van het reisdoel
uuid: 4e82bb17-d447-4ed1-a4fc-e15b0f1b47f0
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 0%

---


# Dagelijks verslag over de variatie van het reisdoel {#daily-trait-variation-report}

Dit rapport retourneert een lijst met kenmerken die ten minste 10.000 keer zijn gerealiseerd in de 30 dagen voorafgaand aan de geselecteerde datum of data en die een standaardafwijking van 1,7 of meer hebben in dezelfde tijdsinterval. Het rapport helpt u evalueren hoe het aantal indrukken van unieke gebruikers in een kenmerk in de loop der tijd fluctueert.

>[!NOTE]
>
>In het dagelijks verslag over de variatie van de treinen in Audience Manager worden de RBAC-beginselen in acht genomen. U kunt slechts eigenschappen van gegevensbronnen zien die u toegang hebt tot gebaseerd op de [RBAC Gebruikersgroep](/help/using/features/administration/administration-overview.md) die u tot behoort.

Standaardafwijking meet de mate van variatie of spreiding ten opzichte van het gemiddelde (of de gemiddelde/verwachte waarde). Een lage standaardafwijking geeft aan dat de gegevenspunten zeer dicht bij het gemiddelde liggen. Een hoge standaardafwijking geeft aan dat de gegevenspunten worden uitgespreid over een groot waardebereik.

![](assets/daily_trait_variation.png)

Gebruik de [!UICONTROL Date] lijst om één of meerdere data voor uw rapport te selecteren. Onder aan de lijst wordt een kleurenstreepjesdiagram weergegeven dat een visuele weergave biedt van het bereik van de standaardafwijking voor alle kenmerken op alle geselecteerde datums. De zwarte verticale lijn geeft het gemiddelde aan.

De middelste kolom bevat een lijst met kenmerken die door [!UICONTROL Trait ID] en [!UICONTROL Trait Name]worden geïdentificeerd. Klik op een kenmerk om een pop-updialoogvenster te openen waarin u de volgende opties kunt selecteren:

* **Alleen bijeenhouden:** Hiermee verwijdert u alle andere kenmerken uit het rapport en geeft u alleen gegevens voor deze eigenschap weer.
* **Uitsluiten:** Verwijdert deze eigenschap uit het rapport en toont gegevens voor alle andere eigenschappen. U kunt meerdere kenmerken uitsluiten.
* **Gegevens weergeven:** Hiermee kunt u gegevens voor die rij weergeven. U kunt ook alle rijen als een tekstbestand downloaden.

In de [!UICONTROL Standard Deviation] kolom worden staafdiagrammen met kleurcodes weergegeven die de standaardafwijking voor elk kenmerk gedurende het geselecteerde interval weergeven. Rode balken geven kenmerken aan met een negatieve standaardafwijking (gegevenspunten zijn meestal onder het gemiddelde). Groene balken geven kenmerken aan met een positieve standaardafwijking (gegevenspunten liggen meestal boven het gemiddelde). Plaats de muisaanwijzer op een willekeurige balk om een pop-upvenster weer te geven met meer informatie en opties voor het behouden of uitsluiten van de betreffende status en voor het weergeven van meer informatie.

De vertoningen van pictogrammen bij de bodem van het rapport dat u gegevens in diverse formaten laat uitvoeren, om het even welke veranderingen terugkeren u aan het rapport (zoals het uitsluiten van eigenschappen) had kunnen aanbrengen, toelaten of onbruikbaar maken automatische updates, en verfrist de gegevens van het rapport. Zie [Rapportpictogrammen en -gereedschappen](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained).

## Gevallen gebruiken {#use-cases}

**Voorbeeld 1**: dit verslag kan zeer nuttig zijn in situaties waarin u eigenschappen met een hoog seizoensgebonden niveau hebt . Stel dat uw online winkel seizoensgebonden promoties van verschillende typen en prijzen test. De volgende kenmerken zijn gedefinieerd in [!DNL Audience Manager]:

* `productPage == "December Promotion"`
* `price > "500"`

Stel dat u het [!UICONTROL Daily Trait Variation] rapport op 20 december uitvoert en u ziet dat de afgelopen 30 dagen een sterke positieve afwijking is opgetreden op de bovengenoemde kenmerken. Dit kan erop wijzen dat uw bezoekers op zoek zijn naar de producten die in uw seizoensbevorderende actie worden vermeld. Om van deze trend te profiteren, kunt u dan meer inspanning investeren in het richten van creatieve mensen voor die specifieke productcategorie op bezoekers die in hen geïnteresseerd zijn.

**Voorbeeld 2**: dit rapport kan u helpen bij het opsporen van anomalieën die te maken hebben met coderingsproblemen of verkeerde configuraties van sporen . Stel dat u de volgende eigenschap hebt gedefinieerd op basis van de categorieën van uw online winkel:

* `productPage == "smartphones"`

Als gevolg van een herconfiguratie van je winkel, splitst u de smartphones pagina in meerdere pagina&#39;s, op basis van merknamen. U bent echter vergeten de kenmerken bij te werken die zijn gedefinieerd in [!DNL Audience Manager].

Een maand later voert u het [!UICONTROL Daily Trait Variation] rapport uit en ziet u een grote negatieve afwijking van het `productPage == "smartphones"` kenmerk, hoewel uw bezoekeraantal is gestegen, volgens uw siteanalyse. Gebaseerd op deze informatie, realiseert u zich dat u niet de eigenschappen [!DNL Audience Manager] voor uw nieuwe productpagina&#39;s hebt bijgewerkt, zodat weet u dat u de volgende eigenschappen moet creëren:

* productPage == &quot;samsung&quot;
* productPage == &quot;apple&quot;
* productPage == &quot;huawei&quot;

Zodra u dit doet, zult u uw publiek zien kwalificeren voor de pas gecreëerde eigenschappen.
