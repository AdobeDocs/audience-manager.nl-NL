---
description: Ontdek de voordelen, de types, en het gebruik van bestemmingen - om het even welk derdesysteem, zoals een advertentieserver of DSP, waar u gegevens deelt. De Bouwer van de Bestemming van het gebruik om koekjes, URL, of server-aan-server bestemmingen tot stand te brengen en te beheren.
keywords: integratiecode, doel, bestemmingsoverzicht, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming, bestemming
landing-page-description: Ontdek de voordelen, de types, en het gebruik van bestemmingen - om het even welk derdesysteem, zoals een advertentieserver of DSP, waar u gegevens deelt. De Bouwer van de Bestemming van het gebruik om koekjes, URL, of server-aan-server bestemmingen tot stand te brengen en te beheren.
seo-title: Destinations
solution: Audience Manager
title: 'Bestemmingen '
uuid: 5c7dbdec-f73f-46fe-9f12-7685e8d7334f
feature: Destination Basics
exl-id: f880bb18-057a-494d-82bf-69fc9f34781f
source-git-commit: 865800eb076811db38aec8e98714ad9712804f77
workflow-type: tm+mt
source-wordcount: '539'
ht-degree: 2%

---

# [!UICONTROL Destinations] Overzicht {#destinations}

In de Audience Manager [!UICONTROL destination] is een systeem van een derde (advertentieserver); [!DNL DSP], en netwerk, enz.) waarmee u data wilt delen. [!UICONTROL Destination Builder] is het gereedschap dat u hebt gebruikt voor het maken en beheren van [!UICONTROL cookie], [!DNL URL], of [!UICONTROL server-to-server destinations].

## Doel en voordelen {#purposes}

<!-- c_destinations.xml -->

[!UICONTROL Destinations] en [!UICONTROL Destination Builder] laten maken [!UICONTROL destinations] en verzend informatie over gesegmenteerde gebruikers naar uw gegevenspartner. Dit helpt u:

* **Protect-gegevenswaarde:** In plaats van alle gebruikersgegevens naar een [!UICONTROL destination], [!UICONTROL Destination Builder] Hiermee kunt u alleen specifieke informatie over gekwalificeerde gebruikers delen.
* **Actie nemen op uw gegevens:** Gegevens verzenden naar een [!UICONTROL destination] de partner helpt hen snel gekwalificeerde publiekssegmenten ontwikkelen en richten.
* **Minder technische overhead:** Zakelijke gebruikers kunnen instellen [!UICONTROL destinations] veilig in de [!UICONTROL Destination Builder] interface. Hierdoor wordt de tijd die nodig is voor het testen vóór de implementatie, verkort. Met [!UICONTROL Destination Builder], maakt, beheert en verwijdert u [!UICONTROL destinations] als uw zaken veranderen, allen zonder het werken door een lange ontwikkelingscyclus.

## Technische overwegingen {#technical-considerations}

<!-- destination-delivery-methods.xml -->

De levering van gegevens hangt af van hoe uw gegevenspartner wil, of kan ontvangen [!UICONTROL destination] informatie. Technische of technische beperkingen kunnen [!UICONTROL destination] van het ontvangen van gegevens via [!DNL URL], [!UICONTROL cookie], of [!UICONTROL server-to-server] processen. Het werk met uw derdepartner om te bepalen welke methode zij kunnen gebruiken.

## Overwegingen voor bedrijven {#business-considerations}

De zakelijke beslissingen voor het selecteren van een leveringsmethode op een andere zijn afhankelijk van de technische mogelijkheden van uw [!UICONTROL destination] partner en wat u met gekwalificeerde gebruikersinformatie wilt doen. Technische beperkingen kunnen bijvoorbeeld uw opties beperken als een [!UICONTROL destination] kan geen gegevens door een bepaalde leveringsmethode ontvangen. Als er echter geen technische problemen zijn, kunt u informatie verzenden op basis van de manier waarop u actie wilt ondernemen met betrekking tot die gegevens. Bijvoorbeeld:

* [!DNL URL]s en [!UICONTROL cookie-based destinations] werken bijna synchroon met gebruikersacties op een pagina.
* [!UICONTROL Server-to-server] methoden zijn goed voor het opbouwen van diepe publiekssegmenten in de loop der tijd .

## [!UICONTROL Destination] Typen en gangbare toepassingen {#destination-types}

De voorbeelden in de volgende tabel kunnen u helpen begrijpen wanneer u een bepaalde [!UICONTROL destination] en de verschillen tussen elk type.

| [!UICONTROL Destination] Type | Gebruikt gewoonlijk | Voorbeeld | Overwegingen |
|--- |--- |--- |--- |
| **[!UICONTROL Adobe Experience Cloud Destinations]** | U moet gegevens naar andere Adobe Experience Cloud-oplossingen verzenden. | Gegevens worden naar Adobe Analytics verzonden. |  |
| **[!UICONTROL People-Based Destinations]** | U moet publiekssegmenten naar op mensen gebaseerde omgevingen, zoals Facebook, verzenden. | Aangepaste aanbiedingen aan bestaande klanten leveren op basis van hun aankoopgeschiedenis | Het richten van het publiek wordt gedaan door gehakte herkenningstekens. Zie [Bestemmingen op basis van personen](people-based-destinations-overview.md). |
| **[!UICONTROL Device-Based Destinations]** (**Server-naar-server**) | <ul><li>Directe gegevensoverdracht is niet vereist.</li><li>Gegevens verzamelen om een grote groep gekwalificeerde gebruikers samen te stellen.</li></ul> | Gegevens verzamelen in de tijd (uren of dagen) om deze te gebruiken in een campagne die op een latere datum moet worden uitgevoerd. | <ul><li>Hiermee worden gegevens over nieuwe en vorige sitebezoekers overgedragen. </li><li>Bezoekers hoeven niet opnieuw te worden gezien om in aanmerking te komen voor andere segmenten.</li></ul> |
| **[!UICONTROL Custom Destinations]** (**URL** of **Cookie**) | U moet gegevens onmiddellijk overbrengen zodat een bestemming actie op een gekwalificeerde gebruiker kan onmiddellijk ondernemen. | Gegevens verzenden vanaf een site voor het kopen van tickets. Een [!UICONTROL URL] of [!UICONTROL cookie destination] om de gebruiker te kwalificeren en onmiddellijk opnieuw te richten. | <ul><li>Hiermee worden alleen gegevens over nieuwe bezoekers overgedragen. </li><li>Bezoekers moeten weer zichtbaar worden om in aanmerking te komen voor het segment.</li></ul> |
