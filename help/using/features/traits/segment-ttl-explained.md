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
source-wordcount: '378'
ht-degree: 0%

---

# Uitleg voor segment- en trainingstijd tot live {#segment-time-to-live-explained}

Hoe het [!UICONTROL time-to-live] ([!DNL TTL]) interval beïnvloedt segmentlidmaatschap.

<!-- segment-ttl-explained.xml -->

## Tijd om te leven

[!DNL TTL] definieert hoe lang een sitebezoeker in een segment blijft na de laatste kwalificatiegebeurtenis. [!DNL TTL] wordt ingesteld op kenmerken en niet op segmenten. Bezoekers vallen uit een segment als ze niet in aanmerking komen voor een eigenschap voor het einde van het [!DNL TTL] -interval. De standaardwaarde [!DNL TTL] voor nieuwe kenmerken is 120 dagen. Wanneer ingesteld op 0 dagen, verloopt de eigenschap nooit. [ plaats de waarde van TTL ](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval) wanneer u creeert of een spoor in de [!UICONTROL Advanced Options] sectie van de interface van de trekkerverwezenlijking uitgeeft.

### 1 dag TTL toegelicht

Wanneer het plaatsen van [!DNL TTL] aan 1 dag, begint de tijdopnemer van TTL de volgende dag na het merkrealisatie, niet het tellen van de uren die op de dag van de eigenlijke realisatie resteren.

Audience Manager berekent de [!DNL TTL] vervaldatum voor kenmerken met 1 dag [!DNL TTL] op basis van de volgende formule:

`24 + (24 - Hour of the day the trait was realized, in UTC)`

* **Voorbeeld 1**: Een spoor realiseerde zich bij 1 :00 [!DNL UTC], met een 1 dag [!DNL TTL]. [!DNL TTL] verloopt 24 + 24 - 1 = 47 uur later.
* **Voorbeeld 2**: Een eigenschap realiseerde zich bij 23 :00 [!DNL UTC], met een 1 dag [!DNL TTL]. [!DNL TTL] verloopt 24 + 24 - 23 = 25 uur later.

## [!DNL TTL] en wegvallen van een segment

Een gebruiker valt buiten een segment als hij of zij niet in aanmerking komt voor een van zijn kenmerken binnen het interval [!DNL TTL] . Als u bijvoorbeeld een segment met één kenmerk hebt met een periode van 30 dagen [!DNL TTL] , zal de gebruiker dat segment verlaten als hij of zij de komende 30 dagen niet meer voor de eigenschap in aanmerking komt.

![](assets/ttl-explained.png)

## [!DNL TTL] en Segment vernieuwen

De [!DNL TTL] wordt opnieuw ingesteld, en de gebruiker blijft in een segment, als deze binnen de [!DNL TTL] -periode in aanmerking komen voor de eigenschap van dat segment. Omdat de meeste segmenten meerdere kenmerken met hun eigen [!DNL TTL] -intervallen bevatten, kan een gebruiker in een segment blijven en het [!DNL TTL] -interval opnieuw instellen, zolang ze in aanmerking blijven komen voor alle kenmerken die aan het segment zijn gekoppeld.

Stel dat u Segment 1 hebt dat bestaat uit Trait A (30 dagen [!DNL TTL]) en Trait B (15 dagen [!DNL TTL] ). Ervan uitgaande dat een bezoeker slechts eenmaal voor elk kenmerk in aanmerking komt, worden in de onderstaande afbeelding het vernieuwingsproces van [!DNL TTL] en de totale duur binnen het segment beschreven.

![](assets/ttl-renewal.png)

## [!DNL Audience Manager] TTLs is Onafhankelijk van de Montages van TTL van de derde

Herinner me, [!DNL TTL] op uw [!DNL Audience Manager] pixel werkt onafhankelijk van [!DNL TTL] die op andere pixel wordt geplaatst door derden wordt gebruikt ([!DNL DSP] s, en netwerken, enz.).

>[!MORELIKETHIS]
>
>* [ plaats een Interval van de Vervalsing van het Beetje ](../../features/traits/create-onboarded-rule-based-traits.md#set-expiration-interval)
