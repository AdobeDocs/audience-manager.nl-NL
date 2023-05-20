---
description: De componenten van de inzameling van gegevens omvatten de Servers van de Inzameling van Gegevens, de DIL API, binnenkomende server-aan-server gegevensoverdrachten, en logboekdossiers.
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: Onderdelen voor dataverzameling
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '741'
ht-degree: 5%

---

# Onderdelen voor dataverzameling{#data-collection-components}

De componenten van de inzameling van gegevens omvatten de Servers van de Inzameling van Gegevens, de DIL API, binnenkomende server-aan-server gegevensoverdrachten, en logboekdossiers.

<!-- 

c_compcollect.xml

 -->

Audience Manager bevat de volgende componenten voor gegevensverzameling:

* [Gegevensverzamelingsservers (DCS) en profielcacheservers (PCS)](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [Data Integration Library (DIL)](../../reference/system-components/components-data-collection.md#dil)
* [Binnenkomende server-naar-server](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Logbestanden](../../reference/system-components/components-data-collection.md#log-files)

## Gegevensverzamelingsservers (DCS) en profielcacheservers (PCS) {#dcs-pcs}

De DCS en PCS werken samen en verlenen afzonderlijk de diensten met betrekking tot de verwezenlijking van de eigenschap, publiekssegmentatie, en gegevensopslag.

**[!UICONTROL Data Collection Servers (DCS)]-functie**

In [!DNL Audience Manager], de DCS:

* Ontvangt en evalueert de gegevens van de eigenschap van een gebeurtenisvraag. Dit omvat informatie die voor segmentatie in real time wordt gebruikt en gegevens die bij geplande intervallen door server-aan-server overdrachten worden overgegaan.
* Segmenteert gebruikers op basis van hun gerealiseerde kenmerken en de kwalificatieregels die u maakt met [Segment Builder](../../features/segments/segment-builder.md).
* Hiermee maakt en beheert u apparaat-id&#39;s en geverifieerde profiel-id&#39;s. Dit omvat id&#39;s voor gegevensleveranciers, gebruikers-id&#39;s, gedeclareerde id&#39;s, integratiecodes, enzovoort.
* Controleert PCS op extra eigenschappen een gebruiker reeds vóór een real-time gebeurtenisvraag heeft gerealiseerd. Dit laat DCS gebruikers kwalificeren die op gegevens in real time en historische gegevens worden gebaseerd.
* Schrijft logbestanden en stuurt deze naar analysesystemen voor opslag en verwerking.

**[!DNL DCS]Beheert de vraag via[!UICONTROL Global Server Load Balancing (GSLB)]**

De [!DNL DCS] is een geografisch gedistribueerd en in evenwicht gebracht systeem. Dit betekent [!DNL Audience Manager] kan verzoeken sturen van en naar een regionaal datacenter op basis van de geografische locatie van een bezoeker van de site. Deze strategie helpt responstijden te verbeteren omdat een [!DNL DCS] de reactie gaat rechtstreeks naar een gegevenscentrum dat informatie over die bezoeker bevat. [!UICONTROL GSLB] maakt ons systeem efficiënt omdat relevante gegevens in de cache worden opgeslagen in servers die het dichtst bij de gebruiker staan.

>[!IMPORTANT]
>
>De [!DNL DCS] detecteert alleen webverkeer dat afkomstig is van apparaten die IPv4 gebruiken.

In een gebeurtenisvraag, wordt de geografische plaats gevangen in een zeer belangrijk-waardepaar die in een grotere lichaam van JSON- gegevens is teruggekeerd. Dit sleutelwaardepaar is het `"dcs_region": region ID` parameter.

![](assets/dcs-map.png)

Als klant neemt u contact op met de [!DNL DCS] indirect via onze code voor gegevensverzameling. U kunt ook rechtstreeks werken met de [!DNL DCS] via een set API&#39;s. Zie [API-methoden en code voor gegevensverzamelingsserver (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

De [!UICONTROL PCS] is een grote database (in feite een grote servercookie). Er worden data opgeslagen voor actieve gebruikers van server-naar-server overdrachten en de [!DNL DCS]. [!UICONTROL PCS]-data bestaan uit apparaat-id’s, geverifieerde profiel-id’s en de gekoppelde eigenschappen. Wanneer de [!DNL DCS] ontvangt een vraag in real time, controleert het [!UICONTROL PCS] voor andere kenmerken kan een gebruiker behoren tot of in aanmerking komen voor. En als een eigenschap later aan een segment wordt toegevoegd, worden die eigenschap-id&#39;s toegevoegd aan de [!UICONTROL PCS] en gebruikers kunnen automatisch voor dat segment in aanmerking komen, zonder een bezoek aan een bepaalde site of app. De [!UICONTROL PCS] helpt verdiepen [!DNL Audience Manager]Het begrip van uw gebruikers omdat het gebruikers in echt - tijd of achter de scènes met nieuwe en historische bezitsgegevens kan aanpassen en segmenteren. Dit gedrag geeft u een vollediger en nauwkeuriger beeld van uw gebruikers dan van kwalificaties in real time alleen.

Er zijn geen controles UI die onze klanten met direct het werk van de [!UICONTROL PCS]. Toegang van de klant tot de [!UICONTROL PCS] indirect is, door zijn rol als gegevensopslag en gegevensoverdracht. De [!UICONTROL PCS] loopt op Apache Cassandra.

**Niet-actieve id&#39;s wissen uit de[!UICONTROL PCS]**

Zoals eerder aangegeven, [!UICONTROL PCS] slaat de eigenschap IDs voor actieve gebruikers op. Een actieve gebruiker is om het even welke gebruiker die door is gezien [Edge-gegevensservers](../../reference/system-components/components-edge.md) vanuit elk domein in de laatste 14 dagen. Deze vraag aan [!UICONTROL PCS] een gebruiker actief houden:

* [!DNL /event] oproepen
* [!DNL /ibs] oproepen (ID syncs)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

De [!UICONTROL PCS] Voettekent als ze 17 dagen inactief zijn. Deze kenmerken gaan echter niet verloren. Ze zijn opgeslagen in Hadoop. Als de gebruiker op een ander moment weer wordt gezien, drukt de Hadoop al zijn kenmerken terug naar de [!UICONTROL PCS], doorgaans binnen een periode van 24 uur.

**Overige [!UICONTROL DCS/PCS] Processen: Privacy opt-out**

Deze serversystemen verwerken privacy- en gebruikersuitsluitingsverzoeken. De gegevens van het gebruikerscookie worden niet verzameld in het logbestand als een gebruiker ervoor heeft gekozen geen gegevens meer te verzamelen. Voor meer informatie over ons privacybeleid raadpleegt u de [Adobe Privacy Center](https://www.adobe.com/nl/privacy/advertising-services.html).

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] Dit is code die u op de pagina plaatst voor gegevensverzameling. Zie de [DIL API](../../dil/dil-overview.md) voor meer informatie over de beschikbare diensten en methodes.

## Binnenkomende server-naar-server {#inbound-outbound-server}

Dit zijn systemen die gegevens ontvangen die door diverse server-aan-server integratie met onze cliënten worden verzonden. Zie de documentatie op [verzenden, publieksgegevens](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) voor meer informatie .

## Logbestanden {#log-files}

De [!UICONTROL PCS] gegevens worden gemaakt en naar de logbestanden geschreven. Deze worden naar andere databasesystemen verzonden voor verwerking, rapportage en opslag.

>[!MORELIKETHIS]
>
>* [Adobe Privacy Center](https://www.adobe.com/nl/privacy.html)

