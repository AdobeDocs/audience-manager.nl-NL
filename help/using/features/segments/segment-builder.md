---
description: Beschrijft hoe te om segmenten met de Bouwer van het Segment tot stand te brengen.
seo-description: Beschrijft hoe te om segmenten met de Bouwer van het Segment tot stand te brengen.
seo-title: Segment Builder
solution: Audience Manager
title: Segment Builder
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '1092'
ht-degree: 1%

---


# [!UICONTROL Segment Builder] {#segment-builder}

Beschrijft de vereiste en facultatieve stappen die tot een segment in [!UICONTROL Segment Builder] leiden.

## Videodemonstratie

Begin door [Create Segments in Audience Manager video](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4) te bekijken. De video bespreekt u het proces van de segmentverwezenlijking. Lees de onderstaande secties voor meer informatie.

## Een [!UICONTROL Segment] {#create-segment} maken

### Sectie Segment Builder

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] bestaat uit drie afzonderlijke delen:  [!UICONTROL Basic Information],  [!UICONTROL Traits]en  [!UICONTROL Destinations Mapping]. Als u een [!UICONTROL segment] wilt maken, vult u de vereiste velden in de secties [!UICONTROL Basic Information] en [!UICONTROL Traits] in. [!UICONTROL Destinations Mapping] instellingen zijn optioneel. Raadpleeg de onderstaande instructies voor meer hulp.

1. In de sectie [Basisinformatie](../../features/segments/segment-builder.md#segment-builder-controls-basics):

   ![create-segment](assets/create-segment.png)

   * Geef de [!UICONTROL segment] een naam. De maximumlengte van een [!UICONTROL segment] naam is 255 karakters.
   * Stel de status [!UICONTROL segment] in (actief is standaard).
   * Kies een [!UICONTROL data source]. Gebruik het eerste drop-down menu aan filter tussen Audience Manager [!UICONTROL data sources], Adobe Analytics rapportreeksen, of allebei. Gebruik vervolgens het tweede vervolgkeuzemenu om uw [!UICONTROL data source] te kiezen. Als u geen Adobe Analytics-rapportreeksen gebruikt, is de [!UICONTROL data source]-typekiezer uitgeschakeld en standaard alleen ingesteld op Audience Manager-gegevensbronnen.
   * Selecteer een [!UICONTROL profile merge rule] voor [!UICONTROL segment] kwalificatie te gebruiken.
   * Wijs [!UICONTROL segment] aan een opslagomslag toe.

1. In de sectie [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits):
   ![segment-builder-kenmerken](assets/segment-builder-traits.png)
   * Zoek naar [!UICONTROL trait] u aan een segment wilt toevoegen en **[!UICONTROL Add Trait]** klikken. Voeg een andere [!UICONTROL trait] toe om een [!UICONTROL trait] groep tot stand te brengen.
   * Klik op **[!UICONTROL Browse All Traits]** om het modaal [!UICONTROL Advanced Search] weer te geven. Zoek naar [!UICONTROL traits] door naam, identiteitskaart, beschrijving of [!UICONTROL data source]. Klik tijdens het zoeken op een map om de resultaten te beperken tot die map en de bijbehorende submappen. U kunt [!UICONTROL traits] ook filteren door [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded], en [!UICONTROL Algorithmic]) of populatietype ([Apparaat ID](../../reference/ids-in-aam.md) en [Apparaat-ID](../../reference/ids-in-aam.md)).
      ![segment-bouwer-browser-eigenschappen](assets/segment-builder-browse-traits.png)
   * Download live [trait recommendations](trait-recommendations.md) aangezien u uw [!UICONTROL segment] bouwt.
   * Klik en sleep [!UICONTROL traits] om afzonderlijke groepen te maken.
   * Houd de cursor tussen groepen om relaties in te stellen met Booleaanse waarden [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT].
   * Houd de muis boven het klokpictogram om [recency en frequency](../../features/segments/recency-and-frequency.md) regels aan [!UICONTROL trait] toe te voegen.
   * De gegevens van de segmentpopulatie bekijken aangezien u [!UICONTROL traits] toevoegt of verwijdert. Klik op **[!UICONTROL Calculate Estimates]** om de geschatte bevolkingsaantallen te zien (of te vernieuwen). Lees meer over [segmentpopulatiegegevens](../../features/segments/segment-builder-data.md#segment-populations) in [!UICONTROL Segment Builder].
   * Klik **[!UICONTROL Save]** wanneer gereed.

1. *(Optioneel)* Wijs een waarde  [!UICONTROL segment] toe aan een  [!UICONTROL destination] in de sectie  [Bestemmingstoewijzing ](../../features/segments/segment-builder.md#segment-builder-controls-destinations) :
   * Zoek naar [!UICONTROL destination] en klik **[!UICONTROL Add Destination]**. De [!UICONTROL destination] moet reeds bestaan alvorens u het aan [!UICONTROL segment] kunt toevoegen.
   * Klik **[!UICONTROL Save]** wanneer gereed.

Bekijk de onderstaande video voor een gedetailleerde uitleg van de werking van maateenheden op verschillende apparaten.

>[!VIDEO](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## [!UICONTROL Segment Builder] Besturingselementen:  [!UICONTROL Basic Information] Sectie  {#segment-builder-controls-basics}

Met de [!UICONTROL Segment Builder]-instellingen kunt u nieuwe kenmerken maken of bestaande kenmerken bewerken. [!UICONTROL the Basic Information] Als u een nieuwe [!UICONTROL segment] wilt maken, voert u een naam in, een [!UICONTROL data source] en selecteert u een opslagmap. Alle andere velden zijn optioneel. Ga naar de sectie [!UICONTROL Traits] als u klaar bent.

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

## [!UICONTROL Segment Builder] Besturingselementen:  [!UICONTROL Traits] Sectie  {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], laat [!UICONTROL Traits] sectie u [!UICONTROL traits] in a [!UICONTROL segment] beheren, &lt;a4 tot> groepen creëren, en plaatsen kwalificatiecriteria. [!UICONTROL trait] Als u een [!UICONTROL trait] aan een [!UICONTROL segment] wilt toevoegen, typt u de naam [!UICONTROL trait] in het zoekveld en klikt u op [!UICONTROL Add Trait]. Sla [!UICONTROL trait] op (als u klaar bent) of ga naar [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Vereisten:** Vul de vereiste velden in de  [!UICONTROL Basic Information] sectie in.

| Veld | Beschrijving |
|--- |--- |
| **[!UICONTROL Basic View]** | Deze sectie verstrekt visuele controles die u laten: <ul><li>Nieuwe [!UICONTROL segments] maken en bestaande &lt;a0/> beheren.</li><li>Verwijder [!UICONTROL traits] uit a [!UICONTROL segment].</li><li>Voeg maximaal 50 (maximum) [!UICONTROL traits] aan [!UICONTROL segment] toe.</li><li>Sleep [!UICONTROL traits] om nieuwe groepen te maken.</li><li>Geef [!UICONTROL traits] en [!UICONTROL trait] groepen weer in een [!UICONTROL segment].</li><li>Stel kwalificatiecriteria in met Booleaanse expressies, vergelijkingsoperatoren en instellingen voor recentie/frequentie.</li></ul> |
| **[!UICONTROL Code View]** | Opent een ontwikkelomgeving die u [!UICONTROL traits], groepen, en kwalificatievereisten met code in plaats van de visuele interface laat creëren en beheren. De codeweergave is handig als uw [!UICONTROL segments]: <ul><li>Bevat meer dan 50 [!UICONTROL traits] in een individu [!UICONTROL segment]. Opmerking: [!UICONTROL Segments] zijn beperkt tot 5000 [!UICONTROL traits] (maximum).</li><li>Bevat veel [!UICONTROL trait] groepen.</li><li>complexe kwalificatievereisten hebben.</li></ul> |
| Zoeken | Hiermee kunt u [!UICONTROL traits] zoeken om aan een [!UICONTROL segment] toe te voegen. |
| Recommendations | Krijg levende aanbevelingen voor gelijkaardige [!UICONTROL traits], van uw eerste-partij [!UICONTROL traits] en [!UICONTROL Audience Marketplace] gegevensvoer dat u aan wordt geabonneerd. Voeg deze aanbevelingen aan de [!UICONTROL segment] regel toe om uw publiek uit te breiden. Lees meer in [Trait Recommendations](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Krijg levende aanbevelingen voor gelijkaardige [!UICONTROL traits], van [!UICONTROL Audience Marketplace] gegevensvoer dat u niet aan wordt geabonneerd. Lees meer in [Trait Recommendations](trait-recommendations.md). |
| Reële en geschatte [!UICONTROL Segment] Groottegegevens | Zie [Populatiedata van eigenschappen en segmenten in Segment Builder](segment-builder-data.md). |

## [!UICONTROL Traits] verwijderen uit een [!UICONTROL Segment] {#remove-traits}

Het beheren van [!UICONTROL traits] in uw [!UICONTROL segments] is een belangrijk deel van het houden van [!UICONTROL segments] levensvatbaar. Voer de volgende stappen uit als u [!UICONTROL traits] uit een [!UICONTROL segment] moet verwijderen.

[!UICONTROL traits] verwijderen uit een [!UICONTROL segment]:

1. Ga naar **[!UICONTROL Audience Data > Segments]**. Blader door de lijst of gebruik de zoekfunctie om de [!UICONTROL segment] te zoeken waarmee u wilt werken.
2. Klik op de naam [!UICONTROL segment] om het detailscherm [!UICONTROL segment] te openen.
3. Klik op **Bewerken** om [!UICONTROL Segment Builder] te openen en klik vervolgens op **Traits** om het deelvenster [!UICONTROL traits] te openen.
4. Houd de muis boven [!UICONTROL trait] om de X te verwijderen en klik vervolgens op de X. Deze actie verwijdert direct [!UICONTROL trait] uit uw [!UICONTROL segment].

## [!UICONTROL Segment Builder] Besturingselementen:  [!UICONTROL Destinations Mappings] Sectie  {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], laat de facultatieve [!UICONTROL Destinations Mapping] sectie u [!UICONTROL segment] gegevens naar een derde [!DNL cookie], [!DNL URL], of [!UICONTROL server-to-server destination] verzenden. Als u een [!UICONTROL destination] wilt toevoegen, zoekt (of bladert) naar een [!UICONTROL destination], geeft u [!UICONTROL destination] specifieke informatie op en klikt u **[!UICONTROL Add Destination]**.

<!-- r_segment_destinations_map.xml -->

### Vereisten

Vul de vereiste velden in de secties [!UICONTROL Basic Information] en [!UICONTROL Traits] in. De bestemming moet ook al bestaan.

### [!UICONTROL Destination Mappings] Zoeken in gereedschappen

Het **[!UICONTROL Destination Mappings]** paneel bevat onderzoekshulpmiddelen zoals die in de lijst hieronder worden beschreven.

| Zoektype | Beschrijving |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Hiermee kunt u zoeken naar een specifieke [!UICONTROL destination] op naam. U kunt zoeken door te typen. Het veld wordt automatisch ingevuld op basis van de zoektermen. Klik **[!UICONTROL Add Destination]** wanneer gereed. |
| **[!UICONTROL Browse All Destinations]** | Blader door een lijst van *all* [!UICONTROL destinations] beschikbaar aan u. Selecteer en voeg [!UICONTROL destinations] aan uw [!UICONTROL segment] van popup lijst toe. |

## Velden in de pop-upvensters [!UICONTROL Destination Mappings] {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], verschijnt [!UICONTROL Add Destination] dialoog nadat u [!UICONTROL destination] selecteert. In dit venster wordt statische informatie weergegeven over de [!UICONTROL destination] en velden die afhankelijk zijn van het type [!UICONTROL destination]. Geef de vereiste informatie op in de lege velden om een [!UICONTROL destination mapping] in te stellen.

>[!NOTE]
>
>Publicatiedata zijn facultatief. Wanneer leeg, wordt de bestemming actief en nooit verloopt.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Velden

Geef in de velden [!UICONTROL Destination Mapping] de sleutelwaardeparen op die worden gebruikt om gegevens naar [!UICONTROL destination] te verzenden. Voer de toets in het eerste veld in en de waarden in het tweede veld. Uw [!UICONTROL cookie destination] pop zou gelijkaardig aan dit kunnen kijken:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Velden

Geef in de velden [!UICONTROL URL] en [!UICONTROL Secure URL] het volledige standaard- of beveiligde adres op dat wordt gebruikt om gegevens naar [!UICONTROL destination] te verzenden.

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Velden

Geef in het veld [!UICONTROL Destination Value] de waarde op (onderdeel van een sleutelwaardepaar) die wordt gebruikt om gegevens naar [!UICONTROL destination] te verzenden.

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Een doel voor cookies maken](../../features/destinations/create-cookie-destination.md)
>* [Een URL-doel maken](../../features/destinations/create-url-destination.md)

