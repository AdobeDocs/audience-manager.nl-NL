---
description: Algemene vragen en problemen in verband met dataverzameling en integratie.
seo-description: Algemene vragen en problemen in verband met dataverzameling en integratie.
seo-title: Veelgestelde vragen over dataverzameling en productintegratie
solution: Audience Manager
title: Veelgestelde vragen over dataverzameling en productintegratie
uuid: fa8e79f4-99cb-41fd-8a85-d4f92d03c7a5
keywords: SFTP; SFTP address; STFP IP address; FTP address
feature: Administration
translation-type: tm+mt
source-git-commit: 1f3b3d7d7ea8eaa0c1b64f147dc60b85f4e2f487
workflow-type: tm+mt
source-wordcount: '1151'
ht-degree: 84%

---


# Veelgestelde vragen over dataverzameling en productintegratie {#data-collection-and-product-integration-faq}

Algemene vragen en problemen in verband met dataverzameling en integratie.

<br> 

**Hoe kan ik binnenkomende traffic onderscheiden van [!DNL DCS]-traffic in [!DNL DCS]-logboekbestandexports?**

Eigenschappen die via [!UICONTROL Inbound] ‘onboarded’ zijn, worden door [!UICONTROL Inbound] ingevuld op dezelfde manier als door [!DNL DCS]. Er zijn verschillende manieren om te zien dat traffic afkomstig is van [!UICONTROL Inbound]:

* Externe IP is ingesteld op 68.67.173.18
* DomainID is ingesteld op 5325
* Regio is ingesteld op 0

<br> 

**Kunt u me een lijst van IP adressen verstrekken ik aan een lijst van gewenste personen voor dpm.demdex.net kan toevoegen?**

Helaas kunnen we dat niet. Deze IP’s worden dynamisch toegewezen, volgens geografische regio, via [!DNL Amazon Web Services]. Daardoor controleert [!DNL Audience Manager] niet het bereik van IP’s die aan dit adres kunnen worden toegewezen.

 

**Kunt u me van een IP adres voorzien ik aan een lijst van gewenste personen voor uw binnenkomende en uitgaande server van SFTP kan toevoegen?**

Ja, zie hieronder.

| Server | IP-adressen |
| ---------|----------|
| ftp-in-gtw.demdex.com | 52.3.74.119; 3.233.68.222 |
| ftp-out-gtw.demdex.com | 23.22.232.252; 18.211.109.184 |

 

De SFTP-servers hieronder zijn afgekeurd. Er worden geen nieuwe accounts ingesteld met deze servers.

| Server | IP-adres |
---------|----------|
| ftp-in.demdex.com | 54.225.117.163 |
| ftp-out.demdex.com | 23.23.188.76 |

 

**Hoe vorm ik mijn instantie van de Audience Manager om de nieuwe servers te gebruiken SFTP?**

Neem contact op met uw [!DNL Audience Manager] consultant of de klantenservice en zij configureren uw nieuwe SFTP-accounts.

 

**Wat zijn de gesteunde authentificatiemethodes voor de nieuwe servers SFTP?**

De nieuwe SFTP-servers (`ftp-in-gtw` en `ftp-out-gtw`) ondersteunen [!DNL OpenSSH Key-Based Authentication]. Wij kunnen de [!DNL SSH] sleutels voor u produceren, of u kunt ons van uw eigen openbare sleutel voorzien.

 

**Wat zijn de vereisten voor codeplaatsing en pagina laden voor een [!UICONTROL DIL]/[!DNL Analytics] Data Integration?**

Als u [!DNL Analytics]-data wilt overbrengen naar [!DNL Audience Manager], laadt u deze [!UICONTROL DIL] na de `s_code`-module, maar *vóór* de `s.t()`-functie. Plaats de code bijvoorbeeld in deze volgorde, of zorg ervoor dat de code in deze volgorde wordt geladen:

1. [!DNL Analytics] `s_code`

2. [!DNL Audience Manager] [!UICONTROL DIL]-module

3. [!DNL Analytics] `s.t()`-functie

Stel als best practice uw [!DNL Audience Manager]- [!DNL Analytics]-integratie in volgens een van deze twee methoden:

* Zet [!UICONTROL DIL] rechtstreeks in de `s_code`.

* Maak [!UICONTROL DIL] en de `s_code` beschikbaar via [!DNL Adobe Experience Platform Launch] of [!DNL Adobe DTM].

Zie [Data Integration Library (DIL)-API](../dil/dil-overview.md).

 

**Waarom ontbreken mijn [!DNL Analytics]-variabelen van een [!DNL Audience Manager]-gebeurteniscall?**

Dit gebeurt gewoonlijk in deze gevallen:

* U maakt [!UICONTROL DIL] beschikbaar via een systeem voor tagmanagement dat asynchroon laadt met andere code-elementen op de pagina.
* De `s.t()`-functie wordt eerder geladen dan [!UICONTROL DIL].

 

**Welke versies van [!DNL Analytics] werken met [!UICONTROL DIL]?**

U moet [!DNL Analytics] versie 20.2 (of hoger) en de [!DNL Adobe AppMeasurement AS]-bibliotheekversie 3.5.2 (of hoger) gebruiken om met [!UICONTROL DIL] te werken. Als u uw versie van [!DNL Analytics] of [!DNL AppMeasurement] niet weet, controleert u de [!DNL Analytics]-call die op basis van de pagina wordt uitgevoerd. Versiegegevens hieronder:

Deze klant gebruikt [!DNL Analytics] versie 24.4:

```
https://112.2o7.net/b/ss/.../1/H.24.4/...
```

Deze klant gebruikt [!DNL AppMeasurement] versie 3.5.2:

```
https://112.2o7.net/b/ss/.../0/FAS-3.5.2-AS3/...
```

<br> 

**Kan ik paginadata verzamelen als ik geen [!DNL Analytics]-klant ben?**

Ja. De [!UICONTROL DIL]-module helpt u paginadata te verzamelen, zelfs als u [!DNL Analytics] niet gebruikt. Als [!UICONTROL DIL] goed is ingesteld, kunnen data worden vastgelegd van en over:

* Metatags
* URL’s en URL-koppen
* Soorten zoekmachines
* Trefwoorden

Daarnaast kunnen clients een eenvoudig onsite object implementeren en dit invullen met sleutelwaardeparen waarop u [!UICONTROL DIL] data wilt laten verzamelen. Zo kunt u specifieke doelgroepdatapunten op uw website toevoegen en verwijderen zonder [!DNL Audience Management]-updates. Werk met uw Partner Solutions-vertegenwoordiger om dit goed in te stellen en ervoor te zorgen dat de [!DNL DIL]-module correct naar het page-object verwijst.

<br> 

**Kan [!UICONTROL DIL] data verzamelen van [!DNL Google Analytics]?**

Ja. [!UICONTROL DIL] kan bepaalde [!DNL Google Analytics]-elementen (GA) verzamelen en die data doorgeven aan [!DNL Audience Manager]. Zie:

* [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics)
* [GA.init](../dil/dil-modules.md#ga-init)

<br> 

**Kan ik onbewerkte data krijgen van [!DNL Audience Manager], en hoe granulair zijn die?**

Ja, [!DNL Audience Manager] kan data aan u verstrekken die zijn verzameld voor gebruikers die we in uw inventory hebben gezien. Dit omvat:

* De unieke gebruikers-id (UUID) die is toegewezen door [!DNL Audience Manager]
* Eigenschap- en segment-id’s
* Ongebruikte signalen
* Tijdstempels
* Pagina-URL’s

<br> 

**[!DNL Google Ad Manager]Ik wil data verzamelen op de ene website, en gebruikers targeten via op een andere website. Moet ik code implementeren op de andere eigenschap als ik geen data van die locatie wil verzamelen?**

Nee. Als de dataverzameling op de tweede website geen vereiste is, hoeft u daar geen DIL te implementeren. As long as you have access to the inventory on the second site via [!DNL Google Ad Manager], you can use the data collection from the initial site and target via [!DNL Google Ad Manager].

<br> 

**Wat is de beste leverancier van data van derden?**

Elke leverancier draagt iets unieks bij, dus het antwoord hangt af van wat u zoekt. We kunnen overlappende rapportage (zonder kosten) inschakelen om u te helpen begrijpen welke provider het beste voor u werkt.

<br> 

**Hoe worden in [!DNL Audience Manager] cookies ingesteld en variabelen doorgegeven aan [!DNL Google Ad Manager]?**

[!DNL Audience Manager] sets 2 cookies: De ene stuurt segmentvariabelen naar de [!DNL Google Ad Manager] advertentietag en de andere stelt de unieke gebruikers-id (UUID) in, die ook door [!DNL Google Ad Manager]wordt gelezen. Door de UUID aan de advertentietag toe te voegen kunnen we rapportage en doelgroepdetectie op gebruikersniveau uitvoeren.

<br> 

**Kunnen we aan een DSP informatie sturen over punten in de conversietrechter die door een gebruiker wordt bereikt?**

Ja. We kunnen trechterdata verzenden, maar het DSP moet de technische mogelijkheden hebben om die te gebruiken. Een DSP moet bevestigen dat meerdere segmenten kunnen worden behandeld. Als dat niet het geval is, moeten we misschien specifieke segmenten maken om een gebruiker uit andere segmenten te halen op basis van conversievoortgang (bijvoorbeeld dat stap 1 en 2 zijn voltooid, maar stap 3 niet). U wilt deze informatie misschien naar een DSP verzenden zodat gebruikers geretarget kunnen worden, naar een bepaalde landingspagina kunnen worden omgeleid, of specifieke creatieve items kunnen weergeven.

<br> 

**Hoe kan ik bevestigen dat via FTP verzonden data zijn opgehaald door [!DNL Audience Manager]?**

Er is een bestand opgehaald wanneer de extensie verandert van `.sync` in `.processed`. Als dit gebeurt, staat het bestand in de wachtrij voor opname. Uw accountmanager kan ook bevestigen wanneer een bestand is geüpload.

<br> 

**Ik wil de functionaliteit van de [DCS-API](../api/dcs-intro/dcs-event-calls/dcs-event-calls.md) testen. Ik verzend gebeurteniscalls zoals hieronder getoond. De calls bevatten [gedeclareerde id’s](../features/declared-ids.md) en signalen, die bepaalde eigenschappen en segmenten zouden moeten realiseren die ik al heb ingesteld. Kan ik de [!UICONTROL General Reports] en [!UICONTROL Trend Reports] gebruiken om te controleren of de eigenschap- en segmentpopulaties toenemen?**

```
https://apse2.demdex.net/event?d_rtbd=json&d_cid=123456%01abc123&c_events=placed-an-order
```

Nee, ga in dit geval niet uit van de [!UICONTROL General Reports] en [!UICONTROL Trend Reports].

De rapporten berekenen populaties op basis van de niet-geverifieerde profielrecords (UUID’s) die we zien in de back-end op het tijdstip dat de rapporten worden gegenereerd.

Bij een eerste call naar de [!DNL DCS] zijn de gedeclareerde id’s *niet* gekoppeld aan een UUID (er is dus geen [demdex-cookie](hhttps://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-am.html) aanwezig aan de clientzijde). De [!DNL DCS] genereert willekeurig een UUID, stelt een [!DNL demdex]-cookie in en geeft dit door in de reactiecall, maar de UUID wordt niet naar de back-end verzonden.

>[!NOTE]
>
>De gegenereerde UUID wordt pas gematerialiseerd in onze back-enddataopslag als het apparaat waarop het cookie is ingesteld, verdere activiteit activeert.

Daardoor zullen de rapporten niet de gebeurtenissen weergeven die door gedeclareerde id’s in uw call zijn geactiveerd. We raden u aan UUID’s, ECID’s (voorheen MID’s) of mobiele apparaat-id’s te gebruiken voor gebeurtenistestcalls naar de [!DNL DCS]. Vervolgens kunt u de eigenschap- en segmentrealisaties in de [!UICONTROL General Reports] en in de [!UICONTROL Trend Reports] verifiëren.

Zie ook de [Index van Audience Manager-id’s](../reference/ids-in-aam.md).

<br> 

**Hoe lang duurt het voordat gebruikersprofielen in alle [regio’s](../api/dcs-intro/dcs-api-reference/dcs-regions.md) worden gesynchroniseerd?**

Het synchroniseren van een gebruikersprofiel in verschillende regio’s duurt meestal maximaal 24 uur. In zeldzame gevallen kan het proces echter tot 48 uur duren.
