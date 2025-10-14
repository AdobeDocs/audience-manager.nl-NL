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
source-wordcount: '487'
ht-degree: 0%

---

# ID-controle en Voegend op lijst van gewenste personen maken

De [!DNL DCS] bewaakt de id&#39;s die het ontvangt en voegt de id&#39;s toe die gedurende een korte periode ongebruikelijk hoog worden verzonden naar een lijst van gewezen personen.

## Overzicht

Om de Audience Manager-infrastructuur tegen kwaadaardige activiteiten te beschermen, gebruikt de [!DNL DCS] een geavanceerd algoritme om de id&#39;s die het ontvangt te controleren. Deze kunnen [!UICONTROL Data Provider Unique User ID] s ([!UICONTROL CRM ID] zijn), [!UICONTROL Audience Manager Unique User ID] s ([!UICONTROL AAM UUID] s), of [!UICONTROL Experience Cloud ID] s ([!UICONTROL ECID] s). Zie [&#x200B; Index van IDs in Audience Manager &#x200B;](../../../reference/ids-in-aam.md) voor gedetailleerde verklaringen van IDs die door Audience Manager wordt gesteund.

[!DNL DCS] controleert de frequentie waarmee het deze IDs ontvangt om potentiële kwaadwillige activiteit te ontdekken. Wanneer [!DNL DCS] in een korte tijd een ongebruikelijk grote hoeveelheid [!DNL DCS] -aanvragen voor een bepaalde id detecteert, wordt die id toegevoegd aan een lijst van gewezen personen.

## Foutcodes

U kunt id&#39;s die aan een lijst van gewezen personen zijn toegevoegd identificeren aan de hand van de foutcodes die u van het dialoogvenster [!DNL DCS] hebt ontvangen. De foutcodes die u ontvangt zijn:

* 303: geblokkeerde klant-id;
* 306: geblokkeerde aangegeven apparaat-id;
* 307: Geblokkeerde profielbewerking voor id.

Zie [&#x200B; Codes van de Fout DCS, Berichten, en Voorbeelden &#x200B;](dcs-error-codes.md) voor details op de foutencodes die u kunt ontvangen.

## Id&#39;s verwijderen uit lijsten van gewezen personen

Id&#39;s die aan lijsten van gewezen personen zijn toegevoegd, mogen in geen enkele toekomstige aanvraag worden gebruikt, omdat ze tot onjuiste gegevensrapportage leiden. Het [!DNL DCS] biedt geen ondersteuning voor het verwijderen van id&#39;s uit lijsten van gewezen personen.

## Effect op id-synchronisatie

[!DNL DCS] vraag kan één of veelvoudige types van IDs omvatten. Vraag die één enkele identiteitskaart bevatten wordt volledig genegeerd als die identiteitskaart aan een lijst van gewezen personen wordt toegevoegd, en geen synchronisatie van identiteitskaart komt in deze situatie voor.

Wanneer een veelvoudige vraag van identiteitskaart ook een gevoegde op lijst van gewenste personen identiteitskaart omvat, negeert [!DNL DCS] ontkende identiteitskaart en gebruikt slechts resterende, toegestane IDs voor synchronisatie.

## Causes and Fixes for ID Voegende op lijst van gewenste personen

De meest voorkomende oorzaak van id&#39;s die aan lijsten van gewezen personen worden toegevoegd, is de onjuiste integratie tussen de klanteninfrastructuur en Audience Manager. Wanneer u een op de lijst met ongewenste personen staan id identificeert, moet u de Audience Manager-integratie grondig controleren. Zie **de Gidsen van de Implementatie en van de Integratie** voor gedetailleerde verklaringen van hoe u Audience Manager zou moeten vormen om met andere oplossingen van Experience Cloud of externe systemen te werken.

Een andere veelvoorkomende oorzaak van id&#39;s die aan lijsten van gewezen personen worden toegevoegd, is het indexeren van bots (webcrawlers), die over het algemeen tot een toename van het verkeer leiden, waardoor dezelfde id&#39;s meerdere keren naar de [!DNL DCS] worden verzonden. Als u indexerende bots identificeert als de reden waarom id&#39;s aan lijsten van gewezen personen worden toegevoegd, moet u beide toegang tot uw website beperken.

Neem contact op met de Klantenondersteuning als u problemen hebt met de integratie. Voordat u een supportverzoek opent, moet u het archief van uw browser `.har` `HTTP` gereed houden. Dit archief helpt het ondersteuningsteam te bepalen waarom de id aan een lijst van gewezen personen is toegevoegd.
