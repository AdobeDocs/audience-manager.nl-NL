---
description: Hoe het tijd-aan-levende (TTL) interval van de eigenschap segmentlidmaatschap beïnvloedt.
seo-description: How trait time-to-live (TTL) interval affects segment membership.
seo-title: Segment and Trait Time to Live Explained
solution: Audience Manager
title: Tijd van segment voor live uitleg
uuid: 5b2c6911-50b9-4b68-9dd4-21128d112eab
feature: Traits
exl-id: 2f019071-f829-4336-b2cf-26ec1f18fc91
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 3%

---

# De levensduur van segmenten en eigenschappen {#segment-time-to-live-explained}

Hoe traditioneel [!UICONTROL time-to-live] ([!DNL TTL])-interval beïnvloedt segmentlidmaatschap.

<!-- segment-ttl-explained.xml -->

## Tijd om te leven

[!DNL TTL] Hiermee bepaalt u hoe lang een sitebezoeker in een segment blijft na de laatste kwalificatiegebeurtenis. [!DNL TTL] wordt ingesteld op eigenschappen en niet op segmenten. Bezoekers vallen buiten een segment als zij niet vóór het einde van de [!DNL TTL] interval. De standaardwaarde [!DNL TTL] voor nieuwe kenmerken is dit 120 dagen . Wanneer ingesteld op 0 dagen, verloopt de eigenschap nooit. [De TTL-waarde instellen](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) wanneer u een kenmerk maakt of bewerkt in het dialoogvenster [!UICONTROL Advanced Options] van de interface voor het maken van de eigenschap.

### 1 dag TTL toegelicht

Wanneer u het [!DNL TTL] tot 1 dag, begint de tijdopnemer van TTL de volgende dag na het merkrealisatie, zonder de uren te tellen die op de dag van de eigenlijke realisatie resteren.

Audience Manager berekent [!DNL TTL] vervaldatum voor kenmerken met 1 dag [!DNL TTL] op basis van de volgende formule:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Voorbeeld 1**: Een eigenschap die om 1:00 wordt gerealiseerd [!DNL UTC], met een dag [!DNL TTL]. [!DNL TTL] verloopt 24 + 24 - 1 = 47 uur later.
* **Voorbeeld 2**: Een eigenschap die om 23:00 werd gerealiseerd [!DNL UTC], met een dag [!DNL TTL]. [!DNL TTL] verloopt 24 + 24 - 23 = 25 uur later.

## [!DNL TTL] en uit een segment vallen

Een gebruiker valt buiten een segment als hij of zij niet in aanmerking komt voor een van zijn kenmerken binnen de [!DNL TTL] interval. Bijvoorbeeld, als u een 1-treksegment met een 30 dagen hebt [!DNL TTL], zal de gebruiker uit dat segment vallen als zij niet binnen 30 dagen opnieuw voor de eigenschap in aanmerking komen.

![](assets/ttl-explained.png)

## [!DNL TTL] en Segmentverlenging

De [!DNL TTL] stelt opnieuw in, en de gebruiker blijft in een segment, als zij voor het bezit van dat segment binnen de [!DNL TTL] periode. Bovendien, omdat de meeste segmenten meerdere kenmerken met hun eigen kenmerken bevatten [!DNL TTL] intervallen, kan een gebruiker in een segment blijven en terugstellen [!DNL TTL] interval, zolang ze in aanmerking blijven komen voor alle kenmerken die aan het segment zijn gekoppeld.

Stel dat u Segment 1 hebt dat bestaat uit Trait A (30 dagen) [!DNL TTL]) en Trait B (15 dagen) [!DNL TTL]). Ervan uitgaande dat een bezoeker slechts eenmaal voor elk kenmerk in aanmerking komt, wordt in de onderstaande afbeelding het volgende lettertype weergegeven [!DNL TTL] het vernieuwingsproces en de totale duur in het segment.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTLs is Onafhankelijk van de Montages van TTL van de derde

Herinner me, [!DNL TTL] instellen op uw [!DNL Audience Manager] pixel werkt onafhankelijk van [!DNL TTL] instellen op andere pixels die door derden worden gebruikt ([!DNL DSP]s, advertentienetwerken, enz.).

>[!MORELIKETHIS]
>
>* [Een interval voor verlopen van sporen instellen](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)

