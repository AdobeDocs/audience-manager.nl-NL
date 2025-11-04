---
description: Beschrijft hoe te om segmenten met de Bouwer van het Segment tot stand te brengen.
seo-description: Describes how to create segments with Segment Builder.
seo-title: Segment Builder
solution: Audience Manager
title: Segment Builder
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
feature: Segments
exl-id: 1bd681e4-fdf7-40df-b497-b1b0bf19d68e
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1048'
ht-degree: 1%

---

# [!UICONTROL Segment Builder] {#segment-builder}

Beschrijft de vereiste en facultatieve stappen die tot een segment in [!UICONTROL Segment Builder] leiden.

## Videodemonstratie

Begin door te letten op [&#x200B; creeer Segmenten in de video van Audience Manager &#x200B;](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4). De video bespreekt u het proces van de segmentverwezenlijking. Lees de onderstaande secties voor meer informatie.

## Een [!UICONTROL Segment] maken {#create-segment}

### Sectie Segment Builder

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] bestaat uit drie afzonderlijke secties: [!UICONTROL Basic Information] , [!UICONTROL Traits] en [!UICONTROL Destinations Mapping] . Als u een [!UICONTROL segment] wilt maken, vult u de vereiste velden in de secties [!UICONTROL Basic Information] en [!UICONTROL Traits] in. [!UICONTROL Destinations Mapping] -instellingen zijn optioneel. Raadpleeg de onderstaande instructies voor meer hulp.

1. In de [&#x200B; Basisinformatie &#x200B;](../../features/segments/segment-builder.md#segment-builder-controls-basics) sectie:

   ![&#x200B; creeer-segment &#x200B;](assets/create-segment.png)

   * Geef de [!UICONTROL segment] een naam. De maximumlengte van een naam van een [!UICONTROL segment] is 255 tekens.
   * Stel de status [!UICONTROL segment] in (actief is standaard).
   * Kies een [!UICONTROL data source] . Gebruik het eerste vervolgkeuzemenu om te filteren tussen Audience Manager [!UICONTROL data sources] , Adobe Analytics-rapportreeksen of beide. Kies vervolgens de gewenste [!UICONTROL data source] in het tweede keuzemenu. Als u geen Adobe Analytics-rapportreeksen gebruikt, is de [!UICONTROL data source] -typekiezer uitgeschakeld en wordt deze standaard alleen toegepast op Audience Manager-gegevensbronnen.
   * Selecteer een [!UICONTROL profile merge rule] voor [!UICONTROL segment] -kwalificatie.
   * Wijs de [!UICONTROL segment] toe aan een opslagmap.

1. In de [&#x200B; sectie van Tanden &#x200B;](../../features/segments/segment-builder.md#segment-builder-controls-traits):
   ![&#x200B; segment-bouwer-trekken &#x200B;](assets/segment-builder-traits.png)
   * Zoek naar [!UICONTROL trait] u aan een segment wilt toevoegen en **[!UICONTROL Add Trait]** klikken. Voeg nog een [!UICONTROL trait] toe om een [!UICONTROL trait] -groep te maken.
   * Klik op [!UICONTROL Advanced Search] om het modaal van **[!UICONTROL Browse All Traits]** weer te geven. Zoek [!UICONTROL traits] op naam, identiteitskaart, beschrijving of [!UICONTROL data source]. Klik tijdens het zoeken op een map om de resultaten te beperken tot die map en de bijbehorende submappen. U kunt [!UICONTROL traits] door [!UICONTROL trait type] ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded], en [!UICONTROL Algorithmic]) of bevolkingstype ([&#x200B; identiteitskaart van het Apparaat &#x200B;](../../reference/ids-in-aam.md) en [&#x200B; identiteitskaart van het Apparaat &#x200B;](../../reference/ids-in-aam.md)) ook filtreren.
     ![&#x200B; segment-bouwer-browser-eigenschappen &#x200B;](assets/segment-builder-browse-traits.png)
   * Krijg levende [&#x200B; aanbevelingen van het dienstreis &#x200B;](trait-recommendations.md) aangezien u uw [!UICONTROL segment] bouwt.
   * Klik en sleep [!UICONTROL traits] om aparte groepen te maken.
   * Houd de cursor tussen groepen om relaties in te stellen met Booleaanse waarden [!UICONTROL AND] , [!UICONTROL OR] , [!UICONTROL AND NOT] .
   * Beweeg over het klokpictogram om [&#x200B; recentie en frequentie &#x200B;](../../features/segments/recency-and-frequency.md) regels aan [!UICONTROL trait] toe te voegen.
   * Gegevens over segmentpopulaties weergeven terwijl u [!UICONTROL traits] toevoegt of verwijdert. Klik op **[!UICONTROL Calculate Estimates]** om de geschatte bevolkingsaantallen te zien (of te vernieuwen). Lees meer over [&#x200B; gegevens van de segmentbevolking &#x200B;](../../features/segments/segment-builder-data.md#segment-populations) in [!UICONTROL Segment Builder].
   * Klik op **[!UICONTROL Save]** als u klaar bent.

1. *(Facultatief)* Kaart a [!UICONTROL segment] aan a [!UICONTROL destination] in de [&#x200B; sectie van de Afbeelding van de Bestemming &#x200B;](../../features/segments/segment-builder.md#segment-builder-controls-destinations):
   * Zoek naar [!UICONTROL destination] en klik **[!UICONTROL Add Destination]**. De instructie [!UICONTROL destination] moet al bestaan voordat u deze aan een [!UICONTROL segment] kunt toevoegen.
   * Klik op **[!UICONTROL Save]** als u klaar bent.

Bekijk de onderstaande video voor een gedetailleerde uitleg van de werking van maateenheden op verschillende apparaten.

>[!VIDEO](https://video.tv.adobe.com/v/33445)

## [!UICONTROL Segment Builder] Besturingselementen: [!UICONTROL Basic Information] Sectie {#segment-builder-controls-basics}

In [!UICONTROL Segment Builder] kunt u met [!UICONTROL the Basic Information] -instellingen nieuwe kenmerken maken of bestaande kenmerken bewerken. Als u een nieuwe [!UICONTROL segment] wilt maken, geeft u een naam, een [!UICONTROL data source] en selecteert u een opslagmap. Alle andere velden zijn optioneel. Ga wanneer u klaar bent verder naar de sectie [!UICONTROL Traits] .

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
|---------|----------|
| **[!UICONTROL Name]** | Geef het segment een korte, logische naam die zijn functie of doel beschrijft. Vermijd afkortingen en speciale tekens. De maximumlengte van een segmentnaam is 255 tekens. |
| **[!UICONTROL Description]** | Een veld voor aanvullende beschrijvende informatie over het segment. |
| **[!UICONTROL Integration Code]** | Een veld voor een door de gebruiker gedefinieerde id of andere bedrijfsspecifieke informatie. |
| **[!UICONTROL Data Source]** | Koppelt het segment aan een specifieke gegevensaanbieder. <br> Gebruik het eerste vervolgkeuzemenu om te filteren tussen Audience Manager-gegevensbronnen, Adobe Analytics-rapportreeksen of beide. Kies vervolgens de gegevensbron in het tweede keuzemenu. <br> Als u geen Adobe Analytics-rapportreeksen gebruikt, wordt de gegevensbrontypekiezer uitgeschakeld en standaard alleen ingesteld op Audience Manager-gegevensbronnen. |
| **[!UICONTROL Profile Merge Rule]** | Hiermee selecteert u de regel voor het samenvoegen van profielen die u wilt gebruiken voor segmentkwalificatie. |
| **[!UICONTROL Status]** | Hiermee activeert of deactiveert u het segment (standaard actief). |
| **Opslag van de Omslag** | Hiermee bepaalt u tot welke opslagmap het segment behoort. |

## [!UICONTROL Segment Builder] Besturingselementen: [!UICONTROL Traits] Sectie {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder] kunt u met de sectie [!UICONTROL Traits] [!UICONTROL traits] in een [!UICONTROL segment] -project beheren, [!UICONTROL trait] -groepen maken en kwalificatiecriteria instellen. Als u een [!UICONTROL trait] aan een [!UICONTROL segment] wilt toevoegen, typt u de naam [!UICONTROL trait] in het zoekveld en klikt u op [!UICONTROL Add Trait] . Sla [!UICONTROL trait] op (als u klaar bent) of ga naar [!UICONTROL Destinations Mapping] .

<!-- r_segment_traits_section.xml-->

**Eerste vereisten:** voltooi de vereiste gebieden in de [!UICONTROL Basic Information] sectie.

| Veld | Beschrijving |
|--- |--- |
| **[!UICONTROL Basic View]** | Deze sectie verstrekt visuele controles die u laten: <ul><li>Nieuwe maken en bestaande [!UICONTROL segments] beheren.</li><li>Verwijder [!UICONTROL traits] uit een [!UICONTROL segment] .</li><li>Voeg maximaal 50 (maximaal) [!UICONTROL traits] toe aan een [!UICONTROL segment] .</li><li>Sleep [!UICONTROL traits] om nieuwe groepen te maken.</li><li>Groepen [!UICONTROL traits] en [!UICONTROL trait] in een [!UICONTROL segment] weergeven.</li><li>Stel kwalificatiecriteria in met Booleaanse expressies, vergelijkingsoperatoren en instellingen voor recentie/frequentie.</li></ul> |
| **[!UICONTROL Code View]** | Hiermee opent u een ontwikkelomgeving waarin u [!UICONTROL traits] , groepen en kwalificatievereisten kunt maken en beheren met code in plaats van met de visuele interface. De codeweergave is handig als uw [!UICONTROL segments] : <ul><li>Bevat meer dan 50 [!UICONTROL traits] in een individu [!UICONTROL segment]. Opmerking: [!UICONTROL Segments] zijn beperkt tot 5000 [!UICONTROL traits] (maximaal).</li><li>Bevat veel [!UICONTROL trait] groepen.</li><li>complexe kwalificatievereisten hebben.</li></ul> |
| Zoeken | Hiermee kunt u zoeken naar [!UICONTROL traits] die aan een [!UICONTROL segment] moet worden toegevoegd. |
| Aanbevelingen | Krijg levende aanbevelingen voor gelijkaardige [!UICONTROL traits], van uw eerste partij [!UICONTROL traits] en [!UICONTROL Audience Marketplace] gegevensvoer dat u aan wordt geabonneerd. Voeg deze aanbevelingen aan de [!UICONTROL segment] regel toe om uw publiek uit te breiden. Lees meer in [&#x200B; Aanbevelingen van het Staal &#x200B;](trait-recommendations.md). |
| **[!UICONTROL Marketplace Recommendations]** | Krijg levende aanbevelingen voor gelijkaardige [!UICONTROL traits], van [!UICONTROL Audience Marketplace] gegevensvoer dat u niet aan wordt geabonneerd. Lees meer in [&#x200B; Aanbevelingen van het Staal &#x200B;](trait-recommendations.md). |
| Gegevens over werkelijke en geschatte [!UICONTROL Segment] grootte | Zie [Populatiedata van eigenschappen en segmenten in Segment Builder](segment-builder-data.md). |

## [!UICONTROL Traits] verwijderen uit een [!UICONTROL Segment] {#remove-traits}

Het beheren van [!UICONTROL traits] in uw [!UICONTROL segments] is een belangrijk onderdeel van het levensvatbaar houden van [!UICONTROL segments] . Voer de volgende stappen uit als u [!UICONTROL traits] uit een [!UICONTROL segment] wilt verwijderen.

[!UICONTROL traits] verwijderen uit een [!UICONTROL segment] :

1. Ga naar **[!UICONTROL Audience Data > Segments]** . Blader door de lijst of gebruik de zoekfunctie om de [!UICONTROL segment] te zoeken waarmee u wilt werken.
2. Klik op de naam [!UICONTROL segment] om het scherm met [!UICONTROL segment] details te openen.
3. Klik **uitgeven** om [!UICONTROL Segment Builder] te openen en dan **Tanden** te klikken om het [!UICONTROL traits] paneel te openen.
4. Houd de cursor boven [!UICONTROL trait] die u wilt verwijderen en klik op de X. Deze handeling verwijdert de [!UICONTROL trait] onmiddellijk uit de [!UICONTROL segment] .

## [!UICONTROL Segment Builder] Besturingselementen: [!UICONTROL Destinations Mappings] Sectie {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder] kunt u met de optionele sectie [!UICONTROL Destinations Mapping] [!UICONTROL segment] gegevens naar derden verzenden [!DNL cookie] , [!DNL URL] of [!UICONTROL server-to-server destination] . Als u een [!UICONTROL destination] -bewerking wilt toevoegen, zoekt (of bladert) u naar een [!UICONTROL destination] -bestand, geeft u [!UICONTROL destination] specifieke informatie op en klikt u op **[!UICONTROL Add Destination]** .

<!-- r_segment_destinations_map.xml -->

### Vereisten

Vul de vereiste velden in de secties [!UICONTROL Basic Information] en [!UICONTROL Traits] in. De bestemming moet ook al bestaan.

### [!UICONTROL Destination Mappings] Zoekgereedschappen

Het deelvenster **[!UICONTROL Destination Mappings]** bevat zoekgereedschappen, zoals in de onderstaande tabel wordt beschreven.

| Zoektype | Beschrijving |
|---|---|
| **[!UICONTROL Search by Destination Name]** | Hiermee kunt u zoeken naar een specifieke [!UICONTROL destination] op naam. U kunt zoeken door te typen. Het veld wordt automatisch ingevuld op basis van de zoektermen. Klik op **[!UICONTROL Add Destination]** als u klaar bent. |
| **[!UICONTROL Browse All Destinations]** | Blader door een lijst van *allen* [!UICONTROL destinations] beschikbaar aan u. Selecteer [!UICONTROL destinations] in de pop-uplijst en voeg deze toe aan uw [!UICONTROL segment] . |

## Velden in pop-upvensters van [!UICONTROL Destination Mappings] {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder] verschijnt het dialoogvenster [!UICONTROL Add Destination] nadat u een [!UICONTROL destination] selecteert. In dit venster wordt statische informatie weergegeven over de [!UICONTROL destination] en de velden die afhankelijk zijn van het [!UICONTROL destination] -type. Geef de vereiste informatie op in de lege velden om een [!UICONTROL destination mapping] in te stellen.

>[!NOTE]
>
>Publicatiedata zijn facultatief. Wanneer leeg, wordt de bestemming actief en nooit verloopt.

<!-- r_add_mappings_pop.xml -->

### [!UICONTROL Cookie Destination] Velden

Geef in de velden [!UICONTROL Destination Mapping] de sleutelwaardeparen op die worden gebruikt om gegevens naar [!UICONTROL destination] te verzenden. Voer de toets in het eerste veld in en de waarden in het tweede veld. De pop van [!UICONTROL cookie destination] kan er ongeveer als volgt uitzien:

![](assets/cookie_modal.PNG)

### [!UICONTROL URL Destination] Velden

Geef in de velden [!UICONTROL URL] en [!UICONTROL Secure URL] het volledige standaard- of beveiligde adres op dat wordt gebruikt voor het verzenden van gegevens naar [!UICONTROL destination] .

![](assets/url_modal.PNG)

### [!UICONTROL Server-to-Server Destination] Velden

Geef in het veld [!UICONTROL Destination Value] de waarde op (onderdeel van een sleutelwaardepaar) die wordt gebruikt om gegevens naar [!UICONTROL destination] te verzenden.

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [&#x200B; creeer een Bestemming van het Koekje &#x200B;](../../features/destinations/create-cookie-destination.md)
>* [&#x200B; creeer een Doel URL &#x200B;](../../features/destinations/create-url-destination.md)
