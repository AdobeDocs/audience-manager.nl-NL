---
description: Retourneert gegevens over het aantal unieke gebruikers dat wordt gedeeld tussen een bepaald kenmerk en een volledig segment.
seo-description: Retourneert gegevens over het aantal unieke gebruikers dat wordt gedeeld tussen een bepaald kenmerk en een volledig segment.
seo-title: Overlaprapport Segment-naar-eigenschap
solution: Audience Manager
title: Overlaprapport Segment-naar-eigenschap
uuid: a6b3dd21-332e-449f-aa01-2beb47f1794e
feature: Rapporten overlappen
exl-id: 7ce3dd2d-ab22-46f8-90bf-a32222df2e76
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '832'
ht-degree: 5%

---

# Overlaprapport Segment-naar-eigenschap{#segment-to-trait-overlap-report}

Retourneert gegevens over het aantal unieke gebruikers dat wordt gedeeld tussen een bepaald kenmerk en een volledig segment.

>[!NOTE]
>
>De overlappende verslagen in Audience Manager houden zich aan de RBAC-beginselen. U kunt segmenten en eigenschappen van gegevensbronnen slechts zien die u toegang tot hebt gebaseerd op [RBAC Gebruikersgroep](/help/using/features/administration/administration-overview.md) die u tot behoort.

<!-- 

c_segment_trait_overlap.xml

 -->

## Overzicht

Als optimalisatiehulpmiddel, [!UICONTROL Segment to Trait Overlap] helpt de rapporten u hoogst geconcentreerde segmenten bouwen of segmentbereik uitbreiden. U kunt bijvoorbeeld gerichte segmenten en kenmerken met een hoge overlapping maken om een bepaald publiek te bereiken. Veel overlappingen kunnen echter leiden tot minder unieke gebruikers (minder bereik). Het runnen van dit rapport helpen bereiken uitbreiden door eigenschappen met veel segmentoverlapping te verwijderen en hen te vervangen met eigenschappen die minder overlapping hebben.

### Voorbeeldrapport

De volgende illustratie verstrekt een overzicht op hoog niveau van het [!UICONTROL Segment-to-Trait Overlap] rapport.

![](assets/segment-to-trait-overlap.png)

### Omlaag boren op individuele gegevenspunten

Selecteer een afzonderlijk punt om de gegevensdetails in een pop-upvenster weer te geven. Uw klikacties werken automatisch gegevens bij die in het rapport worden getoond.

## Segmenten vergelijken met sporen {#comparing-segments-to-traits}

Beschrijft hoe u segmenten en eigenschappen kunt vergelijken om betekenisvolle informatie uit de resultaten af te leiden.

<!-- 

c_compare_s2t.xml

 -->

### Vergelijking van Trait en Segment Uniques: Een voorbeeld

Op het eerste gezicht lijkt het misschien onlogisch om segmenten met kenmerken te vergelijken en te proberen conclusies te trekken uit de resultaten. De segmenten en de kenmerken zijn immers verschillend, zodat hoe kunnen de gegevens die uit verschillende punten worden afgeleid betekenis hebben? Nochtans, in dit geval, vergelijken wij geen eigenschappen en segmenten, maar het aantal unieke bezoekers die tussen hen worden gedeeld. Het gedeelde unieke aantal bezoekers levert de gemeenschappelijke waarde op die een segment mogelijk maakt om een vergelijking tussen de kenmerken te maken.

Het volgende diagram illustreert de relatie tussen een eigenschap en het segment waartoe het behoort. In dit geval hebben we een kenmerk met 10 bezoekers en een segment met 1000 bezoekers. Ze hebben 3 unieke bezoekers gemeen.

![](assets/s2t.png)

Het unieke aantal bezoekers is de algemene constante waarde die door deze verschillende klassen van objecten wordt gedeeld. Hierdoor kunt u de unieke relatie tussen de bezoekers als volgt bepalen:

* Het traject deelt 30% van zijn unieke bezoekers met het segment (3/10 = 0,30).
* Het segment deelt 0,3% van zijn unieke bezoekers met de eigenschap (3/1.000 = 0,003)

### Waarde zoeken in Segment om te zoeken naar Vergelijkingen

Als u de overlapping tussen kenmerken en segmenten bekijkt, kunt u de totale beschikbare bezoekerspool (voorspelling) inschatten of inefficiënte segmenten met te veel overlapping vinden.

<table id="table_5B211EF95216426299EB20253A5A9C1B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gebruiksscenario </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Voorspelling</b> </td> 
   <td colname="col2"> <p>Om de beschikbare bezoekerspool te bepalen, som het verschil tussen het (minder overlapping) het totaal van het spoor en het (minder overlapping) totaal van het segment (minder overlapping). </p> <p>Deze segmentgebonden combinatie zou tot 1004 nieuwe gebruikers kunnen bereiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Inefficiënte segmenten zoeken</b> </td> 
   <td colname="col2"> <p>Als een eigenschap deel van een <span class="wintitle"> EN</span> groep in een segmentdefinitie uitmaakt, zijn de unieke bezoekers die die eigenschap hebben reeds in het segment en niet beschikbaar voor toevoeging aan het segment. U kunt dit rapport gebruiken om relevante eigenschappen met lage overlapping te vinden en hen toe te voegen aan de segmentdefinitie, daarom vergroot het bereik van die groep van het segmentpubliek. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Het begrip van de Filters van Gegevens in het segment-aan-Trait Overlap Rapport {#data-filters-s2t-report}

Beschrijft hoe de eigenschap en het segment unieke overlappende % schuifregelaars werken.

<!-- 

r_s2t_sliders.xml

 -->

Met het [!UICONTROL Segment-to-Trait overlap]-rapport kunt u twee schuifregelaars gebruiken om gegevens te filteren op basis van de eigenschap of het segment van de overlapping %.

* **[!UICONTROL Filter Trait Uniques %:]** Hiermee filtert u gegevens met het percentage unieke bezoekers dat wordt gedeeld tussen de eigenschap en het segment.
* **[!UICONTROL Filter Segment Uniques Overlap %:]** Hiermee filtert u gegevens op basis van het percentage unieke bezoekers dat wordt gedeeld tussen het segment en de eigenschap.

### Voorbeeld

In het onderstaande diagram wordt het verschil weergegeven tussen de vakuniques % en de segment uniques %. In dit geval hebben de kenmerken en segmenten 3 unieke bezoekers. Als verhoudingen:

* Het traject deelt 30% van zijn unieke bezoekers met het segment (3/10 = 0,30).
* Het segment deelt 0,3% van zijn unieke bezoekers met de eigenschap (3/1.000 = 0,003)

![](assets/s2t.png)

## Segment-aan-Trait Gedefinieerde Pop van Gegevens Pop Gebieden {#fields-defined}

Beschrijft de metriek die in popup venster wordt getoond wanneer u een individueel gegevenspunt klikt.

<!-- 

r_s2t_data_pop.xml

 -->

De pop-up voor het [!UICONTROL Segment-to-Trait Overlap] rapport bevat de hieronder metriek. Merk op dat uniques metrisch in de lijst uw *real-time gebruikers* vertegenwoordigt.

<table id="table_4AF72754276242FFB11543635B43AD90"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrisch </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segment-id</span></b> </td> 
   <td colname="col2"> Unieke numerieke id voor het segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Gegevensbron traceren  </span></b> </td> 
   <td colname="col2"> Naam van de eigenaar van de eigenschap. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Type gegevensbron</span></b> </td> 
   <td colname="col2">Hiermee definieert u het type provider waartoe een kenmerk behoort. Kan zijn: 
    <ul id="ul_0477C04A33FD4F5D998B98984E6554D3"> 
     <li id="li_50FCA48EDB5843AB8FB6C34ED2C0067D">Eerste partij (uw eigen eigenschap). </li> 
     <li id="li_4F6148EDAEFE43FA8D505944E9FE3855">Derden (van een externe gegevenspartner/leverancier). </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Gebruikersnaam</span></b> </td> 
   <td colname="col2"> Unieke numerieke id voor de eigenschap. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Naam dienblad</span></b> </td> 
   <td colname="col2"> Naam van de eigenschap. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Uniques Overlap %</span></b> </td> 
   <td colname="col2"> % van de unieke bezoekers deelt een eigenschap met het segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> SegmentUniques overlappen %</span></b> </td> 
   <td colname="col2"> % van de unieke bezoekers deelt een segment met een eigenschap. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Uniques overlappen</span></b> </td> 
   <td colname="col2"> Aantal unieke bezoekers dat tussen het segment en het kenmerk wordt gedeeld. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Segment Uniques</span></b> </td> 
   <td colname="col2"> Aantal unieke bezoekers in het segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b><span class="wintitle"> Trait Uniques</span></b> </td> 
   <td colname="col2"> Aantal unieke bezoekers in de eigenschap. </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Resultaten van filterrapporten met dataregelaars](../../reporting/dynamic-reports/data-sliders.md)
>* [Vormen, kleuren en grootten die worden gebruikt in interactieve rapporten](../../reporting/dynamic-reports/interactive-report-technology.md#shapes-colors-sizes)
>* [Verklaarde pictogrammen en gereedschappen rapporteren](../../reporting/dynamic-reports/interactive-report-technology.md#icons-tools-explained)
>* [Overlaprapporten: updateplanning en minimale segmentgrootte](../../reporting/dynamic-reports/overlap-minimum-segment-size.md)
>* [Datasampling en foutpercentages in geselecteerde Audience Manager-rapporten...](../../reporting/report-sampling.md)
>* [CSV-bestanden voor overlaprapporten](../../reporting/dynamic-reports/overlap-csv-files.md)

