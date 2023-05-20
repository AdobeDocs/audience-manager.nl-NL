---
description: Voor een gegevensfeed zijn een naam, beschrijving, gegevensbron en een overzichtstype vereist. De feeds worden uitgeschakeld totdat u de feed opslaat en activeert. Stel openbare of persoonlijke gegevensfeeds in in Audience Marketplace > Mijn gedeelde gegevens. Alleen beschikbaar voor verkopers van gegevens.
seo-description: A data feed requires a name, description, data source, and a plan type. Feeds are disabled until you save and activate the feed. Set up public or private data feeds in Audience Marketplace > My Shared Data. Available to data sellers only.
seo-title: Create, Price, and Manage Data Feeds
solution: Audience Manager
title: Datafeeds maken, prijzen en beheren
uuid: e28c20b3-33fc-4485-8ee9-8530d126f741
feature: Audience Marketplace
exl-id: e8605e94-e62a-430c-9aef-875f995fb436
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '1257'
ht-degree: 1%

---

# Datafeeds maken, prijzen en beheren {#create-price-and-manage-data-feeds}

## Een openbare of persoonlijke gegevensfeed maken {#create-public-private-data-feed}

Voor een gegevensfeed zijn een naam, beschrijving, gegevensbron en een overzichtstype vereist. De feeds worden uitgeschakeld totdat u de feed opslaat en activeert. Openbare of persoonlijke gegevensfeeds instellen in **[!UICONTROL Audience Marketplace > My Shared Data]**. Alleen beschikbaar voor verkopers van gegevens.

<!-- t_data_feed.xml -->

U moet beheerdersrechten hebben om een openbare of persoonlijke gegevensfeed te maken.
Een gegevensfeed maken:

1. Klik op **[!UICONTROL New Data Feed]**.
1. Geef de gegevensfeed een naam. Kopers van gegevens kunnen op basis van de naam naar je feed zoeken.
1. Geef een korte beschrijving (maximaal 255 tekens).

   Een goede beschrijving moet uw voer nauwkeurig beschrijven. U kunt bijvoorbeeld tekst opnemen voor marketingcategorieën, demografie en geografische dekking (bijvoorbeeld [!DNL US] of Noord-Amerika). Beschrijvende tekst kan worden doorzocht en kopers kunnen je feed zoeken of evalueren. Een goede beschrijving is een belangrijk onderdeel van het aantrekken van abonnees voor uw gegevensinvoer.
1. Selecteer een gegevensbron in het menu **[!UICONTROL Data Source]** opties. Gegevensfeeds zijn beperkt tot één gegevensbron. U kunt niet meerdere gegevensbronnen aan dezelfde gegevensfeed toewijzen.

   >[!IMPORTANT]
   >
   >Alle huidige en toekomstige kenmerken van deze gegevensbron worden als onderdeel van deze feed gedeeld met de kopers van gegevens.

1. In [!UICONTROL Plan Types]selecteert u de gewenste opties en klikt u op **[!UICONTROL Add Plan]**.

   Feeds kunnen meerdere plannen bevatten. Plannen kunnen meerdere gebruiksgevallen bevatten. Zie voor meer informatie [Typen abonnementen voor gegevensfeeds](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#plan-types).

1. Klikken **[!UICONTROL Save]** om de gegevensinvoer op te slaan *zonder* activeren.
1. Een gegevensfeed opslaan en activeren:
   1. Verplaats de **[!UICONTROL Availability]** schuifregelaar naar **[!UICONTROL Active]**.
   1. Klik op **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >* Opgeslagen en geactiveerde gegevensfeeds kunnen niet worden verwijderd.
   >* Kopers zien alleen actieve feeds.


### Optioneel: Een persoonlijke gegevensfeed maken

In de [!UICONTROL Settings] de schuifregelaar naar:

* **[!UICONTROL Private]** en **[!UICONTROL Branded]**: De koper [!UICONTROL Marketplace] in de lijst wordt de naam van de verkoper weergegeven in de kolom met de provider en worden alle andere gegevens verborgen.

* **[!UICONTROL Private]** en **[!UICONTROL Unbranded]**: De koper [!UICONTROL Marketplace] wordt alleen de naam en beschrijving van de gegevensinvoer weergegeven. De naam van de gegevensaanbieder wordt weergegeven als [!UICONTROL Private Seller].

Zie de sectie Kopers in de sectie [Privégegevensfeeds](../../../features/audience-marketplace/marketplace-private-feeds.md).

## De gegevensfeed van een abonnee deactiveren {#deactivate-data-feed}

Als [!UICONTROL Audience Marketplace] -gegevensaanbieder, kunt u de toegang van kopers tot een geabonneerde gegevenstoevoer intrekken. Je kunt een koper uit een feed verwijderen om redenen zoals te late betaling of niet-betaling van kosten of als de gegevens onjuist worden gebruikt.

<!-- marketplace-deactiva4te-subscribers.xml -->

Een abonnee intrekken:

1. In [!UICONTROL My Shared Data], vindt u de feed die de abonnee gebruikt.

   >[!NOTE]
   >
   >Gegevensfeeds met achterstallige accounts worden gemarkeerd met een driehoek-/uitroeptekenpictogram.

1. In de [!UICONTROL Subscribers] klikt u op het blauwe getal waarmee de abonnees van die feed worden geteld. Hiermee wordt de pagina met abonnementsdetails geopend.
1. Verplaats de **[!UICONTROL Subscription]** schuifregelaar naar **[!UICONTROL Off]**. Hiermee wordt een bevestigingsvenster geopend.
1. In de [!UICONTROL Confirmation] pop, klikken **[!UICONTROL Yes]** om een abonnement te deactiveren of **[!UICONTROL Cancel]** om af te sluiten zonder abonnementswijzigingen aan te brengen.

### Wat gebeurt er nadat u een abonnee hebt gedeactiveerd

Als u de toegang tot een gegevensfeed intrekt, wordt een e-mailbericht verzonden naar alle beheerdersgebruikers in de account van de gegevenskoper. Het e-mailbericht bevat een bijlage met ingetrokken kenmerken. Met deze lijst kunnen abonnees gedeactiveerde kenmerken uit hun segmenten en modellen zoeken en verwijderen.

### Facturering en deactivering van diervoeders

Nadat u de toegang tot een gegevensfeed hebt verwijderd, zijn de abonnees verantwoordelijk voor de kosten voor de vorige of huidige maand, afhankelijk van het moment waarop u de feed hebt gedeactiveerd.

## Typen abonnementen voor gegevensfeeds {#plan-types}

[!DNL Plan types] zijn essentiële componenten in een [!UICONTROL Audience Marketplace] gegevensinvoer. Als gegevensleverancier, laten zij u veelvoudige gebruiksgevallen en prijsopties voor uw voer tot stand brengen. Bovendien kan het een goede strategie zijn om een paar plannen voor elke gegevensinvoer te creëren. Dit geeft kopers verschillende opties om te kiezen wanneer ze gegevens zoeken om te modelleren of naar een bestemming te verzenden.

[Een gegevensfeed maken](../../../features/audience-marketplace/marketplace-data-providers/marketplace-create-manage-feeds.md#create-public-private-data-feed) om [!UICONTROL Plan Types].

![](assets/plan_types.png)

## Typen abonnementen en opties hoofdletters/kleine letters gebruiken {#plan-types-use-cases}

<!-- c_feed_options.xml -->

De [!UICONTROL Use Case] Met instellingen kunnen verkopers bepalen hoe kopers je gegevens kunnen gebruiken.

### Segmenten en overlappen

A **[!UICONTROL Segments and Overlap]** use case creëert een plan dat kopers in staat stelt om de gegevens over de kenmerken in een [overlap tussen kenmerk en kenmerk](../../../reporting/dynamic-reports/trait-trait-overlap-report.md#trait-to-trait-overlap-report). Bovendien kunnen kopers je gegevens aan segmenten toevoegen en vergelijken met de [van segment tot kenmerk](../../../reporting/dynamic-reports/segment-trait-overlap-report.md) en [segment-tot-segment](../../../reporting/dynamic-reports/segment-segment-overlap-report.md) rapporten.

Elke gegevensinvoer moet ten minste één [!UICONTROL Segments and Overlap] use case. Kopers kunnen zich niet abonneren op andere plannen in een gegevensfeed als de feed geen [!UICONTROL Segments and Overlap] het geval van gebruik, op zich of in combinatie met een ander geval van gebruik.

Met overlappende vergelijkingen kunnen kopers helpen:

* **Bereik publiek uitbreiden:** Lage overlapping suggereert dat je verkoopcijfers gebruikers bevatten die de koper nog niet eerder heeft gezien. Hierdoor kunnen kopers nieuwe gebruikers aan hun doelsegmenten toevoegen met deze kenmerken.
* **Bestaande doelgroepen verbeteren:** Bij hoge overlapping worden gebruikers in je transacties vermeld die vergelijkbaar zijn met die waarvan de koper al op de hoogte is. Hierdoor kunnen kopers deze kenmerken gebruiken om doelgerichte, geleidelijke verbeteringen door te voeren voor ontwikkelde doelgroepen.

Prijs voor dit gebruik als volgt:

* Maateenheid: Vaste vergoeding
* Prijs: Gratis ($0,00)

### Modellering

A **[!UICONTROL Modeling]** Met gebruik van hoofdletters en kleine letters wordt een abonnement gemaakt waarmee kopers je kenmerken kunnen vergelijken met [algoritmische modellering](../../../features/algorithmic-models/understanding-models.md#understanding-models). Kopers bekijken de modelresultaten om nieuwe soorten publiek in uw gegevens te vinden die gelijkaardige omzettingsattributen aan hun delen. Prijs voor dit gebruik als volgt:

* Maateenheid: Vaste vergoeding
* Prijs: Discount of marktkoers

### Activering

An **[!UICONTROL Activation]** Met gebruik van hoofdletters kunnen kopers gegevens naar een [doel](../../../features/destinations/destinations.md). In dit geval kunnen kopers geen gegevens vergelijken met een overlappend rapport of met een algoritmisch model. Prijs voor dit gebruik als volgt:

* Maateenheid: [!DNL CPM]
* Prijs: [!DNL CPM] marktkoers

## Facturerings- en prijsopties {#billing}

Met de facturerings- en prijsopties bepaalt u hoe kopers voor je gegevens betalen.

<table id="table_CCEAAF24295942EA82F20753827D1A23"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Option </th> 
   <th colname="col2" class="entry"> Beschrijving </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Factureringscyclus</span></b> </td> 
   <td colname="col2"> <b><span class="uicontrol"> Maandelijks in achterstallige betalingen</span></b> is de enige optie. De factureringscyclus eindigt op de tiende dag van elke maand. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Maateenheid</span></b> </td> 
   <td colname="col2">Verkopers van gegevens een CPM-tarief of een vast tarief in rekening brengen. 
    <ul id="ul_D5F125E0F7364C568D9F3107E090059D"> 
     <li id="li_A79F47FFC1DC4B9DADC014621A9C12A1"> Met CPM-prijzen moeten gegevenskopers zelf hun gebruik melden. </li> 
     <li id="li_DFED3194854A492F9DD0E7BA1A655E96">Met een vaste prijs melden gegevenskopers geen gebruik omdat ze een vaste prijs moeten betalen. </li> 
    </ul> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <b><span class="uicontrol"> Prijs</span></b> </td>
   <td colname="col2"> Het bedrag dat een verkoper aan de koper aanrekent als CPM-tarief of forfaitaire prijs in dollars. </td>
  </tr> 
 </tbody> 
</table>

## Opmerkingen bij het abonnement {#plan-notes}

In de **[!UICONTROL Additional Notes]** veld, duurt het even om elk gegevensplan in een feed te beschrijven. Een goede, korte beschrijving helpt kopers de inhoud of het doel van elk abonnement in een gegevensfeed te begrijpen. Kopers kunnen gegevensinvoer en planbeschrijvingen lezen terwijl ze naar nieuwe gegevensbronnen zoeken of deze evalueren.

## Aanvragen voor privégegevensinvoer beheren {#manage-private-requests}

Workflows van leveranciers voor het beheer van persoonlijke feedbackaanvragen van kopers.

Ga naar [!UICONTROL My Shared Data] en:

<!-- t_private_feed_workflows.xml -->

1. Klik op de naam van de persoonlijke gegevensinvoer.
2. Klikken **[!UICONTROL Access Requests]** om alle kopers te bekijken die toegang willen tot je gegevens.
3. In de [!UICONTROL Allow Access] van elk verzoekvakje, klik het vinkje om een verzoek goed te keuren of X om toegang te ontkennen.
4. Bevestig of annuleer de geselecteerde actie in het bevestigingspop-up.

## Kortingen voor gegevensleveranciers {#discounts}

In [!UICONTROL Audience Marketplace]Met kortingen kunt u de gepubliceerde prijs van een gegevensfeed voor individuele abonnees verlagen. U kunt kortingen aanbieden aan abonnees die een abonnementsverzoek hebben ingediend of aan abonnees die om details over een gegeven hebben verzocht. Kortingen van toepassing op [!DNL CPM] en forfaitaire feeds. De kortingen kunnen nuttig zijn wanneer u abonnementsprikkels voor nieuwe klanten wilt verstrekken of klantenloyaliteit te belonen.

## Kortingen toepassen op een gegevensfeed {#apply-discounts}

<!-- marketplace-seller-discounts.xml -->

Als u een feed wilt disconteren, voegt u een kortingsbedrag als een % toe aan het veld voor korting en bevestigt u uw wijzigingen. Gegevensleveranciers kunnen een gegevensfeed in [!UICONTROL Audience Marketplace] van:

* **[!UICONTROL My Shared Data > Potential Subscribers]**
* **[!UICONTROL My Shared Data > Details Requests]**

In deze voorbeelden heeft de verkoper een korting van 10% toegevoegd aan de [!UICONTROL Software Audience] gegevensinvoer.

![](assets/potential_subscribers.png)

![](assets/detail_requests.png)

## Korte feeds controleren {#review-discounted-feeds}

De leveranciers van gegevens kunnen al hun abonnees en gedisconteerde feeds in zien **[!UICONTROL Audience Marketplace > My Shared Data > Current Subscribers]**.

![](assets/subscribers.png)

>[!MORELIKETHIS]
>
>* [Privédatafeeds](../../../features/audience-marketplace/marketplace-private-feeds.md)

