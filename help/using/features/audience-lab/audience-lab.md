---
description: Maak wederzijds uitsluitende testsegmenten in Segment Test Group om de effectiviteit van verschillende doelen te vergelijken en te meten. U kunt een controlegroep opzij zetten en uw segment in percentages van een geheel verdelen, om doeltreffendheid te testen.
seo-description: Create mutually exclusive test segments in Segment Test Groups to compare and measure effectiveness of different destinations. You can set aside a control group and divide your segment into percentages of a whole, in order to test efficacy.
seo-title: Audience Lab
solution: Audience Manager
title: Audience Lab
uuid: aaee820c-1e78-4fd4-bd8f-2629085d78e9
feature: Audience Lab
exl-id: b7fbeb03-52aa-4489-8fcb-45bc2d26621d
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 1%

---

# [!UICONTROL Audience Lab] {#audience-lab}

Maak wederzijds exclusieve testsegmenten in [!UICONTROL Segment Test Groups] om de effectiviteit van verschillende doelen te vergelijken en te meten. U kunt een controlegroep opzij zetten en uw segment in percentages van een geheel verdelen, om doeltreffendheid te testen.

## Overzicht {#audience-lab-overview}

[!UICONTROL Audience Lab] gebruikt [ Verbinding van het Profiel ](../../features/profile-merge-rules/merge-rules-overview.md) om dwars-apparaat het testen te aandrijven. Dit helpt ervoor zorgen een gebruiker voor het zelfde testsegment kwalificeert en de zelfde behandeling over apparaten ontvangt. De testsegmenten in testgroepen zullen de [ Regel van de Fusie van het Profiel ](../../features/profile-merge-rules/merge-rules-dashboard.md) erven het basissegment aan het heeft toegewezen.

In de standaardweergave van [!UICONTROL Audience Lab] wordt een kaart weergegeven voor elk van de testgroepen. Klik op een kaart om de weergave **[!UICONTROL Test Group]** te openen. Deze weergave bevat de volgende informatie:

* **[Testgroepgegevens](../../features/audience-lab/audience-lab-information-view.md)**
* **[Testgroeprapportage](../../features/audience-lab/audience-lab-reporting-view.md)**

U kunt **tot 10 testgroepen** tot stand brengen, elk met **tot 15 testsegmenten**.

![](assets/test-groups-view.PNG)

## Testgroepen zoeken en filteren {#search-and-filter}

Wanneer u meerdere testgroepen met meerdere testsegmenten maakt, is het misschien gemakkelijker om het zoekvak te gebruiken om een specifieke testgroep te zoeken. U kunt naar een testgroep zoeken door:

* de naam van de testgroep;
* De naam van een van de testsegmenten in uw testgroep;
* Beschrijving van de testgroep.

![](assets/search_and_filter_audience_lab.png)

U kunt de testgroepen ook filteren op status. Alle beschikbare statussen worden beschreven in de [ hieronder sectie van de Status ](../../features/audience-lab/audience-lab.md#status).

## [!UICONTROL Status] {#status}

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
   <td colname="col2"> <p>Een <i> actieve </i> testgroep betekent dat het gegeven momenteel naar bestemmingen wordt verzonden. Druk op <b><span class="uicontrol"> Testen onderbreken </span></b> in de <b><span class="uicontrol"> Testgroep </span></b> -kaart om het verzenden van gegevens naar doelen te onderbreken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gepland </span></b> </p> </td> 
   <td colname="col2"> <p>A <i> geplande </i> testgroep is nog niet actief maar kan niet meer worden uitgegeven. Het zal actief worden op de begindatum u in <b> selecteerde creeer de Groepen van de Test </b> tovenaar. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gepauzeerd </span></b> </p> </td> 
   <td colname="col2"> <p>A <i> gepauzeerde </i> testgroep verzendt momenteel geen gegevens naar bestemmingen. Druk op <b><span class="uicontrol"> Actief maken </span></b> in de kaart <b><span class="uicontrol"> Testgroep </span></b> om het verzenden van kenmerken te hervatten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Concept </span></b> </p> </td> 
   <td colname="col2"> <p>A <i> ontwerp </i> testgroep is nog niet actief en kan nog worden uitgegeven. Het verzendt nog geen gegevens naar de in kaart gebrachte bestemmingen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Voltooid </span></b> </p> </td> 
   <td colname="col2"> <p>A <i> voltooide </i> testgroep heeft de einddatum bereikt u in <b><span class="uicontrol"> creeerde de tovenaar van de Groepen van de Test </span></b> selecteerde en het verzenden van het melden van gegevens ophoudt. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Actions] {#actions}

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
   <td colname="col2"> <p>Beschikbaar <b> slechts </b> voor de groepen van de ontwerptest. Hiermee kunt u de wizard <b><span class="uicontrol"> Nieuwe testgroep maken </span></b> hervatten. </p> </td>
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
