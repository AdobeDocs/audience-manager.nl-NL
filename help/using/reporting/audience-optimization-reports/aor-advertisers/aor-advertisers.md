---
description: Audience Optimization for Advertisers kan u helpen potentiële prestatiemogelijkheden voor Audience Manager-segmenten in uw betaalde mediacampagnes te identificeren. In deze rapporten worden de gegevens van de campagneresultaten op het niveau van het logbestand gecombineerd met de gegevens van het Audience Manager-segment om de segmentcentrische optimalisatie te bepalen en een effectieve kanaalmix.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization for Advertisers
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---

# [!UICONTROL Audience Optimization] voor adverteerders{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] voor Advertisers kunt u helpen potentiële prestatiemogelijkheden voor de segmenten van Audience Manager in uw betaalde mediacampagnes te identificeren. In deze rapporten worden de prestaties van de campagne op logniveau gecombineerd met Audience Manager [!UICONTROL segment] -meetgegevens om op segment gerichte optimalisaties te ondersteunen en een effectieve kanaalmix.

## Methoden voor gegevensinname {#data-ingestion-methods}

U kunt gegevens naar [!DNL Audience Manager] verzenden voor gebruik in deze rapporten door beide methoden. Soms verzenden klanten gegevens via beide methoden. Zo zorgt u ervoor dat uw rapporten de meest uitgebreide en nauwkeurige informatie over een bezoeker bevatten. Om de [!UICONTROL Audience Optimization] rapporten te gebruiken, moet uw gebeurtenisvraag *alle* van de parameters omvatten die in het [&#x200B; Overzicht en Toewijzingen voor de documentatie van de Dossiers van Meta-gegevens &#x200B;](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) worden vermeld. U kunt gegevens verzenden via de volgende hieronder vermelde methoden.

* De vraag van het pixel: Om de vereiste meta-gegevensparameters tot [!DNL Audience Manager] over te gaan zie [&#x200B; het Vastleggen van Campagne Gegevens van de Klik via de Vraag van het Pixel &#x200B;](../../../integration/media-data-integration/click-data-pixels.md) en [&#x200B; het Vastleggen van de Gegevens van de Impressie van de Campagne via de Vraag van het Pixel &#x200B;](../../../integration/media-data-integration/impression-data-pixels.md).

* Gegevensbestanden: als u deze rapporten wilt gebruiken om uw eigen gegevens of gegevens te analyseren vanuit een bron die niet is geïntegreerd met [!DNL Audience Manager] , moet u gegevens- en metagegevensbestanden voor die gegevens maken en uploaden. Voor meer informatie, zie {de Dossiers van 0} Gegevens voor de Rapporten van Audience Optimization [&#x200B; en &#x200B;](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) Gegevens en de Dossiers van Meta-gegevens voor de Rapporten van Audience Optimization [.](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Het type rapporten dat u kunt weergeven, is afhankelijk van de groep [!UICONTROL RBAC] waaraan u bent toegewezen. Zie [&#x200B; Beleid &#x200B;](../../../features/administration/administration-overview.md) en [&#x200B; creeer een Groep &#x200B;](../../../features/administration/administration-overview.md#create-group) voor meer informatie.

[!UICONTROL RBAC] -groepen moeten bepaalde gegevensbronnen hebben ingesteld om de [!UICONTROL Audience Optimization] -rapporten te kunnen weergeven. Uw [!DNL Audience Manager] consultant stelt deze [!UICONTROL data sources] voor u in. Hoe meer [!UICONTROL data sources] in elke [!UICONTROL RBAC] -gebruikersgroep, des te meer gegevens die groepsleden kunnen gebruiken. Uw consultant stelt minimaal een van deze [!UICONTROL data sources] -opties in:

* Adverteerder [!UICONTROL data source]
* Merk [!UICONTROL data source]
* Platform [!UICONTROL data source]

Gebruikers die tot meer dan één [!UICONTROL RBAC] gebruikersgroep behoren, kunnen schakelen tussen de weergave van elke groep. De weergegeven gegevens worden bijgewerkt met inachtneming van de geselecteerde groep. Als uw bedrijf [!UICONTROL RBAC] niet gebruikt, hebben alle gebruikers beheerdersrechten en toegang tot alle [!UICONTROL data sources] (conversiegroepen).

## Conversiegroepen {#conversion-groups}

In de [!UICONTROL Audience Optimization] -rapporten is **[!UICONTROL Conversion Groups]** gelijk aan [!UICONTROL data sources] die ten minste één omzettingskenmerk bevatten. [!UICONTROL Data sources] die niet ten minste één omzettingskenmerk bevatten, worden niet weergegeven in de [!UICONTROL Audience Optimization] -rapporten. U kunt de omzettingseigenschappen voor omzettingsgroepen in het [&#x200B; Gerapporteerde rapport van de Tanden van de Omzetting &#x200B;](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) bekijken.
