---
description: Beschrijft de componenten van een segment van de Audience Manager, de uitdrukkingen die worden gebruikt om de criteria van de publiekskwalificatie te plaatsen, en hoe het gegeven in een gebeurtenisvraag wordt overgebracht.
landing-page-description: Beschrijft componenten van een segment, uitdrukkingen die worden gebruikt om de criteria van de publiekskwalificatie te plaatsen, en hoe het gegeven wordt overgebracht.
seo-title: Signalen, eigenschappen en segmenten
solution: Audience Manager
title: Signalen, eigenschappen en segmenten
uuid: 485fcc5c-b289-463b-a610-0d727df90f3c
feature: 'Referenties '
exl-id: ec33f2c3-1589-4c02-a85a-db0d72467f32
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 4%

---

# [!UICONTROL Signals],  [!UICONTROL Traits]en  [!UICONTROL Segments] {#signals-traits-and-segments}

Beschrijft de componenten van [!DNL Audience Manager] [!UICONTROL segment], de uitdrukkingen die worden gebruikt om de criteria van de publiekskwalificatie te plaatsen, en hoe het gegeven in een gebeurtenisvraag wordt overgebracht.

## Samenstelling en doel

[!DNL Audience Manager] de gegevens bestaan uit  [!UICONTROL signals],  [!UICONTROL traits],  [!UICONTROL segments]en bijbehorende kwalificatieregels. De gegevenselementen en -regels worden gecombineerd om [!UICONTROL segments] te maken. [!UICONTROL Segments] sitebezoekers organiseren in verwante groepen. De volgende lijst bepaalt de drie belangrijkste componenten in [!DNL Audience Manager] [!UICONTROL segment].

| Element | Bestaat uit | Voorbeeld |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] zijn de kleinste gegevenseenheden in  [!DNL Audience Manager] en worden uitgedrukt als  [sleutelwaardeparen](../reference/key-value-pairs-explained.md).<br><br><ul><li>De sleutel is een constante die een gegevensset definieert (bijvoorbeeld geslacht, kleur, prijs).</li><li>De waarde is een variabele die gerelateerd is aan de constante (bijvoorbeeld mannelijk/vrouwelijk, groen, 100).</li></ul>Vergelijkingsoperatoren voegen zich bij het sleutelwaardepaar en stellen de relatie tussen deze operatoren in. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaties van een of meer [!UICONTROL signals].<br><br> [!DNL Boolean] Met expressies en vergelijkingsoperatoren kunt u  [!UICONTROL trait] kwalificatieregels maken. <br><br>Maak nauwkeurige kwalificatievereisten met combinaties van  [!UICONTROL traits] en  [!UICONTROL trait] groepen. | Van beschikbare [!UICONTROL signals], kon u een `High End Camera Browser` regel tot stand brengen die als wordt uitgedrukt: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Gebruikers die een set gemeenschappelijke kenmerken delen en in aanmerking komen voor verwante [!UICONTROL traits]. [!DNL Boolean] Met expressies kunt u samen met de eisen voor recentie/frequentie  [!UICONTROL segment] kwalificatieregels maken.<br><br> Maak nauwkeurige kwalificatievereisten met combinaties van  [!UICONTROL trait] en  [!UICONTROL segment] regels. | Op basis van de beschikbare [!UICONTROL traits] en [!UICONTROL signals] kunt u een [!UICONTROL segment]-regel maken, uitgedrukt als:`(product=camera AND type=digital SLR) OR (price>1000)` |

Gebruik het onderstaande diagram om een mentale noot te houden van de relatie tussen [!UICONTROL signals], [!UICONTROL traits] en [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Bouw  [!UICONTROL Traits] en  [!UICONTROL Segment] Regels met Visuele Hulpmiddelen en de Redacteurs van de Code**

Clients beheren [!UICONTROL traits] en [!UICONTROL segments] met visuele gereedschappen en code-editors in de gebruikersinterface [!DNL Audience Manager]. Met de visuele gereedschappen kunt u regels maken met behulp van zoekfuncties, pop-upopties, vervolgkeuzemenu&#39;s en functionaliteit voor slepen en neerzetten. De codeeditors verstrekken geavanceerde gebruikers van een manier om publiekssegmenteringscriteria programmatically te ontwikkelen.

**Gebeurtenisaanroepen verzenden gegevens naar[!DNL Audience Manager]**

Een gebeurtenisvraag verzendt gegevens van uw website naar [!DNL Audience Manager]. De vraag bevat [!UICONTROL signal], [!UICONTROL trait], en [!UICONTROL segment] gegevens in een [!DNL HTTP] verzoek. De gebeurtenis zelf is alles na het `/event` deel van een [!DNL URL] koord. Zoals in het onderstaande voorbeeld wordt getoond, vereist dit proces slechts één enkele gebeurtenisvraag om in veelvoudige variabelen tot [!DNL Audience Manager] over te gaan.

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmenten: doel, samenstelling en regels](../features/segments/segments-purpose.md)

