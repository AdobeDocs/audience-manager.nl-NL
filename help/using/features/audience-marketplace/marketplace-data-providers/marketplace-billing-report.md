---
description: Genereer een factureringsrapport voor Audience Marketplace om het gebruik van de gegevensfeed voor de vorige maand voor elk van uw abonnees te bekijken. U kunt op elk gewenst moment een rapport voor de vorige maand maken. Het rapport is echter nauwkeuriger wanneer u het genereert op of na de tiende dag van de huidige maand.
seo-description: Generate an Audience Marketplace billing report to view data feed usage for the previous month for each of your subscribers. You can create a report for the previous month at any time. However, the report is more accurate when you generate it on or after the 10th day of the current month.
seo-title: Billing for Data Feed Providers
solution: Audience Manager
title: Facturering voor gegevensleveranciers
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
exl-id: aca2cec1-d3a0-421c-83ca-1c11e9e7d4c7
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '400'
ht-degree: 0%

---

# Facturering voor gegevensleveranciers {#billing-for-data-feed-providers}

Genereer een factureringsrapport van [!DNL Audience Marketplace] om het gebruik van de gegevensinvoer voor de vorige maand voor elk van uw abonnees te bekijken. U kunt op elk gewenst moment een rapport voor de vorige maand maken. Het rapport is echter nauwkeuriger wanneer u het genereert op of na de tiende dag van de huidige maand.

## Factuurrapport downloaden {#download-billing-report}

Een rapport downloaden:

1. Ga naar **[!UICONTROL Audience Marketplace > Receivables]** .
1. Klik op **[!UICONTROL Generate Billing Report]**.

## Gedefinieerde velden rapporteren {#report-fields-defined}

Een factureringsrapport bevat de volgende informatie.

<table id="table_B433D5059F6446068683E425B1D87520"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Rapportveld </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> PID gegevensaanbieder </span></b> </p> </td> 
   <td colname="col2"> <p>Uw <span class="keyword"> Audience Manager </span> gegevensleverancier-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Naam gegevensaanbieder </span></b> </p> </td> 
   <td colname="col2"> <p>Uw bedrijf of organisatienaam. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> KOPER PID </span></b> </p> </td> 
   <td colname="col2"> <p>Koper(abonnee)-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Naam koper </span></b> </p> </td> 
   <td colname="col2"> <p>De naam van het bedrijf of de organisatie van de koper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> ID feed </span></b> </p> </td> 
   <td colname="col2"> <p>De id van de gegevensinvoer </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Naam van feed </span></b> </p> </td> 
   <td colname="col2"> <p>De naam van de gegevensinvoer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Gebruik van scenario's </span></b> </p> </td> 
   <td colname="col2"> <p>Met gebruik van gevallen kunnen verkopers bepalen hoe kopers gegevens gebruiken. U kunt onder andere de volgende opties kiezen: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmenten en overlappen </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modellering </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activering </li> 
    </ul> <p>Zie <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Typen plannen voor gegevensfeeds </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Maateenheid </span></b> </p> </td> 
   <td colname="col2"> <p>Geeft CPM of een vaste facturering aan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Lijstprijs </span></b> </p> </td> 
   <td colname="col2"> <p>De abonnementskosten voor elke gegevensinvoer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Discount Price </span></b> </p> </td> 
   <td colname="col2"> <p>De abonnementskosten voor een gedisconteerde gegevensfeed. Zie <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Kortingen voor Leveranciers van Gegevens </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Eenheden </span></b> </p> </td> 
   <td colname="col2"> <p>Varieert per soort voederprijs: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Flatfee data feeds: alleen 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM-gegevensfeeds: retourneert de werkelijke gebruikshoeveelheid voor CPM-gegevensfeeds. Als een abonnee geen gegevens over de indruk van een CPM-feed heeft verschaft, is de cel Units leeg en wordt de cel Flag ingesteld op 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Totale kosten </span></b> </p> </td> 
   <td colname="col2"> <p>Het bedrag <span class="keyword"> Audience Manager </span> factureert een koper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Factureringsperiode </span></b> </p> </td> 
   <td colname="col2"> <p> In het verslag is dit de laatste dag van de vorige maand. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Invoerdatum </span></b> </p> </td> 
   <td colname="col2"> <p>De datum waarop een koper abonnementsgegevens/gebruiksgegevens heeft ingevoerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Begindatum van abonnement </span></b> </p> </td> 
   <td colname="col2"> <p>De datum waarop een koper zijn abonnement op de gegevensinvoer heeft gestart. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Einddatum abonnement </span></b> </p> </td> 
   <td colname="col2"> <p>De datum waarop een koper zijn abonnement op gegevensinvoer heeft beëindigd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Vlag </span></b> </p> </td> 
   <td colname="col2"> <p> <i> voor het voer van CPM slechts </i>. De vlagopties omvatten: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Geeft aan dat een abonnee gebruiksgegevens heeft gerapporteerd aan <span class="keyword"> Audience Manager </span> . </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Geeft aan dat een abonnee geen gebruiksinformatie heeft gerapporteerd aan <span class="keyword"> Audience Manager </span> . </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [&#x200B; Facturerings en de Toewijzing van de Indruk voor de Eigen Gegevens van CPM &#x200B;](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [&#x200B; Facturerings en Toewijzing van de Indrukking voor de Diefstal van de Gegevens van het Vlaming &#x200B;](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [&#x200B; hoe te om het Gebruik van CPM te melden &#x200B;](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)
