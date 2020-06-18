---
description: Een overzicht van de Adresseerbare eigenschap van het Publiek en gebruiksgevallen.
keywords: DIL
seo-description: Een overzicht van de Adresseerbare eigenschap van het Publiek en gebruiksgevallen.
seo-title: Adresseerbaar publiek
solution: Audience Manager
title: Adresseerbaar publiek
topic: DIL API
uuid: 3eb1335a-6949-452b-b77a-697c22856cb3
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '2059'
ht-degree: 0%

---


# Adresseerbaar publiek {#addressable-audiences}

Een overzicht van de [!UICONTROL Addressable Audience] functie en gebruiksgevallen.

## Wat is een adresseerbaar publiek? {#addressable-audience-description}

De [!UICONTROL Addressable Audiences] functie toont de overlap tussen het publiek dat u over al uw eigenschappen ziet waar gegevens en uw geselecteerde bestemming worden [!DNL Audience Manager] verzameld. Om u te helpen dit concept begrijpen, neem een blik hieronder op de illustratie. De overlapping tussen elke cirkel vertegenwoordigt de verschillende soorten adresseerbare soorten publiek.

![](assets/addressableAudienceVenn.png)

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrisch </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
    <tr> 
   <td colname="col1"> <p> <b>Adresseerbare Publiek van de Audience Manager voor een Bestemming</b> </p> </td> 
   <td colname="col2"> <p>Een telling van alle apparaten die met alle klanten van de Audience Manager op platform-niveau tijdens de rapportterugblik periode hebben gecommuniceerd en die met uw gekozen bestemming zouden kunnen worden aangepast. </p> <p>Deze metrisch is nuttig omdat het u toont: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> De grootte van het totale adresseerbare publiek dat de <span class="keyword"> Audience Manager</span> op een bepaalde gericht bestemming kan bereiken. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Hoe groot is de <span class="keyword"> Audience Manager</span> -profielpool voor een doelplatform en de grootte van hun publiek. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Klanttotaal publiek</b> </p> </td> 
   <td colname="col2"> <p>Een telling van apparaten die of een op regel-gebaseerde eigenschap op uw eigenschappen of een onbeheerd spoor van uw off-line dossiers tijdens het terugblik-achtervenster hebben gerealiseerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Adresseerbare Poortverhouding van het publiek</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Een telling van overlapping van apparaten die of een op regel-gebaseerd bezit of een ongebogen eigenschap tijdens het terugblik-achtervenster en apparaten hebben dat wij een identiteitskaart synchronisatie met de gekozen bestemming ongeacht de tijd van syncs hebben. </p> 
    </draft-comment> <p>Deze metrische waarde vertegenwoordigt apparaten die: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Tijdens het terugkijkvenster een op regel gebaseerd of een ongebogen kenmerk hebben bereikt <b>EN</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Identiteitssynchronisatie hebben met de gekozen bestemming ongeacht de tijd van syncs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Klantenovereenkomst</b> </p> </td> 
   <td colname="col2"> <p>Klantadresseerbare doelgroep:totaalpubliek van klant uitgedrukt als %. </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <b>Totale segmentpopulatie</b> </p> </td> 
   <td colname="col2"> <p>Een telling van alle apparaten die een lid van uw segment tijdens de periode van de rapportterugblik waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Segment adresseerbaar publiek</b> </p> </td> 
   <td colname="col2"> <p>Het aantal gebruikers die tot het segment tijdens de rapportterugblik periode behoorden en een actieve synchronisatie van identiteitskaart op uw plaats hebben. Segmenten kunnen uw eigen gegevens van de eerste partij en gegevens van de tweede en derde partij bevatten, via transacties die in de <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>zijn aangeschaft. </p> <p> <p>Tip: Wanneer gebruikt met de periode van de 1 dag terugblik-rug, kan metrisch u helpen de huidige staat van uw segmenten begrijpen. Dit is omdat <span class="wintitle"> Segment Adressable Metrisch van het Publiek</span> de gebruikers vertegenwoordigt die in een segment door de vorige dag bleven. Combineer dit met het feit dat de <span class="keyword"> Audience Manager</span> <span class="wintitle"> Adresseerbare Soorten van publiek</span> dagelijks vernieuwt, combinerend deze metrische en raadplegingsperiode de meest bijgewerkte momentopname van uw segmenten verstrekt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Afstandsfrequentie</b> </p> </td> 
   <td colname="col2"> <p>Segment adresseerbare Publiek HT totale segmentpopulatie uitgedrukt als %. </p> </td> 
  </tr>  
 </tbody> 
</table>

## Adresseerbare interface van het publiek {#addressable-audience-interface}

De [!UICONTROL Addressable Audience] functie verandert dit abstracte concept in kwantificeerbare gegevens. In [!DNL Audience Manager]deze functie wordt de publieksoverlapping weergegeven met gegevensvisualisaties die in één oogopslag informatie en numerieke gegevens in tabelvorm verschaffen.

[!UICONTROL Addressable Audiences] bevindt zich in **[!UICONTROL Audience Data > Destinations]**. Selecteer deze optie **[!UICONTROL Integrated Platforms > Device-Based]** om de meetgegevens voor adressaten weer te geven.

![](assets/addressable-audiences-landing.png)

De drie metriek die u op de [!UICONTROL Addressable Audiences] landingspagina kunt zien, vertegenwoordigen:

| Metrisch | Beschrijving |
---------|----------|
| **[!UICONTROL Addressable Audience (Device)]** | Deze metrische waarde vertegenwoordigt de [!UICONTROL Customer Addressable Audience] (beschreven in de bovenstaande tabel) *voor de laatste 30 dagen.* |
| **[!UICONTROL Match Rate]** | Deze metrische waarde vertegenwoordigt de [!UICONTROL Addressable Audience Match Rate] (beschreven in de bovenstaande tabel) *voor de laatste 30 dagen*. |
| **[!UICONTROL Lifetime Addressable Audience (Device)]** | Een telling van alle apparaten die met alle [!DNL Audience Manager] klanten op platform-niveau tijdens de rapportterugblik periode in wisselwerking hebben gestaan en die met deze bestemming zouden kunnen worden aangepast. Zie Metriek [op](/help/using/features/addressable-audiences.md#platform-level-metrics) Platform-Niveau voor meer informatie. |

Klik op de naam van een server-aan-server bestemming om uw adresseerbare publieksgegevens te bekijken. Nota, keert deze eigenschap gegevens voor server-aan-server slechts bestemmingen terug en de toegang vereist beheerdertoestemmingen.

![](assets/addressableAudiences.png)

Als u deze gegevens controleert, kunt u:

* **Voorspelling en planning:** [!UICONTROL Segment Addressable Audience] de gegevens geven u meer granulariteit in de segmenten u van plan bent om naar een bestemming voor publiek te verzenden richtend en activering.

* **Prestatiebeoordelingen:** De [!UICONTROL Addressable Audiences] functie is ook een hulpprogramma voor probleemoplossing. Het laat u campagneprestaties herzien, campagnebereik begrijpen, en laat u met het richten/activeringspartners kruisen als u niet de resultaten ziet u verwacht.

### Prospecties met gegevens en implicaties van derden voor gelijke tarieven

Alvorens derdegegevens voor publieksverwerving te kopen, kunnen de klanten de overlapping met andere gegevensleveranciers bevestigen. Dit kan u helpen een geïnformeerde beslissing nemen alvorens nieuwe gegevens te kopen. De ID-syncs voor aangekochte gegevens van derden zijn niet alleen afhankelijk van de overlapping van uw gegevens, maar ook van de voetafdrukken van andere leveranciers met alle andere [!DNL Audience Manager] klanten. Uw [!DNL Adobe] consultant kan u helpen aanvullende relevante gegevensbronnen te identificeren om uw prospectiecampagnes te optimaliseren.

### Mobiele gebruikers en gelijke tarieven

Er zijn leemten wanneer gebruikers van mobiele apps verbinding proberen te maken [!DNL Safari] of wanneer er geen cookies van derden aanwezig zijn. Dit maakt het moeilijk om gebruikers met sommige partners te synchroniseren omdat slechts die [!DNL Adobe] IDs voor gesynchroniseerde derdekoekjes in de media leveringslogboeken worden verstrekt. Dit is een reden waarom u [lage gelijke tarieven](../features/addressable-audiences.md#low-match-rates) voor uw bestemmingen zou kunnen zien.

## Datumbereik in adresseerbare soorten publiek en bestemmingen {#date-ranges}

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

## Adresseerbare peilgegevens {#addressable-audience-metrics}

In deze sectie worden de typen metriek beschreven die worden geleverd door [!UICONTROL Addressable Audiences].

### Metriek op klantniveau {#customer-level-metrics}

<!-- addressable-audience-metrics.xml -->

Deze metriek retourneert gegevens voor kenmerken die worden gerealiseerd wanneer bezoekers naar uw site komen of wanneer u binnenkomende gegevensbestanden verzendt naar [!DNL Audience Manager]. Deze metrische gegevens bieden een uitgebreide weergave van de publieksgrootte voor uw account.

<table id="table_6DC02E219B074BF782EAA0E9DB9495FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrisch </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Klantadresseerbare doelgroep</b> </p> </td> 
   <td colname="col2"> 
    <draft-comment> 
     <p>Een telling van overlapping van apparaten die of een op regel-gebaseerd bezit of een ongebogen eigenschap tijdens het terugblik-achtervenster en apparaten hebben dat wij een identiteitskaart synchronisatie met de gekozen bestemming ongeacht de tijd van syncs hebben. </p> 
    </draft-comment> <p>Deze metrische waarde vertegenwoordigt apparaten die: 
     <ul id="ul_B609B402A29D44898DF0B1ABC6011D40"> 
      <li id="li_27A530DE2AEB48069BECFB2D78E94C4E">Tijdens het terugkijkvenster een op regel gebaseerd of een ongebogen kenmerk hebben bereikt <b>EN</b> </li> 
      <li id="li_47C44ECAEC5844DEB11C6A93C8F061BB">Identiteitssynchronisatie hebben met de gekozen bestemming ongeacht de tijd van syncs. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Klanttotaal publiek</b> </p> </td> 
   <td colname="col2"> <p>Een telling van apparaten die of een op regel-gebaseerde eigenschap op uw eigenschappen of een onbeheerd spoor van uw off-line dossiers tijdens het terugblik-achtervenster hebben gerealiseerd. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Klantenovereenkomst</b> </p> </td> 
   <td colname="col2"> <p>Klantadresseerbare doelgroep:totaalpubliek van klant uitgedrukt als %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Identieke cijfers op segmentniveau {#segment-level-metrics}

Deze metriek keert gegevens over segmentlidmaatschap terug. Ze helpen u een gedetailleerdere en nauwkeurigere weergave van de publieksgrootte voor elk van uw segmenten te bieden.

>[!NOTE]
>
>De manier het terugblik-achtervenster wordt toegepast op het segmentniveau is verschillend van dat op het klantenniveau. Bezoekers kunnen 10 dagen geleden naar de site komen en een kenmerk realiseren. Sindsdien kunnen ze in aanmerking komen voor een segment en 2 dagen geleden uit het segment vallen. Wanneer de terugblik van 7 dagen wordt toegepast, zullen deze bezoekers op het segmentniveau maar niet op het klantenniveau worden geteld.

<table id="table_4185AA02CC774B6C93B02E45F88BBBD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrisch </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Segment adresseerbaar publiek</b> </p> </td> 
   <td colname="col2"> <p>Het aantal gebruikers die tot het segment tijdens de rapportterugblik periode behoorden en een actieve synchronisatie van identiteitskaart op uw plaats hebben. Segmenten kunnen uw eigen gegevens van de eerste partij en gegevens van de tweede en derde partij bevatten, via transacties die in de <a href="../features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md"> Audience Marketplace</a>zijn aangeschaft. </p> <p> <p>Tip: Wanneer gebruikt met de periode van de 1 dag terugblik-rug, kan metrisch u helpen de huidige staat van uw segmenten begrijpen. Dit is omdat <span class="wintitle"> Segment Adressable Metrisch van het Publiek</span> de gebruikers vertegenwoordigt die in een segment door de vorige dag bleven. Combineer dit met het feit dat de <span class="keyword"> Audience Manager</span> <span class="wintitle"> Adresseerbare Soorten van publiek</span> dagelijks vernieuwt, combinerend deze metrische en raadplegingsperiode de meest bijgewerkte momentopname van uw segmenten verstrekt. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Totale segmentpopulatie</b> </p> </td> 
   <td colname="col2"> <p>Een telling van alle apparaten die een lid van uw segment tijdens de periode van de rapportterugblik waren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Afstandsfrequentie</b> </p> </td> 
   <td colname="col2"> <p>Segment adresseerbare Publiek HT totale segmentpopulatie uitgedrukt als %. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Metriek op Platform-niveau {#platform-level-metrics}

Deze metrische winst gegevens over activiteiten die over alle [!DNL Audience Manager] klanten worden verzameld. Zij kunnen een breder beeld van het publiek van de klant in vergelijking met de samengevoegde [!DNL Audience Manager] klanten verstrekken.

<table id="table_B6654D9858FF46AF95B1C181D4608D26"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrisch </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Adresseerbare doelgroep van Audience Manager</b> </p> </td> 
   <td colname="col2"> <p>Een telling van alle apparaten die met alle klanten van de Audience Manager op platform-niveau tijdens de rapportterugblik periode hebben gecommuniceerd en die met uw gekozen bestemming zouden kunnen worden aangepast. </p> <p>Deze metrisch is nuttig omdat het u toont: </p> <p> 
     <ul id="ul_67A82A40C7A64457822272B45D2817FC"> 
      <li id="li_DAEFB565CE774F68AA29274A021F1E5A"> De grootte van het totale adresseerbare publiek dat de <span class="keyword"> Audience Manager</span> op een bepaalde gericht bestemming kan bereiken. </li> 
      <li id="li_AF26F88068CA44F7B5C4C42DE5E21055">Hoe groot is de <span class="keyword"> Audience Manager</span> -profielpool voor een doelplatform en de grootte van hun publiek. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Het vergelijken van Klant en Segment Adresseerbare Publiek{#comparing-metrics}

U zou niet de [!UICONTROL Customer Addressable Audience] en [!UICONTROL Segment Addressable Audience] metriek moeten vergelijken om te bepalen als één beduidender is dan andere. Dit zijn afzonderlijke, verschillende en onafhankelijke meetgegevens. Zoals in de bovenstaande definities is beschreven, zijn deze allemaal afgeleid van verschillende gegevenssets. In dat geval hoeft u geen conclusies te trekken als de ene meting groter is dan de andere. Het enige wat u kunt zeggen bij een vergelijking is:

* [!UICONTROL Customer Addressable Audiences] is gebaseerd op de realisatie van de eigenschap *voor uw eigen gegevens* van de eerste partij. Deze metrisch verstrekt een brede, uitvoerige mening van uw integratie met een gegevenspartner.

* [!UICONTROL Segment Addressable Audiences] is gebaseerd op segmentkwalificaties *voor uw eigen gegevens van de eerste partij, plus gegevens* van de tweede en derde partij. Deze metrisch verstrekt korrelige, nauwkeurigere mening van uw adresseerbare publiek in een gericht platform.

## Oorzaken van lage matchingstarieven voor adresseerbare soorten publiek {#low-match-rates}

Veelvoorkomende elementen die verantwoordelijk zijn voor lage [!UICONTROL Addressable Audience] match-percentages of discrepanties in gerapporteerde getallen.

<!-- addressable-audiences.xml -->

<table id="table_895D536F69134330A4F13887ECAFD4F5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Oorzaak </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Mobiel verkeer</b> </p> </td> 
   <td colname="col2"> <p>De meeste server-aan-server integraties baseren zich op synchronisatieprocessen die door derdekoekjes worden vergemakkelijkt. Mobiele omgevingen gebruiken echter geen cookies van derden. Dientengevolge, kunnen uw Adresseerbare aantallen van het Publiek laag in vergelijking met segmentgrootte schijnen. </p> <p>Vanaf januari 2018 kunt u mobiele doelgroepen activeren op dezelfde Google- en Adobe Advertising Cloud-doelen die zijn ingesteld voor op cookies gebaseerd publiek. Hoewel dit betekent dat u segmenten met een gecombineerd cookie en een lidmaatschap voor een mobiele id naar uw Google- en Advertising Cloud-doelen kunt verzenden, moet u er rekening mee houden dat adresseerbare soorten publiek alleen de overlapping tussen cookie-id's en doelen weergeven. De Audience Manager verzendt 100% van mobiele toedieningen naar bestemmingen, maar de mobiele toedieningen worden niet gemeten door de adresseerbare metrisch van het Publiek. </p> <p> <p><b>Opmerking</b>:  Neem bijvoorbeeld een segment met een populatie van 1.000.000. Als u dit segment toewijst aan een Google- of Adobe Advertising Cloud-bestemming, ziet u mogelijk een adresseerbare Publiek van 700.000 apparaten en een Gelijke Snelheid van 70%. Het lidmaatschap van 700.000 bestaat uit cookie-id's die een id-synchronisatie met de bestemming hebben. Uw adresseerbare publiek zou, in feite, veel hoger kunnen zijn, omdat adresseerbare mobiele IDs niet in deze metrisch verschijnen. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Safari-verkeer</b> </p> </td> 
   <td colname="col2"> <p>Safari blokkeert cookies van derden. Zo voorkomt u dat Audience Manager id's synchroniseert met het doel. Met de introductie van <a href="https://webkit.org/blog/8311/intelligent-tracking-prevention-2-0/" format="https" scope="external"> ITP 2.0</a>, kunt u uw adresseerbare publiek verwachten om gebruikers niet Safari te omvatten. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Bijgehouden media-impressies</b> </p> </td> 
   <td colname="col2"> <p>Vanwege aanbevolen procedures voor advertentieservers worden id-syncs niet binnen advertentietags gemaakt. Klanten die veel offsite advertenties maken, synchroniseren gebruikers niet naar integratie van derden in die omgevingen. Ook, zou een grote hoeveelheid verzamelde media impressiegegevens adresseerbare aantallen kunnen verminderen. </p> </td>
  </tr> 
 </tbody> 
</table>

## Problemen oplossen met adresseerbare soorten publiek {#troubleshooting}

Naast het surface gelijke tarieven, kunt u ook gebruiken [!UICONTROL Addressable Audiences] als het oplossen van problemenhulpmiddel.

<!-- addressable-audiences-troubleshooting.xml -->

Bijvoorbeeld, laten wij zeggen u een segment naar een bestemming verzendt en die bestemming toont lage rapporteringsaantallen. Als u de [!UICONTROL Addressable Audience] resultaten controleert, ziet u of dit een technisch probleem is of slechts een geval van lage tarieven. Een lage gelijke tarief toont uw bestemming niet al zo groot voor uw geselecteerde segmenten is. Nochtans, wijst een verschil in de totale adresseerbare publieksaantallen tussen [!DNL Audience Manager] en de bestemming op een integratie, synchronisatie, of ander technisch probleem. Neem in deze gevallen contact op met uw accountmanager.