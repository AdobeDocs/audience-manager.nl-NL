---
description: De componenten van de inzameling van gegevens omvatten de Servers van de Inzameling van Gegevens, DIL API, binnenkomende server-aan-server gegevensoverdrachten, en logboekdossiers.
seo-description: Data collection components include the Data Collection Servers, the DIL API, inbound server-to-server data transfers, and log files.
seo-title: Data Collection Components
solution: Audience Manager
title: Componenten gegevensverzameling
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: System Components
exl-id: 7ae407f1-f1e4-4545-baa2-bcca40aad76f
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 2%

---

# Componenten gegevensverzameling{#data-collection-components}

De componenten van de inzameling van gegevens omvatten de Servers van de Inzameling van Gegevens, DIL API, binnenkomende server-aan-server gegevensoverdrachten, en logboekdossiers.

<!-- 

c_compcollect.xml

 -->

Audience Manager bevat de volgende componenten voor gegevensverzameling:

* {de Servers van de Inzameling van 0} Gegevens (DCS) en de Servers van het Geheime voorgeheugen van het Profiel (PCS) [&#128279;](../../reference/system-components/components-data-collection.md#dcs-pcs)
* [&#x200B; Data Integration Library (DIL) &#x200B;](../../reference/system-components/components-data-collection.md#dil)
* [&#x200B; Binnenkomende Server-aan-Server &#x200B;](../../reference/system-components/components-data-collection.md#inbound-outbound-server)
* [Logbestanden](../../reference/system-components/components-data-collection.md#log-files)

## Gegevensverzamelingsservers (DCS) en profielcacheservers (PCS) {#dcs-pcs}

De DCS en PCS werken samen en verlenen afzonderlijk de diensten met betrekking tot de verwezenlijking van de eigenschap, publiekssegmentatie, en gegevensopslag.

**[!UICONTROL Data Collection Servers (DCS)]-functie**

In [!DNL Audience Manager] wordt de DCS:

* Ontvangt en evalueert de gegevens van de eigenschap van een gebeurtenisvraag. Dit omvat informatie die voor segmentatie in real time wordt gebruikt en gegevens die bij geplande intervallen door server-aan-server overdrachten worden overgegaan.
* De gebruikers van segmenten die op hun gerealiseerde eigenschappen en de kwalificatieregels worden gebaseerd u met [&#x200B; Bouwer van het Segment &#x200B;](../../features/segments/segment-builder.md) creeert.
* Hiermee maakt en beheert u apparaat-id&#39;s en geverifieerde profiel-id&#39;s. Dit omvat id&#39;s voor gegevensleveranciers, gebruikers-id&#39;s, gedeclareerde id&#39;s, integratiecodes, enzovoort.
* Controleert PCS op extra eigenschappen een gebruiker reeds vóór een real-time gebeurtenisvraag heeft gerealiseerd. Dit laat DCS gebruikers kwalificeren die op gegevens in real time en historische gegevens worden gebaseerd.
* Schrijft logbestanden en stuurt deze naar analysesystemen voor opslag en verwerking.

**[!DNL DCS]Beheert de vraag via[!UICONTROL Global Server Load Balancing (GSLB)]**

De [!DNL DCS] is een geografisch gedistribueerd systeem met taakverdeling. Dit betekent dat [!DNL Audience Manager] aanvragen kan sturen van en naar een regionaal datacenter op basis van de geografische locatie van een sitebezoeker. Deze strategie helpt de reactietijden te verbeteren omdat een [!DNL DCS] reactie rechtstreeks naar een datacenter gaat dat informatie over die bezoeker bevat. [!UICONTROL GSLB] maakt ons systeem efficiënt omdat relevante gegevens in de cache worden opgeslagen in servers die het dichtst bij de gebruiker staan.

>[!IMPORTANT]
>
>[!DNL DCS] ontdekt slechts Webverkeer voortkomend uit apparaten die IPv4 gebruiken.

In een gebeurtenisvraag, wordt de geografische plaats gevangen in een zeer belangrijk-waardepaar die in een grotere lichaam van JSON- gegevens is teruggekeerd. Dit sleutelwaardepaar is de parameter `"dcs_region": region ID` .

![](assets/dcs-map.png)

Als klant gebruikt u de [!DNL DCS] indirect via onze code voor gegevensverzameling. U kunt ook rechtstreeks met de [!DNL DCS] werken via een set API&#39;s. Zie {de Server van de Inzameling van 0} Gegevens (DCS) API Methoden en Code [.](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)

**[!UICONTROL Profile Cache Servers (PCS)]**

De [!UICONTROL PCS] is een grote database (in feite een grote servercookie). Er worden data opgeslagen voor actieve gebruikers van server-naar-server overdrachten en de [!DNL DCS]. [!UICONTROL PCS] -gegevens bestaan uit apparaat-id&#39;s, geverifieerde profiel-id&#39;s en de bijbehorende kenmerken. Wanneer de [!DNL DCS] een real-time aanroep ontvangt, controleert de [!UICONTROL PCS] op andere kenmerken waartoe een gebruiker kan behoren of waarvoor hij in aanmerking komt. En als een kenmerk later aan een segment wordt toegevoegd, worden deze doel-id&#39;s toegevoegd aan de [!UICONTROL PCS] en kunnen gebruikers automatisch in aanmerking komen voor dat segment, zonder dat ze een bezoek hoeven te brengen aan een bepaalde site of app. Met [!UICONTROL PCS] krijgt [!DNL Audience Manager] meer inzicht in uw gebruikers, omdat het gebruikers in real-time of achter de schermen kan afstemmen op en segmenteren met nieuwe en historische gegevens over de eigenschap. Dit gedrag geeft u een vollediger en nauwkeuriger beeld van uw gebruikers dan van kwalificaties in real time alleen.

Er zijn geen UI-besturingselementen waarmee onze klanten rechtstreeks met [!UICONTROL PCS] kunnen werken. De toegang van de klant tot [!UICONTROL PCS] is indirect, via zijn rol als gegevensopslag en gegevensoverdracht. De [!UICONTROL PCS] loopt op Apache Cassandra.

**Het zuiveren inactieve identiteitskaart van[!UICONTROL PCS]**

Zoals eerder aangegeven, slaat [!UICONTROL PCS] de standaard-id&#39;s voor actieve gebruikers op. Een actieve gebruiker is om het even welke gebruiker die door de [&#x200B; servers van randgegevens &#x200B;](../../reference/system-components/components-edge.md) van om het even welk domein tijdens de laatste 14 dagen is gezien. Met deze aanroepen van de [!UICONTROL PCS] wordt een gebruiker in een actieve status gehouden:

* [!DNL /event] oproepen
* [!DNL /ibs] aanroepen (ID-syncs)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

De [!UICONTROL PCS] fushes geeft aan of ze 17 dagen lang inactief zijn. Deze kenmerken gaan echter niet verloren. Ze zijn opgeslagen in Hadoop. Als de gebruiker weer op een ander moment wordt gezien, drukt Hadoop al zijn kenmerken terug naar de [!UICONTROL PCS] , meestal binnen een periode van 24 uur.

**Andere [!UICONTROL DCS/PCS] Processen: De Opt-out van de Privacy**

Deze serversystemen verwerken privacy- en gebruikersuitsluitingsverzoeken. De gegevens van het gebruikerscookie worden niet verzameld in het logbestand als een gebruiker ervoor heeft gekozen geen gegevens meer te verzamelen. Voor meer informatie over ons privacybeleid zie het [&#x200B; Centrum van de Privacy van Adobe &#x200B;](https://www.adobe.com/nl/privacy/advertising-services.html).

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] is code die u op de pagina plaatst voor gegevensverzameling. Zie [&#x200B; DIL API &#x200B;](../../dil/dil-overview.md) voor meer informatie over de beschikbare diensten en methodes.

## Binnenkomende server-naar-server {#inbound-outbound-server}

Dit zijn systemen die gegevens ontvangen die door diverse server-aan-server integratie met onze cliënten worden verzonden. Zie de documentatie bij [&#x200B; verzendend publieksgegevens &#x200B;](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) voor meer informatie.

## Logbestanden {#log-files}

In [!UICONTROL PCS] worden gegevens gemaakt en naar de logbestanden geschreven. Deze worden naar andere databasesystemen verzonden voor verwerking, rapportage en opslag.

>[!MORELIKETHIS]
>
>* [&#x200B; het Centrum van de Privacy van Adobe &#x200B;](https://www.adobe.com/nl/privacy.html)
