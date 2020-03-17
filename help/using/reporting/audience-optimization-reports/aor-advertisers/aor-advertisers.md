---
description: De Optimalisering van het publiek voor Advertisers kan u helpen potentiële prestatieskansen voor de segmenten van de Manager van de Publiek over uw betaalde media campagnes identificeren. Deze rapporten combineren de gegevens van campagneresultaten op logboekniveau met de segmentmetriek van de Manager van de Publiek om segment-centric optimalisaties en een efficiënte kanaalmengeling te informeren.
seo-description: De Optimalisering van het publiek voor Advertisers kan u helpen potentiële prestatieskansen voor de segmenten van de Manager van de Publiek over uw betaalde media campagnes identificeren. Deze rapporten combineren de gegevens van campagneresultaten op logboekniveau met de segmentmetriek van de Manager van de Publiek om segment-centric optimalisaties en een efficiënte kanaalmengeling te informeren.
seo-title: Publiek optimaliseren voor adverteerders
solution: Audience Manager
title: Publiek optimaliseren voor adverteerders
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Optimization for Advertisers{#audience-optimization-for-advertisers}

De Optimalisering van het publiek voor Advertisers kan u helpen potentiële prestatieskansen voor de segmenten van de Manager van de Publiek over uw betaalde media campagnes identificeren. Deze rapporten combineren de gegevens van campagneresultaten op logboekniveau met de segmentmetriek van de Manager van de Publiek om segment-centric optimalisaties en een efficiënte kanaalmengeling te informeren.

## Methoden voor gegevensinname {#data-ingestion-methods}

U kunt gegevens naar [!DNL Audience Manager] voor gebruik in deze rapporten door één van beide methodes verzenden. Soms verzenden klanten gegevens via beide methoden. Zo zorgt u ervoor dat uw rapporten de meest uitgebreide en nauwkeurige informatie over een bezoeker bevatten. Om de [!UICONTROL Audience Optimization] rapporten te gebruiken, moet uw gebeurtenisvraag *alle* parameters omvatten die in het [Overzicht en Toewijzingen voor de documentatie van de Dossiers](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) van Meta-gegevens worden vermeld. U kunt gegevens verzenden via de volgende hieronder vermelde methoden.

* Pixelaanroepen: Om de vereiste meta-gegevensparameters over te gaan om [!DNL Audience Manager] het Vastleggen Campagne te zien klik Gegevens via de Vraag [van het Pixel en het](../../../integration/media-data-integration/click-data-pixels.md) Vastleggen van de Gegevens van de Bedrukking van de Campagne via de Vraag [](../../../integration/media-data-integration/impression-data-pixels.md)van het Pixel.

* Gegevensbestanden: Als u deze rapporten wilt gebruiken om uw eigen gegevens of gegevens van een bron te analyseren die niet met geïntegreerd is, moet u gegevens en meta-gegevensdossiers voor die gegevens tot stand brengen en uploaden. [!DNL Audience Manager] Voor meer informatie, zie de Dossiers van [Gegevens voor de Rapporten](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) van de Optimalisering van de Publiek en [Gegevens en de Dossiers van Meta-gegevens voor de Rapporten](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)van de Optimalisering van de Publiek.

## Rolgebaseerde toegangscontroles (RBAC) {#rbac}

Het type rapporten u kunt bekijken hangt van de [!UICONTROL RBAC] groep af u aan wordt toegewezen. Zie [Beleid](../../../features/administration/administration-overview.md) en [creeer een Groep](../../../features/administration/administration-overview.md#create-group) voor meer informatie.

[!UICONTROL RBAC] groepen moeten bepaalde gegevensbronnen hebben opgezet om de [!UICONTROL Audience Optimization] rapporten te bekijken. Uw [!DNL Audience Manager] consultant stelt deze gegevensbronnen voor u in. De meer gegevensbronnen in elke [!UICONTROL RBAC] gebruikersgroep, meer gegevens die groepsleden toegang tot zullen hebben. Uw consultant stelt ten minste een van deze gegevensbronnen in:

* Gegevensbron van adverteerder
* Brand-gegevensbron
* Gegevensbron van platform

Gebruikers die tot meer dan één [!UICONTROL RBAC] gebruikersgroep behoren, kunnen schakelen tussen de weergave van elke groep. De weergegeven gegevens worden bijgewerkt met inachtneming van de geselecteerde groep. Als uw bedrijf niet gebruikt [!UICONTROL RBAC], zullen alle gebruikers beheervoorrechten en toegang tot alle gegevensbronnen (omzettingsgroepen) hebben.

## Conversiegroepen {#conversion-groups}

In de [!UICONTROL Audience Optimization] rapporten, **[!UICONTROL Conversion Groups]** zijn synoniem met gegevensbronnen die minstens één omzettingseigenschap bevatten. Gegevensbronnen die niet ten minste één conversietekenmerk bevatten, komen niet voor in de [!UICONTROL Audience Optimization] rapporten. U kunt de omzettingskenmerken voor conversiegroepen bekijken in het rapport [Gerapporteerde omzettingen](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) .
