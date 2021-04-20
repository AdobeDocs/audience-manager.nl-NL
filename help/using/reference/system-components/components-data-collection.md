---
description: De componenten van de inzameling van gegevens omvatten de Servers van de Inzameling van Gegevens, de DIL API, binnenkomende server-aan-server gegevensoverdrachten, en logboekdossiers.
seo-description: De componenten van de inzameling van gegevens omvatten de Servers van de Inzameling van Gegevens, de DIL API, binnenkomende server-aan-server gegevensoverdrachten, en logboekdossiers.
seo-title: Onderdelen voor dataverzameling
solution: Audience Manager
title: Onderdelen voor dataverzameling
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '764'
ht-degree: 6%

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

In [!DNL Audience Manager], DCS:

* Ontvangt en evalueert de gegevens van de eigenschap van een gebeurtenisvraag. Dit omvat informatie die voor segmentatie in real time wordt gebruikt en gegevens die bij geplande intervallen door server-aan-server overdrachten worden overgegaan.
* Segmenteert gebruikers op basis van hun gerealiseerde kenmerken en de kwalificatieregels die u maakt met [Segment Builder](../../features/segments/segment-builder.md).
* Hiermee maakt en beheert u apparaat-id&#39;s en geverifieerde profiel-id&#39;s. Dit omvat id&#39;s voor gegevensleveranciers, gebruikers-id&#39;s, gedeclareerde id&#39;s, integratiecodes, enzovoort.
* Controleert PCS op extra eigenschappen een gebruiker reeds vóór een real-time gebeurtenisvraag heeft gerealiseerd. Dit laat DCS gebruikers kwalificeren die op gegevens in real time en historische gegevens worden gebaseerd.
* Schrijft logbestanden en stuurt deze naar analysesystemen voor opslag en verwerking.

**[!DNL DCS]Beheert de vraag via[!UICONTROL Global Server Load Balancing (GSLB)]**

[!DNL DCS] is een geografisch verdeeld en lading-in evenwicht brengend systeem. Dit betekent dat [!DNL Audience Manager] aanvragen kan sturen van en naar een regionaal datacenter op basis van de geografische locatie van een bezoeker van de site. Deze strategie helpt reactietijden te verbeteren omdat een [!DNL DCS] reactie rechtstreeks naar een gegevenscentrum gaat dat informatie over die bezoeker bevat. [!UICONTROL GSLB] maakt ons systeem efficiënt omdat relevante gegevens in de cache worden opgeslagen in servers die het dichtst bij de gebruiker staan.

>[!IMPORTANT]
>
>[!DNL DCS] detecteert alleen webverkeer dat afkomstig is van apparaten die IPv4 gebruiken.

In een gebeurtenisvraag, wordt de geografische plaats gevangen in een zeer belangrijk-waardepaar die in een grotere lichaam van JSON- gegevens is teruggekeerd. Dit sleutelwaardepaar is de parameter `"dcs_region": region ID`.

![](assets/dcs-map.png)

Als klant neemt u indirect via onze code voor gegevensverzameling contact op met [!DNL DCS]. U kunt ook rechtstreeks met de [!DNL DCS] via een set API&#39;s werken. Zie [DCS API-methoden (Data Collection Server) en Code](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md).

**[!UICONTROL Profile Cache Servers (PCS)]**

De [!UICONTROL PCS] is een grote database (in feite een grote servercookie). Er worden data opgeslagen voor actieve gebruikers van server-naar-server overdrachten en de [!DNL DCS]. [!UICONTROL PCS]-data bestaan uit apparaat-id’s, geverifieerde profiel-id’s en de gekoppelde eigenschappen. Wanneer [!DNL DCS] een vraag in real time ontvangt, controleert het [!UICONTROL PCS] voor andere eigenschappen een gebruiker kan tot behoren of voor kwalificeren. En als een eigenschap later aan een segment wordt toegevoegd, worden die eigenschap-id&#39;s toegevoegd aan [!UICONTROL PCS] en kunnen gebruikers automatisch in aanmerking komen voor dat segment, zonder een bezoek aan een bepaalde site of app. De [!UICONTROL PCS] helpt [!DNL Audience Manager] het begrip van uw gebruikers te verdiepen omdat het gebruikers in echt - tijd of achter de scènes met nieuwe en historische bezitsgegevens kan aanpassen en segmenteren. Dit gedrag geeft u een vollediger en nauwkeuriger beeld van uw gebruikers dan van kwalificaties in real time alleen.

Er zijn geen besturingselementen voor de gebruikersinterface waarmee onze klanten direct met de [!UICONTROL PCS] kunnen werken. De toegang van de klant tot [!UICONTROL PCS] is indirect, door zijn rol als gegevensopslag en gegevensoverdrachten. De [!UICONTROL PCS] loopt op Apache Cassandra.

**Niet-actieve id&#39;s wissen uit de[!UICONTROL PCS]**

Zoals eerder aangegeven, slaat [!UICONTROL PCS] de eigenschap-id&#39;s voor actieve gebruikers op. Een actieve gebruiker is om het even welke gebruiker die door [Edge gegevensservers](../../reference/system-components/components-edge.md) van om het even welk domein in de afgelopen 14 dagen is gezien. Deze vraag aan [!UICONTROL PCS] houdt een gebruiker in een actieve staat:

* [!DNL /event] oproepen
* [!DNL /ibs] oproepen (ID syncs)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

De [!UICONTROL PCS] spoelt als ze 17 dagen inactief zijn. Deze kenmerken gaan echter niet verloren. Ze zijn opgeslagen in Hadoop. Als de gebruiker opnieuw op een ander tijdstip wordt gezien, dan duwt de Hadoop al hun eigenschappen terug naar [!UICONTROL PCS], typisch binnen een periode van 24 uur.

**Andere  [!UICONTROL DCS/PCS] processen: Privacy opt-out**

Deze serversystemen verwerken privacy- en gebruikersuitsluitingsverzoeken. De gegevens van het gebruikerscookie worden niet verzameld in het logbestand als een gebruiker ervoor heeft gekozen geen gegevens meer te verzamelen. Zie [Adobe Privacy Center](https://www.adobe.com/nl/privacy/advertising-services.html) voor meer informatie over ons privacybeleid.

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] Dit is code die u op de pagina plaatst voor gegevensverzameling. Zie [DIL API](../../dil/dil-overview.md) voor meer informatie over de beschikbare services en methoden.

## Inbound server-aan-server {#inbound-outbound-server}

Dit zijn systemen die gegevens ontvangen die door diverse server-aan-server integratie met onze cliënten worden verzonden. Zie de documentatie over [het verzenden van publieksgegevens](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) voor meer informatie.

## Logbestanden {#log-files}

Met [!UICONTROL PCS] maakt en schrijft u gegevens naar de logbestanden. Deze worden naar andere databasesystemen verzonden voor verwerking, rapportage en opslag.

>[!MORELIKETHIS]
>
>* [Adobe Privacy Center](https://www.adobe.com/nl/privacy.html)

