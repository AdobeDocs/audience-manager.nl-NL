---
description: Begrijp de componenten van een segment van de Audience Manager, de uitdrukkingen die worden gebruikt om de criteria van de publiekskwalificatie te plaatsen, en hoe de gegevens in een gebeurtenisvraag worden overgebracht.
seo-description: Beschrijft de componenten van een segment van de Audience Manager, de uitdrukkingen die worden gebruikt om de criteria van de publiekskwalificatie te plaatsen, en hoe het gegeven in een gebeurtenisvraag wordt overgebracht.
seo-title: Signalen, eigenschappen en segmenten
solution: Audience Manager
title: Signalen, eigenschappen en segmenten
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: reference
translation-type: tm+mt
source-git-commit: 8027f278aa2b879b6cb277f44caf4b62dc75e2c3
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 3%

---


# [!UICONTROL Signals], [!UICONTROL Traits]en [!UICONTROL Segments] {#signals-traits-and-segments}

Beschrijft de componenten van een [!DNL Audience Manager] [!UICONTROL segment], de uitdrukkingen die worden gebruikt om de criteria van de publiekskwalificatie te plaatsen, en hoe het gegeven in een gebeurtenisvraag wordt overgebracht.

## Samenstelling en doel

[!DNL Audience Manager] de gegevens bestaan uit [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]en bijbehorende kwalificatieregels. De gegevenselementen en -regels worden gecombineerd om te maken [!UICONTROL segments]. [!UICONTROL Segments] sitebezoekers organiseren in verwante groepen. De volgende lijst bepaalt de drie belangrijkste componenten in een [!DNL Audience Manager] [!UICONTROL segment].

| Element | Bestaat uit | Voorbeeld |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] zijn de kleinste gegevenseenheden in [!DNL Audience Manager] en worden uitgedrukt als [sleutelwaardeparen](../reference/key-value-pairs-explained.md).<br><br><ul><li>De sleutel is een constante die een gegevensset definieert (bijvoorbeeld geslacht, kleur, prijs).</li><li>De waarde is een variabele die gerelateerd is aan de constante (bijvoorbeeld mannelijk/vrouwelijk, groen, 100).</li></ul>Vergelijkingsoperatoren voegen zich bij het sleutelwaardepaar en stellen de relatie tussen deze operatoren in. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaties van een of meer [!UICONTROL signals].<br><br> [!DNL Boolean] Met expressies en vergelijkingsoperatoren kunt u [!UICONTROL trait] kwalificatieregels maken. <br><br>Maak nauwkeurige kwalificatievereisten met combinaties van [!UICONTROL traits] en [!UICONTROL trait] groepen. | Op basis van de beschikbare code kunt u een [!UICONTROL signals]`High End Camera Browser` regel maken die wordt uitgedrukt als: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Gebruikers die een set gemeenschappelijke kenmerken delen en in aanmerking komen voor verwante kenmerken [!UICONTROL traits]. [!DNL Boolean] Met expressies kunt u samen met de eisen voor recentie/frequentie [!UICONTROL segment] kwalificatieregels maken.<br><br> Maak nauwkeurige kwalificatievereisten met combinaties van [!UICONTROL trait] en [!UICONTROL segment] regels. | Van beschikbare [!UICONTROL traits] en [!UICONTROL signals][!UICONTROL segment] , kon u een regel tot stand brengen die als wordt uitgedrukt:`(product=camera AND type=digital SLR) OR (price>1000)` |

Gebruik het onderstaande diagram om een mentale notitie te maken van de relatie tussen [!UICONTROL signals], [!UICONTROL traits]en [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Bouw[!UICONTROL Traits]en[!UICONTROL Segment]Regels met Visuele Hulpmiddelen en de Redacteurs van de Code**

Clients beheren [!UICONTROL traits] en gebruiken visuele gereedschappen en code-editors in de [!UICONTROL segments] [!DNL Audience Manager] gebruikersinterface. Met de visuele gereedschappen kunt u regels maken met behulp van zoekfuncties, pop-upopties, vervolgkeuzemenu&#39;s en functionaliteit voor slepen en neerzetten. De codeeditors verstrekken geavanceerde gebruikers van een manier om publiekssegmenteringscriteria programmatically te ontwikkelen.

**Gebeurtenisaanroepen verzenden gegevens naar[!DNL Audience Manager]**

Een gebeurtenisaanroep verzendt gegevens van uw website naar [!DNL Audience Manager]. De vraag bevat [!UICONTROL signal], [!UICONTROL trait], en [!UICONTROL segment] gegevens in een [!DNL HTTP] verzoek. De gebeurtenis zelf is alles na het `/event` deel van een [!DNL URL] tekenreeks. Zoals in het onderstaande voorbeeld wordt getoond, is voor dit proces slechts één gebeurtenisaanroep nodig om meerdere variabelen door te geven aan [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmenten: doel, samenstelling en regels](../features/segments/segments-purpose.md)

