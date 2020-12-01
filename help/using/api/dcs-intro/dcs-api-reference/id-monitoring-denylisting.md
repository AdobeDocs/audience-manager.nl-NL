---
description: De DCS bewaakt de id's die het ontvangt en voegt de id's toe die in een korte periode met een ongewoon hoge snelheid naar een lijst van afgewezen personen worden verzonden.
keywords: id;monitoring;dcs
seo-description: De DCS bewaakt de id's die het ontvangt en voegt de id's toe die in een korte periode met een ongewoon hoge snelheid naar een lijst van afgewezen personen worden verzonden.
seo-title: ID-controle en Toevoegend op lijst van gewenste personen maken
solution: Audience Manager
title: ID-controle en Toevoegend op lijst van gewenste personen maken
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID-controle en Toevoegend op lijst van gewenste personen maken

De [!DNL DCS] bewaakt de id&#39;s die het ontvangt en voegt de id&#39;s toe die gedurende een korte periode met een ongewoon hoge snelheid naar een lijst van afgewezen personen worden verzonden.

## Overzicht

Om de infrastructuur van de Audience Manager tegen kwaadwillige activiteit te beschermen, [!DNL DCS] gebruikt een geavanceerd algoritme om identiteitskaarts te controleren het ontvangt. Deze kunnen [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), of [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) zijn. Zie [Index van id&#39;s in Audience Manager](../../../reference/ids-in-aam.md) voor gedetailleerde uitleg van de id&#39;s die door Audience Manager worden ondersteund.

De [!DNL DCS] bewaakt de frequentie waarmee het deze id&#39;s ontvangt om mogelijke kwaadaardige activiteit te detecteren. Wanneer [!DNL DCS] een ongebruikelijk grote hoeveelheid [!DNL DCS] verzoeken om om om het even welke bepaalde identiteitskaart in een korte tijd ontdekt, wordt die identiteitskaart toegevoegd aan een lijst van afgewezen personen.

## Foutcodes

U kunt id&#39;s identificeren die aan een lijst van afgewezen personen zijn toegevoegd door de foutcodes te ontvangen van de [!DNL DCS]. De foutcodes die u ontvangt zijn:

* 303: geblokkeerde klant-id;
* 306: Geblokkeerde gedeclareerde apparaat-id;
* 307: Bewerking van geblokkeerd profiel voor id.

Zie [DCS-foutcodes, -berichten en -voorbeelden](dcs-error-codes.md) voor meer informatie over de foutcodes die u ontvangt.

## Id&#39;s verwijderen uit lijsten van afgewezen personen

Id&#39;s die aan lijsten van afgewezen personen zijn toegevoegd, mogen in geen enkele toekomstige aanvraag worden gebruikt, omdat ze tot onjuiste gegevensrapportage leiden. De [!DNL DCS] ondersteunt het verwijderen van id&#39;s uit lijsten van afgewezen personen niet.

## Effect op id-synchronisatie

[!DNL DCS] De vraag kan één of veelvoudige types van IDs omvatten. Vraag die één enkele identiteitskaart bevatten wordt volledig genegeerd als die identiteitskaart aan een lijst van afgewezen personen wordt toegevoegd, en geen synchronisatie van identiteitskaart komt in deze situatie voor.

Wanneer een veelvoudige vraag van identiteitskaart ook een toegevoegde op lijst van gewenste personen identiteitskaart omvat, negeert [!DNL DCS] ontkende identiteitskaart en gebruikt slechts resterende, toegestane IDs voor synchronisatie.

## Causes and Fixes for ID Toevoegende op lijst van gewenste personen

De meest frequente oorzaak van IDs die aan lijsten van afgewezen personen wordt toegevoegd is de onjuiste integratie tussen klanteninfrastructuur en Audience Manager. Wanneer u een toegevoegde op lijst van gewenste personen identiteitskaart identificeert, zorg ervoor om uw integratie van de Audience Manager grondig te herzien. Zie **Implementatie- en integratiehulplijnen** voor gedetailleerde uitleg van hoe u Audience Manager moet configureren om te werken met andere Experience Cloud-oplossingen of externe systemen.

Een andere veelvoorkomende oorzaak van id&#39;s die aan lijsten van afgewezen personen worden toegevoegd, is het indexeren van bots (webcrawlers), die over het algemeen tot een toename van het verkeer leiden, waardoor dezelfde id&#39;s meerdere keren naar [!DNL DCS] worden verzonden. Als u indexerende bots identificeert als de reden waarom id&#39;s aan lijsten van afgewezen personen worden toegevoegd, moet u beide toegang tot uw website beperken.

Neem contact op met de Klantenondersteuning als u problemen hebt met de integratie. Voordat u een supportverzoek opent, moet u het `.har` `HTTP`-archief van uw browser klaar houden. Dit archief helpt het ondersteuningsteam te bepalen waarom de id aan een lijst van afgewezen personen is toegevoegd.