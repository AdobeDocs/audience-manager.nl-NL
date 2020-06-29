---
description: DCS controleert identiteitskaarts het ontvangt en voegt die toe die tegen een ongebruikelijk hoog tarief over een korte periode aan ontkent lijst worden verzonden.
keywords: id;monitoring;dcs
seo-description: DCS controleert identiteitskaarts het ontvangt en voegt die toe die tegen een ongebruikelijk hoog tarief over een korte periode aan ontkent lijst worden verzonden.
seo-title: ID-controle en Afwijzing
solution: Audience Manager
title: ID-controle en Afwijzing
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '514'
ht-degree: 0%

---


# ID-controle en Afwijzing

De [!DNL DCS] controleert identiteitskaarts het ontvangt en voegt die toe die tegen een ongebruikelijk hoog tarief over een korte periode aan ontkent lijst worden verzonden.

## Overzicht

Om de infrastructuur van de Audience Manager tegen kwaadwillige activiteit te beschermen, [!DNL DCS] gebruikt een geavanceerd algoritme om identiteitskaarts te controleren het ontvangt. Dit kunnen [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), of [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) zijn. Zie [Index van IDs in Audience Manager](../../../reference/ids-in-aam.md) voor gedetailleerde uitleg van IDs die door Audience Manager wordt gesteund.

De [!DNL DCS] monitor de frequentie waarbij het deze IDs ontvangt om potentiële kwaadwillige activiteit te ontdekken. Wanneer het [!DNL DCS] een ongebruikelijk grote hoeveelheid [!DNL DCS] verzoeken om om om het even welke bepaalde identiteitskaart in een korte hoeveelheid tijd ontdekt, wordt die identiteitskaart toegevoegd aan ontkent lijst.

## Foutcodes

U kunt IDs identificeren die aan ontkennen lijst door de foutencodes worden toegevoegd van [!DNL DCS]. De foutcodes die u ontvangt zijn:

* 303: geblokkeerde klant-id;
* 306: Geblokkeerde gedeclareerde apparaat-id;
* 307: Bewerking van geblokkeerd profiel voor id.

Zie [DCS-foutcodes, berichten en voorbeelden](dcs-error-codes.md) voor meer informatie over de foutcodes die u ontvangt.

## Het verwijderen van identiteitskaarts uit ontkent lijsten

Id&#39;s die zijn toegevoegd om lijsten te weigeren, mogen niet worden gebruikt in toekomstige aanvragen, omdat deze tot onjuiste gegevensrapportage leiden. Het [!DNL DCS] steunt niet de verwijdering van IDs van ontkent lijsten.

## Effect op id-synchronisatie

[!DNL DCS] De vraag kan één of veelvoudige types van IDs omvatten. Vraag die één enkele identiteitskaart bevatten wordt volledig genegeerd als die identiteitskaart aan ontkent lijst wordt toegevoegd, en geen synchronisatie van identiteitskaart komt in deze situatie voor.

Wanneer een veelvoudige vraag van identiteitskaart ook een ontkend vermelde identiteitskaart omvat, negeert [!DNL DCS] ontkende identiteitskaart en gebruikt slechts het resterende, toegestane IDs voor synchronisatie.

## Causes and Fixes for ID Denyaanbieding

De meest frequente oorzaak van IDs die wordt toegevoegd om lijsten te ontkennen is de onjuiste integratie tussen klanteninfrastructuur en Audience Manager. Wanneer u een ID op de denylist herkent, moet u de integratie van de Audience Manager grondig controleren. Zie **Implementatie- en integratiegidsen** voor gedetailleerde uitleg over hoe u Audience Manager moet configureren voor gebruik met andere Experience Cloud-oplossingen of externe systemen.

Een andere frequente oorzaak van IDs die wordt toegevoegd om lijsten te ontkennen is indexerende bots (Webkruipende), die over het algemeen verhogingen van verkeer veroorzaken, die tot zelfde IDs leiden die naar de [!DNL DCS] veelvoudige tijden worden verzonden. Als u indexerende bots identificeert als reden voor id&#39;s die worden toegevoegd om lijsten te weigeren, moet u beide toegang tot uw website beperken.

Neem contact op met de Klantenondersteuning als u problemen hebt met de integratie. Voordat u een supportverzoek opent, moet u het `.har` `HTTP` archief van uw browser op de juiste plaats houden. Dit archief helpt het ondersteuningsteam identificeren waarom identiteitskaart aan ontkent lijst werd toegevoegd.