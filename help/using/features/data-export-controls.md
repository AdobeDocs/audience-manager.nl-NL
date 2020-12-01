---
description: De Controles van de Uitvoer van gegevens verhinderen u gegevens naar bestemmingen te verzenden wanneer deze actie gegevensprivacy of overeenkomsten van het gegevensgebruik schendt.
seo-description: De Controles van de Uitvoer van gegevens verhinderen u gegevens naar bestemmingen te verzenden wanneer deze actie gegevensprivacy of overeenkomsten van het gegevensgebruik schendt.
seo-title: Besturingselementen voor data-export
solution: Audience Manager
title: Besturingselementen voor data-export
uuid: de7f3608-c0cb-4049-973a-8be54525c600
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 1%

---


# Besturingselementen voor data-export {#data-export-controls}

[!UICONTROL Data Export Controls] verhindert u gegevens naar bestemmingen te verzenden wanneer deze actie gegevensprivacy of overeenkomsten van het gegevensgebruik schendt.

## Overzicht {#overview}

[!UICONTROL Data Export Controls] Hiermee kunt u  [gegevensbronnen ](../features/datasources-list-and-settings.md#data-sources-list-and-settings) en  [doelen](../features/destinations/destinations.md) classificeren. De classificaties die u toepast, bepalen wanneer gegevens naar een bestemming kunnen of kunnen worden geëxporteerd. Deze functie bestaat uit:

* **[!UICONTROL Data Export Controls]**: U kunt de Controles van de Uitvoer van Gegevens op  *gegevensbronnen* plaatsen. Wanneer geplaatst op een gegevensbron, beperken deze controles hoe die gegevensbron en zijn eigenschappen kunnen worden gebruikt.
* **[!UICONTROL Data Export Labels]**: U kunt de Etiketten van de Uitvoer van Gegevens op  *bestemmingen* plaatsen. Wanneer geplaatst op een bestemming, identificeren deze etiketten hoe de bestemming gegevens gebruikt. Zie [Labels voor gegevensexport toevoegen aan een doel](/help/using/features/destinations/add-data-export-labels.md) om te leren hoe u exportlabels kunt toevoegen aan een doel.

Gebaseerd op de classificaties die op een gegevensbron en een bestemming worden toegepast, houden de uitvoercontroles u tegen van:

* Het toevoegen van een eigenschap aan een segment wanneer het spoor tot een gegevensbron behoort die een controle van de gegevensuitvoer heeft die met een etiket van de gegevensuitvoer op één of meerdere bestemmingen onverenigbaar is dat het segment aan in kaart wordt gebracht.
Stel bijvoorbeeld dat een segment is toegewezen aan een doel met het exportlabel **[!DNL This destination may enable a combination with personally identifiable information (PII)]**. De controles van de uitvoer verhinderen u een eigenschap aan dat segment toe te voegen als de gegevensbron dat het bezit tot behoort een controle van de gegevensuitvoer heeft die **[!DNL Cannot be tied to personally identifiable information (PII)]** zegt.
* Het verzenden van om het even welke gegevens naar een bestemmingsbestemming heeft een etiket van de gegevensuitvoer dat door een controle van de gegevensuitvoer over om het even welk van wordt geblokkeerd:
   * de gegevensbron van een opgenomen kenmerk;
   * De gegevensbron van een eigenschap die in een inbegrepen segment wordt gebruikt;
   * De profielsamenvoegregel die door een inbegrepen segment wordt gebruikt;
   * Om het even welke gegevensbronnen die de het profielfusieregel van een inbegrepen segment gebruikt.

[!UICONTROL Data Export Controls] zijn automatisch beschikbaar voor alle klanten van de Audience Manager. Nochtans, hebt u beheerdertoestemmingen nodig om de uitvoercontroles aan een gegevensbron toe te voegen. Voor het toevoegen van exportlabels aan een bestemming zijn beheerdersmachtigingen *of* voldoende rechten vereist om een bestemming te maken of te bewerken.

## Bepaalt controles en etiketten {#controls-labels}

[!UICONTROL Data Export Controls] Verstrek de volgende controles om u te helpen gegevensbronnen en bestemmingen classificeren.

Als u gegevenslevering wilt blokkeren, moet u een gegevensbron classificeren met een exportbesturingselement en een exportlabel toevoegen aan een bestemming. Als u de uitvoercontroles op een gegevensbron of een bestemming slechts toepast, zal deze eigenschap niet gegevenslevering beperken. Wanneer geplaatst op zowel de gegevensbron *als* bestemming, zullen de de uitvoercontroles de eigenschappen beperken u aan een segment kunt toevoegen en verhinderen verzendend de segmentleden naar een bestemming.

Bovendien moet ten minste één exportlabel overeenkomen met een exportbesturingselement voordat beperkingen voor gegevenslevering van kracht worden. Bijvoorbeeld, zeg u de [!UICONTROL PII] uitvoercontrole aan een gegevensbron toevoegt. Vervolgens voegt u het doellabel voor onsite actie toe aan een doel. In dit geval beperken exportbesturingselementen de gegevenslevering niet omdat de instellingen niet overeenkomen. Als u echter het exportlabel [!UICONTROL PII] aan de bestemming toevoegt, blokkeren de exportbesturingselementen de export.

>[!IMPORTANT]
>
>U kunt niet de uitvoer van een segment blokkeren door een controle van de gegevensuitvoer op de gegevensbron van het segment te plaatsen, moet u de controle op één van beiden van plaatsen:
> * de gegevensbronnen van de in het segment gebruikte kenmerken;
> * De profielsamenvoegregel die door het segment wordt gebruikt;
> * Om het even welke gegevensbronnen die de het profielfusieregel van het segment gebruikt.


<br>

<table id="table_7D1F0270B5604A82B96A13CC49C937C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> De Controles van de Uitvoer van gegevens voor een Gegevensbron </th> 
   <th colname="col2" class="entry"> Labels voor gegevensexport voor een doel </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Geen beperking</span></b> </td> 
   <td colname="col2"> n.v.t. </td> 
   <td colname="col3"> Standaard worden exportbeperkingen niet ingesteld voor nieuwe gegevensbronnen en bestemmingen. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kan niet worden gekoppeld aan persoonlijk identificeerbare informatie</span></b>  (PII) </td> 
   <td colname="col2"> <b><span class="uicontrol"> Deze bestemming kan een combinatie met persoonlijk identificeerbare informatie (PII) toelaten</span></b> </td> 
   <td colname="col3">Wanneer deze optie is geselecteerd, kunt u het volgende niet doen: 
    <ul id="ul_0D5A4D0373374217A4BACDFC3BB2F79D"> 
     <li id="li_C32FC26C6E814412A1C73B840E81BB68">Voeg traits aan segmenten toe die aan bestemmingen worden in kaart gebracht die PII gebruiken. </li> 
     <li id="li_BF4FD10807AF4E109CEA22FBD3F6F9B3">De segmenten van de kaart die met een eigenschap van de gegevensbron aan bestemmingen worden gebouwd die PII gebruiken. </li> 
    </ul> <p>Dit wordt vaak vereist door externe gegevensleveranciers en bij het gebruik van gegevensbronnen die informatie over het bijhouden van advertenties en media bevatten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kan niet worden gebruikt voor on-site advertenties</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Deze bestemming kan worden gebruikt voor on-site en doelgericht</span></b> </td> 
   <td colname="col3">Wanneer deze optie is geselecteerd, kunt u het volgende niet doen: 
    <ul id="ul_5B17972E7E0C424A833AD540DFF3CBF2"> 
     <li id="li_05810CEAC8CB4616BB2D52DDDADA84A8">Vormgeving toevoegen aan segmenten die zijn toegewezen aan doelen die de levering aanpassen op basis van de browsergeschiedenis van een bezoeker. </li> 
     <li id="li_B2C3479ECEA74F49B9A2CFDDEE128DF3">De segmenten van de kaart die met een eigenschap van de gegevensbron aan bestemmingen worden gebouwd die en levering aanpassen die op het Web-doorbladerende geschiedenis van een bezoeker wordt gebaseerd. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kan niet worden gebruikt voor offsite advertenties</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Deze bestemming kan voor off-site en het richten worden gebruikt</span></b> </td> 
   <td colname="col3">Deze beperkingen worden over het algemeen gebruikt met Wanneer geselecteerd, kunt u niet: 
    <ul id="ul_B9352FF5282C481BA3A24C581217A156"> 
     <li id="li_0F89583A603D4CD8804724954CFD52C6">Voeg traits aan segmenten toe die aan bestemmingen worden in kaart gebracht die gebruikers op andere plaatsen opnieuw richten. </li> 
     <li id="li_ABDD8BEDE9AF411695C7BDF9AE522BA7">De segmenten van de kaart die met een eigenschap van de gegevensbron aan bestemmingen worden gebouwd die gebruikers op andere plaatsen opnieuw richten. </li> 
    </ul> <p>Vaak vereist wanneer het werken met gegevens van sociale media platforms. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Kan niet worden gebruikt voor onsite personalisatie</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Deze bestemming kan voor onsite en verpersoonlijking worden gebruikt</span></b> </td> 
   <td colname="col3">Wanneer deze optie is geselecteerd, kunt u het volgende niet doen: 
    <ul id="ul_3360EB209E07402A863F0E7473B99D3F"> 
     <li id="li_88B3842B67E040EB9DC0BBEB8E5EC251">Voeg overvullingen toe aan segmenten die zijn toegewezen aan doelen die inhoud aanpassen op basis van gebruikersbelangen of webbrowsergeschiedenis. </li> 
     <li id="li_6506254CCE6546039A3D82B60368C8B4">De segmenten van de kaart die met een eigenschap van de gegevensbron aan bestemmingen worden gebouwd die inhoud aanpassen die op gebruikersbelangen of Web-doorbladerend geschiedenis wordt gebaseerd. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Workflow {#workflow}

Om te beginnen, herzie de gegevensbron en bestemmingsdocumentatie. Deze artikelen bieden instructies voor het toevoegen van besturingselementen en labels voor exporteren aan uw gegevensbronnen en doelen.

* [Een databron maken](../features/manage-datasources.md#create-data-source)
* [Labels voor gegevensexport toevoegen aan een doel](../features/destinations/add-data-export-labels.md)