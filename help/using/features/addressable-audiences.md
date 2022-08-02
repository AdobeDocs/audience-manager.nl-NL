---
description: Een overzicht van de Adresseerbare eigenschap van het Publiek en gebruiksgevallen.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Addressable Audiences
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1813'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Een overzicht van de [!UICONTROL Addressable Audience] -functies en -gebruik.

## Wat is een [!UICONTROL Addressable Audience]? {#addressable-audience-description}

De [!UICONTROL Addressable Audiences] toont u de overlapping tussen het publiek u over al uw eigenschappen ziet waar [!DNL Audience Manager] verzamelt gegevens en uw geselecteerde bestemming. Om u te helpen dit concept begrijpen, neem een blik hieronder op de illustratie. De overlapping tussen elke cirkel vertegenwoordigt de verschillende soorten adresseerbare soorten publiek.

![](assets/addressableAudienceVenn.png)


| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] voor een [!UICONTROL Destination] | Een telling van alle apparaten die met allen in wisselwerking staan [!DNL Audience Manager] klanten op platformniveau tijdens de periode van de rapportterugblik en die met uw gekozen zou kunnen aanpassen [!UICONTROL destination]. <br><br>Deze metrisch is nuttig omdat het u toont: <ul><li>De omvang van het totaal [!UICONTROL addressable audience] dat [!DNL Audience Manager] kan een specifieke doelgerichte [!UICONTROL destination].</li><li>Hoe groot is het [!DNL Audience Manager] profielpool is bestemd voor een doelplatform en de omvang van hun publiek.</li></ul> |
| [!UICONTROL Customer Total Audience] | Een aantal apparaten dat een van de [!UICONTROL rule-based trait] op uw eigenschappen of [!UICONTROL onboarded trait] uit uw offlinebestanden tijdens het terugzoekvenster. |
| [!UICONTROL Customer Addressable Audience] | Een telling van overlapping van apparaten die één van beiden hebben gerealiseerd [!UICONTROL rule-based trait] of [!UICONTROL onboarded trait] tijdens het terugblik venster en apparaten dat wij een identiteitskaart hebben die met gekozen [!UICONTROL destination] ongeacht de tijd van syncs.<br><br>Deze metrische waarde vertegenwoordigt apparaten die:<ul><li>Heeft u een van de [!UICONTROL rule-based] of [!UICONTROL onboarded trait] tijdens het terugkijkvenster `AND`</li><li>Een id synchroniseren met de gekozen [!UICONTROL destination] ongeacht de tijd van syncs.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] hint [!UICONTROL Customer Total Audience] uitgedrukt als percentage. |
| [!UICONTROL Total Segment Population] | Een telling van alle apparaten die lid van uw [!UICONTROL segment] tijdens de terugkijkperiode van het verslag. |
| [!UICONTROL Segment Addressable Audience] | Het aantal gebruikers dat tot de [!UICONTROL segment] tijdens de terugzoekperiode van het rapport en op uw site hebt u een actieve id-synchronisatie. [!UICONTROL Segments] kan uw eigen gegevens van de eerste partij en gegevens van de tweede en derde partij omvatten, via [!UICONTROL traits] in het [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md). <br><br>Tip: Wanneer gebruikt met de periode van de 1 dag terugblik-rug, kan metrisch u helpen de huidige staat van uw begrijpen [!UICONTROL segments]. Dit komt omdat de [!UICONTROL Segment Addressable Audience] De metrische waarde vertegenwoordigt de gebruikers die in een [!UICONTROL segment] gedurende de voorafgaande dag. Combineer dit met het feit dat [!DNL Audience Manager] vernieuwingen [!UICONTROL Addressable Audiences] dagelijks, verstrekt het combineren van deze metrische en terugzoekperiode de meest bijgewerkte momentopname van uw [!UICONTROL segments]. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] hint [!UICONTROL Total Segment Population] uitgedrukt als percentage. |

## [!UICONTROL Addressable Audiences] Interface {#addressable-audience-interface}

De [!UICONTROL Addressable Audience] Deze functie verandert dit abstracte concept in kwantificeerbare gegevens. In [!DNL Audience Manager]Deze functie toont de publieksoverlapping met gegevensvisualisaties die in één oogopslag informatie en numerieke gegevens in tabelvorm verschaffen.

[!UICONTROL Addressable Audiences] bevindt zich in **[!UICONTROL Audience Data > Destinations]**. Selecteren **[!UICONTROL Integrated Platforms > Device-Based]** om de maatstaven van het publiek te kunnen zien.

![](assets/addressable-audiences-landing.png)

De drie maatstaven die u kunt zien op de [!UICONTROL Addressable Audiences] de landingspagina vertegenwoordigt:

| Metrisch | Beschrijving |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Deze metrische waarde vertegenwoordigt de [!UICONTROL Customer Addressable Audience] (beschreven in de bovenstaande tabel) *gedurende de laatste 30 dagen.* |
| **[!UICONTROL Match Rate]** | Deze metrische waarde vertegenwoordigt de [!UICONTROL Addressable Audience Match Rate] (beschreven in de bovenstaande tabel) *voor de laatste 30 dagen*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Een telling van alle apparaten die met allen in wisselwerking staan [!DNL Audience Manager] klanten op platformniveau tijdens de terugkijkperiode van het rapport en die met dit zouden kunnen worden aangepast [!UICONTROL destination]. Zie [Metriek op Platform-niveau](/help/using/features/addressable-audiences.md#platform-level-metrics) voor meer informatie . |

Klik op de naam van een [!UICONTROL server-to-server destination] om uw adresseerbare publieksgegevens te bekijken. Opmerking: deze functie retourneert gegevens voor [!UICONTROL server-to-server destinations] alleen en toegang vereist beheerdersmachtigingen.

![](assets/addressableAudiences.png)

Als u deze gegevens controleert, kunt u:

* **Voorspelling en planning:** [!UICONTROL Segment Addressable Audience] de gegevens geven u meer granulariteit in de segmenten u van plan bent om naar een bestemming voor publiek te verzenden richtend en activering.

* **Prestatiebeoordelingen:** De [!UICONTROL Addressable Audiences] Deze functie is ook een hulpprogramma voor probleemoplossing. Het laat u campagneprestaties herzien, campagnebereik begrijpen, en laat u met het richten/activeringspartners kruisen als u niet de resultaten ziet u verwacht.

### Prospecties met gegevens en implicaties van derden voor gelijke tarieven

Alvorens derdegegevens voor publieksverwerving te kopen, kunnen de klanten de overlapping met andere gegevensleveranciers bevestigen. Dit kan u helpen een geïnformeerde beslissing nemen alvorens nieuwe gegevens te kopen. De ID-syncs voor aangeschafte gegevens van derden zijn niet alleen afhankelijk van de overlapping van gegevens, maar ook van de voetafdrukken van andere leveranciers [!DNL Audience Manager] klanten. Uw [!DNL Adobe] consultant kan u helpen aanvullende relevante gegevensbronnen te identificeren om uw prospectiecampagnes te optimaliseren.

### Mobiele gebruikers en gelijke tarieven

Er zijn tussenruimten wanneer wordt geprobeerd verbinding te maken [!DNL Safari] of gebruikers van mobiele apps zonder externe [!DNL cookies] aanwezig. Dat maakt het moeilijk om gebruikers met sommige partners te synchroniseren omdat slechts die [!DNL Adobe] Id&#39;s voor gesynchroniseerde derde [!DNL cookies] worden vermeld in de medialeveringslogboeken. Dit is de reden waarom je zou kunnen zien [lage vergelijkingssnelheden](../features/addressable-audiences.md#low-match-rates) voor uw [!UICONTROL destinations].

## Datumbereik in [!UICONTROL Addressable Audiences] en [!UICONTROL Destinations] {#date-ranges}

Lees de secties hieronder voor beschikbare datumwaaiers en hoe de gegevens uit elk interval in de rapporten voor [!UICONTROL Addressable Audience] of [!UICONTROL Destination].

## Beschikbare datumbereiken en tijdzones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Rapporten voor uw [!UICONTROL Addressable Audiences] en [Doelen](../features/destinations/destinations.md) dezelfde datumbereikintervallen gebruiken. De opties voor het datumbereik zijn:

* [!UICONTROL Last 1 Day] (Dit interval loopt van Midnight aan Midnight van de vorige periode van 24 uur. Het is geen metrisch in real time of huidige tijd.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle datums en datumbereiken worden ingesteld in het dialoogvenster [!DNL UTC] tijdzone. Zie [Tijdzones in Audience Manager](../reference/aam-time-zones.md).

## Gegevens in Datumbereik Intervallen {#date-range-intervals}

De [!UICONTROL Addressable Audience] en [!UICONTROL Destination] metriek retourneren een telling van unieke gebruikers voor het geselecteerde tijdinterval. Een bezoeker wordt bijvoorbeeld slechts één keer meegeteld, zelfs als hij meerdere keren naar uw site komt. Het eerste bezoek is het unieke bezoek en wordt opgenomen. De volgende bezoeken komen terug en worden niet geteld omdat ze niet uniek zijn.

Datumbereiken bevatten gegevens voor het geselecteerde tijdinterval of de geselecteerde ouder. En, de gegevens verouderen uit elk rapportinterval aangezien de tijd overgaat. Stel bijvoorbeeld dat u 2 bezoekers ziet nadat u de opdracht [!UICONTROL Last 30 Days] optie. In de rapporten:

* *Wordt* opgenomen in de resultaten die werden geretourneerd met de langere tijdsintervallen (60 dagen, 90 dagen en Lifetime).
* *Wordt niet* opgenomen in de kortere intervallen die voorafgaan aan de [!UICONTROL Last 30 Day] (Huidige, 7 dagen en 14 dagen).

En op dag 31 komen deze bezoekers alleen op in de 60 dagen, 90 dagen, en [!UICONTROL Lifetime] resultaten. Ze zijn ouder dan 30 dagen. Bezoekers zijn niet ouder dan [!UICONTROL Lifetime] interval.

## [!UICONTROL Addressable Audiences] Metrisch {#addressable-audience-metrics}

In deze sectie worden de typen metriek beschreven die worden geleverd door [!UICONTROL Addressable Audiences].

### Metriek op klantniveau {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Deze metriek retourneert gegevens voor kenmerken die worden gerealiseerd wanneer bezoekers naar uw site komen of wanneer u binnenkomende gegevensbestanden verzendt naar [!DNL Audience Manager]. Deze metrische gegevens bieden een uitgebreide weergave van de publieksgrootte voor uw account.

| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Een telling van overlapping van apparaten die één van beiden hebben gerealiseerd [!UICONTROL rule-based trait] of [!UICONTROL onboarded trait] tijdens het terugblik-achtervenster en apparaten dat wij een identiteitskaart synchronisatie met de gekozen bestemming ongeacht de tijd van syncs hebben.<br><br>Deze metrische waarde vertegenwoordigt apparaten die:<ul><li>Heeft u een van de [!UICONTROL rule-based] of [!UICONTROL onboarded trait] tijdens het terugkijkvenster `AND`</li><li>Een id synchroniseren met de gekozen [!UICONTROL destination] ongeacht de tijd van syncs.</li></ul> |
| [!UICONTROL Customer Total Audience] | Een aantal apparaten dat een van de [!UICONTROL rule-based trait] op uw eigenschappen of [!UICONTROL onboarded trait] uit uw offlinebestanden tijdens het terugzoekvenster. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] hint [!UICONTROL Customer Total Audience] uitgedrukt als percentage. |

### Identieke cijfers op segmentniveau {#segment-level-metrics}

Deze metriek retourneert gegevens over [!UICONTROL segment] lidmaatschap. Zij helpen een meer korrelige en nauwkeurige mening van de publieksgrootte voor elk van uw [!UICONTROL segments].

>[!NOTE]
>
>De manier waarop het terugkijkvenster wordt toegepast op de [!UICONTROL segment] niveau verschilt van dat op het niveau van de klant. Bezoekers kunnen naar de site komen en [!UICONTROL trait] 10 dagen geleden konden ze in aanmerking komen voor een [!UICONTROL segment] sindsdien is de [!UICONTROL segment] 2 dagen geleden. Wanneer de terugblik van 7 dagen wordt toegepast, zullen deze bezoekers bij [!UICONTROL segment] niveau, maar niet op het niveau van de klant.

| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Het aantal gebruikers dat tot de [!UICONTROL segment] tijdens de terugzoekperiode van het rapport en op uw site hebt u een actieve id-synchronisatie. De segmenten kunnen uw eigen gegevens van de eerste partij en gegevens van de tweede en derde omvatten, via [!UICONTROL traits] in het [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Tip: Wanneer gebruikt met de periode van de 1 dag terugblik-rug, kan metrisch u helpen de huidige staat van uw begrijpen [!UICONTROL segments]. Dit komt omdat de [!UICONTROL Segment Addressable Audience] De metrische waarde vertegenwoordigt de gebruikers die in een [!UICONTROL segment] gedurende de voorafgaande dag. Combineer dit met het feit dat [!DNL Audience Manager] vernieuwingen [!UICONTROL Addressable Audiences] dagelijks, verstrekt het combineren van deze metrische en terugzoekperiode de meest bijgewerkte momentopname van uw [!UICONTROL segments]. |
| [!UICONTROL Total Segment Population] | Een telling van alle apparaten die lid van uw [!UICONTROL segment] tijdens de terugkijkperiode van het verslag. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] hint [!UICONTROL Total Segment Population] uitgedrukt als percentage. |

### Metriek op Platform-niveau {#platform-level-metrics}

Deze metrische methode retourneert gegevens over activiteiten die over alle [!DNL Audience Manager] klanten. Zij kunnen een breder beeld van het publiek van de klant in vergelijking met de samengevoegde [!DNL Audience Manager] klanten.

| Metrisch | Beschrijving |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Een telling van alle apparaten die met allen in wisselwerking staan [!DNL Audience Manager] klanten op platformniveau tijdens de periode van de rapportterugblik en die met uw gekozen zou kunnen aanpassen [!UICONTROL destination]. <br><br>Deze metrisch is nuttig omdat het u toont:<ul><li>De grootte van de [!UICONTROL total addressable audience] dat [!DNL Audience Manager] kan op een bepaalde doelbestemming bereiken.</li><li>Hoe groot is het [!DNL Audience Manager] profielpool is bestemd voor een doelplatform en de omvang van hun publiek.</li></ul> |

## Vergelijken [!UICONTROL Customer] en [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

Je moet de [!UICONTROL Customer Addressable Audience] en [!UICONTROL Segment Addressable Audience] metriek om te bepalen als één beduidender is dan andere. Dit zijn afzonderlijke, verschillende en onafhankelijke meetgegevens. Zoals in de bovenstaande definities is beschreven, zijn deze allemaal afgeleid van verschillende gegevenssets. In dat geval hoeft u geen conclusies te trekken als de ene meting groter is dan de andere. Het enige wat u kunt zeggen bij een vergelijking is:

* [!UICONTROL Customer Addressable Audiences] is gebaseerd op [!UICONTROL trait] realisaties *voor uw eigen gegevens van de eerste partij*. Deze metrisch verstrekt een brede, uitvoerige mening van uw integratie met een gegevenspartner.

* [!UICONTROL Segment Addressable Audiences] is gebaseerd op segmentkwalificaties *voor uw eigen gegevens van de eerste partij, plus gegevens van de tweede en derde partij*. Deze metrisch verstrekt korrelige, nauwkeurigere mening van uw [!UICONTROL addressable audiences] in een doelplatform.

## Oorzaken van lage matchingstarieven voor [!UICONTROL Addressable Audiences] {#low-match-rates}

Gemeenschappelijke elementen voor laag [!UICONTROL Addressable Audience] gelijke of discrepanties in gerapporteerde getallen.

| Oorzaak | Beschrijving |
|---|---|
| Mobiel verkeer | Meeste [!UICONTROL server-to-server] Integraties zijn afhankelijk van synchronisatieprocessen die door derden worden gefaciliteerd [!DNL cookies]. Mobiele omgevingen maken echter geen gebruik van derden [!DNL cookies]. Als gevolg hiervan [!UICONTROL Addressable Audiences] getallen kunnen laag lijken in vergelijking met [!UICONTROL segment] grootte. <br><br>Vanaf januari 2018 kunt u mobiele doelgroepen in hetzelfde netwerk activeren [!DNL Google] en [!DNL Adobe Advertising Cloud] bestemmingen die zijn ingesteld voor [!UICONTROL cookie-based] publiek. Dit betekent dat u [!UICONTROL segments] met gecombineerde [!DNL cookie] en mobiele id-lidmaatschap voor uw [!DNL Google] en [!DNL Advertising Cloud] doelen, houd er rekening mee dat [!UICONTROL Addressable Audiences] alleen de overlapping weergeven tussen [!DNL cookie] ID&#39;s en doelen. [!DNL Audience Manager] 100 % van het mobiele publiek naar [!UICONTROL destinations], maar mobiele doelgroepen worden niet gemeten door de [!UICONTROL Addressable Audience] metrisch. <br><br>**Opmerking**: Neem bijvoorbeeld een [!UICONTROL segment] met een bevolking van 1.000.000 inwoners. Als u deze toewijst [!UICONTROL segment] een [!DNL Google] of [!DNL Adobe Advertising Cloud] bestemming, zou u een [!UICONTROL Addressable Audience] van 700.000 apparaten en [!UICONTROL Match Rate] van 70%. Het lidmaatschap van 700.000 bestaat uit: [!DNL cookie] Id&#39;s die een id hebben die gesynchroniseerd is met de [!UICONTROL destination]. Uw [!UICONTROL Addressable Audience] Dit kan zelfs veel hoger zijn, omdat adresseerbare mobiele id&#39;s niet in deze metrische code worden weergegeven. |
| [!DNL Safari] Verkeer | [!DNL Safari] blokkeert derden [!DNL cookies]. Dit voorkomt [!DNL Audience Manager] van het synchroniseren van IDs met [!UICONTROL destination]. Met de invoering van [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), kunt u uw [!UICONTROL addressable audiences] niet opnemen [!DNL Safari] gebruikers. |
| Bijgehouden media-impressies | Vanwege aanbevolen procedures voor advertentieservers worden id-syncs niet binnen advertentietags gemaakt. Klanten die veel offsite advertenties maken, synchroniseren gebruikers niet naar integratie van derden in die omgevingen. Bovendien kan een grote hoeveelheid verzamelde media-imitatiegegevens de [!UICONTROL addressable audience] getallen. |

## Problemen oplossen met [!UICONTROL Addressable Audiences] {#troubleshooting}

U kunt niet alleen opvallende overeenkomsten gebruiken [!UICONTROL Addressable Audiences] als hulpmiddel voor probleemoplossing.

Bijvoorbeeld, laten wij zeggen u een segment naar een segment verzendt [!UICONTROL destination] en dat [!UICONTROL destination] geeft lage rapportnummers weer. De [!UICONTROL Addressable Audience] de resultaten zullen u tonen als dit een technisch probleem of enkel een geval van lage gelijke tarieven is. Een lage overeenkomende snelheid geeft uw [!UICONTROL destination] is niet zo geweldig voor uw geselecteerde segmenten. Een verschil in de [!UICONTROL total addressable audience] getallen tussen [!DNL Audience Manager] en de [!UICONTROL destination] Hiermee wordt een integratie-, synchronisatie- of ander technisch probleem aangegeven. Neem in deze gevallen contact op met uw accountmanager.
