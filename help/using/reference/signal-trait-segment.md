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
source-wordcount: '392'
ht-degree: 20%

---

# [!UICONTROL Signals], [!UICONTROL Traits], en [!UICONTROL Segments] {#signals-traits-and-segments}

Beschrijft de componenten van een [!DNL Audience Manager] [!UICONTROL segment], de expressies die worden gebruikt om kwalificatiecriteria voor het publiek in te stellen en de manier waarop gegevens worden verzonden in een gebeurtenisaanroep.

## Samenstelling en doel

[!DNL Audience Manager] gegevens bestaan uit [!UICONTROL signals], [!UICONTROL traits], [!UICONTROL segments]en de desbetreffende kwalificatieregels. De gegevenselementen en -regels worden gecombineerd om [!UICONTROL segments]. [!UICONTROL Segments] sitebezoekers organiseren in verwante groepen. In de volgende tabel worden de drie hoofdcomponenten in een [!DNL Audience Manager] [!UICONTROL segment].

| Element | Bestaat uit | Voorbeeld |
|---|---|---|
| [!UICONTROL Signal] | [!UICONTROL Signals] zijn de kleinste gegevenseenheden in [!DNL Audience Manager] en uitgedrukt als [sleutelwaardeparen](../reference/key-value-pairs-explained.md).<br><br><ul><li>De sleutel is een constante die een gegevensset definieert (bijvoorbeeld geslacht, kleur, prijs).</li><li>De waarde is een variabele die gerelateerd is aan de constante (bijvoorbeeld mannelijk/vrouwelijk, groen, 100).</li></ul>Vergelijkingsoperatoren voegen zich bij het sleutelwaardepaar en stellen de relatie tussen deze operatoren in. | <ul><li>`product=camera`</li><li>`price>1000`</li><li>`type=digital SLR`</li></ul> |
| [!UICONTROL Trait] | Combinaties van een of meer [!UICONTROL signals].<br><br> [!DNL Boolean] Met expressies en vergelijkingsoperatoren kunt u [!UICONTROL trait] kwalificatieregels. <br><br>Nauwkeurige kwalificatievereisten maken met combinaties van [!UICONTROL traits] en [!UICONTROL trait] groepen. | Via de beschikbare [!UICONTROL signals]kunt u een `High End Camera Browser` regel uitgedrukt als: `product=camera AND price>1000` |
| [!UICONTROL Segment] | Gebruikers die een set gemeenschappelijke kenmerken delen en in aanmerking komen voor verwante kenmerken [!UICONTROL traits]. [!DNL Boolean] Met expressies kunt u, samen met de vereisten voor recentie/frequentie, [!UICONTROL segment] kwalificatieregels.<br><br> Nauwkeurige kwalificatievereisten maken met combinaties van [!UICONTROL trait] en [!UICONTROL segment] regels. | Via de beschikbare [!UICONTROL traits] en [!UICONTROL signals]kunt u een [!UICONTROL segment] regel uitgedrukt als:`(product=camera AND type=digital SLR) OR (price>1000)` |

Gebruik het onderstaande diagram om de relatie tussen de [!UICONTROL signals], [!UICONTROL traits], en [!UICONTROL segments].

![](assets/signals-traits-segments.png)

**Opbouwen [!UICONTROL Traits] en [!UICONTROL Segment] Regels met Visuele Hulpmiddelen en de Redacteurs van de Code**

Clients beheren [!UICONTROL traits] en [!UICONTROL segments] met visuele gereedschappen en code-editors in de [!DNL Audience Manager] gebruikersinterface. Met de visuele gereedschappen kunt u regels maken met behulp van zoekfuncties, pop-upopties, vervolgkeuzemenu&#39;s en functionaliteit voor slepen en neerzetten. De codeeditors verstrekken geavanceerde gebruikers van een manier om publiekssegmenteringscriteria programmatically te ontwikkelen.

**Gebeurtenisaanroepen verzenden gegevens naar[!DNL Audience Manager]**

Een gebeurtenisaanroep verzendt gegevens van uw website naar [!DNL Audience Manager]. De vraag bevat [!UICONTROL signal], [!UICONTROL trait], en [!UICONTROL segment] gegevens in een [!DNL HTTP] verzoek. De gebeurtenis zelf is alles na de `/event` deel van een [!DNL URL] tekenreeks. Zoals in het onderstaande voorbeeld wordt getoond, is voor dit proces slechts één gebeurtenisaanroep nodig om meerdere variabelen door te geven aan [!DNL Audience Manager].

`https://<domain>/event?product=camera&price>100`

>[!MORELIKETHIS]
>
>* [Segmenten: doel, samenstelling en regels](../features/segments/segments-purpose.md)

