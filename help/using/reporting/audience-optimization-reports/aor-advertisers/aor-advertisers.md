---
description: Audience Optimization voor adverteerders kan u helpen potentiële prestatiemogelijkheden voor de segmenten van de Audience Manager in uw betaalde mediacampagnes te identificeren. In deze rapporten worden de gegevens van de campagneresultaten op het niveau van het logbestand gecombineerd met de gegevens van het Audience Manager-segment om op segment gerichte optimalisaties en een effectieve kanaalmix te informeren.
seo-description: Audience Optimization for Advertisers can help you identify potential performance opportunities for Audience Manager segments across your paid media campaigns. These reports combine log-level campaign performance data with Audience Manager segment metrics to inform segment-centric optimizations and an effective channel mix.
seo-title: Audience Optimization for Advertisers
solution: Audience Manager
title: Audience Optimization voor adverteerders
uuid: 852d550e-3c7f-4750-9abc-365c3a6f7883
feature: Audience Optimization Reports
exl-id: 13595778-3d3a-4c83-a84f-4bc3af1ee367
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '406'
ht-degree: 0%

---

# [!UICONTROL Audience Optimization] voor adverteerders{#audience-optimization-for-advertisers}

[!UICONTROL Audience Optimization] voor Advertisers kunt u helpen potentiële prestatiemogelijkheden voor de segmenten van de Audience Manager over uw betaalde media campagnes identificeren. Deze rapporten combineren de gegevens van campagneprestaties op logboekniveau met Audience Manager [!UICONTROL segment] metriek om segment-centric optimalisaties en een efficiënte kanaalmengeling te informeren.

## Methoden voor gegevensinname {#data-ingestion-methods}

U kunt gegevens verzenden naar [!DNL Audience Manager] voor gebruik in deze rapporten door een van deze methoden. Soms verzenden klanten gegevens via beide methoden. Zo zorgt u ervoor dat uw rapporten de meest uitgebreide en nauwkeurige informatie over een bezoeker bevatten. Als u de opdracht [!UICONTROL Audience Optimization] rapporten, uw gebeurtenisvraag moet omvatten *alles* van de in de [Overzicht en toewijzingen voor metagegevensbestanden](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) documentatie. U kunt gegevens verzenden via de volgende hieronder vermelde methoden.

* Pixelaanroepen: De vereiste metagegevensparameters doorgeven aan [!DNL Audience Manager] zie [Het vangen van Campagne klikt Gegevens via de Vraag van het Pixel](../../../integration/media-data-integration/click-data-pixels.md) en [Vastleggen van Campagne-indrukgegevens via pixelaanroepen](../../../integration/media-data-integration/impression-data-pixels.md).

* Gegevensbestanden: Als u deze rapporten wilt gebruiken om uw eigen gegevens of gegevens uit een bron te analyseren die niet met geïntegreerd is [!DNL Audience Manager], moet u gegevens- en metagegevensbestanden voor die gegevens maken en uploaden. Zie voor meer informatie [Gegevensbestanden voor Audience Optimization-rapporten](../../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) en [Gegevens- en metagegevensbestanden voor Audience Optimization-rapporten](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md).

## [!UICONTROL Role-Based Access Controls] (RBAC) {#rbac}

Het type rapporten dat u kunt weergeven, is afhankelijk van het dialoogvenster [!UICONTROL RBAC] groep waaraan u bent toegewezen. Zie [Beheer](../../../features/administration/administration-overview.md) en [Een groep maken](../../../features/administration/administration-overview.md#create-group) voor meer informatie .

[!UICONTROL RBAC] groepen moeten bepaalde gegevensbronnen hebben ingesteld om de [!UICONTROL Audience Optimization] rapporten. Uw [!DNL Audience Manager] consultant zal deze [!UICONTROL data sources] voor jou. Hoe meer [!UICONTROL data sources] in elke [!UICONTROL RBAC] gebruikersgroep, de meer gegevens die die groepsleden toegang tot zullen hebben. Uw consultant stelt minimaal een van deze [!UICONTROL data sources]:

* Adverteerder [!UICONTROL data source &#x200B;]
* Merk [!UICONTROL data source]
* Platform [!UICONTROL data source]

Gebruikers die tot meerdere gebruikers behoren [!UICONTROL RBAC] de gebruikersgroep kan tussen de mening van elke groep schakelen. De weergegeven gegevens worden bijgewerkt met inachtneming van de geselecteerde groep. Als uw bedrijf het niet gebruikt [!UICONTROL RBAC], hebben alle gebruikers beheerdersrechten en hebben toegang tot alle [!UICONTROL data sources] (conversiegroepen).

## Conversiegroepen {#conversion-groups}

In de [!UICONTROL Audience Optimization] verslagen, **[!UICONTROL Conversion Groups]** zijn synoniem met [!UICONTROL data sources] die ten minste één omzettingskenmerk bevatten. [!UICONTROL Data sources] die niet ten minste één omzettingskenmerk bevatten, worden niet in de [!UICONTROL Audience Optimization] rapporten. U kunt de conversiekenmerken voor conversiegroepen weergeven in het dialoogvenster [Gerapporteerde omzettingskenmerken](../../../reporting/audience-optimization-reports/aor-advertisers/reported-conversion-traits.md) verslag.
