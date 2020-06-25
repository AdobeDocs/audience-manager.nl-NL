---
description: De componenten van de inzameling van gegevens omvatten de Servers van de Inzameling van Gegevens, DIL API, binnenkomende server-aan-server gegevensoverdrachten, en logboekdossiers.
seo-description: De componenten van de inzameling van gegevens omvatten de Servers van de Inzameling van Gegevens, DIL API, binnenkomende server-aan-server gegevensoverdrachten, en logboekdossiers.
seo-title: Componenten gegevensverzameling
solution: Audience Manager
title: Componenten gegevensverzameling
uuid: 51bb1719-5ff2-4bc7-8eb1-98795e05d08f
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '762'
ht-degree: 0%

---


# Componenten gegevensverzameling{#data-collection-components}

De componenten van de inzameling van gegevens omvatten de Servers van de Inzameling van Gegevens, DIL API, binnenkomende server-aan-server gegevensoverdrachten, en logboekdossiers.

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

**[!UICONTROL Data Collection Servers (DCS)]-functie **

In [!DNL Audience Manager]de DCS:

* Ontvangt en evalueert de gegevens van de eigenschap van een gebeurtenisvraag. Dit omvat informatie die voor segmentatie in real time wordt gebruikt en gegevens die bij geplande intervallen door server-aan-server overdrachten worden overgegaan.
* De gebruikers van segmenten die op hun gerealiseerde eigenschappen en de kwalificatieregels worden gebaseerd u met de Bouwer [van het](../../features/segments/segment-builder.md)Segment creeert.
* Hiermee maakt en beheert u apparaat-id&#39;s en geverifieerde profiel-id&#39;s. Dit omvat id&#39;s voor gegevensleveranciers, gebruikers-id&#39;s, gedeclareerde id&#39;s, integratiecodes, enzovoort.
* Controleert PCS op extra eigenschappen een gebruiker reeds vóór een real-time gebeurtenisvraag heeft gerealiseerd. Dit laat DCS gebruikers kwalificeren die op gegevens in real time en historische gegevens worden gebaseerd.
* Schrijft logbestanden en stuurt deze naar analysesystemen voor opslag en verwerking.

**[!DNL DCS]Beheert de vraag via[!UICONTROL Global Server Load Balancing (GSLB)]**

Het [!DNL DCS] is een geografisch gedistribueerd en evenwichtig systeem. Dit betekent [!DNL Audience Manager] dat verzoeken van en naar een regionaal datacenter kunnen worden gericht op basis van de geografische locatie van een bezoeker van de site. Deze strategie helpt reactietijden te verbeteren omdat een [!DNL DCS] reactie rechtstreeks naar een gegevenscentrum gaat dat informatie over die bezoeker bevat. [!UICONTROL GSLB] maakt ons systeem efficiënt omdat relevante gegevens in de cache worden opgeslagen in servers die het dichtst bij de gebruiker staan.

>[!IMPORTANT]
>
>Het [!DNL DCS] detecteert alleen webverkeer dat afkomstig is van apparaten die IPv4 gebruiken.

In een gebeurtenisvraag, wordt de geografische plaats gevangen in een zeer belangrijk-waardepaar die in een grotere lichaam van JSON- gegevens is teruggekeerd. Dit sleutelwaardepaar is de `"dcs_region": region ID` parameter.

![](assets/dcs-map.png)

Als klant gaat u [!DNL DCS] indirect via onze code voor gegevensverzameling aan met de klant. U kunt ook rechtstreeks met de API&#39;s werken [!DNL DCS] via een set. Zie API-methoden en -code [voor DCS (](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)Data Collection Server).

**[!UICONTROL Profile Cache Servers (PCS)]**

Het [!UICONTROL PCS] is een grote database (eigenlijk een grote server-side cookie). Er worden gegevens opgeslagen die voor actieve gebruikers zijn ontvangen van server-naar-server overdrachten en de [!DNL DCS]gegevens. [!UICONTROL PCS] gegevens bestaan uit apparaat-id&#39;s, geverifieerde profiel-id&#39;s en de bijbehorende kenmerken. Wanneer de gebruiker een vraag in real time [!DNL DCS] ontvangt, controleert het [!UICONTROL PCS] voor andere eigenschappen een gebruiker tot kan behoren of voor kwalificeert. En als een eigenschap later aan een segment wordt toegevoegd, worden deze eigenschap-id&#39;s toegevoegd aan het segment [!UICONTROL PCS] en kunnen gebruikers automatisch in aanmerking komen voor dat segment, zonder een bezoek aan een bepaalde site of app. De [!UICONTROL PCS] hulp vergroot [!DNL Audience Manager]het begrip van uw gebruikers omdat het gebruikers in echt - tijd of achter de scènes met nieuwe en historische bezitsgegevens kan aanpassen en segmenteren. Dit gedrag geeft u een vollediger en nauwkeuriger beeld van uw gebruikers dan van kwalificaties in real time alleen.

Er zijn geen controles UI die onze klanten met het [!UICONTROL PCS]laten werken. De toegang van de klant tot het [!UICONTROL PCS] is indirect, door zijn rol als gegevensopslag en gegevensoverdrachten. Het [!UICONTROL PCS] loopt op Apache Cassandra.

**Niet-actieve id&#39;s wissen uit de[!UICONTROL PCS]**

Zoals eerder aangegeven, worden de [!UICONTROL PCS] standaard-id&#39;s voor actieve gebruikers opgeslagen. Een actieve gebruiker is om het even welke gebruiker die door de [Edge gegevensservers](../../reference/system-components/components-edge.md) van om het even welk domein tijdens de laatste 14 dagen is gezien. Deze vraag aan [!UICONTROL PCS] houdt een gebruiker in een actieve staat:

* [!DNL /event] oproepen
* [!DNL /ibs] oproepen (ID syncs)

<!-- 

Removed /dpm calls from the bulleted list. /dpm calls have been deprecated.

 -->

De [!UICONTROL PCS] flushes kenmerkt zich als ze 17 dagen inactief zijn. Deze kenmerken gaan echter niet verloren. Ze zijn opgeslagen in Hadoop. Als de gebruiker weer op een ander moment wordt gezien, dan drukt Hadoop al zijn kenmerken terug naar de [!UICONTROL PCS], meestal binnen een periode van 24 uur.

**Andere[!UICONTROL DCS/PCS]processen: Privacy opt-out**

Deze serversystemen verwerken privacy- en gebruikersuitsluitingsverzoeken. De gegevens van het gebruikerscookie worden niet verzameld in het logbestand als een gebruiker ervoor heeft gekozen geen gegevens meer te verzamelen. Zie het [Adobe Privacy Center](https://www.adobe.com/privacy/advertising-services.html)voor meer informatie over ons privacybeleid.

## Data Integration Library (DIL) {#dil}

[!UICONTROL DIL] Dit is code die u op de pagina plaatst voor gegevensverzameling. Zie de [DIL API](../../dil/dil-overview.md) voor meer informatie over beschikbare services en methoden.

## Binnenkomende server-naar-server {#inbound-outbound-server}

Dit zijn systemen die gegevens ontvangen die door diverse server-aan-server integratie met onze cliënten worden verzonden. Zie de documentatie over het [verzenden van publieksgegevens](/help/using/integration/sending-audience-data/real-time-data-integration/real-time-tech-specs.md) voor meer informatie.

## Logbestanden {#log-files}

De code [!UICONTROL PCS] maakt gegevens en schrijft deze naar de logbestanden. Deze worden naar andere databasesystemen verzonden voor verwerking, rapportage en opslag.

>[!MORELIKETHIS]
>
>* [Adobe Privacy Center](https://www.adobe.com/privacy.html)

