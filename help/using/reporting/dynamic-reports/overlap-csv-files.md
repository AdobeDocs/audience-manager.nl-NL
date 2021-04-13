---
description: U kunt een .csv- dossier voor een Rapport van de Overlapping verzoeken wanneer dat rapport zijn 1 miljoen verslaggrens bereikt. Een rapport kan deze limiet hebben bereikt wanneer u het bericht "Onverwachte fout is opgetreden" ziet. Neem contact op met de klantenservice om een gecomprimeerd .csv-bestand aan te vragen waarmee u in uw eigen databasesysteem kunt importeren en werken. De dossiers zijn beschikbaar voor segment-aan-segment, segment-aan-eigenschap, en de eigenschap-aan-lijn overlappende rapporten.
seo-description: U kunt een .csv- dossier voor een Rapport van de Overlapping verzoeken wanneer dat rapport zijn 1 miljoen verslaggrens bereikt. Een rapport kan deze limiet hebben bereikt wanneer u het bericht "Onverwachte fout is opgetreden" ziet. Neem contact op met de klantenservice om een gecomprimeerd .csv-bestand aan te vragen waarmee u in uw eigen databasesysteem kunt importeren en werken. De dossiers zijn beschikbaar voor segment-aan-segment, segment-aan-eigenschap, en de eigenschap-aan-lijn overlappende rapporten.
seo-title: CSV-bestanden voor overlaprapporten
solution: Audience Manager
title: CSV-bestanden voor overlaprapporten
uuid: 047e440e-00c5-4d06-a809-51d776326cd6
feature: Rapporten overlappen
exl-id: 759c39cb-64ec-47dd-a3a4-027408aa6b5e
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 2%

---

# CSV-bestanden voor overlaprapporten{#csv-files-for-overlap-reports}

U kunt een .csv- dossier voor een Rapport van de Overlapping verzoeken wanneer dat rapport zijn 1 miljoen verslaggrens bereikt. Een rapport kan deze limiet hebben bereikt wanneer u het bericht &quot;Onverwachte fout is opgetreden&quot; ziet. Neem contact op met de klantenservice om een gecomprimeerd .csv-bestand aan te vragen waarmee u in uw eigen databasesysteem kunt importeren en werken. De dossiers zijn beschikbaar voor segment-aan-segment, segment-aan-eigenschap, en de eigenschap-aan-lijn overlappende rapporten.

## Metagegevens bestandsnaam {#file-name-metadata}

In de volgende tabel vindt u een overzicht en beschrijving van de naamconventies voor bestanden en de bestandsextensies die worden gebruikt in een overlappend CSV-bestand. In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

<table id="table_C99FCABA365B4AB99620F27D4414E623"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metagegevenselement </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Bestandsextensie </p> </td> 
   <td colname="col2"> <p>Overlap rapportbestanden worden gecomprimeerd met gzip en hebben een bestandsextensie <code> .gz</code>. U moet de extensie <code> .csv</code> aan het bestand toevoegen na decompressie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Bestandsnaam </p> </td> 
   <td colname="col2"> <p>Syntaxis bestandsnaam: </p> <p> 
     <ul id="ul_D69D320A1AE94361B75D2AB47F90C4D1"> 
      <li id="li_FFB104975D104050AB67FEEC903C6E2E">Segment-aan-segment dossiers: <code>S2S_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_7DEC51D693FB4377840D652AF40386EF">Bestanden segmenteren naar doel: <code>S2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
      <li id="li_CCB35A2BCB714E518AB279D453740623">Trait-to-trait bestanden: <code>T2T_overlap_<i>partner ID</i>_<i>yyyy-mm-dd</i>_<i>date range</i></code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Datumbereik </p> </td> 
   <td colname="col2"> <p>De datumwaaier voor een rapport is een 5 cijferidentiteitskaart die omvat: </p> <p> 
     <ul id="ul_7B334CDFD7DA42AC8F383BE0F8F77FB9"> 
      <li id="li_0045DED532E747C08824DCC98A9174B3"> <code> 70000</code> voor een verslag van 7 dagen. </li> 
      <li id="li_3A22775F78E648BF8AC32A9E1AF1F5DE"> <code> 30000</code> voor een verslag van 30 dagen. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Meerdere bestanden </p> </td> 
   <td colname="col2"> <p>Het laatste cijfer in de bestandsnaam wordt verhoogd als een rapport meerdere bestanden bevat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Voorbeelden </p> </td> 
   <td colname="col2"> <p>Voorbeelden van bestandsnamen voor één rapport: </p> <p> 
     <ul id="ul_EED13F73F37D48868236F8945E19C88F"> 
      <li id="li_55DD677F9BA7460AA4AAD27AFD08A5AE">Enkel bestand van 7 dagen: <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_487F8B76B7F24DCEB890C2D8186728F7">Enkel bestand van 30 dagen: <code> S2S_overlap_12345_2017_01_14_30000.gz</code> </li> 
     </ul> </p> <p>Voorbeelden van bestandsnamen voor een rapport met meerdere bestanden: </p> <p> 
     <ul id="ul_D307EECBB3524962AB8C8332BF699D29"> 
      <li id="li_9FA3B5539E5A4F95899075866D96DEA0"> <code> S2S_overlap_12345_2017_01_14_70000.gz</code> </li> 
      <li id="li_D8776BD8BAD842C29119B7765F258384"> <code> S2S_overlap_12345_2017_01_14_70001.gz</code> </li> 
      <li id="li_E97AC7696E954A9DAE3DA4E51B5C1B0E"> <code> S2S_overlap_12345_2017_01_14_70002.gz</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Bestandsinhoud {#file-contents}

In het bestand worden tekenreeksgegevens tussen dubbele aanhalingstekens geplaatst. Zie de mock-gegevens hieronder. Dit is afgebroken om kort te zijn en op het scherm te passen.

```js
//File header
"segment_id1","segment_name1","segment_id2","segment_name3,"range_id",...
//File body
"123456","segmentA","654321","segmentB","30","yyyy-mm-dd","98765",...
```

## Segment-aan-segment Rapportrecords {#segment-segment-records}

Een gegevensbestand voor uw [Segment-aan-SegmentOverlap Report](segment-segment-overlap-report.md) bevat de volgende verslagen.

<table id="table_1BDC7019DF2543069D7AE229C5E2454E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id1</code> </p> </td> 
   <td colname="col2"> <p>De id van het segment dat u vergelijkt met het basislijnsegment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name1</code> </p> </td> 
   <td colname="col2"> <p>De naam van het segment dat u vergelijkt met de basislijnsegmenten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_id2</code> </p> </td> 
   <td colname="col2"> <p>De id van het basislijnsegment. Het basislijnsegment is het segment dat u met andere segmenten wilt vergelijken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_name2</code> </p> </td> 
   <td colname="col2"> <p>De naam van het basislijnsegment dat u met andere segmenten vergelijkt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>U kunt rapporten krijgen voor 7- en 30-dagen terugblik-achterintervallen. De <code> rangeid</code> komt overeen met de hieronder getoonde tijdintervallen. </p> <p> 
     <ul id="ul_129D6CB0EB6F48F28440D22DA257D1A4"> 
      <li id="li_5FC34516A437459F854C81B1CE353B89"> <code> 7</code>: 7 dagen </li> 
      <li id="li_2CECC5039DAF4796BCCF27DACC3754A3"> <code> 30</code>: 30 dagen </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>De verwerkingsdatum voor een rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques1</code> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke gebruikers in het segment u aan het basislijnsegment vergelijkt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques2</code> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke gebruikers in het basislijnsegment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Een totaal aantal van de overlapping van unieke gebruikers tussen het basislijnsegment en de andere segmenten die ter vergelijking zijn geselecteerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>De procentuele overlapping van unieke gebruikers tussen het basislijnsegment en de andere segmenten die ter vergelijking zijn geselecteerd. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Segment-aan-Trait Rapportrecords {#segment-trait-records}

Een gegevensbestand voor uw [Segment-aan-Trait Rapport van de Overlapping](segment-trait-overlap-report.md) bevat de volgende verslagen.

<table id="table_45270B5D01014AD99921B320D3A32DB6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> trait_id</code> </p> </td> 
   <td colname="col2"> <p>Gebruikersnaam dienstreis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_name</code> </p> </td> 
   <td colname="col2"> <p>Naam dienblad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>De ID van de gegevensaanbieder. Id's zijn: </p> <p> 
     <ul id="ul_B40EF144552B4BD3A1C2AE2BAFFC5A68"> 
      <li id="li_8E3B524C615F4047A5A06AF2EDF9C758"> <code> 1st Party</code> </li> 
      <li id="li_F0979659028F4E2D989F1F3D1014FD3A"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Naam van de gegevensaanbieder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>U kunt rapporten krijgen voor 7- en 30-dagen terugblik-achterintervallen. De <code> rangeid</code> komt overeen met de hieronder getoonde tijdintervallen. </p> <p> 
     <ul id="ul_4B07DFF4A226428A930E22B5FF73E1D0"> 
      <li id="li_4BD0F8AE64C74D7BBE2298F19E2F5328"> <code> 7</code>: 7 dagen </li> 
      <li id="li_7C0C0D2CD9144C4CAF00EDEA90929104"> <code> 30</code>: 30 dagen </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>De verwerkingsdatum voor een rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques</code> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke gebruikers in het geselecteerde segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke gebruikers in een kenmerk. In het UI-rapport wordt dit nummer weergegeven in het pop-upvenster wanneer u de muisaanwijzer op een kenmerk in de warmteafspeelresultaten plaatst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke gebruikers dat wordt gedeeld tussen de geselecteerde segmenten en kenmerken. In het UI-rapport wordt dit nummer weergegeven in het pop-upvenster wanneer u de muisaanwijzer op een kenmerk in de warmteafspeelresultaten plaatst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% van de unieke gebruikers die het kenmerk en het segment overlappen. In het UI-rapport wordt dit nummer weergegeven in het pop-upvenster wanneer u de muisaanwijzer op een kenmerk in de warmteafspeelresultaten plaatst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> segment_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% van de uniques-gebruikers die het segment en het kenmerk overlappen. In het UI-rapport wordt dit nummer weergegeven in het pop-upvenster wanneer u de muisaanwijzer op een kenmerk in de warmteafspeelresultaten plaatst. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Trait-to-Trait Report Records {#trait-trait-records}

Een gegevensbestand voor uw [Trait-to-Trait Overlap Report](trait-trait-overlap-report.md) bevat de volgende verslagen.

<table id="table_603216E6AFE4439A87C91DDFF2989F53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Label </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_id</code> </p> </td> 
   <td colname="col2"> <p>De id van de eigenschap die u vergelijkt met de basislijneigenschap. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_name</code> </p> </td> 
   <td colname="col2"> <p>De naam van de eigenschap die u vergelijkt met de basislijneigenschap. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_id</code> </p> </td> 
   <td colname="col2"> <p>De id van uw basislijnkenmerk. De basislijneigenschap is de eigenschap die u met andere kenmerken wilt vergelijken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_name</code> </p> </td> 
   <td colname="col2"> <p>De naam van de basislijneigenschap die u vergelijkt met andere kenmerken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider_type</code> </p> </td> 
   <td colname="col2"> <p>De ID van de gegevensaanbieder. Id's zijn: </p> <p> 
     <ul id="ul_FB6FCAF484BE404B8987B54078F5E858"> 
      <li id="li_5E473205AB494D199FBDF22CAA4A1C57"> <code> 1st Party</code> </li> 
      <li id="li_C9A5F455FB6D458F9DDB56EDBF5A6304"> <code> 3rd Party</code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dataprovider</code> </p> </td> 
   <td colname="col2"> <p>Naam van de gegevensaanbieder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> rangeid</code> </p> </td> 
   <td colname="col2"> <p>U kunt rapporten krijgen voor 7- en 30-dagen terugblik-achterintervallen. De <code> rangeid</code> komt overeen met de hieronder getoonde tijdintervallen. </p> <p> 
     <ul id="ul_BC2C41B90F864522B075EFDED33537EC"> 
      <li id="li_929639F70A1A4039BA19332562B71845"> <code> 7</code>: 7 dagen </li> 
      <li id="li_1C489A4B755D4444AD5FAAF0B492F412"> <code> 30</code>: 30 dagen </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> datethru</code> </p> </td> 
   <td colname="col2"> <p>De verwerkingsdatum voor een rapport. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke gebruikers dat wordt gedeeld tussen de geselecteerde kenmerken. In het UI-rapport wordt dit nummer weergegeven in het pop-upvenster wanneer u de muisaanwijzer op een kenmerk in de warmteafspeelresultaten plaatst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques</code> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke gebruikers in een basiskenmerk. In het UI-rapport wordt dit nummer weergegeven in het pop-upvenster wanneer u de muisaanwijzer op een kenmerk in de warmteafspeelresultaten plaatst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_uniques</code> </p> </td> 
   <td colname="col2"> <p>Het aantal unieke gebruikers dat wordt gedeeld tussen de geselecteerde kenmerken. In het UI-rapport wordt dit nummer weergegeven in het pop-upvenster wanneer u de muisaanwijzer op een kenmerk in de warmteafspeelresultaten plaatst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> overlap_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% van de unieke gebruikers die de geselecteerde kenmerken overlappen. In het UI-rapport wordt dit nummer weergegeven in het pop-upvenster wanneer u de muisaanwijzer op een kenmerk in de warmteafspeelresultaten plaatst. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> base_trait_uniques_overlap_perc</code> </p> </td> 
   <td colname="col2"> <p>% van de uniques-gebruikers die de geselecteerde kenmerken overlappen. In het UI-rapport wordt dit nummer weergegeven in het pop-upvenster wanneer u de muisaanwijzer op een kenmerk in de warmteafspeelresultaten plaatst. </p> </td> 
  </tr> 
 </tbody> 
</table>
