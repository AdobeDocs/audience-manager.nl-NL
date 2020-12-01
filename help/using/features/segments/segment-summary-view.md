---
description: De segmentsummiere pagina toont details zoals naam, eigenschappen in het segment, regels, prestatiesgegevens, en de informatie van de bestemmingstoewijzing.
seo-description: De segmentsummiere pagina toont details zoals naam, eigenschappen in het segment, regels, prestatiesgegevens, en de informatie van de bestemmingstoewijzing.
seo-title: Pagina Segmentdetails
solution: Audience Manager
title: Pagina Segmentdetails
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 0%

---


# Pagina met segmentdetails {#segment-summary-view}

De detailspagina voor een individueel segment verstrekt een overzicht van de segmentdetails, zoals de segmentnaam, identiteitskaart, prestatiesmetriek, regels die het segment, en de bestemmingstoewijzingen bepalen. Als u deze details wilt weergeven, gaat u naar **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** en klikt u op de naam van het segment waarmee u wilt werken.

## Segmentbeheertools {#segment-management-tools}

De bovenkant van de pagina van de segmentdetails bewaart de hulpmiddelen die u kunt gebruiken om uw segmenten te beheren:

1. **[!UICONTROL Add New]**: Met deze optie activeert u de segmenten  [!UICONTROL Segment Builder] en maakt u nieuwe segmenten.
2. **[!UICONTROL Edit]**: Gebruik deze optie om de configuratie van het huidige segment te wijzigen.
3. **[!UICONTROL Duplicate]**: Gebruik deze optie om een kopie van het huidige segment te maken.
4. **[!UICONTROL Delete]**: Gebruik deze optie om het huidige segment uit uw rekening van de Audience Manager te verwijderen.
5. **[!UICONTROL Marketplace Recommendations]**: Met deze optie kunt u vergelijkbare segmenten vinden als de segmenten die u bekijkt, op basis van  [!UICONTROL Audience Marketplace] gegevensfeeds waarop u geen abonnement hebt. Zie [Audience Marketplace voor de Kopers van Gegevens](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) om te leren hoe te om de Marketplace te navigeren en gelijkaardige segmenten te vinden.

![basissegmentinformatie](assets/basic-segment-information.png)

## Segmentinformatie {#basics}

Onder de hulpmiddelen van het segmentbeheer kunt u de volgende segmentinformatie vinden:

1. **[!UICONTROL Basic Information]:** Hiermee geeft u de vereiste en optionele details weer die bij het maken van het segment zijn opgegeven. Zie [Segment Builder](segment-builder.md) voor een gedetailleerd overzicht van wat deze gebieden betekenen.
2. **[!UICONTROL Segment Graph]:** Hier worden de prestatiegegevens grafisch weergegeven en voor vaste intervallen van 1, 7, 14, 30, 60 en 90 dagen. Wij verklaren segmentpopulatieaantallen in [afzonderlijk artikel](../../features/segments/segment-builder-data.md).

   ![segmentgrafiek](assets/segment-graph.png)

3. **[!UICONTROL Identity Type Breakdown ]:** Het rapport toont het aantal mensen of huishoudens die voor een segment in aanmerking komen door het aantal dwars-apparaat IDs en/of Externe identiteitskaart van de Grafiek van het Apparaat te tellen die met de apparaten verbonden zijn die voor het segment (aangetoond door  [!UICONTROL Total Segment Population]) kwalificeren. De apparaat-id&#39;s en externe apparaatgrafiek-id&#39;s die in dit rapport worden weergegeven, worden gebruikt om profielen samen te voegen met de regel voor het samenvoegen van profielen die het segment gebruikt. Dit rapport wordt alleen weergegeven als u een apparaatgegevensbron of een externe apparaatgrafiek hebt geselecteerd in de regel voor het samenvoegen van profielen die het segment gebruikt.

   ![segmentgrafiek](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager toont slechts [!UICONTROL Identity Type Breakdown] rapport als u dwars-apparaat IDs voor het segment gekwalificeerd hebt.

   Bekijk de video hieronder voor een overzicht van [!UICONTROL Identity Type Breakdown].
   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

4. **[!UICONTROL Segment Rules]:** Maakt een lijst van eigenschappen in het segment samen met kwalificatieregels.
5. **[!UICONTROL Destination Mappings]:** Vermeldt bestemmingstoewijzingen voor het segment.
6. **[!UICONTROL Management Tools]:** Controles die u, segmenten tot stand laten brengen uitgeven, klonen en schrappen.