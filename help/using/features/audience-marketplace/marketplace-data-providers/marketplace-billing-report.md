---
description: Een factureringsrapport voor Audience Marketplace genereren om het gebruik van de gegevensfeed voor de vorige maand voor elk van uw abonnees te bekijken. U kunt op elk gewenst moment een rapport voor de vorige maand maken. Het rapport is echter nauwkeuriger wanneer u het genereert op of na de tiende dag van de huidige maand.
seo-description: Een factureringsrapport voor Audience Marketplace genereren om het gebruik van de gegevensfeed voor de vorige maand voor elk van uw abonnees te bekijken. U kunt op elk gewenst moment een rapport voor de vorige maand maken. Het rapport is echter nauwkeuriger wanneer u het genereert op of na de tiende dag van de huidige maand.
seo-title: Facturering voor gegevensleveranciers
solution: Audience Manager
title: Facturering voor gegevensleveranciers
topic: DIL API
uuid: 4e11dbd2-91fd-4b59-a66d-86a92e0de655
feature: Audience Marketplace
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---


# Facturering voor gegevensleveranciers {#billing-for-data-feed-providers}

Genereer een factureringsrapport om het gebruik van de gegevensfeed voor de vorige maand voor elk van uw abonnees te bekijken. [!DNL Audience Marketplace] U kunt op elk gewenst moment een rapport voor de vorige maand maken. Het rapport is echter nauwkeuriger wanneer u het genereert op of na de tiende dag van de huidige maand.

## Factuurrapport downloaden {#download-billing-report}

Een rapport downloaden:

1. Ga naar **[!UICONTROL Audience Marketplace > Receivables]**.
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
   <td colname="col1"> <p><b><span class="uicontrol"> PID gegevensaanbieder</span></b> </p> </td> 
   <td colname="col2"> <p>De gegevensaanbieder-id van uw <span class="keyword"> Audience Manager</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Naam gegevensaanbieder</span></b> </p> </td> 
   <td colname="col2"> <p>Uw bedrijf of organisatienaam. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Koper heeft betaald</span></b> </p> </td> 
   <td colname="col2"> <p>Koper(abonnee)-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Naam koper</span></b> </p> </td> 
   <td colname="col2"> <p>De naam van het bedrijf of de organisatie van de koper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Feed-id</span></b> </p> </td> 
   <td colname="col2"> <p>De id van de gegevensinvoer </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Naam van feed</span></b> </p> </td> 
   <td colname="col2"> <p>De naam van de gegevensinvoer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Gebruik van abonnementen</span></b> </p> </td> 
   <td colname="col2"> <p>Met gebruik van gevallen kunnen verkopers bepalen hoe kopers gegevens gebruiken. De volgende opties zijn beschikbaar: </p> 
    <ul id="ul_8230A93B5DCE4C10B025D3C761F72CEF"> 
     <li id="li_3400C6475F6D43D7AF54D9A0ED9C09E0">Segmenten en overlappen </li> 
     <li id="li_65DFEF1EA6C341ACB5B72FF629F10AFC">Modellering </li> 
     <li id="li_B84935B93ADE4D299732CE7E099DF7B3">Activering </li> 
    </ul> <p>Zie <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types"> Abonnementtypen voor gegevensfeeds</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Maateenheid</span></b> </p> </td> 
   <td colname="col2"> <p>Geeft CPM- of forfaitaire facturering aan. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Aanbiedingsprijs</span></b> </p> </td> 
   <td colname="col2"> <p>De abonnementskosten voor elke gegevensinvoer. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Korte prijs</span></b> </p> </td> 
   <td colname="col2"> <p>De abonnementskosten voor een gedisconteerde gegevensfeed. Zie <a href="../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#discounts"> Kortingen voor Leveranciers</a>van Gegevens. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Eenheden</span></b> </p> </td> 
   <td colname="col2"> <p>Varieert per soort voederprijs: </p> 
    <ul id="ul_01550B436EEE4FBC8C9945E08E3CE2C6"> 
     <li id="li_C589F6A751AB407E853AC6F726A47F14">Vaste gegevensinvoer: Retourneert alleen 1. </li> 
     <li id="li_F93F8AEB2D8C45BFA0305E7808AFF848">CPM-gegevensfeeds: Keert de daadwerkelijke gebruikshoeveelheid voor CPM gegevensvoer terug. Als een abonnee geen peilingsgegevens voor een CPM voer heeft verstrekt, is de cel van Eenheden leeg en de cel van de Vlag wordt geplaatst aan 1. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Totale kosten</span></b> </p> </td> 
   <td colname="col2"> <p>De Audience Manager <span class="keyword"></span> betaalt een koper. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Factureringsperiode</span></b> </p> </td> 
   <td colname="col2"> <p> In het verslag is dit de laatste dag van de vorige maand. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Invoerdatum</span></b> </p> </td> 
   <td colname="col2"> <p>De datum waarop een koper abonnementsgegevens/gebruiksgegevens heeft ingevoerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Begindatum van abonnement</span></b> </p> </td> 
   <td colname="col2"> <p>De datum waarop een koper zijn abonnement op de gegevensinvoer heeft gestart. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Einddatum abonnement</span></b> </p> </td> 
   <td colname="col2"> <p>De datum waarop een koper zijn abonnement op gegevensinvoer heeft beëindigd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b><span class="uicontrol"> Markering</span></b> </p> </td> 
   <td colname="col2"> <p> <i>Alleen</i>voor CPM-feeds. De vlagopties omvatten: </p> 
    <ul id="ul_509BC73B754A43299F8D719AB0805ABD"> 
     <li id="li_AB35E33B68EC49A187495DF6B9D86563">0: Geeft aan dat een abonnee gebruiksgegevens heeft gerapporteerd aan de <span class="keyword"> Audience Manager</span>. </li> 
     <li id="li_2E4871B127A84EC586A9F3659F52D67E">1: Geeft aan dat een abonnee geen gebruiksgegevens aan de <span class="keyword"> Audience Manager</span>heeft gerapporteerd. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Facturerings en Toewijzing van de Indruk voor de Diervoeders van CPM- Gegevens](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#cost-attribution)
>* [Facturerings- en impressietoewijzing voor gegevens met vaste kosten](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md)
>* [Hoe te om CPM Gebruik te melden](../../../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md#report-cpm-usage)

