---
description: Audience Optimization voor adverteerders kan u helpen potentiële prestatiemogelijkheden voor de segmenten van de Audience Manager in uw betaalde mediacampagnes te identificeren. In deze rapporten worden de gegevens van de campagneresultaten op het niveau van het logbestand gecombineerd met de gegevens van het Audience Manager-segment om op segment gerichte optimalisaties en een effectieve kanaalmix te informeren.
seo-description: Audience Optimization voor adverteerders kan u helpen potentiële prestatiemogelijkheden voor de segmenten van de Audience Manager in uw betaalde mediacampagnes te identificeren. In deze rapporten worden de gegevens van de campagneresultaten op het niveau van het logbestand gecombineerd met de gegevens van het Audience Manager-segment om op segment gerichte optimalisaties en een effectieve kanaalmix te informeren.
seo-title: Audience Optimization voor adverteerders
solution: Audience Manager
title: Audience Optimization voor adverteerders
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 2%

---

# [!UICONTROL Audience Optimization] voor adverteerders{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] voor Advertisers kunt u helpen potentiële prestatiemogelijkheden voor de segmenten van de Audience Manager over uw betaalde media campagnes identificeren. In deze rapporten worden de gegevens van de campagneresultaten op logboekniveau gecombineerd met de Audience Manager [!UICONTROL segment]-meetwaarden om op segment gerichte optimalisaties en een effectieve kanaalmix te informeren.

## Methoden voor gegevensinname {#data-ingestion-methods}

U kunt gegevens naar [!DNL Audience Manager] voor gebruik in deze rapporten door één van beide methodes verzenden. Soms verzenden klanten gegevens via beide methoden. Zo zorgt u ervoor dat uw rapporten de meest uitgebreide en nauwkeurige informatie over een bezoeker bevatten. Als u de [!UICONTROL Audience Optimization]-rapporten wilt gebruiken, moet uw gebeurtenisaanroep *all* van de parameters bevatten die worden vermeld in de [Overzicht en toewijzingen voor metagegevensbestanden](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md)-documentatie. U kunt gegevens verzenden via de volgende hieronder vermelde methoden.

* Pixelaanroepen: Als u de vereiste metagegevensparameters wilt doorgeven aan [!DNL Audience Manager], zie [Campagne vastleggen, klikt u op Gegevens via Pixelaanroepen](../../../integration/media-data-integration/click-data-pixels.md) en [Campagne-indrukgegevens vastleggen via Pixelaanroepen](../../../integration/media-data-integration/impression-data-pixels.md).

* Gegevensbestanden: Als u deze rapporten wilt gebruiken om uw eigen gegevens of gegevens uit een bron te analyseren die niet met [!DNL Audience Manager] geïntegreerd is, moet u gegevens en meta-gegevensdossiers voor die gegevens tot stand brengen en uploaden. Zie [Gegevensbestanden voor Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) en [Gegevens- en metagegevensbestanden voor Audience Optimization Reports](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) voor meer informatie.

## [!UICONTROL Role-Based Access Controls] (RBAC)  {#rbac}

Het type rapporten u kunt bekijken hangt van de [!UICONTROL RBAC] groep af u aan wordt toegewezen. Zie [Beheer](../../../features/administration/administration-overview.md) en [Een groep maken](../../../features/administration/administration-overview.md#create-group) voor meer informatie.

[!UICONTROL RBAC] groepen moeten bepaalde gegevensbronnen hebben opgezet om de  [!UICONTROL Audience Optimization] rapporten te bekijken. Uw [!DNL Audience Manager] consultant stelt deze [!UICONTROL data sources] voor u in. Hoe meer [!UICONTROL data sources] in elke [!UICONTROL RBAC] gebruikersgroep, hoe meer gegevens die groepsleden toegang hebben. Uw consultant stelt ten minste een van deze [!UICONTROL data sources] in:

* Adverteerder [!UICONTROL data source ]
* Merk [!UICONTROL data source]
* Platform [!UICONTROL data source]

Gebruikers die tot meer dan één [!UICONTROL RBAC] gebruikersgroep behoren, kunnen tussen de mening van elke groep schakelen. De weergegeven gegevens worden bijgewerkt met inachtneming van de geselecteerde groep. Als uw bedrijf [!UICONTROL RBAC] niet gebruikt, hebben alle gebruikers beheerdersrechten en toegang tot alle [!UICONTROL data sources] (conversiegroepen).

## Conversiegroepen {#conversion-groups}

In de [!UICONTROL Audience Optimization] rapporten, **[!UICONTROL Conversion Groups]** zijn synoniem met [!UICONTROL data sources] die minstens één omzettingseigenschap bevatten. [!UICONTROL Data sources] die niet ten minste één omzettingskenmerk bevatten, worden niet in de  [!UICONTROL Audience Optimization] rapporten vermeld. U kunt de omzettingskenmerken voor omzettingsgroepen in [Gerapporteerde Traits van de Omzetting](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) rapport bekijken.
