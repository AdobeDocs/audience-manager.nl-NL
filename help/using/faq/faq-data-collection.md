---
description: Algemene vragen over gegevensverzameling en integratie.
seo-description: Algemene vragen over gegevensverzameling en integratie.
seo-title: Veelgestelde vragen over gegevensverzameling en productintegratie
solution: Audience Manager
title: Veelgestelde vragen over gegevensverzameling en productintegratie
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
translation-type: tm+mt
source-git-commit: 92751df14777335744db69bfb0c9b7b2f9088785
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 0%

---


# Veelgestelde vragen over gegevensverzameling en productintegratie{#data-collection-and-product-integration-faq}

Algemene vragen over gegevensverzameling en integratie.

<br> 

<!-- 

faq_data_collection_integration.xml

 -->

**Hoe kan ik binnenkomend verkeer van[!UICONTROL DCS]verkeer in de uitvoer van het[!UICONTROL DCS]logboekdossier onderscheiden?**

De treinen die via [!UICONTROL Inbound] worden ingelegd, worden op dezelfde manier gevuld als [!UICONTROL Inbound] de reizigers [!UICONTROL DCS]. Er zijn een paar verschillende manieren om te zien dat het verkeer uit kwam [!UICONTROL Inbound]:

* Externe IP wordt ingesteld op 68.67.173.18
* DomainID wordt ingesteld op 5325
* Regio wordt ingesteld op 0

<br> 

**Kunt u me een lijst van IP adressen verstrekken ik aan kan toevoegen toestaan lijst voor dpm.demdex.net?**

Helaas kunnen we dat niet. Deze IPs wordt dynamisch toegewezen, door geografisch gebied, door [!DNL Amazon Web Services]. Dientengevolge, controleert [!DNL Audience Manager] niet de waaier van IPs die aan dit adres kan worden toegewezen.

<br> 

**Kan u me van een IP adres voorzien ik aan kan toevoegen sta lijst voor uw binnenkomende en uitgaande server sFTP toe?**

Ja, zie hieronder.

| Item | Adres |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

<br> 

**Wat zijn de vereisten voor plaatsing van de code en het laden van de pagina voor een[!UICONTROL DIL]/[!DNL Analytics]Integratie van Gegevens?**

Als u [!DNL Analytics] gegevens wilt overbrengen naar [!DNL Audience Manager], laadt u deze [!UICONTROL DIL] na de `s_code` module, maar *vóór* de `s.t()` functie. Plaats de code bijvoorbeeld in de volgende volgorde of zorg ervoor dat deze wordt geladen:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL] module

3. [!DNL Analytics] `s.t()` function

Stel uw [!DNL Audience Manager]- [!DNL Analytics] integratie met een van de volgende twee methoden als beste praktijken in:

* Zet [!UICONTROL DIL] rechtstreeks in de `s_code`.

* Serve [!UICONTROL DIL] en de `s_code` doorheen [!DNL Adobe Experience Platform Launch] of [!DNL Adobe DTM].

Zie [Data Integration Library (DIL) API](../dil/dil-overview.md).

<br> 

**Waarom ontbreken mijn[!DNL Analytics]variabelen van een[!DNL Audience Manager]gebeurtenisvraag?**

Dit gebeurt gewoonlijk wanneer:

* U gebruikt [!UICONTROL DIL] een tagbeheersysteem dat het asynchroon laadt met andere code-elementen op de pagina.
* De `s.t()` functie wordt eerder geladen [!UICONTROL DIL].

<br> 

**Met welke versies van[!DNL Analytics]werken[!UICONTROL DIL]?**

U moet [!DNL Analytics] versie 20.2 (of hoger) en de [!DNL Adobe AppMeasurement AS] bibliotheekversie 3.5.2 (of hoger) gebruiken om met [!UICONTROL DIL]. Als u uw [!DNL Analytics] of [!DNL AppMeasurement] versie niet kent, controleer de [!DNL Analytics] vraag die van de pagina wordt gemaakt. Versiegegevens hieronder:

Deze klant gebruikt [!DNL Analytics] versie 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Deze klant gebruikt [!DNL AppMeasurement] versie 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Kan ik paginagegevens verzamelen als ik geen[!DNL Analytics]klant ben?**

Ja. De [!UICONTROL DIL] module helpt u paginagegevens te verzamelen zelfs als u niet gebruikt [!DNL Analytics]. Wanneer de opstelling behoorlijk, gegevens van en over kan vangen over: [!UICONTROL DIL]

* Meta-tags
* URL&#39;s en URL-kopteksten
* Motortypen zoeken
* Trefwoorden

Daarnaast kunnen clients een eenvoudig onsite object implementeren en dit vullen met sleutelwaardeparen waarop u gegevens wilt verzamelen. [!UICONTROL DIL] Zo kunt u specifieke publieksgegevenspunten op uw site toevoegen en verwijderen zonder [!DNL Audience Management] updates. Het werk met uw vertegenwoordiger van de Oplossingen van de Partner om dit te plaatsen en de [!DNL DIL] moduleverwijzingen correct te verzekeren het paginavoorwerp.

<br> 

**Kunnen gegevens[!UICONTROL DIL]verzamelen van[!DNL Google Analytics]?**

Ja. [!UICONTROL DIL] kan bepaalde [!DNL Google Analytics] (GA) elementen verzamelen en die gegevens doorgeven aan [!DNL Audience Manager]. Zie:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Kan ik onbewerkte gegevens krijgen van[!DNL Audience Manager]en hoe korrelig is het?**

Ja, [!DNL Audience Manager] kan u gegevens verstrekken die voor gebruikers worden verzameld die wij in uw inventaris hebben gezien. Dit omvat:

* De unieke gebruikersnaam (UUID) die is toegewezen door [!DNL Audience Manager]
* Trait- en segment-id&#39;s
* Ongebruikte signalen
* Tijdstempels
* Pagina-URL&#39;s

<br> 

**Ik wil gegevens op één site verzamelen en gebruikers als doel instellen via DFP op een andere site. Moet ik code op het andere bezit opstellen als ik geen gegevens van die plaats wil verzamelen?**

Nee. Als de gegevensinzameling op de tweede plaats geen vereiste is, te hoeven u niet om DIL daar op te stellen. Zolang u toegang tot de inventaris op de tweede plaats via DFP hebt, kunt u de gegevensinzameling van de aanvankelijke plaats en doel via DFP gebruiken.

<br> 

**Wat is de beste leverancier van gegevens van derden?**

Elke leverancier brengt iets uniek aan de lijst, zodat hangt het antwoord af van wat u zoekt. Wij kunnen overlappende rapportage (zonder kosten) inschakelen om u te helpen begrijpen welke provider het beste voor u werkt.

<br> 

**Hoe worden cookies ingesteld en variabelen doorgegeven aan DFP?[!DNL Audience Manager]**

[!DNL Audience Manager] sets 2 cookies: De ene stuurt segmentvariabelen naar de DFP ad-tag en de andere stelt onze unieke gebruikers-id (UUID) in, die ook door DFP wordt gelezen. Door de UUID aan de advertentietag toe te voegen, kunnen we rapportage op gebruikersniveau en publieksdetectie uitvoeren.

<br> 

**Kunnen wij een DSP informatie over punten in de omzettingstunnel verzenden die door een gebruiker wordt bereikt?**

Ja. We kunnen trechter-gegevens verzenden, maar het DSP moet over de technische mogelijkheden beschikken om het te gebruiken. Een DSP moet bevestigen zij veelvoudige segmenten kunnen behandelen. Als dat niet het geval is, moeten we wellicht specifieke segmenten maken om een gebruiker uit andere segmenten te halen op basis van de voortgang van de conversie (bijvoorbeeld voltooide stap 1 en 2, maar niet stap 3). U kunt deze informatie naar een DSP willen verzenden zodat zij gebruikers kunnen opnieuw richten, hen aan een specifieke landingspagina, of specifieke creatieven tonen.

<br> 

**Hoe kan ik bevestigen dat via FTP verzonden gegevens zijn opgehaald door[!DNL Audience Manager].**

Er is een bestand opgehaald wanneer de extensie verandert van `.sync` in `.processed`. Als dit gebeurt, bevindt het bestand zich in de wachtrij met ingevulde gegevens. Uw accountmanager kan ook bevestigen wanneer een bestand is geüpload.

<br> 

**Ik wil de functionaliteit van de[DCS API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)testen. Ik verzend gebeurtenisvraag zoals hieronder getoond. De vraag bevat[Gedeclareerde IDs](../features/declared-ids.md)en signalen, die sommige eigenschappen en segmenten zouden moeten realiseren ik reeds opstelling. Kan ik het gebruiken[!UICONTROL General Reports]en[!UICONTROL Trend Reports]om te verifiëren of de eigenschap en segmentpopulaties toenemen?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Nee, ga niet uit van het [!UICONTROL General Reports] en [!UICONTROL Trend Reports] in dit geval.

De rapporten berekenen populaties die op de unauthenticated profielverslagen (UUIDs) worden gebaseerd wij in het achtereind zien op het tijdstip dat de rapporten worden geproduceerd.

Bij een eerste aanroep naar de id zijn de gedeclareerde id&#39;s [!UICONTROL DCS]niet *gekoppeld aan een UUID (er is dus geen* demdex-cookie [](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) aanwezig aan de clientzijde). De [!UICONTROL DCS] URL genereert een UUID willekeurig en stelt een [!DNL demdex] cookie in en geeft deze door in de antwoordaanroep, maar de UUID wordt niet naar de backend verzonden.

>[!NOTE]
>
>De gegenereerde UUID wordt pas geconcretiseerd in onze back-endgegevensopslag als het apparaat waarop het cookie is ingesteld, verdere activiteit activeert.

Om deze reden, zullen de rapporten niet op de gebeurtenissen wijzen die door gedeclareerde IDs in uw vraag worden teweeggebracht. We raden u aan UUID, ECID (voorheen MID) of mobiele apparaat-id&#39;s te gebruiken voor gebeurtenistestaanroepen naar de [!UICONTROL DCS]server. Dan, kunt u de eigenschap en segmentrealisaties in [!UICONTROL General Reports] en in [!UICONTROL Trend Reports]. verifiëren.

Zie ook de [Index van Audience Manager-id&#39;s](../reference/ids-in-aam.md).

<br> 

**Hoe lang duurt het voordat gebruikersprofielen in alle[regio](../api/dcs-intro/dcs-api-reference/dcs-regions.md)&#39;s worden gesynchroniseerd?**

Het synchroniseren van een gebruikersprofiel in verschillende regio&#39;s duurt meestal maximaal 24 uur. In zeldzame gevallen kan het proces echter tot 48 uur duren.
