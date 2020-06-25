---
description: De Optimalisering van het publiek voor Advertisers kan u helpen potentiële prestatiemogelijkheden voor de segmenten van de Audience Manager over uw betaalde media campagnes identificeren. In deze rapporten worden de gegevens van de campagneresultaten op het niveau van het logbestand gecombineerd met de gegevens van het Audience Manager-segment om op segment gerichte optimalisaties en een effectieve kanaalmix te informeren.
seo-description: De Optimalisering van het publiek voor Advertisers kan u helpen potentiële prestatiemogelijkheden voor de segmenten van de Audience Manager over uw betaalde media campagnes identificeren. In deze rapporten worden de gegevens van de campagneresultaten op het niveau van het logbestand gecombineerd met de gegevens van het Audience Manager-segment om op segment gerichte optimalisaties en een effectieve kanaalmix te informeren.
seo-title: Publiek optimaliseren voor adverteerders
solution: Audience Manager
title: Publiek optimaliseren voor adverteerders
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: audience optimization reports
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 0%

---


# [!UICONTROL Audience Optimization] voor adverteerders{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] voor Advertisers kunt u helpen potentiële prestatiemogelijkheden voor de segmenten van de Audience Manager over uw betaalde media campagnes identificeren. In deze rapporten worden de gegevens van de campagneresultaten op het niveau van het logbestand gecombineerd met de [!UICONTROL segment] meetgegevens van de Audience Manager om de segmentcentrische optimalisatie te bepalen en een effectieve kanaalmix.

## Methoden voor gegevensinname {#data-ingestion-methods}

U kunt gegevens naar [!DNL Audience Manager] voor gebruik in deze rapporten door één van beide methodes verzenden. Soms verzenden klanten gegevens via beide methoden. Zo zorgt u ervoor dat uw rapporten de meest uitgebreide en nauwkeurige informatie over een bezoeker bevatten. Om de [!UICONTROL Audience Optimization] rapporten te gebruiken, moet uw gebeurtenisvraag *alle* parameters omvatten die in het [Overzicht en Toewijzingen voor de documentatie van de Dossiers](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) van Meta-gegevens worden vermeld. U kunt gegevens verzenden via de volgende hieronder vermelde methoden.

* Pixelaanroepen: Om de vereiste meta-gegevensparameters over te gaan om [!DNL Audience Manager] het Vastleggen Campagne te zien klik Gegevens via de Vraag [van het Pixel en het](../../../integration/media-data-integration/click-data-pixels.md) Vastleggen van de Gegevens van de Bedrukking van de Campagne via de Vraag [](../../../integration/media-data-integration/impression-data-pixels.md)van het Pixel.

* Gegevensbestanden: Als u deze rapporten wilt gebruiken om uw eigen gegevens of gegevens van een bron te analyseren die niet met geïntegreerd is, moet u gegevens en meta-gegevensdossiers voor die gegevens tot stand brengen en uploaden. [!DNL Audience Manager] Voor meer informatie, zie de Dossiers van [Gegevens voor de Rapporten](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) van de Optimalisering van de Publiek en [Gegevens en de Dossiers van Meta-gegevens voor de Rapporten](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)van de Optimalisering van de Publiek.

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Het type rapporten u kunt bekijken hangt van de [!UICONTROL RBAC] groep af u aan wordt toegewezen. Zie [Beleid](../../../features/administration/administration-overview.md) en [creeer een Groep](../../../features/administration/administration-overview.md#create-group) voor meer informatie.

[!UICONTROL RBAC] groepen moeten bepaalde gegevensbronnen hebben opgezet om de [!UICONTROL Audience Optimization] rapporten te bekijken. Uw [!DNL Audience Manager] consultant stelt deze [!UICONTROL data sources] voor u in. Hoe meer [!UICONTROL data sources] in elke [!UICONTROL RBAC] gebruikersgroep, des te meer gegevens de groepsleden tot wie toegang hebben. Uw consultant stelt ten minste een van de volgende instellingen in [!UICONTROL data sources]:

* Adverteerder [!UICONTROL data source ]
* Merk [!UICONTROL data source]
* Platform [!UICONTROL data source]

Gebruikers die tot meer dan één [!UICONTROL RBAC] gebruikersgroep behoren, kunnen schakelen tussen de weergave van elke groep. De weergegeven gegevens worden bijgewerkt met inachtneming van de geselecteerde groep. Als uw bedrijf niet [!UICONTROL RBAC]gebruikt, hebben alle gebruikers beheerdersrechten en toegang tot alle [!UICONTROL data sources] (conversiegroepen).

## Conversiegroepen {#conversion-groups}

In de [!UICONTROL Audience Optimization] rapporten, **[!UICONTROL Conversion Groups]** zijn synoniem met [!UICONTROL data sources] die minstens één omzettingseigenschap bevatten. [!UICONTROL Data sources] die niet ten minste één omzettingskenmerk bevatten, worden niet in de [!UICONTROL Audience Optimization] rapporten vermeld. U kunt de omzettingskenmerken voor conversiegroepen bekijken in het rapport [Gerapporteerde omzettingen](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) .
