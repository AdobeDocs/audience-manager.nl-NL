---
description: Ontdek de voordelen, de types en het gebruik van bestemmingen - elk systeem van derden, zoals een advertentieserver of DSP, waar u gegevens deelt. Gebruik Destination Builder om cookies, URL- of server-naar-server-bestemmingen te maken en beheren.
keywords: integratiecode, doel, bestemmingsoverzicht, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming
landing-page-description: Ontdek de voordelen, de types en het gebruik van bestemmingen - elk systeem van derden, zoals een advertentieserver of DSP, waar u gegevens deelt. Gebruik Destination Builder om cookies, URL- of server-naar-server-bestemmingen te maken en beheren.
short-description: Ontdek de voordelen, de types en het gebruik van bestemmingen - elk systeem van derden, zoals een advertentieserver of DSP, waar u gegevens deelt. Gebruik Destination Builder om cookies, URL- of server-naar-server-bestemmingen te maken en beheren.
seo-title: Destinations
solution: Audience Manager
title: Doelen
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 5d62ecabfe66faa024f8e89149e47dd76d1bba86
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 18%

---

# [!UICONTROL Destinations] Overzicht {#destinations}

In Audience Manager is een [!UICONTROL destination] -systeem een systeem van derden (advertentieserver, [!DNL DSP] , netwerk, enz.) waarmee u gegevens wilt delen. [!UICONTROL Destination Builder] is het gereedschap dat u hebt gebruikt voor het maken en beheren van [!UICONTROL cookie] , [!DNL URL] of [!UICONTROL server-to-server destinations] .

## Doel en voordelen {#purposes}

<!-- c_destinations.xml -->

Met [!UICONTROL Destinations] en [!UICONTROL Destination Builder] kunt u [!UICONTROL destinations] maken en informatie over gesegmenteerde gebruikers naar uw gegevenspartner sturen. Dit helpt u:

* **beschermt gegevenswaarde:** eerder dan verzendt alle gebruikersgegevens naar a [!UICONTROL destination], [!UICONTROL Destination Builder] laat u specifieke informatie over gekwalificeerde slechts gebruikers delen.
* **neem actie op uw gegevens:** Verzendend gegevens aan een [!UICONTROL destination] partner helpt hen snel gekwalificeerde publiekssegmenten ontwikkelen en richten.
* **Verminder technische overheadkosten:** de Bedrijfs gebruikers kunnen opstelling [!UICONTROL destinations] veilig in de [!UICONTROL Destination Builder] interface. Hierdoor wordt de tijd die nodig is voor het testen vóór de implementatie beperkt. Met [!UICONTROL Destination Builder] maakt, beheert en verwijdert u [!UICONTROL destinations] wanneer uw bedrijf iets anders nodig heeft, allemaal zonder een lange ontwikkelingscyclus door te voeren.

## Technische overwegingen {#technical-considerations}

<!-- destination-delivery-methods.xml -->

De gegevenslevering hangt af van hoe uw gegevenspartner [!UICONTROL destination] informatie wil of kan ontvangen. Technische of technische beperkingen kunnen voorkomen dat een [!UICONTROL destination] gegevens ontvangt via [!DNL URL] -, [!UICONTROL cookie] - of [!UICONTROL server-to-server] -processen. Het werk met uw derdepartner om te bepalen welke methode zij kunnen gebruiken.

## Overwegingen voor bedrijven {#business-considerations}

De zakelijke beslissingen voor het selecteren van een leveringsmethode op een andere zijn afhankelijk van de technische mogelijkheden van uw [!UICONTROL destination] -partner en van wat u wilt doen met gekwalificeerde gebruikersinformatie. Technische beperkingen kunnen bijvoorbeeld uw opties beperken als een [!UICONTROL destination] geen gegevens kan ontvangen via een bepaalde leveringsmethode. Als er echter geen technische problemen zijn, kunt u informatie verzenden op basis van de manier waarop u actie wilt ondernemen met betrekking tot die gegevens. Bijvoorbeeld:

* [!DNL URL] en [!UICONTROL cookie-based destinations] werken bijna synchroon met gebruikersacties op een pagina.
* [!UICONTROL Server-to-server] -methoden zijn geschikt voor het opbouwen van diepe publiekssegmenten in de loop der tijd.

## [!UICONTROL Destination] Typen en gangbare toepassingen {#destination-types}

De voorbeelden in de volgende tabel kunnen u helpen begrijpen wanneer u een bepaald [!UICONTROL destination] type moet gebruiken en welke verschillen er tussen de verschillende typen bestaan.

| [!UICONTROL Destination] Type | Gebruikt gewoonlijk | Voorbeeld | Overwegingen |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | U moet gegevens naar andere Adobe Experience Cloud-oplossingen verzenden. | Gegevens worden naar Adobe Analytics verzonden. |  |
| **[!UICONTROL People-Based Destinations]** | U moet publiekssegmenten naar op mensen gebaseerde omgevingen, zoals Facebook, verzenden. | Aangepaste aanbiedingen aan bestaande klanten leveren op basis van hun aankoopgeschiedenis | Het richten van het publiek wordt gedaan door gehakte herkenningstekens. Zie [ op mensen-Gebaseerde Doelen ](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**server-aan-server**) | <ul><li>Directe gegevensoverdracht is niet vereist.</li><li>Gegevens verzamelen om een grote groep gekwalificeerde gebruikers samen te stellen.</li></ul> | Gegevens verzamelen in de tijd (uren of dagen) om deze te gebruiken in een campagne die op een latere datum moet worden uitgevoerd. | <ul><li>Hiermee worden gegevens over nieuwe en vorige sitebezoekers overgedragen. </li><li>Bezoekers hoeven niet opnieuw te worden gezien om in aanmerking te komen voor andere segmenten.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** of **Koekje**) | U moet gegevens onmiddellijk overbrengen zodat een bestemming actie op een gekwalificeerde gebruiker kan onmiddellijk ondernemen. | Gegevens verzenden vanaf een site voor het kopen van tickets. Gebruik een [!UICONTROL URL] of [!UICONTROL cookie destination] om de gebruiker in aanmerking te nemen en onmiddellijk een nieuwe bestemming te geven. | <ul><li>Hiermee worden alleen gegevens over nieuwe bezoekers overgedragen. </li><li>Bezoekers moeten weer zichtbaar worden om in aanmerking te komen voor het segment.</li></ul> |
