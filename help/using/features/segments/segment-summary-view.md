---
description: De segmentsummiere pagina toont details zoals naam, eigenschappen in het segment, regels, prestatiesgegevens, en de informatie van de bestemmingstoewijzing.
seo-description: The segment summary page displays details such as name, traits in the segment, rules, performance data, and destination mapping information.
seo-title: Segment Details Page
solution: Audience Manager
title: Pagina Segmentdetails
uuid: e844e423-9701-42d4-9ba5-d82f41358adc
keywords: Onderverdeling van identiteitstype, identiteitsonderbreking, publieksidentificatierapportage, apparaatoverschrijdende id, apparaat-id
feature: Segments
exl-id: d33c8146-fd98-47fc-aa3d-96f002538df4
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 0%

---

# Pagina Segmentdetails {#segment-summary-view}

De detailspagina voor een individueel segment verstrekt een overzicht van de segmentdetails, zoals de segmentnaam, identiteitskaart, prestatiesmetriek, regels die het segment, en de bestemmingstoewijzingen bepalen. Als u deze details wilt weergeven, gaat u naar **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** en klikt u op de naam van het segment waarmee u wilt werken.

## Segmentbeheertools {#segment-management-tools}

De bovenkant van de pagina van de segmentdetails bewaart de hulpmiddelen die u kunt gebruiken om uw segmenten te beheren:

1. **[!UICONTROL Add New]**: Gebruik deze optie om [!UICONTROL Segment Builder] te activeren en nieuwe segmenten te maken.
2. **[!UICONTROL Edit]**: Gebruik deze optie om de configuratie van het huidige segment te wijzigen.
3. **[!UICONTROL Duplicate]**: Gebruik deze optie om een kopie van het huidige segment te maken.
4. **[!UICONTROL Delete]**: Gebruik deze optie om het huidige segment uit uw Audience Manager-account te verwijderen.
5. **[!UICONTROL Marketplace Recommendations]**: met deze optie kunt u zoeken naar segmenten die vergelijkbaar zijn met de segmenten die u bekijkt, vanuit [!UICONTROL Audience Marketplace] -gegevensfeeds waarop u geen abonnement hebt. Zie [&#x200B; Audience Marketplace voor de Kopers van Gegevens &#x200B;](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) leren hoe te om de Marketplace te navigeren en gelijkaardige segmenten te vinden.

![&#x200B; basis-segment-informatie &#x200B;](assets/basic-segment-information.png)

## Segmentinformatie {#basics}

Onder de hulpmiddelen van het segmentbeheer kunt u de volgende segmentinformatie vinden:

1. **[!UICONTROL Basic Information]:** toont vereiste en facultatieve details die bij de verwezenlijking van het segment werden gespecificeerd. Zie {de Bouwer van het 0} Segment [&#x200B; voor een gedetailleerd overzicht van wat deze gebieden betekenen.](segment-builder.md)
1. **[!UICONTROL Segment Graph]:** geeft prestatiegegevens grafisch weer en voor vaste intervallen van 1, 7, 14, 30, 60 en 90 dagen. Wij verklaren segmentpopulatieaantallen in a [&#x200B; afzonderlijk artikel &#x200B;](../../features/segments/segment-builder-data.md).

   ![&#x200B; segmenten-grafiek &#x200B;](assets/segment-graph.png)

1. **[!UICONTROL Identity Type Breakdown]:** het rapport toont het aantal mensen of huishoudens die voor een segment door het aantal dwars-apparaat IDs en/of Externe identiteitskaart van de Grafiek van het Apparaat te tellen die met de apparaten verbonden zijn die voor het segment (die door [!UICONTROL Total Segment Population] worden getoond) kwalificeren. De apparaat-id&#39;s en externe apparaatgrafiek-id&#39;s die in dit rapport worden weergegeven, worden gebruikt om profielen samen te voegen met de regel voor het samenvoegen van profielen die het segment gebruikt. Dit rapport wordt alleen weergegeven als u een apparaatgegevensbron of een externe apparaatgrafiek hebt geselecteerd in de regel voor het samenvoegen van profielen die het segment gebruikt.

   ![&#x200B; segmenten-grafiek &#x200B;](assets/segment-type.png)

   >[!NOTE]
   >
   >Audience Manager geeft het [!UICONTROL Identity Type Breakdown] -rapport alleen weer als u id&#39;s voor alle apparaten hebt die voor het segment zijn gekwalificeerd.

   Bekijk de onderstaande video voor een overzicht van [!UICONTROL Identity Type Breakdown] .

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

1. **[!UICONTROL Segment Rules]:** maakt een lijst van eigenschappen in het segment samen met kwalificatieregels.
1. **[!UICONTROL Destination Mappings]:** maakt een lijst van bestemmingstoewijzingen voor het segment.
1. **[!UICONTROL Management Tools]:** Controles die u, segmenten tot stand laten brengen uitgeven, klonen en schrappen.
