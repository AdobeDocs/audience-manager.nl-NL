---
description: Een overzicht van de Adresseerbare eigenschap van het Publiek en gebruiksgevallen.
keywords: DIL
seo-description: Een overzicht van de Adresseerbare eigenschap van het Publiek en gebruiksgevallen.
seo-title: Addressable Audiences
solution: Audience Manager
title: Adresseerbaar publiek
topic-edit: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
feature: Matchpercentages
exl-id: 2728e4a8-522c-423f-a6ef-e4dd624f69e5
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1827'
ht-degree: 0%

---

# [!UICONTROL Addressable Audiences] {#addressable-audiences}

Een overzicht van de [!UICONTROL Addressable Audience] eigenschap en gebruiksgevallen.

## Wat is een [!UICONTROL Addressable Audience]? {#addressable-audience-description}

De functie [!UICONTROL Addressable Audiences] toont u de overlapping tussen het publiek u over al uw eigenschappen ziet waar [!DNL Audience Manager] gegevens en uw geselecteerde bestemming verzamelt. Om u te helpen dit concept begrijpen, neem een blik hieronder op de illustratie. De overlapping tussen elke cirkel vertegenwoordigt de verschillende soorten adresseerbare soorten publiek.

![](assets/addressableAudienceVenn.png)


| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Audience Manager Addressable Audience] voor een  [!UICONTROL Destination] | Een telling van alle apparaten die met alle [!DNL Audience Manager] klanten op het platform-niveau tijdens de rapport terugblik-periode hebben interactie gehad en die met uw gekozen [!UICONTROL destination] zouden kunnen worden aangepast. <br><br>Deze metrisch is nuttig omdat het u toont: <ul><li>De grootte van het totaal [!UICONTROL addressable audience] dat [!DNL Audience Manager] op een bepaald richten [!UICONTROL destination] kan bereiken.</li><li>Hoe groot is de [!DNL Audience Manager] profielpool voor een doelplatform en de grootte van hun publiek.</li></ul> |
| [!UICONTROL Customer Total Audience] | Een aantal apparaten dat of [!UICONTROL rule-based trait] op uw eigenschappen of [!UICONTROL onboarded trait] van uw off-line dossiers tijdens het terugblik-achtervenster heeft gerealiseerd. |
| [!UICONTROL Addressable Audience Match Rate] | Een telling van overlapping van apparaten die of [!UICONTROL rule-based trait] of [!UICONTROL onboarded trait] tijdens het terugblik venster en apparaten hebben dat wij een identiteitskaart synchronisatie met gekozen [!UICONTROL destination] ongeacht de tijd van syncs hebben.<br><br>Deze metrische waarde vertegenwoordigt apparaten die:<ul><li>Tijdens het terugkijkvenster `AND` een [!UICONTROL rule-based] of een [!UICONTROL onboarded trait] hebben gerealiseerd</li><li>Een id synchroniseren met de gekozen [!UICONTROL destination] ongeacht de tijd van syncs.</li> |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] Ht  [!UICONTROL Customer Total Audience] uitgedrukt als percentage. |
| [!UICONTROL Total Segment Population] | Een telling van alle apparaten die een lid van uw [!UICONTROL segment] tijdens de rapportterugblik periode waren. |
| [!UICONTROL Segment Addressable Audience] | Het aantal gebruikers dat tijdens de terugkijkperiode van het rapport tot [!UICONTROL segment] behoorde en een actieve synchronisatie van identiteitskaart op uw plaats hebben. [!UICONTROL Segments] U kunt uw eigen gegevens van de eerste partij en gegevens van de tweede en derde partij via  [!UICONTROL traits] verkregen in  [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) omvatten. <br><br>Tip: Wanneer gebruikt met de periode van de 1 dag terugblik-rug, kan metrisch u helpen de huidige staat van uw begrijpen  [!UICONTROL segments]. Dit komt omdat de [!UICONTROL Segment Addressable Audience] metrische waarde de gebruikers vertegenwoordigt die in [!UICONTROL segment] door de vorige dag bleven. Combineer dit met het feit dat [!DNL Audience Manager] [!UICONTROL Addressable Audiences] dagelijks vernieuwt, combinerend deze metrische en raadplegingsperiode de meest bijgewerkte momentopname van uw [!UICONTROL segments] verstrekt. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] Ht  [!UICONTROL Total Segment Population] uitgedrukt als percentage. |

## [!UICONTROL Addressable Audiences] Interface  {#addressable-audience-interface}

Met de functie [!UICONTROL Addressable Audience] wordt dit abstracte concept omgezet in kwantificeerbare gegevens. In [!DNL Audience Manager], toont deze eigenschap publiek overlappend met gegevensvisualisaties die bij-a-blik informatie samen met numerieke gegevens in tabelvorm verstrekken.

[!UICONTROL Addressable Audiences] bevindt zich in  **[!UICONTROL Audience Data > Destinations]**. Selecteer **[!UICONTROL Integrated Platforms > Device-Based]** om adresseerbare publieksmetriek te zien.

![](assets/addressable-audiences-landing.png)

De drie metriek die u op de [!UICONTROL Addressable Audiences] landingspagina kunt zien vertegenwoordigen:

| Metrisch | Beschrijving |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Deze metrische waarde vertegenwoordigt [!UICONTROL Customer Addressable Audience] (beschreven in de bovenstaande tabel) *voor de laatste 30 dagen.* |
| **[!UICONTROL Match Rate]** | Deze metrische waarde vertegenwoordigt [!UICONTROL Addressable Audience Match Rate] (beschreven in de lijst hierboven) *voor de laatste 30 dagen*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Een telling van alle apparaten die met alle [!DNL Audience Manager] klanten op het platform-niveau tijdens de rapport terugkerende periode hebben interactie gehad en die met dit [!UICONTROL destination] zouden kunnen worden aangepast. Zie [Metriek op Platform-niveau](/help/using/features/addressable-audiences.md#platform-level-metrics) voor meer informatie. |

Klik op de naam van een [!UICONTROL server-to-server destination] om uw adresseerbare publieksgegevens te bekijken. Nota, keert deze eigenschap gegevens voor [!UICONTROL server-to-server destinations] slechts terug en de toegang vereist beheerdertoestemmingen.

![](assets/addressableAudiences.png)

Als u deze gegevens controleert, kunt u:

* **Prognoseren en plannen:** [!UICONTROL Segment Addressable Audience] gegevens geven u meer granulariteit in de segmenten u van plan bent naar een bestemming te verzenden voor doelgroep en activering.

* **Prestatiebeoordelingen:** de  [!UICONTROL Addressable Audiences] functie is ook een hulpprogramma voor het oplossen van problemen. Het laat u campagneprestaties herzien, campagnebereik begrijpen, en laat u met het richten/activeringspartners kruisen als u niet de resultaten ziet u verwacht.

### Prospecties met gegevens en implicaties van derden voor gelijke tarieven

Alvorens derdegegevens voor publieksverwerving te kopen, kunnen de klanten de overlapping met andere gegevensleveranciers bevestigen. Dit kan u helpen een geïnformeerde beslissing nemen alvorens nieuwe gegevens te kopen. De ID-syncs voor aangeschafte gegevens van derden zijn niet alleen afhankelijk van de overlapping van uw gegevens, maar ook van de voetafdrukken van externe providers met alle andere [!DNL Audience Manager]-klanten. Uw [!DNL Adobe]-consultant kan u helpen aanvullende relevante gegevensbronnen te identificeren om uw prospectiecampagnes te optimaliseren.

### Mobiele gebruikers en gelijke tarieven

Er zijn hiaten wanneer het proberen om [!DNL Safari] of mobiele gebruikers van de app te verbinden waar er geen derde [!DNL cookies] aanwezig zijn. Dat maakt het moeilijk om gebruikers met sommige partners te synchroniseren omdat slechts die [!DNL Adobe] IDs voor gesynchroniseerde derde [!DNL cookies] in de media leveringslogboeken worden verstrekt. Dit is een reden waarom u [lage gelijke tarieven](../features/addressable-audiences.md#low-match-rates) voor uw [!UICONTROL destinations] zou kunnen zien.

## Datumbereik in [!UICONTROL Addressable Audiences] en [!UICONTROL Destinations] {#date-ranges}

Lees de secties hieronder voor beschikbare datumwaaiers en hoe de gegevens uit elk interval in de rapporten voor [!UICONTROL Addressable Audience] of [!UICONTROL Destination] verouderen.

## Beschikbare datumbereiken en tijdzones {#available-date-ranges}

<!-- addressable-audience-dates.xml -->

Rapporten voor uw [!UICONTROL Addressable Audiences] en [Doelen](../features/destinations/destinations.md) gebruiken de zelfde intervallen van het datumbereik. De opties voor het datumbereik zijn:

* [!UICONTROL Last 1 Day] (Dit interval loopt van Midnight aan Midnight van de vorige periode van 24 uur. Het is geen metrisch in real time of huidige tijd.)
* [!UICONTROL Last 7 Days]
* [!UICONTROL Last 14 Days]
* [!UICONTROL Last 30 Days]
* [!UICONTROL Last 60 Days]
* [!UICONTROL Last 90 Days]
* [!UICONTROL Lifetime]

Alle datums en datumbereiken worden ingesteld in de tijdzone [!DNL UTC]. Zie [Tijdzones in Audience Manager](../reference/aam-time-zones.md).

## Gegevens in Datumbereik-intervallen {#date-range-intervals}

De [!UICONTROL Addressable Audience] en [!UICONTROL Destination] metriek keren een telling van unieke gebruikers voor het geselecteerde tijdinterval terug. Een bezoeker wordt bijvoorbeeld slechts één keer meegeteld, zelfs als hij meerdere keren naar uw site komt. Het eerste bezoek is het unieke bezoek en wordt opgenomen. De volgende bezoeken komen terug en worden niet geteld omdat ze niet uniek zijn.

Datumbereiken bevatten gegevens voor het geselecteerde tijdinterval of de geselecteerde ouder. En, de gegevens verouderen uit elk rapportinterval aangezien de tijd overgaat. Stel bijvoorbeeld dat u 2 bezoekers ziet nadat u de optie [!UICONTROL Last 30 Days] hebt gekozen. In de rapporten:

* *Wordt* opgenomen in de resultaten die worden geretourneerd met de langere tijdsintervallen (60 dagen, 90 dagen en Lifetime).
* *Wordt niet* opgenomen in de kortere intervallen die aan de  [!UICONTROL Last 30 Day] optie voorafgaan (Huidige, 7 dagen en 14 dagen).

Op dag 31 komen deze bezoekers alleen voor in de 60 dagen, 90 dagen en de resultaten [!UICONTROL Lifetime]. Ze zijn ouder dan 30 dagen. Bezoekers verouderen niet uit het [!UICONTROL Lifetime] interval.

## [!UICONTROL Addressable Audiences] Metrisch  {#addressable-audience-metrics}

In deze sectie worden de typen metriek beschreven die worden geleverd door [!UICONTROL Addressable Audiences].

### Metriek op klantniveau {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Deze metriek retourneert gegevens voor kenmerken die worden gerealiseerd wanneer bezoekers naar uw site komen of wanneer u binnenkomende gegevensbestanden verzendt naar [!DNL Audience Manager]. Deze metrische gegevens bieden een uitgebreide weergave van de publieksgrootte voor uw account.

| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Customer Addressable Audience] | Een telling van overlapping van apparaten die of [!UICONTROL rule-based trait] of [!UICONTROL onboarded trait] tijdens het terugblik venster en apparaten hebben dat wij een identiteitskaart synchronisatie met de gekozen bestemming ongeacht de tijd van syncs hebben gerealiseerd.<br><br>Deze metrische waarde vertegenwoordigt apparaten die:<ul><li>Tijdens het terugkijkvenster `AND` een [!UICONTROL rule-based] of een [!UICONTROL onboarded trait] hebben gerealiseerd</li><li>Een id synchroniseren met de gekozen [!UICONTROL destination] ongeacht de tijd van syncs.</li></ul> |
| [!UICONTROL Customer Total Audience] | Een aantal apparaten dat of [!UICONTROL rule-based trait] op uw eigenschappen of [!UICONTROL onboarded trait] van uw off-line dossiers tijdens het terugblik-achtervenster heeft gerealiseerd. |
| [!UICONTROL Customer Match Rate] | [!UICONTROL Customer Addressable Audience] Ht  [!UICONTROL Customer Total Audience] uitgedrukt als percentage. |

### Segmentniveau afstemmen {#segment-level-metrics}

Deze cijfers geven gegevens weer over [!UICONTROL segment]-lidmaatschap. Zij helpen een meer korrelige en nauwkeurige mening van de publieksgrootte voor elk van uw [!UICONTROL segments] verstrekken.

>[!NOTE]
>
>De wijze waarop het terugkijkvenster op [!UICONTROL segment] niveau wordt toegepast is verschillend van dat op het niveau van de klant. Bezoekers kunnen 10 dagen geleden naar de site komen en een [!UICONTROL trait] realiseren. Sindsdien kunnen ze in aanmerking komen voor een [!UICONTROL segment] en 2 dagen geleden uit de [!UICONTROL segment] vallen. Wanneer de terugblik van 7 dagen wordt toegepast, zullen deze bezoekers op [!UICONTROL segment] niveau maar niet op het niveau van de klant worden geteld.

| Metrisch | Beschrijving |
|---|---|
| [!UICONTROL Segment Addressable Audience] | Het aantal gebruikers dat tijdens de terugkijkperiode van het rapport tot [!UICONTROL segment] behoorde en een actieve synchronisatie van identiteitskaart op uw plaats hebben. Segmenten kunnen uw eigen gegevens van de eerste partij en gegevens van de tweede en derde partij bevatten, via [!UICONTROL traits] die zijn verkregen in [Audience Marketplace](../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md).<br><br>Tip: Wanneer gebruikt met de periode van de 1 dag terugblik-rug, kan metrisch u helpen de huidige staat van uw begrijpen  [!UICONTROL segments]. Dit komt omdat de [!UICONTROL Segment Addressable Audience] metrische waarde de gebruikers vertegenwoordigt die in [!UICONTROL segment] door de vorige dag bleven. Combineer dit met het feit dat [!DNL Audience Manager] [!UICONTROL Addressable Audiences] dagelijks vernieuwt, combinerend deze metrische en raadplegingsperiode de meest bijgewerkte momentopname van uw [!UICONTROL segments] verstrekt. |
| [!UICONTROL Total Segment Population] | Een telling van alle apparaten die een lid van uw [!UICONTROL segment] tijdens de rapportterugblik periode waren. |
| [!UICONTROL Segment Match Rate] | [!UICONTROL Segment Addressable Audience] Ht  [!UICONTROL Total Segment Population] uitgedrukt als percentage. |

### Metriek op Platform-niveau {#platform-level-metrics}

Deze maatstaf geeft gegevens over activiteiten die zijn verzameld voor alle [!DNL Audience Manager]-klanten. Zij kunnen een breder beeld van het publiek van de klant in vergelijking met de samengevoegde [!DNL Audience Manager] klanten verstrekken.

| Metrisch | Beschrijving |
|---|---|
| [!DNL Audience Manager] [!UICONTROL Addressable Audience] | Een telling van alle apparaten die met alle [!DNL Audience Manager] klanten op het platform-niveau tijdens de rapport terugblik-periode hebben interactie gehad en die met uw gekozen [!UICONTROL destination] zouden kunnen worden aangepast. <br><br>Deze metrisch is nuttig omdat het u toont:<ul><li>De grootte van [!UICONTROL total addressable audience] die [!DNL Audience Manager] op een bepaalde het richten bestemming kan bereiken.</li><li>Hoe groot is de [!DNL Audience Manager] profielpool voor een doelplatform en de grootte van hun publiek.</li></ul> |

## Vergelijken van [!UICONTROL Customer] en [!UICONTROL Segment Addressable Audiences] {#comparing-metrics}

U zou niet de [!UICONTROL Customer Addressable Audience] en [!UICONTROL Segment Addressable Audience] metriek moeten vergelijken om te bepalen als één belangrijker dan andere is. Dit zijn afzonderlijke, verschillende en onafhankelijke meetgegevens. Zoals in de bovenstaande definities is beschreven, zijn deze allemaal afgeleid van verschillende gegevenssets. In dat geval hoeft u geen conclusies te trekken als de ene meting groter is dan de andere. Het enige wat u kunt zeggen bij een vergelijking is:

* [!UICONTROL Customer Addressable Audiences] is gebaseerd op  [!UICONTROL trait] realisaties  *voor uw eigen gegevens* van de eerste partij. Deze metrisch verstrekt een brede, uitvoerige mening van uw integratie met een gegevenspartner.

* [!UICONTROL Segment Addressable Audiences] is gebaseerd op segmentkwalificaties  *voor uw eigen gegevens van de eerste partij, plus gegevens* van de tweede en derde partij. Deze metrisch verstrekt korrelige, nauwkeurigere mening van uw [!UICONTROL addressable audiences] in een gericht platform.

## Causes of low Match Rates for [!UICONTROL Addressable Audiences] {#low-match-rates}

Veelvoorkomende elementen die verantwoordelijk zijn voor lage [!UICONTROL Addressable Audience]-matrixen of discrepanties in gerapporteerde getallen.

| Oorzaak | Beschrijving |
|---|---|
| Mobiel verkeer | De meeste [!UICONTROL server-to-server] integraties vertrouwen op synchronisatieprocessen die door derde worden vergemakkelijkt [!DNL cookies]. Mobiele omgevingen gebruiken echter geen externe [!DNL cookies]. Hierdoor kunnen uw [!UICONTROL Addressable Audiences] cijfers laag lijken in vergelijking met [!UICONTROL segment] formaat. <br><br>Vanaf januari 2018 kunt u mobiele doelgroepen activeren op dezelfde  [!DNL Google] en  [!DNL Adobe Advertising Cloud] bestemmingen als voor  [!UICONTROL cookie-based] het publiek. Hoewel dit betekent dat u [!UICONTROL segments] met gecombineerd [!DNL cookie] en mobiel ID lidmaatschap naar uw [!DNL Google] en [!DNL Advertising Cloud] bestemmingen kunt verzenden, houd in mening dat [!UICONTROL Addressable Audiences] slechts de overlapping tussen [!DNL cookie] IDs en bestemmingen toont. [!DNL Audience Manager] 100 % van de mobiele doelgroepen wordt naar het mobiele publiek gestuurd ,  [!UICONTROL destinations]maar mobiele doelgroepen worden niet met de  [!UICONTROL Addressable Audience] meetnorm gemeten . <br><br>**Opmerking**: Neem bijvoorbeeld een bestand  [!UICONTROL segment] met een populatie van 1.000.000. Als u deze [!UICONTROL segment] aan een [!DNL Google] of [!DNL Adobe Advertising Cloud] bestemming in kaart brengt, zou u [!UICONTROL Addressable Audience] van 700.000 apparaten en [!UICONTROL Match Rate] van 70% kunnen zien. Het lidmaatschap van 700.000 bestaat uit [!DNL cookie] IDs die een identiteitskaart synchronisatie met [!UICONTROL destination] hebben. Uw [!UICONTROL Addressable Audience] zou, in feite veel hoger kunnen zijn, omdat adresseerbare mobiele IDs niet in deze metrisch verschijnen. |
| [!DNL Safari] Verkeer | [!DNL Safari] blokkeert derden  [!DNL cookies]. Zo voorkomt u dat [!DNL Audience Manager] id&#39;s synchroniseert met [!UICONTROL destination]. Met de introductie van [ITP 2.0](https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/), kunt u uw [!UICONTROL addressable audiences] verwachten om [!DNL Safari] gebruikers niet te omvatten. |
| Bijgehouden media-impressies | Vanwege aanbevolen procedures voor advertentieservers worden id-syncs niet binnen advertentietags gemaakt. Klanten die veel offsite advertenties maken, synchroniseren gebruikers niet naar integratie van derden in die omgevingen. Bovendien kan een grote hoeveelheid verzamelde gegevens over mediaminiëring [!UICONTROL addressable audience] getallen verlagen. |

## Problemen oplossen met [!UICONTROL Addressable Audiences] {#troubleshooting}

Naast het surface gelijke tarief, kunt u [!UICONTROL Addressable Audiences] als het oplossen van problemenhulpmiddel ook gebruiken.

Bijvoorbeeld, laten wij zeggen u een segment naar [!UICONTROL destination] verzendt en dat [!UICONTROL destination] lage rapporteringsaantallen toont. Als u de resultaten van [!UICONTROL Addressable Audience] controleert, ziet u dat dit een technisch probleem is of slechts een geval van lage overeenkomstenpercentages. Een lage gelijke tarief toont uw [!UICONTROL destination] niet al zo groot voor uw geselecteerde segmenten is. Een verschil in de [!UICONTROL total addressable audience] getallen tussen [!DNL Audience Manager] en [!UICONTROL destination] duidt echter op een integratie, synchronisatie of ander technisch probleem. Neem in deze gevallen contact op met uw accountmanager.
