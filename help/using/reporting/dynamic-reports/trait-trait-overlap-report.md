---
description: Retourneert gegevens over het aantal unieke gebruikers dat wordt gedeeld door al uw eerste en externe kenmerken.
seo-description: Retourneert gegevens over het aantal unieke gebruikers dat wordt gedeeld door al uw eerste en externe kenmerken.
seo-title: Overlaprapport Eigenschap-naar-eigenschap
solution: Audience Manager
title: Overlaprapport Eigenschap-naar-eigenschap
uuid: 7fb3fc9e-0e0b-492a-9c3a-04356afb19c7
feature: Overlap Reports
exl-id: cbc933bb-f2af-4ad0-8eb9-cbec1ee952e0
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '489'
ht-degree: 8%

---

# Overlaprapport Eigenschap-naar-eigenschap{#trait-to-trait-overlap-report}

Retourneert gegevens over het aantal unieke gebruikers dat wordt gedeeld door al uw eerste en externe kenmerken.

>[!NOTE]
>
>De overlappende verslagen in Audience Manager houden zich aan de RBAC-beginselen. U kunt slechts eigenschappen van gegevensbronnen zien die u toegang tot gebaseerd op [RBAC Gebruikersgroep](/help/using/features/administration/administration-overview.md) hebt dat u tot behoort.

<!-- 

c_overlap_reports.xml

 -->

## Overzicht

Het [!UICONTROL Trait-to-Trait Overlap] rapport keert gegevens over het % van unieke gebruikers terug die tussen al uw eigen eigenschappen en uw derdeeigenschappen worden gedeeld. Dit rapport helpt u als een optimalisatiehulpmiddel:

* Maak segmenten met een hoge of lage overlapping, afhankelijk van uw behoeften. Traits met hoge overlap geven u een doelgroep, maar minder unieke bezoekers. Traits met een lage overlapping kunnen nuttig zijn om een grotere, unieke bezoekersset te bereiken.
* Taakgegevens van derden valideren: De sterke overlapping tussen gelijkaardige eerste en derdeeigenschappen wijst erop dat het bezit van uw gegevenspartner nauwkeurig en betrouwbaar is. Omgekeerd kan een lage overlapping erop wijzen dat een derdetekenmerk misschien niet de zelfde informatie zoals uw eigen, gelijkaardige eerstepartijeigenschap kan bevatten.
* Vind onverwachte overlapping tussen eigenschappen en gebruik die informatie om innovatieve segmenten te bouwen.

## Voorbeeldrapport

De volgende illustratie verstrekt een overzicht op hoog niveau van elementen in het [!UICONTROL Trait-to-Trait Overlap] rapport.

>[!NOTE]
>
>Het [!UICONTROL Trait-to-Trait Overlap] rapport keert een leeg gebied terug wanneer het de zelfde eigenschap aan zich vergelijkt.

![](assets/trait-to-trait-overlap.png)

## Omlaag boren op individuele gegevenspunten

Selecteer een afzonderlijk punt om de gegevensdetails in een pop-upvenster weer te geven. Uw klikacties werken automatisch gegevens bij die in het rapport worden getoond.

## Trait-to-Trait Overlap Data Pop Fields gedefinieerd {#field-definitions}

Beschrijft de metriek die in popup venster wordt getoond wanneer u een individueel gegevenspunt klikt.

<!-- 

r_t2t_data_pop.xml

 -->

De pop-up voor het [!UICONTROL Trait-to-Trait Overlap] rapport bevat de hieronder metriek. Merk op dat uniques metrisch in de lijst uw *real-time gebruikers* vertegenwoordigt.

<table id="table_A2A0CFC47C1A404994B82E6630E711A2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrisch </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlappen %</span></b> </td> 
   <td colname="col2"> Hiermee wordt het % van de unieke overlapping tussen de vergeleken kenmerken weergegeven (overlappende uniques/trait uniques). </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Type gegevensbron</span></b> </td> 
   <td colname="col2">Hiermee definieert u het type gegevensbron waartoe een eigenschap behoort. Kan zijn: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Eerste partij (uw eigen eigenschap). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Derden (van een externe gegevenspartner/leverancier). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlappende Tray-id</span></b> </td> 
   <td colname="col2"> Unieke numerieke id voor de overlappende eigenschap. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlappende tracknaam</span></b> </td> 
   <td colname="col2"> Naam van de overlappende eigenschap. </td> 
  </tr>
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Taaknummer 2</span></b> </td> 
   <td colname="col2"> Unieke numerieke id voor de eigenschap in uw basisgegevensbron. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Naam dienstreis 2</span></b> </td> 
   <td colname="col2"> Naam van het kenmerk in de basisgegevensbron. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniques overlappen</span></b> </td> 
   <td colname="col2"> <p>Audience Manager gebruikt de volgende formule om overlap % te verkrijgen:</p> <p>Overlappende Uniques / (Base trait Uniques + Overlapping trait Uniques - Overlappende Uniques)</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Overlappende standaardinstellingen</span></b> </td> 
   <td colname="col2"> Het aantal unieke bezoekers van de overlappende eigenschap. </td> 
  </tr> 
    <tr> 
   <td colname="col1"><b><span class="wintitle"> Basistrekken Uniques</span></b> </td> 
   <td colname="col2"> Het aantal unieke bezoekers vanaf de basiseigenschap. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Resultaten van filterrapporten met dataregelaars](../../reporting/dynamic-reports/data-sliders.md)
>* [Vormen, kleuren en grootten die worden gebruikt in dynamische rapporten](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Verklaarde pictogrammen en gereedschappen rapporteren](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Overlaprapporten: updateplanning en minimale segmentgrootte](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datasampling en foutpercentages in geselecteerde Audience Manager-rapporten...](../../reporting/report-sampling.md)
>* [CSV-bestanden voor overlaprapporten](../../reporting/dynamic-reports/overlap-csv-files.md)

