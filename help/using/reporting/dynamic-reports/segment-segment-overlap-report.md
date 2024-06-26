---
description: Retourneert gegevens over het aantal unieke gebruikers dat wordt gedeeld tussen uw segmenten.
seo-description: Returns data on how many unique users are shared between your segments.
seo-title: Segment-to-Segment Overlap Report
solution: Audience Manager
title: Overlaprapport Segment-naar-segment
uuid: 0339eb6c-6355-44a3-9c46-f159485449d1
feature: Overlap Reports
exl-id: 43a8ea20-3197-4623-a03a-bfe40e5049cd
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 10%

---

# Overlaprapport Segment-naar-segment{#segment-to-segment-overlap-report}

Retourneert gegevens over het aantal unieke gebruikers dat wordt gedeeld tussen uw segmenten.

>[!NOTE]
>
>De overlappende verslagen in Audience Manager houden zich aan de RBAC-beginselen. U kunt segmenten van gegevensbronnen slechts zien die u toegang hebt tot gebaseerd op [RBAC-gebruikersgroep](/help/using/features/administration/administration-overview.md) dat u tot behoort.

<!-- 

c_segment_segment_overlap.xml

 -->

## Overzicht

De [!UICONTROL Segment-to-Segment Overlap] het rapport kan u helpen:

* Identificeer segmenten met hoge of lage overlapping, afhankelijk van uw behoeften. Traits met hoge overlap geven u een doelgroep, maar minder unieke bezoekers. Traits met een lage overlapping kunnen nuttig zijn om een grotere, unieke bezoekersset te bereiken.
* Vind onverwachte overlapping en gebruik die informatie om nieuwe, krachtige segmenten te bouwen.

## Voorbeeldrapport

De volgende illustratie biedt een overzicht op hoog niveau van de [!UICONTROL Segment-to-Segment Overlap] verslag.

>[!NOTE]
>
>De [!UICONTROL Segment-to-Segment Overlap] het rapport keert een leeg gebied terug wanneer het het zelfde segment aan zich vergelijkt.

![](assets/segment-to-segment-overlap.png)

## Omlaag boren op individuele gegevenspunten

Selecteer een afzonderlijk punt om de gegevensdetails in een pop-upvenster weer te geven. Uw klikacties werken automatisch gegevens bij die in het rapport worden getoond.

## Gedefinieerde velden van gegevenspop-item-overlap {#fields-defined}

<!-- 

r_s2s_data_pop.xml

 -->

De pop-up voor de [!UICONTROL Segment-to-Segment Overlap] rapport bevat de onderstaande meetgegevens. Merk op dat de unieke metrische waarde in de tabel uw *realtime gebruikers*.

| Metrisch | Beschrijving |
|---|---|
| **[!UICONTROL Base Segment ID]** | Unieke numerieke id voor het segment dat in de rapportresultaten wordt weergegeven. Wordt weergegeven als rij-id voor het segment. |
| **[!UICONTROL Base Segment Name]** | Naam van het segment dat in de rij van de rapportresultaten verschijnt. |
| **[!UICONTROL Overlapping Segment ID]** | Unieke numerieke id voor het segment dat u selecteert wanneer u het rapport uitvoert. Wordt weergegeven als kolom-id voor het segment. |
| **[!UICONTROL Overlapping Segment Name]** | Naam van het segment u selecteert wanneer het runnen van het rapport. Verschijnt in de kolom van de rapportresultaten. |
| **[!UICONTROL Base Segment Uniques]** | Het aantal unieke bezoekers in uw basissegment. |
| **[!UICONTROL Base Segment Uniques]** | Het aantal unieke bezoekers in uw overlappende segment. |
| **[!UICONTROL Overlapping Uniques]** | Het aantal unieke bezoekers dat wordt gedeeld tussen de vergeleken segmenten. |
| **[!UICONTROL Overlap %]** | Audience Manager gebruikt de volgende formule om overlap % te verkrijgen: Overlappende Uniques / (Base Segment Uniques + Overlappende Segment Uniques - Overlappende Uniques) |



>[!MORELIKETHIS]
>
>* [Resultaten van filterrapporten met dataregelaars](../../reporting/dynamic-reports/data-sliders.md)
>* [Vormen, kleuren en grootten die worden gebruikt in interactieve rapporten](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Verklaarde pictogrammen en gereedschappen rapporteren](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Overlaprapporten: updateplanning en minimale segmentgrootte](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datasampling en foutpercentages in geselecteerde Audience Manager-rapporten...](../../reporting/report-sampling.md)
>* [CSV-bestanden voor overlaprapporten](../../reporting/dynamic-reports/overlap-csv-files.md)

