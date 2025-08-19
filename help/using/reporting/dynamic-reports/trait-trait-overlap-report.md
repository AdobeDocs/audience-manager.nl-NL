---
description: Retourneert gegevens over het aantal unieke gebruikers dat wordt gedeeld door al uw eerste en externe kenmerken.
seo-description: Returns data on the number of unique users shared among all your first and third-party traits.
seo-title: Trait-to-Trait Overlap Report
solution: Audience Manager
title: Rapport overlappingen trait-to-Trait
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
source-git-commit: 6cc1351c3a84d4d2219f33ef6175f182b9641377
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 4%

---

# Rapport overlappingen trait-to-Trait{#trait-to-trait-overlap-report}

Retourneert gegevens over het aantal unieke gebruikers dat wordt gedeeld door al uw eerste en externe kenmerken.

>[!NOTE]
>
>De overlappende rapporten in Audience Manager houden zich aan de RBAC-beginselen. U kunt slechts sporen van gegevensbronnen zien die u toegang tot hebt gebaseerd op de [ RBAC Gebruikersgroep ](/help/using/features/administration/administration-overview.md) die u tot behoort.

<!-- 

c_overlap_reports.xml

 -->

## Overzicht

Het rapport [!UICONTROL Trait-to-Trait Overlap] retourneert gegevens over het percentage unieke gebruikers dat wordt gedeeld tussen al uw eigen kenmerken en uw externe kenmerken. Dit rapport helpt u als een optimalisatiehulpmiddel:

* Maak segmenten met een hoge of lage overlapping, afhankelijk van uw behoeften. Traits met hoge overlap geven u een doelgroep, maar minder unieke bezoekers. Traits met een lage overlapping kunnen nuttig zijn om een grotere, unieke bezoekersset te bereiken.
* Valideer gegevens van de derdelandeneigenschap: De sterke overlapping tussen gelijkaardige eerste en derdeeigenschappen wijst erop dat het bezit van uw gegevenspartner nauwkeurig en betrouwbaar is. Omgekeerd kan een lage overlapping erop wijzen dat een derdetekenmerk misschien niet de zelfde informatie zoals uw eigen, gelijkaardige eerstepartijeigenschap kan bevatten.
* Vind onverwachte overlapping tussen eigenschappen en gebruik die informatie om innovatieve segmenten te bouwen.

## Voorbeeldrapport

De volgende afbeelding biedt een overzicht op hoog niveau van elementen in het [!UICONTROL Trait-to-Trait Overlap] -rapport.

>[!NOTE]
>
>Het rapport [!UICONTROL Trait-to-Trait Overlap] retourneert een leeg veld wanneer dezelfde eigenschap wordt vergeleken met zichzelf.

>[!NOTE]
>
>De eigenschappen van de omslag zijn niet beschikbaar voor vergelijking binnen de eigenschap-aan-lijn overlappende rapporten. Door een segment te creëren die een bepaald omslagspoor gebruiken, kunt u analyse via het [ segment-aan-lijn overlappen rapport ](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md) uitvoeren.

![](assets/trait-to-trait-overlap.png)

## Omlaag boren op individuele gegevenspunten

Selecteer een afzonderlijk punt om de gegevensdetails in een pop-upvenster weer te geven. Uw klikacties werken automatisch gegevens bij die in het rapport worden getoond.

## Gedefinieerde velden van pop-upvelden overlappende gegevens overtrekken naar overtrek {#field-definitions}

Beschrijft de metriek die in popup venster wordt getoond wanneer u een individueel gegevenspunt klikt.

<!-- 

r_t2t_data_pop.xml

 -->

De pop-up voor het [!UICONTROL Trait-to-Trait Overlap] rapport bevat de hieronder metriek. Merk op dat uniques metrisch in de lijst uw *gebruikers in real time* vertegenwoordigt.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrisch </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlap % </span></b> </td> 
   <td colname="col2"> Hiermee wordt het % van de unieke overlapping tussen de vergeleken kenmerken weergegeven (overlappende uniques/trait uniques). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Source-gegevenstype voor gegevens </span></b> </td> 
   <td colname="col2">Hiermee definieert u het type gegevensbron waartoe een eigenschap behoort. Kan zijn: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Eerste partij (uw eigen eigenschap). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Derden (van een externe gegevenspartner/leverancier). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlappende Trait-id </span></b> </td> 
   <td colname="col2"> Unieke numerieke id voor de overlappende eigenschap. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlappende naam overtrek </span></b> </td> 
   <td colname="col2"> Naam van de overlappende eigenschap. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait ID 2 </span></b> </td> 
   <td colname="col2"> Unieke numerieke id voor de eigenschap in uw basisgegevensbron. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Naam track 2 </span></b> </td> 
   <td colname="col2"> Naam van het kenmerk in de basisgegevensbron. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniques overlappen </span></b> </td> 
   <td colname="col2"> <p>Audience Manager gebruikt de volgende formule om overlap % te verkrijgen:</p> <p>Overlappende Uniques / (Base trait Uniques + Overlapping trait Uniques - Overlappende Uniques)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlappende Trait Uniques </span></b> </td> 
   <td colname="col2"> Het aantal unieke bezoekers van de overlappende eigenschap. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniques voor basistrekken </span></b> </td> 
   <td colname="col2"> Het aantal unieke bezoekers vanaf de basiseigenschap. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Resultaten van filterrapporten met dataregelaars](../../reporting/dynamic-reports/data-sliders.md)
>* [ Vormen, Kleuren, en Grootte die in Dynamische Rapporten ](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes) worden gebruikt
>* [ Verklaarde pictogrammen en Hulpmiddelen van het 0&rbrace; Rapport &lbrace;](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Overlaprapporten: updateplanning en minimale segmentgrootte](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [ de Steekproef van Gegevens en de Tarieven van de Fout in de Geselecteerde Rapporten van Audience Manager... ](../../reporting/report-sampling.md)
>* [CSV-bestanden voor overlaprapporten](../../reporting/dynamic-reports/overlap-csv-files.md)
