---
description: Een overzicht van de Adresseerbare eigenschap van het Publiek en gebruiksgevallen.
keywords: DIL
seo-description: An overview of the Addressable Audience feature and use cases.
seo-title: Addressable Audiences
solution: Audience Manager
title: Adresseerbaar publiek
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Match Rates
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
source-git-commit: cecdc0b0f43a146e11f7d23eb21a06146496ac2d
workflow-type: tm+mt
source-wordcount: '1831'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Een overzicht van de functies en gebruiksgevallen van [!UICONTROL Addressable Audience] .

## Wat is een [!UICONTROL Addressable Audience] ? {#addressable-audience-description}

Met de functie [!UICONTROL Addressable Audiences] kunt u zien wat de overlap is tussen het publiek dat u ziet in al uw eigenschappen waar [!DNL Audience Manager] gegevens verzamelt en het geselecteerde doel. Om u te helpen dit concept begrijpen, neem een blik hieronder op de illustratie. De overlapping tussen elke cirkel vertegenwoordigt de verschillende soorten adresseerbare soorten publiek.

![](assets/addressableAudienceVenn.png)


| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] voor een [!UICONTROL Destination] | Een telling van alle apparaten die met alle [!DNL Audience Manager] klanten op platform-niveau tijdens de rapportperiode hebben interactie gehad en die met uw gekozen [!UICONTROL destination] zouden kunnen worden aangepast. <br><br> dit metrisch is nuttig omdat het u toont: <ul><li>De grootte van het totaal [!UICONTROL addressable audience] dat [!DNL Audience Manager] bij een bepaald doel kan bereiken [!UICONTROL destination].</li><li>Hoe groot de [!DNL Audience Manager] -profielpool is voor een doelplatform en de grootte van hun publiek.</li></ul> |
| [!UICONTROL Customer Total Audience] | Een aantal apparaten die een [!UICONTROL rule-based trait] op uw eigenschappen of een [!UICONTROL onboarded trait] van uw offline bestanden tijdens het terugzoekvenster hebben gerealiseerd. |
| [!UICONTROL Customer Addressable Audience] | Een telling van overlapping van apparaten die een [!UICONTROL rule-based trait] of een [!UICONTROL onboarded trait] tijdens het terugblik venster en apparaten hebben dat wij een identiteitskaart synchronisatie met gekozen [!UICONTROL destination] ongeacht de tijd van syncs hebben gerealiseerd.<br><br> dit metrisch vertegenwoordigt apparaten die:<ul><li>Een [!UICONTROL rule-based] of [!UICONTROL onboarded trait] tijdens het terugkijkvenster `AND` hebben gerealiseerd</li><li>Een id synchroniseren met de gekozen [!UICONTROL destination] ongeacht de tijd van syncs.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience]:t [!UICONTROL Customer Total Audience] uitgedrukt als een percentage. |
| [!UICONTROL Total Segment Population] | Een telling van alle apparaten die een lid van uw [!UICONTROL segment] tijdens de rapportterugblik periode waren. |
| [!UICONTROL Segment Addressable Audience] | Het aantal gebruikers dat tijdens de terugkijkperiode van het rapport tot [!UICONTROL segment] behoorde en een actieve synchronisatie van identiteitskaart op uw plaats hebben. [!UICONTROL Segments] kan uw eigen eerste partijgegevens en tweede en derdegegevens omvatten, via [!UICONTROL traits] die in [&#x200B; Audience Marketplace &#x200B;](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) wordt verworven. <br><br> Uiteinde: Wanneer gebruikt met de periode van de 1-dag terugblik, kan metrisch u helpen de huidige staat van uw [!UICONTROL segments] begrijpen. De reden hiervoor is dat de [!UICONTROL Segment Addressable Audience] -meting de gebruikers vertegenwoordigt die de vorige dag in een [!UICONTROL segment] zijn gebleven. Combineer dit met het feit dat [!DNL Audience Manager] verfrist [!UICONTROL Addressable Audiences] dagelijks, combinerend deze metrische en raadplegingsperiode de meest bijgewerkte momentopname van uw [!UICONTROL segments] verstrekt. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience]:t [!UICONTROL Total Segment Population] uitgedrukt als een percentage. |

## [!UICONTROL Addressable Audiences] Interface {#addressable-audience-interface}

Met de functie [!UICONTROL Addressable Audience] verandert u dit abstracte concept in kwantificeerbare gegevens. In [!DNL Audience Manager] toont deze functie de publieksoverlapping met gegevensvisualisaties die in één oogopslag informatie en numerieke gegevens in tabelvorm verschaffen.

[!UICONTROL Addressable Audiences] bevindt zich in **[!UICONTROL Audience Data > Destinations]** . Selecteer **[!UICONTROL Integrated Platforms > Device-Based]** om meetgegevens voor adressaten weer te geven.

![](assets/addressable-audiences-landing.png)

De drie metriek die u op de landingspagina van [!UICONTROL Addressable Audiences] kunt zien, vertegenwoordigen:

| Metrisch | Beschrijving |
|---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Deze metrisch vertegenwoordigt [!UICONTROL Customer Addressable Audience] (die in de lijst hierboven wordt beschreven) *voor de laatste 30 dagen.* |
| **[!UICONTROL Match Rate]** | Deze metrisch vertegenwoordigt [!UICONTROL Addressable Audience Match Rate] (die in de lijst hierboven wordt beschreven) *voor de laatste 30 dagen*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Een telling van alle apparaten die met alle [!DNL Audience Manager] klanten op platform-niveau tijdens de rapport terugkerende periode hebben interactie gehad en die met dit [!UICONTROL destination] zouden kunnen worden aangepast. Zie [&#x200B; Platform-Vlakke Metriek &#x200B;](/help/using/features/addressable-audiences.md#platform-level-metrics) voor meer informatie. |

Klik op de naam van een [!UICONTROL server-to-server destination] om de adresseerbare publieksgegevens weer te geven. Deze functie retourneert alleen gegevens voor [!UICONTROL server-to-server destinations] en voor toegang zijn beheerdersmachtigingen vereist.

![](assets/addressableAudiences.png)

Als u deze gegevens controleert, kunt u het volgende doen:

* **Voorspelling en planning:** [!UICONTROL Segment Addressable Audience] gegevens geeft u meer granulariteit in de segmenten u van plan bent naar een bestemming voor publiek te verzenden richtend en activering.

* **de revisies van Prestaties:** de [!UICONTROL Addressable Audiences] eigenschap is ook een het oplossen van problemenhulpmiddel. Het laat u campagneprestaties herzien, campagnebereik begrijpen, en laat u met het richten/activeringspartners kruisen als u niet de resultaten ziet u verwacht.

### Prospecties met gegevens en implicaties van derden voor gelijke tarieven

Alvorens derdegegevens voor publieksverwerving te kopen, kunnen de klanten de overlapping met andere gegevensleveranciers bevestigen. Dit kan u helpen een geïnformeerde beslissing nemen alvorens nieuwe gegevens te kopen. De ID-syncs voor aangekochte gegevens van derden zijn niet alleen afhankelijk van de overlapping van uw gegevens, maar ook van de voetafdrukken van andere leveranciers met alle andere klanten van [!DNL Audience Manager] . Uw [!DNL Adobe] -consultant kan u helpen aanvullende relevante gegevensbronnen te identificeren om uw prospectiecampagnes te optimaliseren.

### Mobiele gebruikers en gelijke tarieven

Er zijn gaten wanneer u probeert verbinding te maken met [!DNL Safari] of gebruikers van mobiele apps waarin geen externe [!DNL cookies] aanwezig is. Hierdoor is het moeilijk om gebruikers met bepaalde partners te synchroniseren, omdat alleen die [!DNL Adobe] ID&#39;s voor gesynchroniseerde derden [!DNL cookies] worden vermeld in de medialeveringslogboeken. Dit is een reden waarom u [&#x200B; lage gelijke tarieven &#x200B;](../features/addressable-audiences.md#low-match-rates) voor uw [!UICONTROL destinations] zou kunnen zien.

## Datumbereik in [!UICONTROL Addressable Audiences] en [!UICONTROL Destinations] {#date-ranges}

Lees de onderstaande secties voor beschikbare datumbereiken en hoe gegevens van elk interval in de rapporten voor een [!UICONTROL Addressable Audience] of [!UICONTROL Destination] verouderen.

## Beschikbare datumbereiken en tijdzones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

De rapporten voor uw [!UICONTROL Addressable Audiences] en [&#x200B; Doelen &#x200B;](../features/destinations/destinations.md) gebruiken de zelfde intervallen van de datumwaaier. De opties voor het datumbereik zijn:

* [!UICONTROL Last 1 Day] (Dit interval loopt van Midnight tot Midnight van de vorige periode van 24 uur. Het is geen metrisch in real time of huidige tijd.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle datums en datumbereiken worden ingesteld in de tijdzone van [!DNL UTC] . Zie [&#x200B; Gebieden van de Tijd in Audience Manager &#x200B;](../reference/aam-time-zones.md).

## Gegevens in Datumbereik Intervallen {#date-range-intervals}

De metriek [!UICONTROL Addressable Audience] en [!UICONTROL Destination] keren een aantal unieke gebruikers voor het geselecteerde tijdinterval terug. Een bezoeker wordt bijvoorbeeld slechts één keer meegeteld, zelfs als hij meerdere keren naar uw site komt. Het eerste bezoek is het unieke bezoek en wordt opgenomen. De volgende bezoeken komen terug en worden niet geteld omdat ze niet uniek zijn.

Datumbereiken bevatten gegevens voor het geselecteerde tijdinterval of de geselecteerde ouder. En, de gegevens verouderen uit elk rapportinterval aangezien de tijd overgaat. Stel dat u twee bezoekers ziet nadat u de optie [!UICONTROL Last 30 Days] hebt gekozen. In de rapporten:

* *zal* inbegrepen in de resultaten zijn die door de langere tijdintervallen (60 dagen, 90 dagen, en Levensduur) zijn teruggekeerd.
* *zal niet* inbegrepen in de kortere intervallen zijn die de [!UICONTROL Last 30 Day] optie (Huidige, 7 dagen, en 14 dagen) voorafgaan.

En op dag 31 komen deze bezoekers alleen voor in de 60 dagen, 90 dagen en [!UICONTROL Lifetime] resultaten. Ze zijn ouder dan 30 dagen. Bezoekers verouderen niet buiten het [!UICONTROL Lifetime] -interval.

## [!UICONTROL Addressable Audiences] Metriek {#addressable-audience-metrics}

In deze sectie worden de typen metriek beschreven die door [!UICONTROL Addressable Audiences] worden verschaft.

### Metriek op klantniveau {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Deze metriek retourneert gegevens voor kenmerken die worden gerealiseerd wanneer bezoekers naar uw site komen of wanneer u binnenkomende gegevensbestanden verzendt naar [!DNL Audience Manager] . Deze metrische gegevens bieden een uitgebreide weergave van de omvang van het publiek voor uw account.

| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Een telling van overlapping van apparaten die een [!UICONTROL rule-based trait] of een [!UICONTROL onboarded trait] tijdens het terugblik venster en apparaten hebben gerealiseerd dat wij een identiteitskaart synchronisatie met de gekozen bestemming ongeacht de tijd van syncs hebben.<br><br> dit metrisch vertegenwoordigt apparaten die:<ul><li>Een [!UICONTROL rule-based] of [!UICONTROL onboarded trait] tijdens het terugkijkvenster `AND` hebben gerealiseerd</li><li>Een id synchroniseren met de gekozen [!UICONTROL destination] ongeacht de tijd van syncs.</li></ul> |
| [!UICONTROL Customer Total Audience] | Een aantal apparaten die een [!UICONTROL rule-based trait] op uw eigenschappen of een [!UICONTROL onboarded trait] van uw offline bestanden tijdens het terugzoekvenster hebben gerealiseerd. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience]:t [!UICONTROL Customer Total Audience] uitgedrukt als een percentage. |

### Identieke cijfers op segmentniveau {#segment-level-metrics}

Deze cijfers geven gegevens weer over een [!UICONTROL segment] -lidmaatschap. Ze zorgen voor een gedetailleerdere en nauwkeurigere weergave van de publieksgrootte voor elk van de [!UICONTROL segments] .

>[!NOTE]
>
>De manier waarop het terugkijkvenster op [!UICONTROL segment] niveau wordt toegepast is verschillend van dat op het niveau van de klant. Bezoekers kunnen [!UICONTROL trait] 10 dagen geleden naar de site komen en ze kunnen sindsdien in aanmerking komen voor een [!UICONTROL segment] -machtiging en 2 dagen geleden buiten de [!UICONTROL segment] -pagina vallen. Wanneer de terugblik van 7 dagen wordt toegepast, zullen deze bezoekers op het [!UICONTROL segment] niveau maar niet op het klantenniveau worden geteld.

| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Het aantal gebruikers dat tijdens de terugkijkperiode van het rapport tot [!UICONTROL segment] behoorde en een actieve synchronisatie van identiteitskaart op uw plaats hebben. De segmenten kunnen uw eigen eerste partijgegevens en tweede partij en derdegegevens omvatten, via [!UICONTROL traits] die in [&#x200B; Audience Marketplace &#x200B;](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) wordt verworven.<br><br> Uiteinde: Wanneer gebruikt met de periode van de 1-dag terugblik, kan metrisch u helpen de huidige staat van uw [!UICONTROL segments] begrijpen. De reden hiervoor is dat de [!UICONTROL Segment Addressable Audience] -meting de gebruikers vertegenwoordigt die de vorige dag in een [!UICONTROL segment] zijn gebleven. Combineer dit met het feit dat [!DNL Audience Manager] verfrist [!UICONTROL Addressable Audiences] dagelijks, combinerend deze metrische en raadplegingsperiode de meest bijgewerkte momentopname van uw [!UICONTROL segments] verstrekt. |
| [!UICONTROL Total Segment Population] | Een telling van alle apparaten die een lid van uw [!UICONTROL segment] tijdens de rapportterugblik periode waren. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience]:t [!UICONTROL Total Segment Population] uitgedrukt als een percentage. |

### Metriek op platformniveau {#platform-level-metrics}

Deze metrische waarde geeft gegevens over activiteiten die door alle [!DNL Audience Manager] klanten zijn verzameld. Ze kunnen een bredere visie bieden op het publiek van de klant in vergelijking met de geaggregeerde [!DNL Audience Manager] -klanten.

| Metrisch | Beschrijving |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Een telling van alle apparaten die met alle [!DNL Audience Manager] klanten op platform-niveau tijdens de rapportperiode hebben interactie gehad en die met uw gekozen [!UICONTROL destination] zouden kunnen worden aangepast. <br><br> dit metrisch is nuttig omdat het u toont:<ul><li>De grootte van de [!UICONTROL total addressable audience] die [!DNL Audience Manager] op een bepaalde doelbestemming kan bereiken.</li><li>Hoe groot de [!DNL Audience Manager] -profielpool is voor een doelplatform en de grootte van hun publiek.</li></ul> |

## [!UICONTROL Customer] en [!UICONTROL Segment Addressable Audiences] vergelijken {#comparing-metrics}

U moet de metriek [!UICONTROL Customer Addressable Audience] en [!UICONTROL Segment Addressable Audience] niet vergelijken om te bepalen als één beduidender is dan andere. Dit zijn afzonderlijke, verschillende en onafhankelijke meetgegevens. Zoals in de bovenstaande definities is beschreven, zijn deze allemaal afgeleid van verschillende gegevenssets. In dat geval hoeft u geen conclusies te trekken als de ene meting groter is dan de andere. Het enige wat u kunt zeggen bij het vergelijken van deze is:

* [!UICONTROL Customer Addressable Audiences] is gebaseerd op [!UICONTROL trait] realisaties *voor uw eigen, eerste partijgegevens*. Deze metrisch verstrekt een brede, uitvoerige mening van uw integratie met een gegevenspartner.

* [!UICONTROL Segment Addressable Audiences] is gebaseerd op segmentkwalificaties *voor uw eigen eerste-partijgegevens, plus tweede en derdegegevens*. Deze metrisch verstrekt korrelige, nauwkeurigere mening van uw [!UICONTROL addressable audiences] in een gericht platform.

## Oorzaken van lage matchingstarieven voor [!UICONTROL Addressable Audiences] {#low-match-rates}

Veelvoorkomende elementen die verantwoordelijk zijn voor lage [!UICONTROL Addressable Audience] match rates of verschillen in gerapporteerde getallen.

| Oorzaak | Beschrijving |
|---|---|
| Mobiel verkeer | De meeste [!UICONTROL server-to-server] -integraties zijn afhankelijk van synchronisatieprocessen die door derden zijn gefaciliteerd [!DNL cookies] . Mobiele omgevingen gebruiken echter geen externe [!DNL cookies] . Hierdoor kunnen uw [!UICONTROL Addressable Audiences] getallen laag lijken in vergelijking met [!UICONTROL segment] size. <br><br> Vanaf Januari 2018, kunt u mobiele publiek in de zelfde [!DNL Google] en [!DNL Adobe Advertising Cloud] bestemmingen activeren opstelling voor [!UICONTROL cookie-based] publiek. Dit betekent dat u [!UICONTROL segments] met gecombineerde [!DNL cookie] en mobiele-id-leden naar uw [!DNL Google] - en [!DNL Advertising Cloud] -doelen kunt verzenden, maar houd er rekening mee dat [!UICONTROL Addressable Audiences] alleen de overlapping tussen [!DNL cookie] id&#39;s en doelen weergeeft. [!DNL Audience Manager] verzendt 100% van het mobiele publiek naar [!UICONTROL destinations] , maar het mobiele publiek wordt niet gemeten met de [!UICONTROL Addressable Audience] -meetwaarde. <br><br>**Nota**: Bijvoorbeeld, neem a [!UICONTROL segment] met een bevolking van 1.000.000. Als u deze [!UICONTROL segment] toewijst aan een [!DNL Google] - of [!DNL Adobe Advertising Cloud] -doel, ziet u mogelijk een [!UICONTROL Addressable Audience] van 700.000 apparaten en een [!UICONTROL Match Rate] van 70%. Het lidmaatschap van 700.000 bestaat uit [!DNL cookie] id&#39;s met een id die gesynchroniseerd zijn met de [!UICONTROL destination] . De waarde [!UICONTROL Addressable Audience] kan zelfs veel hoger zijn, omdat adresseerbare mobiele id&#39;s niet in deze metrische code worden weergegeven. |
| [!DNL Safari] Verkeer | [!DNL Safari] blokkeert derden [!DNL cookies] . Zo voorkomt u dat [!DNL Audience Manager] id&#39;s synchroniseert met de [!UICONTROL destination] . Met de introductie van [&#x200B; ITP 2.0 &#x200B;](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), kunt u uw [!UICONTROL addressable audiences] verwachten om [!DNL Safari] gebruikers niet te omvatten. |
| Bijgehouden media-impressies | Vanwege aanbevolen procedures voor advertentieservers worden id-syncs niet binnen advertentietags gemaakt. Klanten die veel offsite advertenties maken, synchroniseren gebruikers niet naar integratie van derden in die omgevingen. Bovendien kan een grote hoeveelheid verzamelde mediaminiaturen [!UICONTROL addressable audience] getallen verlagen. |

## Problemen oplossen met [!UICONTROL Addressable Audiences] {#troubleshooting}

U kunt [!UICONTROL Addressable Audiences] niet alleen gebruiken voor het zoeken naar overeenkomsten, maar ook voor het oplossen van problemen.

Stel bijvoorbeeld dat u een segment naar een [!UICONTROL destination] verzendt en dat [!UICONTROL destination] lage rapportnummers bevat. Als u de resultaten van [!UICONTROL Addressable Audience] controleert, wordt u weergegeven of dit een technisch probleem is of slechts een geval van lage overeenkomende snelheden. Bij een lage overeenkomende snelheid wordt getoond dat de [!UICONTROL destination] niet helemaal ideaal is voor de geselecteerde segmenten. Een verschil in de [!UICONTROL total addressable audience] getallen tussen [!DNL Audience Manager] en [!UICONTROL destination] geeft echter een integratie, synchronisatie of ander technisch probleem aan. Neem in deze gevallen contact op met uw accountmanager.
