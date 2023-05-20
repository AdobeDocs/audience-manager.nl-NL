---
description: De DCS bewaakt de id's die het ontvangt en voegt de id's toe die in een korte periode met een ongewoon hoge snelheid naar een lijst van gewezen personen worden verzonden.
keywords: id;monitoring;dcs
seo-description: The DCS monitors the IDs it receives and adds those that are being sent at an unusually high rate over a short period of time to a deny list.
seo-title: ID Monitoring and Denylisting
solution: Audience Manager
title: ID-controle en Voegend op lijst van gewenste personen maken
uuid: 498e0316-cf1b-43e9-88ba-338ee0daf225
feature: DCS
exl-id: 8fd31b00-a822-4fd5-b6f5-7f20546da1d9
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# ID-controle en Voegend op lijst van gewenste personen maken

De [!DNL DCS] controleert de id&#39;s die het ontvangt en voegt de id&#39;s die gedurende een korte periode ongebruikelijk hoog worden verzonden, toe aan een lijst van gewezen personen.

## Overzicht

Om de infrastructuur van de Audience Manager tegen kwaadwillige activiteit te beschermen, [!DNL DCS] gebruikt een geavanceerd algoritme om de IDs te controleren het ontvangt. Deze kunnen [!UICONTROL Data Provider Unique User ID]s ([!UICONTROL CRM ID]s), [!UICONTROL Audience Manager Unique User ID]s ([!UICONTROL AAM UUID]s), of [!UICONTROL Experience Cloud ID]s ([!UICONTROL ECID]s). Zie [Index van id&#39;s in Audience Manager](../../../reference/ids-in-aam.md) voor gedetailleerde uitleg van de id&#39;s die door Audience Manager worden ondersteund.

De [!DNL DCS] bewaakt de frequentie waarmee deze id&#39;s worden ontvangen om mogelijke schadelijke activiteit op te sporen. Wanneer de [!DNL DCS] detecteert een ongebruikelijk grote hoeveelheid van [!DNL DCS] aanvragen voor een bepaalde id binnen een korte tijd, die id wordt toegevoegd aan een lijst van gewezen personen.

## Foutcodes

U kunt id&#39;s identificeren die aan een lijst van gewezen personen zijn toegevoegd met de foutcodes die u ontvangt van de [!DNL DCS]. De foutcodes die u ontvangt zijn:

* 303: geblokkeerde klant-id;
* 306: Geblokkeerde gedeclareerde apparaat-id;
* 307: Bewerking van geblokkeerd profiel voor id.

Zie [DCS-foutcodes, berichten en voorbeelden](dcs-error-codes.md) voor meer informatie over de foutcodes die u ontvangt.

## Id&#39;s verwijderen uit lijsten van gewezen personen

Id&#39;s die aan lijsten van gewezen personen zijn toegevoegd, mogen in geen enkele toekomstige aanvraag worden gebruikt, omdat ze tot onjuiste gegevensrapportage leiden. De [!DNL DCS] biedt geen ondersteuning voor het verwijderen van id&#39;s uit lijsten van gewezen personen.

## Effect op id-synchronisatie

[!DNL DCS] De vraag kan één of veelvoudige types van IDs omvatten. Vraag die één enkele identiteitskaart bevatten wordt volledig genegeerd als die identiteitskaart aan een lijst van gewezen personen wordt toegevoegd, en geen synchronisatie van identiteitskaart komt in deze situatie voor.

Wanneer een veelvoudige vraag van identiteitskaart ook een gevoegde op lijst van gewenste personen identiteitskaart omvat, [!DNL DCS] negeert ontkende identiteitskaart en gebruikt slechts resterende, toegestane IDs voor synchronisatie.

## Causes and Fixes for ID Voegende op lijst van gewenste personen

De meest frequente oorzaak van IDs die aan lijsten van gewezen personen wordt toegevoegd is de onjuiste integratie tussen klanteninfrastructuur en Audience Manager. Wanneer u een gevoegde op lijst van gewenste personen identiteitskaart identificeert, zorg ervoor om uw integratie van de Audience Manager grondig te herzien. Zie **Implementatie- en integratiehulplijnen** voor gedetailleerde verklaringen van hoe u Audience Manager zou moeten vormen om met andere oplossingen van Experience Cloud of externe systemen te werken.

Een andere veelvoorkomende oorzaak van id&#39;s die aan lijsten van gewezen personen worden toegevoegd, is het indexeren van bots (webcrawlers), die over het algemeen tot een toename van het verkeer leiden, waardoor dezelfde id&#39;s naar de [!DNL DCS] meerdere keren. Als u indexerende bots identificeert als de reden waarom id&#39;s aan lijsten van gewezen personen worden toegevoegd, moet u beide toegang tot uw website beperken.

Neem contact op met de Klantenondersteuning als u problemen hebt met de integratie. Voordat u een supportverzoek opent, moet u ervoor zorgen dat u de `.har` `HTTP` archief van uw browser klaar. Dit archief helpt het ondersteuningsteam te bepalen waarom de id aan een lijst van gewezen personen is toegevoegd.
