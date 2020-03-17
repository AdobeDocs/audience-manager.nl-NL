---
description: Maak wederzijds uitsluitende testsegmenten in Segment Test Group om de effectiviteit van verschillende doelen te vergelijken en te meten. U kunt een controlegroep opzij zetten en uw segment in percentages van een geheel verdelen, om doeltreffendheid te testen.
seo-description: Maak wederzijds uitsluitende testsegmenten in Segment Test Group om de effectiviteit van verschillende doelen te vergelijken en te meten. U kunt een controlegroep opzij zetten en uw segment in percentages van een geheel verdelen, om doeltreffendheid te testen.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
topic: DIL API
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Audience Lab {#audience-lab}

Maak wederzijds uitsluitende testsegmenten in [!UICONTROL Segment Test Groups] om de doeltreffendheid van verschillende bestemmingen te vergelijken en te meten. U kunt een controlegroep opzij zetten en uw segment in percentages van een geheel verdelen, om doeltreffendheid te testen.

## Overzicht {#audience-lab-overview}

[!UICONTROL Audience Lab] Gebruikt de Verbinding [van het](../../features/profile-merge-rules/merge-rules-overview.md) Profiel aan macht dwars-apparaat het testen. Dit helpt ervoor zorgen een gebruiker voor het zelfde testsegment kwalificeert en de zelfde behandeling over apparaten ontvangt. De testsegmenten in testgroepen zullen de Regel [van de Fusie van het](../../features/profile-merge-rules/merge-rules-dashboard.md) Profiel erven het basissegment aan het heeft toegewezen.

In de [!UICONTROL Audience Lab] standaardweergave wordt een kaart weergegeven voor elk van de testgroepen. Klik op een kaart om de **[!UICONTROL Test Group]** weergave te openen. Deze weergave bevat de volgende informatie:

* **[Gegevens testgroep](../../features/audience-lab/audience-lab-information-view.md)**
* **[Rapportering testgroep](../../features/audience-lab/audience-lab-reporting-view.md)**

U kunt **maximaal 10 testgroepen** maken, elk met **maximaal 15 testsegmenten**.

![](assets/test-groups-view.PNG)

## Testgroepen zoeken en filteren {#search-and-filter}

Wanneer u meerdere testgroepen met meerdere testsegmenten maakt, is het misschien gemakkelijker om het zoekvak te gebruiken om een specifieke testgroep te zoeken. U kunt naar een testgroep zoeken door:

* de naam van de testgroep;
* De naam van een van de testsegmenten in uw testgroep;
* Beschrijving van de testgroep.

![](assets/search_and_filter_audience_lab.png)

U kunt de testgroepen ook filteren op status. Alle beschikbare statussen worden beschreven in de sectie [Status](../../features/audience-lab/audience-lab.md#status) hieronder.

## Status {#status}

De status van een testgroep kan actief, gepland, gepauzeerd, concept of voltooid zijn. Meer informatie over elk van deze in de onderstaande tabel:

<table id="table_7A0388BA02E045AC971C06A22DAC2C63"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Status </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Actief </span></b> </p> </td> 
   <td colname="col2"> <p>Een <i>actieve</i> testgroep betekent dat de gegevens momenteel naar bestemmingen worden verzonden. De Test van de Pauze van de Pauze <b><span class="uicontrol"> in de kaart van de Groep van de </span></b> <b><span class="uicontrol"> </span></b> Test om het verzenden van gegevens naar bestemmingen op te schorten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gepland </span></b> </p> </td> 
   <td colname="col2"> <p>Een <i>geplande</i> testgroep is nog niet actief maar kan niet meer worden bewerkt. Deze wordt actief op de begindatum die u hebt geselecteerd in de wizard Testgroepen <b></b> maken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gepauzeerd </span></b> </p> </td> 
   <td colname="col2"> <p>Een <i>gepauzeerde</i> testgroep verzendt momenteel geen gegevens naar bestemmingen. De pers <b><span class="uicontrol"> maakt Actief </span></b> in de <b><span class="uicontrol"> </span></b> kaart van de Groep van de Test om het verzenden van eigenschappen te hervatten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Concept </span></b> </p> </td> 
   <td colname="col2"> <p>Een <i>concepttestgroep</i> is nog niet actief en kan nog steeds worden bewerkt. Het verzendt nog geen gegevens naar de in kaart gebrachte bestemmingen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Voltooid </span></b> </p> </td> 
   <td colname="col2"> <p>Een <i>voltooide</i> testgroep heeft de einddatum bereikt u in de <b><span class="uicontrol"> </span></b> Create tovenaar van de Groepen van de Test selecteerde en het verzenden van het melden van gegevens ophoudt. </p> </td>
  </tr>
 </tbody>
</table>

## Handelingen {#actions}

<table id="table_481A411E2D2F4FE891595D00E775CF60"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Handelingen </th> 
   <th colname="col2" class="entry"> Beschrijving </th>
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bewerken </span></b> </p> </td>
   <td colname="col2"> <p>Deze optie is <b>alleen</b> beschikbaar voor concepttestgroepen. Hiermee kunt u de <b><span class="uicontrol"> </span></b> wizard Nieuwe testgroep maken hervatten. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Pauzeren </span></b> </p> </td>
   <td colname="col2"> <p>Beschikbaar voor actieve testgroepen. Staat u toe om het verzenden van de testsegmenten aan bestemmingen te pauzeren. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Actief maken </span></b> </p> </td>
   <td colname="col2"> <p>Beschikbaar voor gepauzeerde testgroepen. Staat u toe om het verzenden van de testsegmenten naar bestemmingen te hervatten. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Weergave </span></b> </p> </td>
   <td colname="col2"> <p>Beschikbaar voor voltooide testgroepen. Staat u toe om de rapporteringsinformatie te bekijken de test heeft geproduceerd. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Dupliceren </span></b> </p> </td>
   <td colname="col2"> <p>Staat u toe om een nieuwe testgroep met de zelfde configuratie tot stand te brengen zoals u dupliceert. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Verwijderen </span></b> </p> </td>
   <td colname="col2"> <p>Hiermee kunt u een testgroep verwijderen. De testsegmenten worden ontkoppeld van de bestemmingen, het basislijnsegment en de conversietekenmerken die aan de testgroep zijn gekoppeld, zijn volledig bewerkbaar. In een waarschuwing wordt u gevraagd het CSV-bestand te downloaden wanneer u een testgroep verwijdert om de melding indien gewenst op te slaan. </p> </td>
  </tr>
 </tbody>
</table>