---
description: Beschrijft hoe te om segmenten met de Bouwer van het Segment tot stand te brengen.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Segment Builder
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: 1fc17678ba632bfa17f7525c4fc4ff3b534acf94
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 1%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Beschrijft de vereiste en facultatieve stappen die tot een segment binnen leiden [!UICONTROL Segment Builder].

## Videodemonstratie

Begin met het bekijken van de [Segmenten maken in video Audience Manager](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). De video bespreekt u het proces van de segmentverwezenlijking. Lees de onderstaande secties voor meer informatie.

## Een [!UICONTROL Segment] {#create-segment}

### Sectie Segment Builder

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] bestaat uit drie afzonderlijke delen: [!UICONTROL Basic Information], [!UICONTROL Traits], en [!UICONTROL Destinations Mapping]. Als u een [!UICONTROL segment], vult de vereiste velden in de [!UICONTROL Basic Information] en [!UICONTROL Traits] secties. [!UICONTROL Destinations Mapping] instellingen zijn optioneel. Raadpleeg de onderstaande instructies voor meer hulp.

1. In de [Basisinformatie](../../features/segments/segment-builder.md#segment-builder-controls-basics) sectie:

   ![create-segment](assets/create-segment.png)

   * Geef de naam [!UICONTROL segment]. De maximumlengte van een [!UICONTROL segment] name is 255 characters.
   * Stel de [!UICONTROL segment] status (actief is standaard).
   * Kies een [!UICONTROL data source]. Gebruik het eerste drop-down menu om tussen Audience Manager te filtreren [!UICONTROL data sources], Adobe Analytics rapport suites, of beide. Kies vervolgens in het tweede keuzemenu de optie [!UICONTROL data source]. Als u Adobe Analytics niet gebruikt, kunt u het volgende doen: [!UICONTROL data source] type selector is uitgeschakeld en wordt standaard alleen ingesteld op Audience Manager-gegevensbronnen.
   * Selecteer een [!UICONTROL profile merge rule] te gebruiken voor [!UICONTROL segment] kwalificatie.
   * Wijs het [!UICONTROL segment] naar een opslagmap.

1. In de [Treinen](../../features/segments/segment-builder.md#segment-builder-controls-traits) sectie:
   ![segment-builder-kenmerken](assets/segment-builder-traits.png)
   * Zoeken naar [!UICONTROL trait] u wilt aan een segment toevoegen en klikken **[!UICONTROL Add Trait]**. Nog een toevoegen [!UICONTROL trait] om een [!UICONTROL trait] groep.
   * De [!UICONTROL Advanced Search] modal door te klikken **[!UICONTROL Browse All Traits]**. Zoeken naar [!UICONTROL traits] op naam, id, beschrijving of [!UICONTROL data source]. Klik tijdens het zoeken op een map om de resultaten te beperken tot die map en de bijbehorende submappen. U kunt ook filteren [!UICONTROL traits] door [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded], en [!UICONTROL Algorithmic]) of type populatie ([Apparaat-id](../../reference/ids-in-aam.md) en [Apparaatoverschrijdende id](../../reference/ids-in-aam.md)).

      ![segment-bouwer-browser-eigenschappen](assets/segment-builder-browse-traits.png)
   * Live gaan [aanbevelingen betreffende eigenschappen](trait-recommendations.md) wanneer u uw [!UICONTROL segment].
   * Klikken en slepen [!UICONTROL traits] om afzonderlijke groepen te maken.
   * Houd de muisaanwijzer tussen groepen om relaties met Boolean in te stellen [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT] waarden.
   * Houd de muisaanwijzer boven het klokpictogram dat u wilt toevoegen [recentie en frequentie](../../features/segments/recency-and-frequency.md) de [!UICONTROL trait].
   * De gegevens van de segmentpopulatie weergeven zoals u toevoegt of verwijdert [!UICONTROL traits]. Klikken **[!UICONTROL Calculate Estimates]** om de geschatte bevolkingsaantallen te zien (of te vernieuwen). Meer informatie over [segmentpopulatiegegevens](../../features/segments/segment-builder-data.md#segment-populations) in de [!UICONTROL Segment Builder].
   * Klikken **[!UICONTROL Save]** wanneer gereed.

1. *(Optioneel)* Een kaart toewijzen [!UICONTROL segment] een [!UICONTROL destination] in de [Toewijzing bestemming](../../features/segments/segment-builder.md#segment-builder-controls-destinations) sectie:
   * Zoeken naar [!UICONTROL destination] en klik op **[!UICONTROL Add Destination]**. Opmerking: [!UICONTROL destination] moet al bestaan voordat u deze aan een [!UICONTROL segment].
   * Klikken **[!UICONTROL Save]** wanneer gereed.

Bekijk de onderstaande video voor een gedetailleerde uitleg van de werking van maateenheden op verschillende apparaten.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Besturingselementen: [!UICONTROL Basic Information] Sectie {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder], [!UICONTROL the Basic Information] Met instellingen kunt u nieuwe kenmerken maken of bestaande kenmerken bewerken. Een nieuwe [!UICONTROL segment], geef een naam op [!UICONTROL data source]en selecteer een opslagmap. Alle andere velden zijn optioneel. Naar de [!UICONTROL Traits] sectie als u klaar bent.

<!-- r_segment_basic_info_section.xml -->

<!--

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Field </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Name</b> </td> 
   <td colname="col2"> <p>Give the segment a short, logical name that describes its function or purpose. Avoid abbreviations and special characters. The maximum length of a segment name is 255 characters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Description</b> </td> 
   <td colname="col2"> <p>A field for additional descriptive information about the segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integration Code</b> </td> 
   <td colname="col2"> <p>A field for a user-defined ID or other company-specific information. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Data Source</b> </td> 
   <td colname="col2"> <p>Associates the segment with a specific data provider. <p>Use the first drop-down menu to filter between Audience Manager data sources, Adobe Analytics report suites, or both. Then, use the second drop-down menu to choose your data source.</p><p> If you are not using Adobe Analytics report suites, the data source type selector is disabled and defaulted to Audience Manager data sources only.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Profile Merge Rule</b> </td> 
   <td colname="col2"> <p>Selects the Profile Merge Rule to use for segment qualification. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Activates or deactivates the segment (active by default). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Folder Storage</b> </td> 
   <td colname="col2"> <p>Determines which storage folder the segment belongs to. </p> </td> 
  </tr> 
 </tbody> 
</table>

-->

| Veld | Beschrijving |
---------|----------
| **[!UICONTROL Name]** | Geef het segment een korte, logische naam die zijn functie of doel beschrijft. Vermijd afkortingen en speciale tekens. De maximumlengte van een segmentnaam is 255 tekens. |
| **[!UICONTROL Description]** | Een veld voor aanvullende beschrijvende informatie over het segment. |
| **[!UICONTROL Integration Code]** | Een veld voor een door de gebruiker gedefinieerde id of andere bedrijfsspecifieke informatie. |
| **[!UICONTROL Data Source]** | Koppelt het segment aan een specifieke gegevensaanbieder. <br> Gebruik het eerste drop-down menu aan filter tussen de gegevensbronnen van de Audience Manager, Adobe Analytics rapportreeksen, of allebei. Kies vervolgens de gegevensbron in het tweede keuzemenu. <br> Als u Adobe Analytics-rapportreeksen niet gebruikt, is de gegevensbrontypekiezer uitgeschakeld en standaard alleen ingesteld op Audience Manager-gegevensbronnen. |
| **[!UICONTROL Profile Merge Rule]** | Hiermee selecteert u de regel voor het samenvoegen van profielen die u wilt gebruiken voor segmentkwalificatie. |
| **[!UICONTROL Status]** | Hiermee activeert of deactiveert u het segment (standaard actief). |
| **Mapopslag** | Hiermee bepaalt u tot welke opslagmap het segment behoort. |

## [!UICONTROL Segment Builder] Besturingselementen: [!UICONTROL Traits] Sectie {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder]de [!UICONTROL Traits] sectie laat u beheren [!UICONTROL traits] in een [!UICONTROL segment], maken [!UICONTROL trait] groepen en kwalificatiecriteria instellen. Als u een [!UICONTROL trait] een [!UICONTROL segment], typt u de [!UICONTROL trait] naam in het zoekveld en klik op [!UICONTROL Add Trait]. Sla de [!UICONTROL trait] (indien voltooid) of ga door naar [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Vereisten:** Vul de vereiste velden in het dialoogvenster [!UICONTROL Basic Information] sectie.

| Veld | Beschrijving |
|--- |--- |
| **[!UICONTROL Basic View]** | Deze sectie verstrekt visuele controles die u laten: <ul><li>Nieuwe maken en bestaande [!UICONTROL segments].</li><li>Verwijderen [!UICONTROL traits] van een [!UICONTROL segment].</li><li>Toevoegen tot maximaal 50 (maximaal) [!UICONTROL traits] een [!UICONTROL segment].</li><li>Slepen en neerzetten [!UICONTROL traits] om nieuwe groepen te maken.</li><li>Weergave [!UICONTROL traits] en [!UICONTROL trait] groepen in een [!UICONTROL segment].</li><li>Stel kwalificatiecriteria in met Booleaanse expressies, vergelijkingsoperatoren en instellingen voor recentie/frequentie.</li></ul> |
| **[!UICONTROL Code View]** | Hiermee opent u een ontwikkelomgeving waarin u bestanden kunt maken en beheren [!UICONTROL traits], groepen en kwalificatievereisten met code in plaats van de visuele interface. De codeweergave is handig als uw [!UICONTROL segments]: <ul><li>Bevat meer dan 50 [!UICONTROL traits] in een persoon [!UICONTROL segment]. Opmerking: [!UICONTROL Segments] beperkt zijn tot 5000 [!UICONTROL traits] (maximaal).</li><li>Bevat veel [!UICONTROL trait] groepen.</li><li>complexe kwalificatievereisten hebben.</li></ul> |
| Zoeken | Helpt u te vinden [!UICONTROL traits] om aan een [!UICONTROL segment]. |
| Recommendations | Live aanbevelingen voor vergelijkbare [!UICONTROL traits], van uw eerste partij [!UICONTROL traits] en [!UICONTROL Audience Marketplace] gegevensfeeds waarop u bent geabonneerd. Deze aanbevelingen toevoegen aan de [!UICONTROL segment] om uw publiek uit te breiden. Meer informatie in [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Live aanbevelingen voor vergelijkbare [!UICONTROL traits], van [!UICONTROL Audience Marketplace] gegevensfeeds waarop u geen abonnement hebt. Meer informatie in [Trait Recommendations](trait-recommendations.md). |
| Reëel en geraamd [!UICONTROL Segment] Groottegegevens | Zie [Populatiedata van eigenschappen en segmenten in Segment Builder](segment-builder-data.md). |

## Verwijderen [!UICONTROL Traits] van een [!UICONTROL Segment] {#remove-traits}

Het beheren van [!UICONTROL traits] in uw [!UICONTROL segments] is een belangrijk onderdeel van het handhaven [!UICONTROL segments] levensvatbaar. Voer de volgende stappen uit als u het bestand wilt verwijderen [!UICONTROL traits] van een [!UICONTROL segment].

Om te verwijderen [!UICONTROL traits] van een [!UICONTROL segment]:

1. Ga naar **[!UICONTROL Audience Data > Segments]**. Blader door de lijst of gebruik de zoekfunctie om de [!UICONTROL segment] u wilt met werken.
2. Klik op de knop [!UICONTROL segment] naam om de [!UICONTROL segment] detailscherm.
3. Klikken **Bewerken** openen [!UICONTROL Segment Builder] en klik vervolgens op **Treinen** om de [!UICONTROL traits] deelvenster.
4. Houd de aanwijzer boven de [!UICONTROL trait] u wilt schrappen en dan X klikken. Met deze handeling verwijdert u onmiddellijk de [!UICONTROL trait] van uw [!UICONTROL segment].

## [!UICONTROL Segment Builder] Besturingselementen: [!UICONTROL Destinations Mappings] Sectie {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], de facultatieve [!UICONTROL Destinations Mapping] sectie kunt u verzenden [!UICONTROL segment] gegevens aan derden [!DNL cookie], [!DNL URL], of [!UICONTROL server-to-server destination]. Als u een [!UICONTROL destination], zoek (of blader) naar een [!UICONTROL destination], verstrekken [!UICONTROL destination] specifieke informatie en klik op **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Vereisten

Vul de vereiste velden in het dialoogvenster [!UICONTROL Basic Information] en [!UICONTROL Traits] secties. De bestemming moet ook al bestaan.

### [!UICONTROL Destination Mappings] Zoeken in gereedschappen

De **[!UICONTROL Destination Mappings]** bevat zoekgereedschappen zoals in de onderstaande tabel wordt beschreven.

| Zoektype | Beschrijving |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Hiermee kunt u zoeken naar een specifieke [!UICONTROL destination] op naam. U kunt zoeken door te typen. Het veld wordt automatisch ingevuld op basis van de zoektermen. Klikken **[!UICONTROL Add Destination]** wanneer gereed. |
| **[!UICONTROL Browse All Destinations]** | Blader door een lijst met *alles* [!UICONTROL destinations] beschikbaar voor u. Selecteren en toevoegen [!UICONTROL destinations] aan uw [!UICONTROL segment] uit de keuzelijst. |

## Velden in de [!UICONTROL Destination Mappings] Pop-upvensters {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder]de [!UICONTROL Add Destination] verschijnt nadat u een [!UICONTROL destination]. In dit venster wordt statische informatie over de [!UICONTROL destination] en velden die afhankelijk zijn van de [!UICONTROL destination] type. Geef de vereiste informatie op in lege velden om een [!UICONTROL destination mapping].

>[!NOTE]
>
>Publicatiedata zijn facultatief. Wanneer leeg, wordt de bestemming actief en nooit verloopt.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Velden

In de [!UICONTROL Destination Mapping] velden, geeft u de sleutelwaardeparen op die worden gebruikt om gegevens naar de [!UICONTROL destination]. Voer de toets in het eerste veld in en de waarden in het tweede veld. Uw [!UICONTROL cookie destination] pop kan er ongeveer als volgt uitzien :

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Velden

In de [!UICONTROL URL] en [!UICONTROL Secure URL] velden, geeft u het volledige standaard- of beveiligde adres op dat wordt gebruikt voor het verzenden van gegevens naar de [!UICONTROL destination].

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Velden

In de [!UICONTROL Destination Value] veld geeft de waarde op (onderdeel van een sleutelwaardepaar) die wordt gebruikt voor het verzenden van gegevens naar de [!UICONTROL destination].

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Een doel voor cookies maken](../../features/destinations/create-cookie-destination.md)
>* [Een URL-doel maken](../../features/destinations/create-url-destination.md)

