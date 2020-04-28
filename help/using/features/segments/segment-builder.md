---
description: Beschrijft hoe te om segmenten met de Bouwer van het Segment tot stand te brengen.
seo-description: Beschrijft hoe te om segmenten met de Bouwer van het Segment tot stand te brengen.
seo-title: Segment Builder
solution: Audience Manager
title: Segment Builder
uuid: 5ca924a5-2b29-4802-ab02-e292d77a0aae
translation-type: tm+mt
source-git-commit: 723c75e8946c42779b4c27727ff9e6398b5fc9b1

---


# Segment Builder {#segment-builder}

Beschrijft de vereiste en facultatieve stappen die een segment binnen creëren [!UICONTROL Segment Builder].

## Videodemonstratie

Begin door de [Create Segments in de video](https://images-tv.adobe.com/avp/vr/b7f88801-efe0-4786-9d58-554db16b34eb/81b6f004-cec0-452c-9b35-dabdc69ae3b4/9dc8a1d4-350d-46c3-90a6-5197dfb76f40_20180130023449.854x480at800_h264.mp4)van de Manager van de Publiek te bekijken. De video bespreekt u het proces van de segmentverwezenlijking. Lees de onderstaande secties voor meer informatie.

## Een segment maken {#create-segment}

### Sectie Segment Builder

<!-- t_create_segment.xml -->

[!UICONTROL Segment Builder] bestaat uit drie afzonderlijke delen: [!UICONTROL Basic Information], [!UICONTROL Traits], en [!UICONTROL Destinations Mapping]. Als u een segment wilt maken, vult u de vereiste velden in de [!UICONTROL Basic Information] secties en [!UICONTROL Traits] secties in. [!UICONTROL Destinations Mapping] instellingen zijn optioneel. Raadpleeg de onderstaande instructies voor meer hulp.

1. In het gedeelte [Basisinformatie](../../features/segments/segment-builder.md#segment-builder-controls-basics) :

   ![create-segment](assets/create-segment.png)

   * Geef het segment een naam. De maximumlengte van een segmentnaam is 255 tekens.
   * Stel de segmentstatus in (actief is standaard).
   * Kies een gegevensbron. Gebruik het eerste vervolgkeuzemenu om te filteren tussen de gegevensbronnen van Audience Manager, Adobe Analytics-rapportreeksen of beide. Kies vervolgens de gegevensbron in het tweede keuzemenu. Als u geen Adobe Analytics-rapportreeksen gebruikt, is de gegevensbrontypekiezer uitgeschakeld en standaard alleen ingesteld op Audience Manager-gegevensbronnen.
   * Selecteer een regel voor het samenvoegen van profielen die u wilt gebruiken voor segmentkwalificatie.
   * Wijs het segment toe aan een opslagmap.

1. In de sectie [Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits) :
   ![segment-builder-kenmerken](assets/segment-builder-traits.png)
   * Zoek de eigenschap u aan een segment wilt toevoegen en klik **[!UICONTROL Add Trait]**. Voeg een andere eigenschap toe om een groep eigenschappen te maken.
   * Open de modus Geavanceerd zoeken door op **[!UICONTROL Browse All Traits]** te klikken. Zoek naar eigenschappen door naam, identiteitskaart, beschrijving of gegevensbron. Klik tijdens het zoeken op een map om de resultaten te beperken tot die map en de bijbehorende submappen. U kunt ook kenmerken filteren op type ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded]en [!UICONTROL Algorithmic]) of type populatie ([apparaat-id](../../reference/ids-in-aam.md) en [apparaat-id](../../reference/ids-in-aam.md)).
      ![segment-bouwer-browser-eigenschappen](assets/segment-builder-browse-traits.png)
   * Krijg levende [trekkenaanbevelingen](trait-recommendations.md) aangezien u uw segment bouwt.
   * Klik en sleep kenmerken om aparte groepen te maken.
   * Houd de muisaanwijzer tussen groepen om relaties in te stellen met Booleaanse [!UICONTROL AND], [!UICONTROL OR][!UICONTROL AND NOT] waarden.
   * Houd de muisaanwijzer boven het klokpictogram om de [recenentie- en frequentieregels](../../features/segments/recency-and-frequency.md) toe te voegen aan het kenmerk.
   * De gegevens van de segmentpopulatie bekijken aangezien u eigenschappen toevoegt of verwijdert. Klik **[!UICONTROL Calculate Estimates]** om de geschatte bevolkingsaantallen te zien (of te verfrissen). Lees meer over de gegevens [van de](../../features/segments/segment-builder-data.md#segment-populations) segmentpopulatie in de Bouwer van het Segment.
   * Klik **[!UICONTROL Save]** wanneer gereed.

1. *(Optioneel)* Wijs een segment toe aan een doel in de sectie [Toewijzing](../../features/segments/segment-builder.md#segment-builder-controls-destinations) bestemming:
   * Zoek naar de bestemming en klik **[!UICONTROL Add Destination]**. Nota, moet de bestemming reeds bestaan alvorens u het aan een segment kunt toevoegen.
   * Klik **[!UICONTROL Save]** wanneer gereed.

## Besturingselementen voor Segment Builder: Sectie Basisinformatie {#segment-builder-controls-basics}

Met [!UICONTROL Segment Builder]de [!UICONTROL the Basic Information] instellingen kunt u nieuwe kenmerken maken of bestaande kenmerken bewerken. Als u een nieuw segment wilt maken, geeft u een naam, een gegevensbron en selecteert u een opslagmap. Alle andere velden zijn optioneel. Ga wanneer gereed naar de [!UICONTROL Traits] sectie.

<!-- r_segment_basic_info_section.xml -->

<table id="table_39DA4BC9470448B48F6654F2774EE0D5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Veld </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Naam</b> </td> 
   <td colname="col2"> <p>Geef het segment een korte, logische naam die zijn functie of doel beschrijft. Vermijd afkortingen en speciale tekens. De maximumlengte van een segmentnaam is 255 tekens. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Beschrijving</b> </td> 
   <td colname="col2"> <p>Een veld voor aanvullende beschrijvende informatie over het segment. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Integratiecode</b> </td> 
   <td colname="col2"> <p>Een veld voor een door de gebruiker gedefinieerde id of andere bedrijfsspecifieke informatie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Gegevensbron</b> </td> 
   <td colname="col2"> <p>Koppelt het segment aan een specifieke gegevensaanbieder. <p>Gebruik het eerste vervolgkeuzemenu om te filteren tussen de gegevensbronnen van Audience Manager, Adobe Analytics-rapportreeksen of beide. Kies vervolgens de gegevensbron in het tweede keuzemenu.</p><p> Als u geen Adobe Analytics-rapportreeksen gebruikt, is de gegevensbrontypekiezer uitgeschakeld en standaard alleen ingesteld op Audience Manager-gegevensbronnen.</p></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Regel voor samenvoegen van profiel</b> </td> 
   <td colname="col2"> <p>Hiermee selecteert u de regel voor het samenvoegen van profielen die u wilt gebruiken voor segmentkwalificatie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Status</b> </td> 
   <td colname="col2"> <p>Hiermee activeert of deactiveert u het segment (standaard actief). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Mapopslag</b> </td> 
   <td colname="col2"> <p>Hiermee bepaalt u tot welke opslagmap het segment behoort. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Besturingselementen voor Segment Builder: Sectie Traits {#segment-builder-controls-traits}

In [!UICONTROL Segment Builder], laat de [!UICONTROL Traits] sectie u eigenschappen in een segment beheren, de groepen van het trekteken tot stand brengen, en kwalificatiecriteria plaatsen. Als u een eigenschap aan een segment wilt toevoegen, typt u de naam van de eigenschap in het zoekveld en klikt u [!UICONTROL Add Trait]. Sla de eigenschap op (als u klaar bent) of ga naar [!UICONTROL Destinations Mapping].

<!-- r_segment_traits_section.xml-->

**Vereisten:** Vul de vereiste velden in de [!UICONTROL Basic Information] sectie in.

| Veld | Beschrijving |
|--- |--- |
| Basisweergave | Deze sectie verstrekt visuele controles die u laten: <ul><li>Nieuwe segmenten maken en bestaande segmenten beheren.</li><li>Hiermee verwijdert u kenmerken uit een segment.</li><li>Voeg maximaal 50 (maximum) kenmerken aan een segment toe.</li><li>Met slepen en neerzetten kunt u nieuwe groepen maken.</li><li>De eigenschappen en de trekkengroepen van de mening in een segment.</li><li>Stel kwalificatiecriteria in met Booleaanse expressies, vergelijkingsoperatoren en instellingen voor recentie/frequentie.</li></ul> |
| Codeweergave | Opent een ontwikkelomgeving waarmee u eigenschappen, groepen en kwalificatievereisten met code in plaats van de visuele interface kunt maken en beheren. De codeweergave is handig als uw segmenten: <ul><li>Bevat meer dan 50 kenmerken in een afzonderlijk segment. Opmerking: Segmenten zijn beperkt tot maximaal 5000 kenmerken.</li><li>Bevat veel groepen kenmerken.</li><li>complexe kwalificatievereisten hebben.</li></ul> |
| Zoeken | Hiermee kunt u uitvullingen voor een segment zoeken. |
| Aanbevelingen | Krijg levende aanbevelingen voor gelijkaardige eigenschappen, van uw eerstepartijeigenschappen en [!UICONTROL Audience Marketplace] gegevensvoer die u aan wordt geabonneerd. Voeg deze aanbevelingen aan de segmentregel toe om uw publiek uit te breiden. Lees meer in de Aanbevelingen [van het](trait-recommendations.md)Spoor. |
| Aanbevelingen voor plaats van markt | Krijg levende aanbevelingen voor gelijkaardige eigenschappen, van [!UICONTROL Audience Marketplace] gegevensvoer dat u niet aan wordt geabonneerd. Lees meer in de Aanbevelingen [van het](trait-recommendations.md)Spoor. |
| Gegevens over werkelijke en geschatte segmentgrootte | Zie [Trait and Segment Population Data in Segment Builder](segment-builder-data.md). |

## Traits verwijderen uit een segment {#remove-traits}

Het beheren van de kenmerken in uw segmenten is een belangrijk onderdeel van het levensvatbaar houden van segmenten. Voer de volgende stappen uit als u kenmerken uit een segment moet verwijderen.

Om sporen uit een segment te verwijderen:

1. Ga naar **Poortgegevens > Segmenten**. Blader door de lijst of gebruik de zoekfunctie om het segment te zoeken waarmee u wilt werken.
2. Klik de segmentnaam om het scherm van segmentdetails te openen.
3. Klik op **Bewerken** om de Segmentbouwer te openen en klik vervolgens op **Vertrekken** om het deelvenster Handelingen te openen.
4. Houd de cursor boven het kenmerk dat u wilt verwijderen en klik op de X. Met deze handeling verwijdert u de eigenschap direct uit het segment.

## Besturingselementen voor Segment Builder: Sectie Toewijzingen doelen {#segment-builder-controls-destinations}

In [!UICONTROL Segment Builder], laat de facultatieve [!UICONTROL Destinations Mapping] sectie u segmentgegevens naar een derde [!DNL cookie], [!DNL URL], of server-aan-server bestemming verzenden. Als u een doel wilt toevoegen, zoekt (of bladert) u naar een bestemming, geeft u doelspecifieke informatie op en klikt u **[!UICONTROL Add Destination]** op deze informatie.

<!-- r_segment_destinations_map.xml -->

### Vereisten

Vul de vereiste velden in de [!UICONTROL Basic Information] secties en [!UICONTROL Traits] secties in. De bestemming moet ook al bestaan.

### Zoekgereedschappen voor doeltoewijzingen

Het **[!UICONTROL Destination Mappings]** deelvenster bevat zoekgereedschappen, zoals in de onderstaande tabel wordt beschreven.

| Zoektype | Beschrijving |
|---|---|
| **Zoeken op doelnaam** | Hiermee kunt u naar een specifiek doel op naam zoeken. U kunt zoeken door te typen. Het veld wordt automatisch ingevuld op basis van de zoektermen. Klik **[!UICONTROL Add Destination]** wanneer gereed. |
| **Bladeren door alle doelen** | Blader door een lijst met *alle* bestemmingen die voor u beschikbaar zijn. Selecteer en voeg bestemmingen aan uw segment van popup lijst toe. |

## Velden in Pop-upvensters voor bestemmingstoewijzingen {#fields-in-dest-mappings}

In [!UICONTROL Segment Builder], verschijnt de [!UICONTROL Add Destination] dialoog nadat u een bestemming selecteert. Dit venster toont statische informatie over de bestemming en gebieden die afhankelijk van het bestemmingstype variëren. Geef de vereiste informatie op in de lege velden om een doeltoewijzing in te stellen.

>[!NOTE]
>
>Publicatiedata zijn facultatief. Wanneer leeg, wordt de bestemming actief en nooit verloopt.

<!-- r_add_mappings_pop.xml -->

### Cookie-doelvelden

Geef in de [!UICONTROL Destination Mapping] velden de sleutel-waardeparen op die worden gebruikt om gegevens naar de bestemming te verzenden. Voer de toets in het eerste veld in en de waarden in het tweede veld. De doelpop van uw cookie kan er als volgt uitzien:

![](assets/cookie_modal.PNG)

### URL-doelvelden

Geef in de velden [!UICONTROL URL] en [!UICONTROL Secure URL] velden het volledige standaard- of beveiligde adres op dat wordt gebruikt om gegevens naar de bestemming te verzenden.

![](assets/url_modal.PNG)

### Server-naar-server doelvelden

Geef in het [!UICONTROL Destination Value] veld de waarde op (onderdeel van een sleutelwaardepaar) die wordt gebruikt om gegevens naar het doel te verzenden.

![](assets/s2s_modal.PNG)

>[!MORELIKETHIS]
>
>* [Een doel voor cookies maken](../../features/destinations/create-cookie-destination.md)
>* [Een URL-doel maken](../../features/destinations/create-url-destination.md)

