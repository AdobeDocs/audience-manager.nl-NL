---
description: In Audience Manager, is een bestemming om het even welk derdesysteem (ad server, DSP, en netwerk, enz.) waarmee u data wilt delen. De Bouwer van de bestemming is het hulpmiddel u gebruikte om koekje, URL, of server-aan-server bestemmingen tot stand te brengen en te beheren.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: In Audience Manager, is een bestemming om het even welk derdesysteem (ad server, DSP, en netwerk, enz.) waarmee u data wilt delen. De Bouwer van de bestemming is het hulpmiddel u gebruikte om koekje, URL, of server-aan-server bestemmingen tot stand te brengen en te beheren.
seo-title: 'Bestemmingen '
solution: Audience Manager
title: 'Bestemmingen '
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 5%

---


# [!UICONTROL Destinations] Overzicht {#destinations}

In Audience Manager, [!UICONTROL destination] is een systeem van derden (advertentieserver, [!DNL DSP]en netwerk, enz.) waarmee u data wilt delen. [!UICONTROL Destination Builder] Dit is het gereedschap dat u hebt gebruikt voor het maken en beheren [!UICONTROL cookie], [!DNL URL]of [!UICONTROL server-to-server destinations].

## Doel en voordelen {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] en [!UICONTROL Destination Builder] laat u informatie over gesegmenteerde gebruikers tot stand brengen [!UICONTROL destinations] en verzenden naar uw gegevenspartner. Dit helpt u:

* **Gegevenswaarde beveiligen:** In plaats van alle gebruikersgegevens naar een [!UICONTROL destination]server te verzenden, kunt [!UICONTROL Destination Builder] u specifieke informatie alleen over gekwalificeerde gebruikers delen.
* **Actie nemen op uw gegevens:** Het verzenden van gegevens naar een [!UICONTROL destination] partner helpt hen snel gekwalificeerde publiekssegmenten ontwikkelen en richten.
* **Minder technische overhead:** Zakelijke gebruikers kunnen de installatie [!UICONTROL destinations] veilig uitvoeren in de [!UICONTROL Destination Builder] interface. Hierdoor wordt de tijd die nodig is voor het testen vóór de implementatie, verkort. Met [!UICONTROL Destination Builder], creeert, beheert en schrapt u, [!UICONTROL destinations] aangezien uw bedrijfsbehoeften veranderen, allen zonder het werken door een lange ontwikkelingscyclus.

## Technische overwegingen {#technical-considerations}

<!-- destination-delivery-methods.xml -->

De levering van gegevens hangt af van hoe uw gegevenspartner [!UICONTROL destination] informatie wil, of kan ontvangen. Technische of technische beperkingen kunnen voorkomen dat een [!UICONTROL destination] gebruiker gegevens ontvangt via [!DNL URL], [!UICONTROL cookie]of [!UICONTROL server-to-server] processen. Het werk met uw derdepartner om te bepalen welke methode zij kunnen gebruiken.

## Overwegingen voor bedrijven {#business-considerations}

De bedrijfsbesluiten voor het selecteren van één leveringsmethode over een andere hangen van de technische mogelijkheden van uw [!UICONTROL destination] partner en af wat u met gekwalificeerde gebruikersinformatie wilt doen. Technische beperkingen kunnen bijvoorbeeld uw opties beperken als een gebruiker gegevens niet via een bepaalde leveringsmethode [!UICONTROL destination] kan ontvangen. Als er echter geen technische problemen zijn, kunt u informatie verzenden op basis van de manier waarop u actie wilt ondernemen met betrekking tot die gegevens. Bijvoorbeeld:

* [!DNL URL]en werken bijna synchroon met gebruikershandelingen op een pagina. [!UICONTROL cookie-based destinations]
* [!UICONTROL Server-to-server] methoden zijn goed voor het opbouwen van diepe publiekssegmenten in de loop der tijd .

## [!UICONTROL Destination] Typen en gangbare toepassingen {#destination-types}

De voorbeelden in de volgende tabel kunnen u helpen begrijpen wanneer u een bepaald type gebruikt [!UICONTROL destination] en welke verschillen er tussen de verschillende typen zijn.

| [!UICONTROL Destination] Type | Gebruikt gewoonlijk | Voorbeeld | Overwegingen |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | U moet gegevens naar andere Adobe Experience Cloud-oplossingen verzenden. | Gegevens worden naar Adobe Analytics verzonden. |  |
| **[!UICONTROL People-Based Destinations]** | U moet publiekssegmenten naar op mensen gebaseerde omgevingen, zoals Facebook, verzenden. | Aangepaste aanbiedingen aan bestaande klanten leveren op basis van hun aankoopgeschiedenis | Het richten van het publiek wordt gedaan door gehakte herkenningstekens. Zie Op [mensen gebaseerde Doelen](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-naar-server**) | <ul><li>Directe gegevensoverdracht is niet vereist.</li><li>Gegevens verzamelen om een grote groep gekwalificeerde gebruikers samen te stellen.</li></ul> | Gegevens verzamelen in de tijd (uren of dagen) om deze te gebruiken in een campagne die op een latere datum moet worden uitgevoerd. | <ul><li>Hiermee worden gegevens over nieuwe en vorige sitebezoekers overgedragen. </li><li>Bezoekers hoeven niet opnieuw te worden gezien om in aanmerking te komen voor andere segmenten.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** of **cookie**) | U moet gegevens onmiddellijk overbrengen zodat een bestemming actie op een gekwalificeerde gebruiker kan onmiddellijk ondernemen. | Gegevens verzenden vanaf een site voor het kopen van tickets. Gebruik een [!UICONTROL URL] of [!UICONTROL cookie destination] om de gebruiker in aanmerking te nemen en het doel onmiddellijk te wijzigen. | <ul><li>Hiermee worden alleen gegevens over nieuwe bezoekers overgedragen. </li><li>Bezoekers moeten weer zichtbaar worden om in aanmerking te komen voor het segment.</li></ul> |
