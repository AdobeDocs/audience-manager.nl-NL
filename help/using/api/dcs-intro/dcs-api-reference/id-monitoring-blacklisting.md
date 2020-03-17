---
description: De DCS bewaakt de id's die het ontvangt en somt de id's op die in een korte periode met een ongewoon hoge snelheid worden verzonden.
keywords: id;monitoring;blacklisting;dcs
seo-description: De DCS bewaakt de id's die het ontvangt en somt de id's op die in een korte periode met een ongewoon hoge snelheid worden verzonden.
seo-title: ID-controle en Blackvermelding
solution: Audience Manager
title: ID-controle en Blackvermelding
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
translation-type: tm+mt
source-git-commit: 1300c29cbd5dce26357dc698f2f6efc5bdb32bdb

---


# ID-controle en Blackvermelding

De [!UICONTROL DCS] monitoren de id&#39;s die ze ontvangen en de zwarte lijsten geven de id&#39;s weer die in een korte periode ongebruikelijk hoog worden verzonden.

## Overzicht

Om de infrastructuur van de Manager van de Publiek tegen kwaadwillige activiteit te beschermen, [!UICONTROL DCS] gebruikt een geavanceerd algoritme om identiteitskaarts te controleren het ontvangt. Dit kunnen [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), of [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s) zijn. Zie [Index van IDs in de Manager](../../../reference/ids-in-aam.md) van het Publiek voor gedetailleerde verklaringen van identiteitskaarts die door de Manager van het Publiek wordt gesteund.

De [!UICONTROL DCS] monitor de frequentie waarbij het deze IDs ontvangt om potentiële kwaadwillige activiteit te ontdekken. Wanneer de id in een korte tijd een ongewoon grote hoeveelheid [!UICONTROL DCS] aanvragen voor een bepaalde id [!UICONTROL DCS] detecteert, wordt die id op de zwarte lijst gezet.

## Foutcodes

U kunt op de zwarte lijst geplaatste id&#39;s identificeren aan de hand van de foutcodes die u van het [!UICONTROL DCS]formulier hebt ontvangen. De foutcodes die u ontvangt zijn:

* 303: geblokkeerde klant-id;
* 306: Geblokkeerde gedeclareerde apparaat-id;
* 307: Bewerking van geblokkeerd profiel voor id.

Zie [DCS-foutcodes, berichten en voorbeelden](dcs-error-codes.md) voor meer informatie over de foutcodes die u ontvangt.

## Uitdrukking op zwarte lijst

ID&#39;s op de zwarte lijst mogen niet worden gebruikt in toekomstige aanvragen, omdat deze leiden tot onjuiste gegevensrapportage. De [!UICONTROL DCS] biedt geen ondersteuning voor het ongedaan maken van een zwarte lijst van id&#39;s.

## Effect op id-synchronisatie

[!UICONTROL DCS] De vraag kan één of veelvoudige types van IDs omvatten. Vraag die één enkele identiteitskaart bevatten wordt volledig genegeerd als die identiteitskaart op zwarte lijst staat, en geen synchronisatie van identiteitskaart komt in deze situatie voor.

Wanneer een meervoudige id-aanroep ook een op de zwarte lijst staande id bevat, wordt de id op de zwarte lijst [!UICONTROL DCS] genegeerd en worden alleen de resterende, niet op de zwarte lijst geplaatste id&#39;s voor synchronisatie gebruikt.

## Causes and Fixes for ID Blacklist

De meest voorkomende oorzaak van id&#39;s die op de zwarte lijst staan, is de onjuiste integratie tussen de infrastructuur van de klant en de manager van het publiek. Wanneer u een op de zwarte lijst geplaatste id identificeert, moet u de integratie van Audience Manager grondig controleren. Zie **Implementatie- en integratiehulplijnen** voor gedetailleerde uitleg over hoe u Audience Manager moet configureren voor samenwerking met andere Experience Cloud-oplossingen of externe systemen.

Een andere veelvoorkomende oorzaak van op de zwarte lijst geplaatste id&#39;s is het indexeren van bots (webcrawlers), die over het algemeen leiden tot een toename van het verkeer, waardoor dezelfde id&#39;s meerdere keren naar de [!UICONTROL DCS] gebruiker worden verzonden. Als je indexeerbots identificeert als de reden voor ID-zwarte lijsten, moet je beide toegang tot je website beperken.

Neem contact op met de Klantenondersteuning als u problemen hebt met de integratie. Voordat u een supportverzoek opent, moet u het `.har` `HTTP` archief van uw browser op de juiste plaats houden. Met dit archief kan het ondersteuningsteam vaststellen waarom de ID-zwarte lijst is geplaatst.