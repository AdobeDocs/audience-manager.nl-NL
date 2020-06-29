---
description: Een overzicht van de Adresseerbare eigenschap van het Publiek en gebruiksgevallen.
keywords: DIL
seo-description: Een overzicht van de Adresseerbare eigenschap van het Publiek en gebruiksgevallen.
seo-title: Adresseerbaar publiek
solution: Audience Manager
title: Adresseerbaar publiek
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1824'
ht-degree: 0%

---


# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Een overzicht van de [!UICONTROL Addressable Audience] functie en gebruiksgevallen.

## Wat is een [!UICONTROL Addressable Audience]probleem? {#addressable-audience-description}

De [!UICONTROL Addressable Audiences] functie toont de overlap tussen het publiek dat u over al uw eigenschappen ziet waar gegevens en uw geselecteerde bestemming worden [!DNL Audience Manager] verzameld. Om u te helpen dit concept begrijpen, neem een blik hieronder op de illustratie. De overlapping tussen elke cirkel vertegenwoordigt de verschillende soorten adresseerbare soorten publiek.

![](assets/addressableAudienceVenn.png)


| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] voor een [!UICONTROL Destination] | Een telling van alle apparaten die met alle [!DNL Audience Manager] klanten op platform-niveau tijdens de rapportterugblik periode hebben interactie gehad en die met uw gekozen zouden kunnen worden aangepast [!UICONTROL destination]. <br><br>Deze metrisch is nuttig omdat het u toont: <ul><li>De grootte van het totaal [!UICONTROL addressable audience] dat op een bepaalde gerichte doelstelling [!DNL Audience Manager] kan bereiken [!UICONTROL destination].</li><li>Hoe groot is de [!DNL Audience Manager] profielpool voor een doelplatform en de grootte van hun publiek.</li></ul> |
| [!UICONTROL Customer Total Audience] | Een aantal apparaten die of een [!UICONTROL rule-based trait] op uw eigenschappen of een [!UICONTROL onboarded trait] van uw off-line dossiers tijdens het terugblik-achtervenster hebben gerealiseerd. |
| [!UICONTROL Addressable Audience Match Rate] | Een telling van overlapping van apparaten die of een [!UICONTROL rule-based trait] of een [!UICONTROL onboarded trait] tijdens het terugblik-achtervenster en apparaten hebben dat wij een identiteitskaart synchronisatie met gekozen [!UICONTROL destination] ongeacht de tijd van syncs hebben.<br><br>Deze metrische waarde vertegenwoordigt apparaten die:<ul><li>Tijdens het terugkijkvenster een [!UICONTROL rule-based] of een [!UICONTROL onboarded trait] gebeurtenis hebben gerealiseerd `AND`</li><li>Een id synchroniseren met de gekozen id, [!UICONTROL destination] ongeacht de tijd van de syncs.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] Ht [!UICONTROL Customer Total Audience] uitgedrukt als percentage. |
| [!UICONTROL Total Segment Population] | Een telling van alle apparaten die een lid van uw [!UICONTROL segment] tijdens de rapport terugkerende periode waren. |
| [!UICONTROL Segment Addressable Audience] | Het aantal gebruikers dat [!UICONTROL segment] tijdens de terugblik-achter periode van het rapport behoorde en een actieve synchronisatie van identiteitskaart op uw plaats hebben. [!UICONTROL Segments] U kunt uw eigen gegevens van de eerste partij en gegevens van de tweede en derde partij via [!UICONTROL traits] de [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md)opnemen. <br><br>Tip: Wanneer gebruikt met de periode van de 1 dag terugblik-rug, kan metrisch u helpen de huidige staat van uw begrijpen [!UICONTROL segments]. Dit is omdat [!UICONTROL Segment Addressable Audience] metrisch de gebruikers vertegenwoordigt die in een [!UICONTROL segment] door de vorige dag bleven. Combineer dit met het feit dat [!DNL Audience Manager] verfrist [!UICONTROL Addressable Audiences] dagelijks, combinerend deze metrische en raadplegingsperiode de meest bijgewerkte momentopname van uw [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] Ht [!UICONTROL Total Segment Population] uitgedrukt als percentage. |

## [!UICONTROL Addressable Audiences] Interface {#addressable-audience-interface}

De [!UICONTROL Addressable Audience] functie verandert dit abstracte concept in kwantificeerbare gegevens. In [!DNL Audience Manager]deze functie wordt de publieksoverlapping weergegeven met gegevensvisualisaties die in één oogopslag informatie en numerieke gegevens in tabelvorm verschaffen.

[!UICONTROL Addressable Audiences] bevindt zich in **[!UICONTROL Audience Data > Destinations]**. Selecteer deze optie **[!UICONTROL Integrated Platforms > Device-Based]** om de meetgegevens voor adressaten weer te geven.

![](assets/addressable-audiences-landing.png)

De drie metriek die u op de [!UICONTROL Addressable Audiences] landingspagina kunt zien, vertegenwoordigen:

| Metrisch | Beschrijving |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Deze metrische waarde vertegenwoordigt de [!UICONTROL Customer Addressable Audience] (beschreven in de bovenstaande tabel) *voor de laatste 30 dagen.* |
| **[!UICONTROL Match Rate]** | Deze metrische waarde vertegenwoordigt de [!UICONTROL Addressable Audience Match Rate] (beschreven in de bovenstaande tabel) *voor de laatste 30 dagen*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Een telling van alle apparaten die met alle [!DNL Audience Manager] klanten op platform-niveau tijdens de rapportterugblik periode hebben interactie gehad en die met dit zouden kunnen worden aangepast [!UICONTROL destination]. Zie Metriek [op](/help/using/features/addressable-audiences.md#platform-level-metrics) Platform-Niveau voor meer informatie. |

Klik op de naam van een groep [!UICONTROL server-to-server destination] om de adresseerbare gegevens weer te geven. Nota, keert deze eigenschap gegevens voor slechts en de toegang vereist beheerdertoestemmingen terug. [!UICONTROL server-to-server destinations]

![](assets/addressableAudiences.png)

Als u deze gegevens controleert, kunt u:

* **Voorspelling en planning:** [!UICONTROL Segment Addressable Audience] de gegevens geven u meer granulariteit in de segmenten u van plan bent om naar een bestemming voor publiek te verzenden richtend en activering.

* **Prestatiebeoordelingen:** De [!UICONTROL Addressable Audiences] functie is ook een hulpprogramma voor probleemoplossing. Het laat u campagneprestaties herzien, campagnebereik begrijpen, en laat u met het richten/activeringspartners kruisen als u niet de resultaten ziet u verwacht.

### Prospecties met gegevens en implicaties van derden voor gelijke tarieven

Alvorens derdegegevens voor publieksverwerving te kopen, kunnen de klanten de overlapping met andere gegevensleveranciers bevestigen. Dit kan u helpen een geïnformeerde beslissing nemen alvorens nieuwe gegevens te kopen. De ID-syncs voor aangekochte gegevens van derden zijn niet alleen afhankelijk van de overlapping van uw gegevens, maar ook van de voetafdrukken van andere leveranciers met alle andere [!DNL Audience Manager] klanten. Uw [!DNL Adobe] consultant kan u helpen aanvullende relevante gegevensbronnen te identificeren om uw prospectiecampagnes te optimaliseren.

### Mobiele gebruikers en gelijke tarieven

Er zijn leemten wanneer u probeert verbinding te maken met gebruikers van mobiele apps [!DNL Safari] of gebruikers van mobiele apps waarbij geen externe [!DNL cookies] deelnemers aanwezig zijn. Dat maakt het moeilijk om gebruikers met sommige partners te synchroniseren omdat slechts die [!DNL Adobe] IDs voor gesynchroniseerde derde in de media leveringslogboeken [!DNL cookies] wordt verstrekt. Dit is een reden waarom je misschien [lage match-rates](../features/addressable-audiences.md#low-match-rates) ziet voor je [!UICONTROL destinations].

## Datumbereik in [!UICONTROL Addressable Audiences] en [!UICONTROL Destinations] {#date-ranges}

Lees de secties hieronder voor beschikbare datumwaaiers en hoe de gegevens uit elk interval in de rapporten voor een [!UICONTROL Addressable Audience] of [!UICONTROL Destination].

## Beschikbare datumbereiken en tijdzones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Rapporten voor uw [!UICONTROL Addressable Audiences] en [Doelen](../features/destinations/destinations.md) gebruiken de zelfde intervallen van de datumwaaier. De opties voor het datumbereik zijn:

* [!UICONTROL Last 1 Day] (Dit interval loopt van Midnight aan Midnight van de vorige periode van 24 uur. Het is geen metrisch in real time of huidige tijd.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle datums en datumbereiken worden ingesteld in de [!DNL UTC] tijdzone. Zie [Tijdzones in Audience Manager](../reference/aam-time-zones.md).

## Gegevens in Datumbereik Intervallen {#date-range-intervals}

De [!UICONTROL Addressable Audience] en [!UICONTROL Destination] metriek keren een telling van unieke gebruikers voor het geselecteerde tijdinterval terug. Een bezoeker wordt bijvoorbeeld slechts één keer meegeteld, zelfs als hij meerdere keren naar uw site komt. Het eerste bezoek is het unieke bezoek en wordt opgenomen. De volgende bezoeken komen terug en worden niet geteld omdat ze niet uniek zijn.

Datumbereiken bevatten gegevens voor het geselecteerde tijdinterval of de geselecteerde ouder. En, de gegevens verouderen uit elk rapportinterval aangezien de tijd overgaat. Stel dat u 2 bezoekers ziet nadat u de [!UICONTROL Last 30 Days] optie hebt gekozen. In de rapporten:

* *Wordt* opgenomen in de resultaten die worden geretourneerd met de langere tijdsintervallen (60 dagen, 90 dagen en Lifetime).
* *Wordt* niet opgenomen in de kortere intervallen die voorafgaan aan de [!UICONTROL Last 30 Day] optie (Huidige, 7 dagen en 14 dagen).

En op dag 31 komen deze bezoekers alleen in de 60 dagen, 90 dagen en [!UICONTROL Lifetime] resultaten. Ze zijn ouder dan 30 dagen. Bezoekers verouderen niet buiten het [!UICONTROL Lifetime] interval.

## [!UICONTROL Addressable Audiences] Metrisch {#addressable-audience-metrics}

In deze sectie worden de typen metriek beschreven die worden geleverd door [!UICONTROL Addressable Audiences].

### Metriek op klantniveau {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Deze metriek retourneert gegevens voor kenmerken die worden gerealiseerd wanneer bezoekers naar uw site komen of wanneer u binnenkomende gegevensbestanden verzendt naar [!DNL Audience Manager]. Deze metrische gegevens bieden een uitgebreide weergave van de publieksgrootte voor uw account.

| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Een telling van overlapping van apparaten die of een [!UICONTROL rule-based trait] of een [!UICONTROL onboarded trait] tijdens het terugblik-achtervenster en apparaten hebben dat wij een identiteitskaart synchronisatie met de gekozen bestemming ongeacht de tijd van syncs hebben.<br><br>Deze metrische waarde vertegenwoordigt apparaten die:<ul><li>Tijdens het terugkijkvenster een [!UICONTROL rule-based] of een [!UICONTROL onboarded trait] gebeurtenis hebben gerealiseerd `AND`</li><li>Een id synchroniseren met de gekozen id, [!UICONTROL destination] ongeacht de tijd van de syncs.</li></ul> |
| [!UICONTROL Customer Total Audience] | Een aantal apparaten die of een [!UICONTROL rule-based trait] op uw eigenschappen of een [!UICONTROL onboarded trait] van uw off-line dossiers tijdens het terugblik-achtervenster hebben gerealiseerd. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] Ht [!UICONTROL Customer Total Audience] uitgedrukt als percentage. |

### Identieke cijfers op segmentniveau {#segment-level-metrics}

Deze cijfers geven gegevens over [!UICONTROL segment] lidmaatschap. Ze zorgen voor een gedetailleerdere en nauwkeurigere weergave van de omvang van het publiek voor elk van uw [!UICONTROL segments]gebruikers.

>[!NOTE]
>
>De manier waarop het terugblik-achtervenster op het [!UICONTROL segment] niveau wordt toegepast is verschillend van dat op het klantenniveau. Bezoekers kunnen 10 [!UICONTROL trait] dagen geleden naar de site komen en ze kunnen [!UICONTROL segment] sindsdien in aanmerking komen voor een vergoeding en de [!UICONTROL segment] 2 dagen geleden verlaten. Wanneer de terugblik van 7 dagen wordt toegepast, zullen deze bezoekers op het [!UICONTROL segment] niveau maar niet op het klantenniveau worden geteld.

| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Het aantal gebruikers dat [!UICONTROL segment] tijdens de terugblik-achter periode van het rapport behoorde en een actieve synchronisatie van identiteitskaart op uw plaats hebben. Segmenten kunnen uw eigen gegevens van de eerste partij en gegevens van de tweede en derde partij bevatten, via [!UICONTROL traits] overgenomen in de [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Tip: Wanneer gebruikt met de periode van de 1 dag terugblik-rug, kan metrisch u helpen de huidige staat van uw begrijpen [!UICONTROL segments]. Dit is omdat [!UICONTROL Segment Addressable Audience] metrisch de gebruikers vertegenwoordigt die in een [!UICONTROL segment] door de vorige dag bleven. Combineer dit met het feit dat [!DNL Audience Manager] verfrist [!UICONTROL Addressable Audiences] dagelijks, combinerend deze metrische en raadplegingsperiode de meest bijgewerkte momentopname van uw [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Een telling van alle apparaten die een lid van uw [!UICONTROL segment] tijdens de rapport terugkerende periode waren. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] Ht [!UICONTROL Total Segment Population] uitgedrukt als percentage. |

### Metriek op Platform-niveau {#platform-level-metrics}

Deze metrische winst gegevens over activiteiten die over alle [!DNL Audience Manager] klanten worden verzameld. Zij kunnen een breder beeld van het publiek van de klant in vergelijking met de samengevoegde [!DNL Audience Manager] klanten verstrekken.

| Metrisch | Beschrijving |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Een telling van alle apparaten die met alle [!DNL Audience Manager] klanten op platform-niveau tijdens de rapportterugblik periode hebben interactie gehad en die met uw gekozen zouden kunnen worden aangepast [!UICONTROL destination]. <br><br>Deze metrisch is nuttig omdat het u toont:<ul><li>De grootte van [!UICONTROL total addressable audience] die op een bepaalde gericht bestemming [!DNL Audience Manager] kan bereiken.</li><li>Hoe groot is de [!DNL Audience Manager] profielpool voor een doelplatform en de grootte van hun publiek.</li></ul> |

## Vergelijken [!UICONTROL Customer] en [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

U zou niet de [!UICONTROL Customer Addressable Audience] en [!UICONTROL Segment Addressable Audience] metriek moeten vergelijken om te bepalen als één beduidender is dan andere. Dit zijn afzonderlijke, verschillende en onafhankelijke meetgegevens. Zoals in de bovenstaande definities is beschreven, zijn deze allemaal afgeleid van verschillende gegevenssets. In dat geval hoeft u geen conclusies te trekken als de ene meting groter is dan de andere. Het enige wat u kunt zeggen bij een vergelijking is:

* [!UICONTROL Customer Addressable Audiences] is gebaseerd op [!UICONTROL trait] realisaties *voor uw eigen gegevens* van de eerste partij. Deze metrisch verstrekt een brede, uitvoerige mening van uw integratie met een gegevenspartner.

* [!UICONTROL Segment Addressable Audiences] is gebaseerd op segmentkwalificaties *voor uw eigen gegevens van de eerste partij, plus gegevens* van de tweede en derde partij. Deze metrisch verstrekt korrelige, nauwkeurigere mening van uw [!UICONTROL addressable audiences] in een gericht platform.

## Oorzaken van lage matchingstarieven voor [!UICONTROL Addressable Audiences] {#low-match-rates}

Veelvoorkomende elementen die verantwoordelijk zijn voor lage [!UICONTROL Addressable Audience] match-percentages of discrepanties in gerapporteerde getallen.

| Oorzaak | Beschrijving |
|---|---|
| Mobiel verkeer | De meeste [!UICONTROL server-to-server] integraties zijn afhankelijk van synchronisatieprocessen die door derden worden gefaciliteerd [!DNL cookies]. Mobiele omgevingen maken echter geen gebruik van derden [!DNL cookies]. Hierdoor kunnen uw [!UICONTROL Addressable Audiences] getallen laag lijken in vergelijking met de [!UICONTROL segment] grootte. <br><br>Vanaf januari 2018 kunt u mobiele doelgroepen activeren op dezelfde [!DNL Google] en [!DNL Adobe Advertising Cloud] bestemmingen als voor [!UICONTROL cookie-based] doelgroepen. Hoewel dit betekent dat u [!UICONTROL segments] met gecombineerd [!DNL cookie] en mobiel id-lidmaatschap naar uw [!DNL Google] en [!DNL Advertising Cloud] doelen kunt verzenden, moet u er rekening mee houden dat [!UICONTROL Addressable Audiences] alleen de overlapping tussen [!DNL cookie] id&#39;s en doelen wordt weergegeven. [!DNL Audience Manager] 100 % van de mobiele doelgroepen wordt naar het mobiele publiek gestuurd [!UICONTROL destinations], maar mobiele doelgroepen worden niet met de [!UICONTROL Addressable Audience] meetnorm gemeten. <br><br>**Opmerking **: Neem bijvoorbeeld een bestand[!UICONTROL segment]met een populatie van 1.000.000. Als u dit[!UICONTROL segment]aan een[!DNL Google]of[!DNL Adobe Advertising Cloud]bestemming in kaart brengt, zou u een[!UICONTROL Addressable Audience]van 700.000 apparaten en een[!UICONTROL Match Rate]van 70% kunnen zien. Het lidmaatschap van 700.000 bestaat uit[!DNL cookie]id&#39;s die een id hebben die synchroon is met de[!UICONTROL destination]id. Uw[!UICONTROL Addressable Audience]kan zelfs veel hoger zijn, omdat adresseerbare mobiele id&#39;s niet in deze metrische code worden weergegeven. |
| [!DNL Safari] Verkeer | [!DNL Safari] blokkeert derden [!DNL cookies]. Zo voorkomt u dat id&#39; [!DNL Audience Manager] s worden gesynchroniseerd met de [!UICONTROL destination]. Met de introductie van [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), kunt u verwachten dat u [!UICONTROL addressable audiences] geen [!DNL Safari] gebruikers omvat. |
| Bijgehouden media-impressies | Vanwege aanbevolen procedures voor advertentieservers worden id-syncs niet binnen advertentietags gemaakt. Klanten die veel offsite advertenties maken, synchroniseren gebruikers niet naar integratie van derden in die omgevingen. Bovendien kan een grote hoeveelheid verzamelde gegevens die de indruk wekken van media [!UICONTROL addressable audience] getallen verlagen. |

## Problemen oplossen met [!UICONTROL Addressable Audiences] {#troubleshooting}

Naast het surface gelijke tarieven, kunt u ook gebruiken [!UICONTROL Addressable Audiences] als het oplossen van problemenhulpmiddel.

Bijvoorbeeld, laten wij zeggen u een segment naar een segment verzendt [!UICONTROL destination] en dat lage rapporteringsaantallen [!UICONTROL destination] toont. Als u de [!UICONTROL Addressable Audience] resultaten controleert, ziet u of dit een technisch probleem is of slechts een geval van lage tarieven. Een lage gelijke tarief toont u [!UICONTROL destination] niet al zo groot voor uw geselecteerde segmenten is. Nochtans, wijst een verschil in de [!UICONTROL total addressable audience] aantallen tussen [!DNL Audience Manager] en [!UICONTROL destination] op een integratie, synchronisatie, of ander technisch probleem. Neem in deze gevallen contact op met uw accountmanager.
