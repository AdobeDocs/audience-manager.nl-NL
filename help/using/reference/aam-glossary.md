---
description: Definities en koppelingen naar verdere informatie.
seo-description: Definitions and links to further reading.
seo-title: Glossary
solution: Audience Manager
title: Woordenlijst
uuid: 01fc26f5-db9d-4e90-b4c1-27c6a510accc
feature: Reference
exl-id: 9e2ee3d3-01b2-4038-abda-fedf0f16f163
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1157'
ht-degree: 96%

---

# Woordenlijst{#glossary}

Definities en koppelingen naar verdere informatie.

## A-B {#a-b}

**Algorithmic Models**

Gebruik [!UICONTROL Algorithmic Modeling] als middel om verder te reiken dan de kern van gebruikers die u hebt geïdentificeerd. Met deze functie kunt u nieuwe, unieke doelgroepen ontdekken via geautomatiseerde data-analyse. Beheer uw [!UICONTROL Algorithmic Models] in **[!UICONTROL Audience Data > Models]**.

Zie [Inzicht in Algorithmic Models](../features/algorithmic-models/algo-models-overview.md).

**BAAAM**

[!UICONTROL Bulk Management Tools]. De [!UICONTROL Bulk Management Tools] in [!DNL Audience Manager] zijn een reeks op Microsoft Excel gebaseerde tools waarmee u meerdere objecten tegelijk met één bewerking kunt maken, wijzigen of verwijderen. U kunt werken met databronnen, afgeleide signalen, bestemmingen, mappen, segmenten, en eigenschappen. De functie gebruikt een Microsoft Excel-spreadsheet met macro’s die veilige, geverifieerde calls uitvoeren naar de [!DNL Audience Manager]-API’s.

Zie [Bulkbeheertools](../reference/bulk-management-tools/bulk-management-intro.md).

## C-D {#c-d}

**CDF**

[!UICONTROL Customer Data Feed]. Een [!UICONTROL CDF]-bestand vertegenwoordigt een bulkdownload van data die door [!DNL Audience Manager] zijn verzameld, en biedt u de mogelijkheid om te werken met [!DNL Audience Manager]-data die buiten de door onze gebruikersinterface opgelegde beperkingen vallen. Een [!UICONTROL CDF]-bestand bevat dezelfde data die een [!DNL Audience Manager]-gebeurteniscall (`/event`) naar onze servers verzendt. Dit omvat data zoals gebruikers-id’s, eigenschap-id’s, segment-id’s en alle andere parameters die door een gebeurteniscall worden vastgelegd.

Zie [Klantdatafeeds](../features/cdf-files.md).

**CRM-id**

De CRM-id is de id waarmee klanten gebruikers in hun eigen CRM-systeem identificeren. In plaats van een CRM-id gebruiken we in Audience Manager de term DPUUID.

Zie DPUUID in de [Index van in id’s in Audience Manager](../reference/ids-in-aam.md).



**Customer Addressable Audience**

In [Addressable Audience](/help/using/features/addressable-audiences.md) staat dit cijfer voor apparaten waarvoor het volgende geldt:
* Ze hebben een op regels gebaseerde, of een onboarded eigenschap gerealiseerd tijdens het terugkijkvenster
  **AND**
* Ze hebben een id-synchronisatie met de gekozen bestemming, ongeacht het tijdstip van de synchronisaties.



**Klantkenmerken**

Zie [Klantattributen](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=nl-NL) in de [!DNL Experience Cloud Core Services]-productdocumentatie.



**Klantmatchpercentage**

Customer Addressable Audience ÷ Customer Total Audience uitgedrukt als %. Zie [Addressable Audience](/help/using/features/addressable-audiences.md).



**Customer Total Audience**

In [Addressable Audience](/help/using/features/addressable-audiences.md) staat dit cijfer voor het aantal apparaten dat een op regels gebaseerde eigenschap heeft gerealiseerd op uw eigenschappen, of een onboarded eigenschap op basis van uw offline bestanden tijdens het terugkijkvenster.



**demdex.net**

Demdex.net is een verouderd domein dat wordt beheerd door [!DNL Adobe]. Het geeft de oorspronkelijke naam weer van [!DNL Audience Manager] van vóór de acquisitie ([!DNL Demdex]). [!DNL Adobe] nam [!DNL Demdex] over in 2011 en wijzigde het merk van het bedrijf in [!DNL Audience Manager]. Alle HTTP-calls naar `demdex.net`-domeinen worden verzonden naar [!DNL Adobe].

Zie [Inzicht in calls naar het Demdex-domein](../reference/demdex-calls.md).



**DAID**

[!UICONTROL Device Advertising IDs] zijn unieke apparaat-id’s die worden gebruikt om een mobiel apparaat te identificeren. Deze id’s worden toegewezen door de fabrikant van het apparaat en niet door Adobe. We ondersteunen iOS- en Android-apparaat-id’s in [!DNL Audience Manager].

Zie de [Index van id’s in Audience Manager](../reference/ids-in-aam.md).



**Bestemming**

In [!DNL Audience Manager] is een doel elk ander systeem (advertentieserver, DSP, netwerk, enz.) waarmee u gegevens wilt delen. De [!UICONTROL Destination Builder] in onze UI biedt de tools waarmee u deze processen voor datalevering kunt maken en beheren. [!DNL Audience Manager]-bestemmingsfuncties bevinden zich in **[!UICONTROL Audience Data > Destinations]**.



**DIL**

De [!UICONTROL Data Integration Library] is een API-bibliotheek die door [!DNL Audience Manager] wordt gebruikt om data over gebruikersinteractie te verzamelen. Zie [Data Integration Library (DIL)-API](../dil/dil-overview.md).



**dpm**

[!UICONTROL Data Provider Match]. Dit laat interne [!DNL Adobe]-systemen weten dat een call van [!DNL Audience Manager] of de id-service klantdata doorgeeft voor synchronisatie of id-aanvraag. Zie [Inzicht in calls naar het Demdex-domein](../reference/demdex-calls.md).

## E-F {#e-f}

**Experience Cloud ID (ECID)**

Vroeger bekend als de [!DNL Marketing Cloud]-id (MID of MCID). De [!DNL Experience Cloud]-id staat centraal in de id-service. Dit is een unieke en permanente id voor bezoekers van uw website. Zie Cookies en de [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=nl-NL).



**Mapeigenschap**

Automatische groepering van eigenschappen binnen uw maptaxonomie. Elke map in de hiërarchie maakt automatisch een eigenschap die kan worden gebruikt om segmenten te definiëren.

Zie [Mapeigenschappen: Info](../features/traits/about-folder-traits.md).



**Frequentielimitering**

Een limiet voor het aantal keren dat een adverteerder een bepaald creatief item aan een eindgebruiker wil laten zien. U kunt verschillende expressies voor frequentielimitering configureren in [!UICONTROL Segment Builder].

Zie [Recentheid en frequentie](../features/segments/recency-and-frequency.md).

## G-H {#g-h}

**GAID**

Google-reclame-id, de unieke apparaat-id die Google toewijst aan hardwareapparaten met het Android-besturingssysteem. Zie de [Index van id’s in Audience Manager](../reference/ids-in-aam.md).



**GUID**

Een acroniem voor Globally Unique Identifier. Wij gebruiken de term GUID niet in [!DNL Audience Manager]. In ons geval is de GUID de [!DNL Audience Manager]-UUID.
Zie de [Index van id’s in Audience Manager](../reference/ids-in-aam.md).

## I-J {#i-j}

**IDFA**

Id voor adverteerders, de unieke apparaat-id die Apple aan zijn producten toewijst. Zie de [Index van id’s in Audience Manager](../reference/ids-in-aam.md).



**Binnenkomend**

Het proces waardoor u doelgroepdata van andere bronnen naar [!DNL Audience Manager] kunt verzenden. Zie [Doelgroepdata verzenden](/help/using/integration/sending-audience-data/send-audience-data.md).



**Integratiecode**

Wanneer u werkt met de [!DNL Audience Manager]-UI of -API, kunt u een integratiecode toevoegen wanneer u eigenschappen, segmenten of databronnen maakt. In die gevallen hebben integratiecodes verschillende doeleinden:

* [!UICONTROL Traits]: een integratiecode is een veld voor een id, een SKU of een andere waarde die door uw interne bedrijfsprocessen wordt gebruikt. Optioneel.
* [!UICONTROL Segments]: een integratiecode is een veld voor een door de gebruiker gedefinieerde id of andere bedrijfsspecifieke informatie. Optioneel.
* [!UICONTROL Data Sources]: integratiecodes zijn vereist wanneer u cross-device databronnen wilt maken, de Adobe Experience Platform Identity Service wilt gebruiken of met [!UICONTROL Profile Merge Rules] wilt werken. Zie [Een databron maken](../features/manage-datasources.md#create-data-source) voor meer informatie.

## K-L {#k-l}

**[!UICONTROL Look-alike modeling]**

Zie [Algorithmic Models](../reference/aam-glossary.md#a-b).

## M-N {#m-n}

**MCID**, **MID**

Zie de [Experience Cloud ID](../reference/aam-glossary.md#e-f).

## O-P {#o-p}

**PCS**

[!UICONTROL Profile Cache Server]. Het [!UICONTROL PCS] is een grote database die op Apache Cassandra draait. Er worden data opgeslagen voor actieve gebruikers van server-naar-server overdrachten en de [!DNL DCS]. [!UICONTROL PCS]-data bestaan uit apparaat-id’s, geverifieerde profiel-id’s en de gekoppelde eigenschappen.

Zie [Onderdelen voor dataverzameling](../reference/system-components/components-data-collection.md).



**Profielkoppeling**

Zie [Definities van opties voor regels voor profielsamenvoeging](../features/profile-merge-rules/merge-rule-definitions.md).



**Regels voor profielsamenvoeging**

Met [!UICONTROL Profile Merge Rules] kunt u het type data bepalen dat door [!DNL Audience Manager] voor segmentatie wordt gebruikt.

Zie [Definities van opties voor regels voor profielsamenvoeging](../features/profile-merge-rules/merge-rule-definitions.md).

## Q-R {#q-r}

**Realisatie**

De actie waardoor een bezoeker op uw website kwalificeert voor een eigenschap. U kunt de tool [Bezoekersprofiel-viewer](../features/visitor-profile-viewer.md) gebruiken om informatie te krijgen over eigenschaprealisatie door een bepaalde gebruiker.

## S-T {#s-t}

**Segment**

Een segment (of een doelgroep) is een verzameling gebruikers die gemeenschappelijke eigenschappen hebben.

Zie [Segmenten: doel, samenstelling en regels](../features/segments/segments-purpose.md).



**Segment Addressable Audience**

In [Addressable Audience](/help/using/features/addressable-audiences.md) staat dit cijfer voor het aantal gebruikers dat tot het segment behoorde tijdens de rapportage-terugkijkperiode en een actieve id-synchronisatie op uw website heeft. Segmenten kunnen uw eigen data en data van tweede en derde partijen bevatten via eigenschappen die in [Audience Marketplace](/help/using/features/audience-marketplace/audience-marketplace.md) zijn verkregen.



**Segment Total Population**

In [Addressable Audience](/help/using/features/addressable-audiences.md) staat dit cijfer voor het totale aantal apparaten dat tot uw segment behoorde tijdens de rapportage-terugkijkperiode.



**Segmentmatchpercentage**

Segment Addressable Audience ÷ Total Segment Population uitgedrukt als %. Zie [Addressable Audience](/help/using/features/addressable-audiences.md).



**Signaal**

Signalen zijn de kleinste data-eenheden in [!DNL Audience Manager] en worden uitgedrukt als sleutelwaardeparen.

Zie [Signalen, eigenschappen en segmenten](../reference/signal-trait-segment.md).



**Eigenschap**

Een eigenschap is een combinatie van een of meer signalen. Zie [Signalen, eigenschappen en segmenten](../reference/signal-trait-segment.md).



**Eigenschappopulatie**

Zie [Populatiedata van eigenschappen en segmenten in Segment Builder](../features/segments/segment-builder-data.md).

**TTL (Time-to-Live, levensduur)**

TTL bepaalt hoeveel dagen een gekwalificeerde bezoeker in een eigenschap blijft. TTL wordt ingesteld op eigenschappen en niet op segmenten. Bezoekers verdwijnen uit een segment als ze vóór het einde van het TTL-interval geen kwalificerende eigenschap zien. Lees meer in [De levensduur van segmenten en eigenschappen](/help/using/features/traits/segment-ttl-explained.md).



## U-V {#u-v}

**UUID**

[!DNL Audience Manager] Unieke gebruikers-id. Zie de [Index van id’s in Audience Manager](../reference/ids-in-aam.md).



**Bezoekers-id**

De [!DNL Experience Cloud]id-service (voorheen bezoekers-id) verschaft een universele, permanente id aan de hand waarvan uw bezoekers kunnen worden geïdentificeerd in alle oplossingen in de [!DNL Experience Cloud].

Raadpleeg de documentatie bij de [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL).

## W-X-Y-Z {#w-z}
