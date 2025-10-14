---
description: Leer over de componenten van een segment en de expressies die worden gebruikt om de kwalificatiecriteria van de doelgroep in te stellen. Meer informatie over de manier waarop gegevens worden verzonden.
landing-page-description: Leer over de componenten van een segment en de expressies die worden gebruikt om de kwalificatiecriteria van de doelgroep in te stellen. Meer informatie over de manier waarop gegevens worden verzonden.
short-description: Leer over de componenten van een segment en de expressies die worden gebruikt om de kwalificatiecriteria van de doelgroep in te stellen. Meer informatie over de manier waarop gegevens worden verzonden.
seo-title: Signals, Traits, and Segments
solution: Audience Manager
title: Signalen, eigenschappen en segmenten
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: Reference
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 20%

---

# [!UICONTROL Signals] , [!UICONTROL Traits] en [!UICONTROL Segments] {#signals-traits-and-segments}

Beschrijft de componenten van een [!DNL Audience Manager] [!UICONTROL segment] , de uitdrukkingen die worden gebruikt om de criteria van de publiekskwalificatie te plaatsen, en hoe de gegevens in een gebeurtenisvraag worden overgebracht.

## Samenstelling en doel

[!DNL Audience Manager] -gegevens bestaan uit [!UICONTROL signals] , [!UICONTROL traits] , [!UICONTROL segments] en gerelateerde kwalificatieregels. De gegevenselementen en -regels worden gecombineerd om [!UICONTROL segments] te maken. [!UICONTROL Segments] organiseert sitebezoekers in verwante groepen. In de volgende tabel worden de drie hoofdcomponenten in een [!DNL Audience Manager] [!UICONTROL segment] gedefinieerd.

| Element | Bestaat uit | Voorbeeld |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] zijn de kleinste gegevenseenheden in [!DNL Audience Manager] en als [&#x200B; zeer belangrijk-waardeparen &#x200B;](../reference/key-value-pairs-explained.md) uitgedrukt.<br><br><ul><li>De sleutel is een constante die een gegevensset definieert (bijvoorbeeld geslacht, kleur, prijs).</li><li>De waarde is een variabele die gerelateerd is aan de constante (bijvoorbeeld man/vrouw, groen, 100).</li></ul>Vergelijkingsoperatoren voegen zich bij het sleutelwaardepaar en stellen de relatie tussen deze operatoren in. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaties van een of meer [!UICONTROL signals].<br><br> Met [!DNL Boolean] -expressies en vergelijkingsoperatoren kunt u [!UICONTROL trait] -kwalificatieregels maken. <br><br> creeer nauwkeurige kwalificatievereisten met combinaties [!UICONTROL traits] en [!UICONTROL trait] groepen. | Via het beschikbare [!UICONTROL signals] kunt u een `High End Camera Browser` -regel maken die wordt uitgedrukt als: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Gebruikers die een set algemene kenmerken delen en in aanmerking komen voor verwante [!UICONTROL traits] . Met [!DNL Boolean] -expressies kunt u samen met de vereisten voor frequentie en frequentie [!UICONTROL segment] -kwalificatieregels maken.<br><br> Maak nauwkeurige kwalificatievereisten met combinaties van [!UICONTROL trait] - en [!UICONTROL segment] -regels. | Van beschikbare [!UICONTROL traits] en [!UICONTROL signals], kon u een [!UICONTROL segment] regel tot stand brengen die als wordt uitgedrukt: `(product=camera AND type=digital SLR) OR (price>1000)` |

Gebruik het onderstaande diagram om een mentale noot te houden van de relatie tussen [!UICONTROL signals] , [!UICONTROL traits] en [!UICONTROL segments] .

![](assets/signals-traits-segments.png)

**bouwt [!UICONTROL Traits] en [!UICONTROL Segment] Regels met Visuele Hulpmiddelen en de Redacteurs van de Code**

Clients beheren [!UICONTROL traits] en [!UICONTROL segments] met visuele gereedschappen en code-editors in de gebruikersinterface van [!DNL Audience Manager] . Met de visuele gereedschappen kunt u regels maken met behulp van zoekfuncties, pop-upopties, vervolgkeuzemenu&#39;s en functionaliteit voor slepen en neerzetten. De codeeditors verstrekken geavanceerde gebruikers van een manier om publiekssegmenteringscriteria programmatically te ontwikkelen.

**De Vraag van de gebeurtenis verzendt Gegevens naar[!DNL Audience Manager]**

Een gebeurtenisaanroep verzendt gegevens van uw website naar [!DNL Audience Manager] . De aanroep bevat [!UICONTROL signal] , [!UICONTROL trait] en [!UICONTROL segment] gegevens in een [!DNL HTTP] request. De gebeurtenis zelf is alles na het `/event` -gedeelte van een [!DNL URL] -tekenreeks. Zoals in het onderstaande voorbeeld wordt getoond, is voor dit proces slechts één gebeurtenisaanroep nodig om meerdere variabelen door te geven aan [!DNL Audience Manager] .

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmenten: doel, samenstelling en regels](../features/segments/segments-purpose.md)
