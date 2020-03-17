---
description: In de Manager van de Publiek, is een bestemming om het even welk derdesysteem (ad server, DSP, en netwerk, enz.) waarmee u gegevens wilt delen. De Bouwer van de bestemming is het hulpmiddel u gebruikte om koekje, URL, of server-aan-server bestemmingen tot stand te brengen en te beheren.
keywords: integration code, destination, destination overview, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination, destination
seo-description: In de Manager van de Publiek, is een bestemming om het even welk derdesysteem (ad server, DSP, en netwerk, enz.) waarmee u gegevens wilt delen. De Bouwer van de bestemming is het hulpmiddel u gebruikte om koekje, URL, of server-aan-server bestemmingen tot stand te brengen en te beheren.
seo-title: Doelen
solution: Audience Manager
title: Doelen
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
translation-type: tm+mt
source-git-commit: e141d04201b94bac30cdbe97818cb8eb91ebbaea

---


# Destinations Overview {#destinations}

In de Manager van de Publiek, is een bestemming om het even welk derdesysteem (advertentieserver, [!DNL DSP], en netwerk, enz.) waarmee u gegevens wilt delen. [!UICONTROL Destination Builder] is het hulpmiddel u gebruikte om koekje, [!DNL URL], of server-aan-server bestemmingen tot stand te brengen en te beheren.

## Doel en voordelen {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] en [!UICONTROL Destination Builder] laat u bestemmingen tot stand brengen en informatie over gesegmenteerde gebruikers naar uw gegevenspartner verzenden. Dit helpt u:

* **Gegevenswaarde beveiligen:** In plaats van alle gebruikersgegevens naar een bestemming te verzenden, [!UICONTROL Destination Builder] kunt u specifieke informatie alleen over gekwalificeerde gebruikers delen.
* **Actie nemen op uw gegevens:** Het verzenden van gegevens naar een bestemmingspartner helpt hen snel gekwalificeerde publiekssegmenten ontwikkelen en richten.
* **Minder technische overhead:** De zakelijke gebruikers kunnen de doelen veilig in de [!UICONTROL Destination Builder] interface instellen. Hierdoor wordt de tijd die nodig is voor het testen vóór de implementatie, verkort. Met [!UICONTROL Destination Builder], creeert u, beheert en schrapt bestemmingen aangezien uw bedrijfsbehoeften veranderen, allen zonder het werken door een lange ontwikkelingscyclus.

## Technische overwegingen {#technical-considerations}

<!-- destination-delivery-methods.xml -->

De levering van gegevens hangt af van hoe uw gegevenspartner bestemmingsinformatie wil, of kan ontvangen. De technische of technische beperkingen kunnen een bestemming verhinderen gegevens via [!DNL URL], koekje, of server-aan-server processen te ontvangen. Het werk met uw derdepartner om te bepalen welke methode zij kunnen gebruiken.

## Overwegingen voor bedrijven {#business-considerations}

De bedrijfsbesluiten voor het selecteren van één leveringsmethode over een andere hangen van de technische mogelijkheden van uw bestemmingspartner af en wat u met gekwalificeerde gebruikersinformatie wilt doen. Technische beperkingen kunnen bijvoorbeeld uw opties beperken als een bestemming geen gegevens kan ontvangen via een bepaalde leveringsmethode. Als er echter geen technische problemen zijn, kunt u informatie verzenden op basis van de manier waarop u actie wilt ondernemen met betrekking tot die gegevens. Bijvoorbeeld:

* [!DNL URL]s en op cookies gebaseerde doelen werken bijna synchroon met gebruikersacties op een pagina.
* Server-aan-server methodes zijn goed om diepe publiekssegmenten in tijd te bouwen.

## Doeltypen en typisch gebruik {#destination-types}

De voorbeelden in de volgende lijst kunnen u helpen begrijpen wanneer om een bepaalde bestemming en de verschillen tussen elk type te gebruiken.

| Doeltype | Gebruikt gewoonlijk | Voorbeeld | Overwegingen |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | U moet gegevens naar andere Adobe Experience Cloud-oplossingen verzenden. | Gegevens worden verzonden naar Adobe Analytics. |  |
| **[!UICONTROL People-Based Destinations]** | U moet publiekssegmenten naar op mensen gebaseerde omgevingen, zoals Facebook, verzenden. | Aangepaste aanbiedingen aan bestaande klanten leveren op basis van hun aankoopgeschiedenis | Het richten van het publiek wordt gedaan door gehakte herkenningstekens. Zie Op [mensen gebaseerde Doelen](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-naar-server**) | <ul><li>Directe gegevensoverdracht is niet vereist.</li><li>Gegevens verzamelen om een grote groep gekwalificeerde gebruikers samen te stellen.</li></ul> | Gegevens verzamelen in de tijd (uren of dagen) om deze te gebruiken in een campagne die op een latere datum moet worden uitgevoerd. | <ul><li>Hiermee worden gegevens over nieuwe en vorige sitebezoekers overgedragen. </li><li>Bezoekers hoeven niet opnieuw te worden gezien om in aanmerking te komen voor andere segmenten.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** of **cookie**) | U moet gegevens onmiddellijk overbrengen zodat een bestemming actie op een gekwalificeerde gebruiker kan onmiddellijk ondernemen. | Gegevens verzenden vanaf een site voor het kopen van tickets. Gebruik een URL of een cookie-bestemming om de gebruiker in aanmerking te laten komen en onmiddellijk opnieuw als doel in te stellen. | <ul><li>Hiermee worden alleen gegevens over nieuwe bezoekers overgedragen. </li><li>Bezoekers moeten weer zichtbaar worden om in aanmerking te komen voor het segment.</li></ul> |
