---
description: Een overzicht op hoog niveau van de wijze waarop Audience Managers informatie uitwisselen met andere gegevensleveranciers en -systemen.
seo-description: Een overzicht op hoog niveau van de wijze waarop Audience Managers informatie uitwisselen met andere gegevensleveranciers en -systemen.
seo-title: Methoden voor Data Integration
solution: Audience Manager
title: Methoden voor Data Integration
uuid: 17a4179a-e99b-49eb-8f45-f2946afbd27f
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1085'
ht-degree: 1%

---


# Methoden voor Data Integration {#data-integration-methods}

Een overzicht op hoog niveau van de wijze waarop Audience Managers informatie uitwisselen met andere gegevensleveranciers en -systemen.

## Ondersteunde methoden voor gegevensintegratie: In real time en [!DNL Server-to-Server] {#supported-methods}

Het kiezen van de juiste integratiemethode hangt van een combinatie bedrijfsvereisten en de technische mogelijkheden van uw gegevenspartner af. Audience Managers wisselen bezoekersinformatie uit met andere gegevensleveranciers op een van de volgende manieren:

* **Real-time:** Hiermee worden gegevens direct overgedragen wanneer een gebruiker uw site bezoekt. Deze methode wordt ook wel *`synchronous`* integratie genoemd.
* **Batch ([!DNL Server-to-Server]):** Hiermee worden gegevens tussen servers overgedragen volgens een ingestelde planning nadat een bezoeker de pagina heeft verlaten. Deze methode wordt ook wel een *`out-of-band`* of een *`asynchronous`* integratie genoemd.

## Vereisten: Een Trait Taxonomie maken {#prereqs}

Voordat het integratieproces begint, moet u [eigenschappen](../features/traits/create-onboarded-rule-based-traits.md) en een [mapstructuur](../features/traits/trait-storage.md#create-trait-storage-folder) in de [!DNL Audience Manager] gebruikersinterface maken. De taxonomie zal al uw [!UICONTROL traits] georganiseerd in een logische hiërarchie bevatten.

## Gebruiksscenario&#39;s voor integratie {#integration-use-cases}

Een gebruiksscenario van de integratiemethodes van de gegevens van de Audience Manager samen met de voor- en nadelen van elk.

### Real-Time [!DNL Server-to-Server] integratie

<!-- c_int_types_use_cases.xml -->

Een gegevensintegratie in real time [!DNL server-to-server] synchroniseert snel gebruikersgegevens tussen de servers van de Audience Manager en een ander gericht systeem. In de meeste gevallen vindt de gegevensuitwisseling plaats binnen seconden of minuten, afhankelijk van de vernieuwingsfrequentie van het doelsysteem. Nota, echter, bepaalt het gerichte systeem dit vernieuwt interval, niet Audience Manager. Bovendien kan de vernieuwingsfrequentie per systeem verschillen. Een [!UICONTROL server-to-server] integratie in real time is het voorkeurstype voor gegevensuitwisseling. De Audience Manager gebruikt deze methode wanneer het richten van partners het kan steunen.

<table id="simpletable_5307DEC378E5486CB92A354287F33AD8"> 
 <tr class="strow">
  <td class="stentry"> <p>Voordelen: </p></td>
  <td class="stentry"> 
   <ul id="ul_F251AFF8A2FA49D0849E36D7FAE87DE7"> 
    <li id="li_1737EBB1AD8844BD87E736BB4D8080EF">Hiermee kunt u gebruikers in aanmerking laten komen voor segmenten zonder deze opnieuw te zien op de pagina, in een videospeler, enz. </li>
    <li id="li_1C1F346CB7BD40508AA5A6918C6B8514"> Vermindert het aantal vraag van HTTP van de pagina. Minder vraag helpt de gebruikerservaring bewaren. </li>
    <li id="li_046BF4568B104F53A0E5372568C957CD">Hiermee kunt u sneller actie ondernemen bij een gekwalificeerde gebruiker. </li>
    <li id="li_70F7AB19AC5D4A9AB80216A2B05163B8">Nuttig bij de overgang naar een DSP voor offsite targeting. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nadelen:</td>
  <td class="stentry"> Minder nuttig voor onsite het richten wanneer u de gebruiker op de zelfde pagina, of de volgende pagina moet richten, die op het kwalificeren van een gebruiker voor dat segment wordt gebaseerd.</td>
 </tr>
</table>

### [!DNL Server-to-Server] Batchintegratie

Bij een [!DNL server-to-server] batchintegratie worden gegevens gebundeld en verzonden naar andere systemen met ingestelde intervallen in plaats van in realtime. De intervallen voor gegevensoverdracht beginnen na 24 uur. Sommige gegevensleveranciers steunen slechts dit integratietype. Maar we hebben een algemene trend gezien die afsteekt van batchintegratie naar realtime integratiemethodologieën.

<table id="simpletable_6878241639114DE68E61A251486C6317"> 
 <tr class="strow">
  <td class="stentry"> <p>Voordelen: </p></td>
  <td class="stentry"> 
   <ul id="ul_1E9B48B06E764D3AB6F2D702EB4922DC"> 
    <li id="li_1CF0E018660347B3A5AF79160F74FBDB">Hiermee kunt u gebruikers in aanmerking laten komen voor segmenten zonder deze opnieuw te zien op de pagina, in een videospeler, enz. </li> 
    <li id="li_B6A9DF9C0D8B44A48F032F2FDB5B3956">Nuttig voor het richten dat niet tijdgevoelig is. </li>
   </ul></td>
 </tr>
 <tr class="strow">
  <td class="stentry"> Nadelen:</td>
  <td class="stentry"> Het synchronisatieinterval kan het richten tegen de huidigste gegevens vertragen.</td>
 </tr>
</table>

### Vraag in real time

In real time vraag uitwisselingsgegevens met Audience Manager onmiddellijk, aangezien een gebruiker uw plaats bezoekt of actie op de pagina neemt. Met deze methode, krijgen de het richten systemen de meest bijgewerkte gegevens van de segmentkwalificatie en kunnen die informatie in aanmerking nemen tijdens een inhoud of een leveringsbesluit. Dit proces werkt ook met uitgever en servers waar we gekwalificeerde segmenten bijwerken naar een cookie van de eerste partij die in een advertentie wordt gelezen als sleutelwaardeparen. Momenteel, gebruikt de Audience Manager vraag in real time om met [!DNL Adobe Target] en andere systemen van het inhoudbeheer te integreren.

<table> 
 <tr>
  <td> <p>Voordelen: </p></td>
  <td> <p> Hiermee kunt u de volgende pagina, het inhoudsgebied of de advertentie als doel instellen op basis van de meest recente segmentkwalificatie. </p></td> 
 </tr> 
 <tr>
  <td> <p>Nadelen: </p></td>
  <td> <p>Voegt een vraag aan Audience Manager van de pagina toe.</p></td>
 </tr> 
</table>


### Pixels Syncs to Targeing Systems

Pixelsynchronisatie wijst segmenten toe aan pixels op de pagina. De pixel brandt en brengt gegevens over wanneer een gebruiker voor een bepaald segment kwalificeert. Pixelsynchronisatie is een rudimentair en onbetrouwbaar mechanisme voor gegevensoverdracht. De belangrijkste gegevensleveranciers en -systemen gebruiken dit zelden.

<table id="simpletable_39E4CD139CCF4417842AA28CDFFB6EB1"> 
 <tr class="strow">
  <td class="stentry"> <p>Voordelen: </p></td>
  <td class="stentry"> <p> Gegevensoverdracht in realtime. </p></td> 
 </tr> 
 <tr class="strow">
  <td class="stentry"> <p>Nadelen: </p></td>
  <td class="stentry"> 
   <ul id="ul_5217EDC82434401493C2C96823C068E9"> 
    <li id="li_26EB0458CA1844908C005A47F55E50AC">Kan veel cliënt-zijvraag van de pagina toevoegen. </li>
    <li id="li_CD91F3DC92F2429293787D61506E5E04">Onbetrouwbaar voor gegevensoverdracht. 5% tot 20% verlies is normaal. </li>
   </ul></td>
 </tr> 
</table>

## Hoe te om een Methode van de Levering van Gegevens te kiezen {#data-delivery-choices}

Beschrijft technische en bedrijfsredenen om gegevens via synchrone (real time) of asynchrone (server-aan-server) methodologieën te verzenden.

<!-- c_int_delivery_choices.xml -->

### Een type gegevenslevering selecteren

* **Technische overwegingen:** De levering van gegevens hangt van de technische mogelijkheden van de gegevenspartner af. Audience Manager kan gegevens in real time van browser of door partijupdates verzenden/ontvangen door off-line, server-aan-server communicatie processen.
* **Overwegingen voor bedrijven:** De bedrijfsredenen om één leveringsmethode of een andere te selecteren hangen van de technische mogelijkheden van uw bestemmingspartner af en hoe u deze gegevens wilt gebruiken. Over het algemeen zijn synchrone gegevensoverdrachten handig wanneer u onmiddellijk actie moet ondernemen met betrekking tot gebruikersgegevens. Asynchrone gegevensoverdrachten kunnen nuttig zijn wanneer de directe actie niet wordt vereist en wanneer u tijd hebt om diepere gebruikersprofielen voor later gebruik te bouwen.

## Real-Time Data Transfer Process {#real-time-data-transfer-process}

Een algemeen overzicht van hoe de Audience Manager een synchrone gegevensuitwisseling met een derde verkoper uitvoert.

### Real-time gegevensoverdracht

<!-- c_int_overview_sync.xml -->

In real time gegevensoverdrachten verzenden en ontvangen segment IDs als gebruikersbezoeken of voeren actie op uw plaats. Over het algemeen zijn synchrone gegevensoverdrachten handig wanneer u gebruikers meteen moet kwalificeren of segmenteren terwijl ze door uw voorraad navigeren.

### Stappen voor realtime gegevensintegratie

Het integratieproces van gegevens in real time werkt als volgt:

1. Een gebruiker bezoekt de plaats van een klant die Audience Manager code bevat.
1. Audience Manager laadt een Iframe en roept het bestand [!UICONTROL Data Collection Server] ([!DNL DCS]) aan.
1. De [!DNL DCS] vraag de derdenserver (in echt - tijd) om te controleren of heeft de verkoper om het even welke segmentinformatie over de gebruiker.
1. De derde keert segmentinformatie over die gebruiker aan Audience Manager terug.
1. Audience Manager neemt segmentinformatie op en stelt het ter beschikking voor het richten.

![](assets/rt_reduce70.png)

## Proces voor batchdataoverdracht {#batch-data-transfer-process}

Een algemeen overzicht van hoe de Audience Manager gegevens synchroon (in real time) met een derdeverkoper ruilt.

### Batchgegevensintegratie

<!-- c_int_overview_async.xml -->

Het batch- ([!DNL server-to-server]) gegevensintegratieproces volgt de meeste stappen die worden beschreven in het realtime gegevensoverdrachtproces. In plaats van segment-id&#39;s direct te retourneren, worden gebruikersgegevens echter opgeslagen op onze servers en met regelmatige tussenpozen gesynchroniseerd met een externe gegevensaanbieder. Het asynchrone proces voor gegevensoverdracht is handig wanneer:

* Directe gegevensoverdracht is niet vereist.
* Gegevens verzamelen om een grote groep gesegmenteerde gebruikers samen te stellen.
* U wilt gegevensdiscrepanties en `HTTP` vraag van browser verminderen.

### Stappen voor integratie van batchgegevens

1. Een gebruiker bezoekt een klantsite.
1. Audience Manager en de externe gegevensaanbieder wijzen de bezoeker een unieke id toe (meestal met een cookie).
1. Audience Manager roept de gegevensleverancier van de derde aan om bezoeker IDs aan te passen.
1. Een gepland verzoek, gewoonlijk op een dagelijks interval, ruilt de gegevens van het bezoekerssegment tussen Audience Manager en uw derdegegevensleverancier.

![](assets/s2s_70.png)

Voor informatie beschrijvend de tijdkaders wanneer de Audience Manager binnenkomende en uitgaande [!DNL Server-to-Server] ([!UICONTROL S2S]) dossieroverdrachten verwerkt, zie de Richtlijnen [van de Tijd van de Overdracht van het](../reference/reporting-file-transfer-timeframe.md)Melden en van het Dossier van de Overdracht.
