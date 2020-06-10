---
description: DCS controleert identiteitskaarts het ontvangt en voegt die toe die tegen een ongebruikelijk hoog tarief over een korte periode aan ontkent lijst worden verzonden.
keywords: id;monitoring;dcs
seo-description: DCS controleert identiteitskaarts het ontvangt en voegt die toe die tegen een ongebruikelijk hoog tarief over een korte periode aan ontkent lijst worden verzonden.
seo-title: ID-controle en Afwijzing
solution: Audience Manager
title: ID-controle en Afwijzing
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID-controle en Afwijzing

De [!UICONTROL DCS] controleert identiteitskaarts het ontvangt en voegt die toe die tegen een ongebruikelijk hoog tarief over een korte periode aan ontkent lijst worden verzonden.

## Overzicht

Om de infrastructuur van de Manager van de Publiek tegen kwaadwillige activiteit te beschermen, [!UICONTROL DCS] gebruikt een geavanceerd algoritme om identiteitskaarts te controleren het ontvangt. Dit kunnen [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), of [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) zijn. Zie [Index van IDs in de Manager](../../../reference/ids-in-aam.md) van het Publiek voor gedetailleerde verklaringen van identiteitskaarts die door de Manager van het Publiek wordt gesteund.

De [!UICONTROL DCS] monitor de frequentie waarbij het deze IDs ontvangt om potentiële kwaadwillige activiteit te ontdekken. Wanneer het [!UICONTROL DCS] een ongebruikelijk grote hoeveelheid [!UICONTROL DCS] verzoeken om om om het even welke bepaalde identiteitskaart in een korte hoeveelheid tijd ontdekt, wordt die identiteitskaart toegevoegd aan ontkent lijst.

## Foutcodes

U kunt IDs identificeren die aan ontkennen lijst door de foutencodes worden toegevoegd van [!UICONTROL DCS]. De foutcodes die u ontvangt zijn:

* 303: geblokkeerde klant-id;
* 306: Geblokkeerde gedeclareerde apparaat-id;
* 307: Bewerking van geblokkeerd profiel voor id.

Zie [DCS-foutcodes, berichten en voorbeelden](dcs-error-codes.md) voor meer informatie over de foutcodes die u ontvangt.

## Het verwijderen van identiteitskaarts uit ontkent lijsten

Id&#39;s die zijn toegevoegd om lijsten te weigeren, mogen niet worden gebruikt in toekomstige aanvragen, omdat deze tot onjuiste gegevensrapportage leiden. Het [!UICONTROL DCS] steunt niet de verwijdering van IDs van ontkent lijsten.

## Effect op id-synchronisatie

[!UICONTROL DCS] De vraag kan één of veelvoudige types van IDs omvatten. Vraag die één enkele identiteitskaart bevatten wordt volledig genegeerd als die identiteitskaart aan ontkent lijst wordt toegevoegd, en geen synchronisatie van identiteitskaart komt in deze situatie voor.

Wanneer een veelvoudige vraag van identiteitskaart ook een ontkend vermelde identiteitskaart omvat, negeert [!UICONTROL DCS] ontkende identiteitskaart en gebruikt slechts het resterende, toegestane IDs voor synchronisatie.

## Causes and Fixes for ID Denyaanbieding

De meest frequente oorzaak van IDs die wordt toegevoegd om lijsten te ontkennen is de onjuiste integratie tussen de klanteninfrastructuur en de Manager van het Publiek. Wanneer u een ontkennende identiteitskaart identificeert, zorg ervoor om uw integratie van de Manager van de Publiek grondig te herzien. Zie **Implementatie- en integratiehulplijnen** voor gedetailleerde uitleg over hoe u Audience Manager moet configureren voor samenwerking met andere Experience Cloud-oplossingen of externe systemen.

Een andere frequente oorzaak van IDs die wordt toegevoegd om lijsten te ontkennen is indexerende bots (Webkruipende), die over het algemeen verhogingen van verkeer veroorzaken, die tot zelfde IDs leiden die naar de [!UICONTROL DCS] veelvoudige tijden worden verzonden. Als u indexerende bots identificeert als reden voor id&#39;s die worden toegevoegd om lijsten te weigeren, moet u beide toegang tot uw website beperken.

Neem contact op met de Klantenondersteuning als u problemen hebt met de integratie. Voordat u een supportverzoek opent, moet u het `.har` `HTTP` archief van uw browser op de juiste plaats houden. Dit archief helpt het ondersteuningsteam identificeren waarom identiteitskaart aan ontkent lijst werd toegevoegd.