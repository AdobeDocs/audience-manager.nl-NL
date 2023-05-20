---
description: Kopers van gegevens van Audience Marketplace komen overeen om alle advertenties te melden die zijn gediend met gebruikmaking van de kenmerken in de gegevenstoevoer tegen een prijs per duizend en op basis van indrukken (CPM). Het CPM-gebruik is verschuldigd op de vijfde dag van elke kalendermaand en omvat gegevens voor de voorgaande maand. Abonnees met vaste kosten hoeven het gebruik niet te melden.
seo-description: Audience Marketplace data buyers agree to report all ad impressions served using traits contained in the data feed priced on a cost per thousand ad impressions (CPM) basis. CPM usage is due on the 5th day of each calendar month and includes data for previous month. Flat fee subscribers do not need to report usage.
seo-title: Billing for Data Feed Buyers
solution: Audience Manager
title: Facturering voor datafeedkopers
keywords: Rapportage op segmentniveau, segmentniveau, segmentniveau
uuid: d7236667-282b-4160-9909-579721af4016
feature: Audience Marketplace
exl-id: 401cf3be-fa84-4654-936e-e2871fef0be9
source-git-commit: 88ed0b28fdf5dc03c8a878529d65b4bc844ea6c9
workflow-type: tm+mt
source-wordcount: '2002'
ht-degree: 0%

---

# Facturering voor datafeedkopers {#billing-for-data-feed-buyers}

Kopers van Audience Marketplace-gegevens stemmen ermee in alle advertenties te melden die zijn gediend met gebruik van de kenmerken in de gegevenstoevoer die zijn geprijsd op een prijs per duizend en indrukkingen ([!DNL CPM]). [!DNL CPM] het gebruik is verschuldigd op de vijfde dag van elke kalendermaand en omvat gegevens voor de vorige maand. Abonnees met vaste kosten hoeven het gebruik niet te melden.

<br>

## Hoe te om CPM Gebruik te melden {#report-cpm-usage}

<!-- t_marketplace_report_cpm_usage.xml -->

[!UICONTROL Audience Marketplace] kopers van gegevens komen overeen alle gebruikte indrukken te melden met behulp van de kenmerken in de gegevenstoevoer tegen een prijs per duizend en indrukkingen ([!DNL CPM]). [!DNL CPM] het gebruik is verschuldigd op de 5 dagen van elke kalendermaand en omvat gegevens voor de vorige maand. Abonnees met vaste kosten hoeven het gebruik niet te melden.

[!UICONTROL Audience Marketplace] biedt twee manieren om te rapporteren [!DNL CPM] gebruik:

* **Rapportage op segmentniveau**: dit wordt aanbevolen [!DNL CPM] de methode voor gebruiksrapportage. Wanneer u rapporteert [!DNL CPM] gebruik op segmentniveau, wordt de gegevens input-vlakke rapporteringssectie automatisch ingevuld met de overeenkomstige gebruiksbedragen, die op de algoritmen worden gebaseerd die in [Kostentoerekeningswaarde voor CPM-gegevensfeeds](#cost-attribution).
* **Rapportage op het niveau van gegevenstoevoer**: deze methode vereist dat u de [!DNL CPM] gebruik voor elke gegevensinvoer, op basis van de in [Kostentoerekeningswaarde voor CPM-gegevensfeeds](#cost-attribution). Deze methode is echter lastiger en vatbaarder voor fouten dan rapportage op segmentniveau.

<br>

## CPM-gebruik op segmentniveau rapporteren {#segment-level-report}

De [!UICONTROL Segment Usage] het lusje staat u toe om segment-vlakke gebruik te melden, terwijl het tonen van de segmenten die door de bestemmingen worden gegroepeerd zij aan in kaart worden gebracht.

Na rapportage [!DNL CPM] gebruik op segmentniveau; [!UICONTROL Audience Marketplace] wijst automatisch het juiste gebruik toe aan de overeenkomstige gegevensfeeds, gebaseerd op de [Kostentoerekeningswaarde voor CPM-gegevensfeeds](#cost-attribution).

Rapport [!DNL CPM] gebruik op segmentniveau:

1. Ga naar **[!UICONTROL Audience Marketplace > Payables]**.
1. Selecteer **[!UICONTROL Segment Usage]** tab.
1. Vul het gebruik voor uw segmenten in. U kunt de [!UICONTROL Search] doos om de segmenten te filtreren als u slechts gebruik voor sommige van hen moet melden.
1. Klik op **[!UICONTROL Edit Segments Usage]**.
1. Voer de [!DNL CPM] gebruiksbedrag in de [!UICONTROL Usage] kolom.
1. Klikken **[!UICONTROL Save]** als u klaar bent en het bevestigingsvenster bekijkt.

   ![segmentgebruik bevestigen](assets/confirm-segment-usage.png)

1. Klik op **[!UICONTROL Confirm]**.

Zie ook onze videodemonstratie van hoe u segment-vlakke gebruik kunt melden:

>[!VIDEO](https://video.tv.adobe.com/v/25522/)

 

## CPM-gebruik rapporteren op het niveau van gegevensfeed {#feed-level-report}

Rapportage op het niveau van gegevensfeed is lastiger en vatbaarder voor fouten, omdat u de gegevens afzonderlijk moet berekenen [!DNL CPM] gebruik voor elke gegevensinvoer. We raden u aan [CPM-gebruik op segmentniveau rapporteren](#segment-level-report) in plaats daarvan.

Rapport [!DNL CPM] gebruik op segmentniveau:

1. Ga naar **[!UICONTROL Audience Marketplace > Payables]**.
2. Selecteer **[!UICONTROL Feed Usage]** tab.
3. Gebruik de [!UICONTROL Search] om de gegevensfeeds te filteren en de feeds te identificeren waarvoor u gebruik moet melden.
4. Klik op **[!UICONTROL Edit Feeds Usage]**.
5. De [!DNL CPM] gebruik voor elke gegevensinvoer op basis van de [Kostentoerekeningswaarde voor CPM-gegevensfeeds](#cost-attribution)en voert u deze in in het dialoogvenster [!UICONTROL Usage] kolom.
6. Klikken **[!UICONTROL Save]** als u klaar bent en het bevestigingsvenster bekijkt.

   ![bevestiging van het gebruik van diervoeders](assets/confirm-feed-usage.png)

7. Klik op **[!UICONTROL Confirm]**.

<br>

## Bulkrapportage

Fouten en overhead tijdens de rapportage verminderen [!DNL CPM] gebruik, kunt u de bulkrapporteringsoptie gebruiken om een [!DNL CSV] bestand met de gegevensfeeds en -segmenten, vult het gebruik in en uploadt het terug naar [!DNL Audience Manager]. U kunt bulkrapportering gebruiken om zowel voer als segmentgebruik te melden.

Bijwerken [!DNL CPM] bulkgebruik:

1. Ga naar **[!UICONTROL Audience Marketplace > Payables]**.
1. Selecteer **[!UICONTROL Feed Usage]** of **[!UICONTROL Segment Usage]** , afhankelijk van het type rapportage dat u wilt bijwerken.
1. Klikken **[!UICONTROL Edit Feeds Usage]** of **[!UICONTROL Edit Segments Usage]**.
1. Klikken **[!UICONTROL download the current usage]** om ervoor te zorgen dat u een geldig CSV-bestand gebruikt.
1. Open het bestand op uw computer en vul het gebruiksrapport in.
1. Klikken **[!UICONTROL Choose a CSV file]** om het bijgewerkte gebruiksrapport te uploaden.

   ![usage-report-csv](assets/usage-report-csv.png)

1. [!DNL Audience Manager] valideert het bestand zodra u het uploadt en vraagt u of het fouten in het bestand detecteert.

<br>

### Fouten bij validatie van bulkrapportage

| Foutbericht | Beschrijving | Repareren |
| ------------- | -------------| -----|
| Ongeldige invoer | [!DNL Audience Manager] een wijziging in de [!DNL CSV] bestandsschema, zoals ontbrekende kolommen of wijzigingen in kolomtitels. | Wijzig de tabelstructuur niet. |
| Niet gevonden | Voor [!UICONTROL Segment Level Reporting], [!DNL Audience Manager] kan de [!UICONTROL Segment ID] en [!UICONTROL Destination ID] combinatie. Voor [!UICONTROL Feed Level Reporting], [!DNL Audience Manager] kan de [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], en [!UICONTROL Use Case] combinatie. | Voor [!UICONTROL Segment Level Reporting]de geldigheid van de [!UICONTROL Segment ID] en [!UICONTROL Destination ID] combinatie. Voor [!UICONTROL Feed Level Reporting]de geldigheid van de [!UICONTROL Data Provider Name], [!UICONTROL Feed Name], en [!UICONTROL Use Case] combinatie. |
| Dubbele records gevonden | [!DNL Audience Manager] dubbele records met verschillende afbeeldingswaarden gedetecteerd. | Herzie het rapport en zorg ervoor u niet verschillende gebruikswaarden voor het zelfde gegeven of segment meldt. |
| Waarden niet ondersteund | [!DNL Audience Manager] gedetecteerde niet-numerieke waarden in de [!DNL Audience Manager] kolom. | Controleer het rapport en zorg ervoor dat u alleen numerieke waarden opgeeft in het dialoogvenster [!DNL Audience Manager] kolom. |
| Kopteksten voor verplichte velden ontbreken | [!DNL Audience Manager] ontbrekende tabelkoppen voor verplichte velden gevonden. Voor [!UICONTROL Segment Level Reporting]De verplichte velden zijn: [!UICONTROL Segment ID], [!UICONTROL Destination ID]. Voor [!UICONTROL Feed Level Reporting]De verplichte velden zijn: [!UICONTROL Data Provider Name], [!UICONTROL Data Feed Name],  [!UICONTROL Use Case] | Controleer het rapport en zorg ervoor dat er niet met de tabelkoppen is geknoeid. |

>[!NOTE]
>Rijen verwijderen uit de [!DNL CSV] het gebruiksrapport heeft geen invloed op het bestaande gebruiksrapport. [!DNL Audience Manager] alleen de velden verwerkt die in het rapport zijn opgenomen.

<br>

## [!DNL CPM] Beste praktijken melden

<table id="table_E68FA2130D1C495FAB8982DFB6A31FD9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recommendations </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Het totale aantal afdrukken altijd rapporteren</b> </p> </td> 
   <td colname="col2"> <p>Voor CPM-schoktotalen: </p>
   <p> Rapporteer het totale aantal indrukken, zonder decimalen te gebruiken. De Audience Manager berekent automatisch CPM dat op het totale aantal wordt gebaseerd u rapporteert.</p><p>Als u 1.234.567 beelden moet melden, rapporteer het precies zo. U te hoeven niet om het totale aantal beelden door 1.000 te verdelen om CPM te berekenen.</p><p>De reizen die worden gebruikt om uw Web of toepassingsinhoud (de Optimalisering van de Inhoud) te optimaliseren gebruikend hulpmiddelen zoals Adobe Target of een bestemming van de Analyse bijdragen niet tot de totalen van het Gebruik voor CPM plannen. Gegevensleveranciers worden doorgaans gecompenseerd voor de optimalisatie van inhoud met behulp van platte vergoedingsplannen.</p><p>Zie <a href="#cost-attribution">Kostentoerekeningswaarde voor CPM-gegevensfeeds</a> voor meer informatie . </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Aankruisen aan het maandelijkse rapporteringsinterval</b> </p> </td> 
   <td colname="col2"> <p>Het rapportsysteem wordt na de 5e van elke maand gesloten. Als u er niet in slaagt om CPM gebruik tegen dan te melden, moet u dat bedrag aan het rapport voor de volgende maand toevoegen. Stel bijvoorbeeld dat u in oktober 1000 afbeeldingen gebruikt, de rapportdeadline van oktober mist en in november 1000 afbeeldingen gebruikt. In dit geval rapporteert u het totaal voor oktober en november (2000) in december, tussen de eerste en de vijfde.</p><p><b>Tip</b>: U zou altijd moeten proberen om CPM gebruik voor de vorige maand tussen de 1e en 5e dagen van de volgende maand te melden.</p><p>U kunt CPM gebruik zo laat zoals de 5e van de nieuwe kalendermaand melden, maar dit wordt niet geadviseerd. Het melden van CPM gebruik vóór de 5e van elke maand geeft de Audience Manager tijd om de gegevens te controleren en te verwerken.</p> </td>
  </tr> 
 </tbody> 
</table>

<br>

## Kostentoerekeningswaarde voor CPM-gegevensfeeds {#cost-attribution}

In [!UICONTROL Audience Marketplace] u moet de bedragen van de zelfrapportering elke maand, voor elk van uw segmenten. We raden aan om rapportage uit te voeren [!DNL CPM] gebruik op segmentniveau, zodat de kostentoerekening automatisch plaatsvindt.

<!-- marketplace_cpm_billing.xml -->

### Overzicht van facturering {#billing-summary}

U moet [!DNL CPM] de hoeveelheden gegevens die tijdens de eerste tot en met de vijfde dag van elke kalendermaand worden ingevoerd. Om dit correct te doen, adviseren wij u [CPM-gebruik op segmentniveau rapporteren](#segment-level-report).

>[!TIP]
>Wanneer u rapporteert [!DNL CPM] gebruik op segmentniveau, wordt de gegevens input-vlakke rapporteringssectie automatisch ingevuld met de overeenkomstige gebruiksbedragen.

Moet u [!UICONTROL Report CPM Usage at Data Feed Level], moet u alle indrukkingen die in de voorafgaande kalendermaand voor elk diervoeder zijn geleverd individueel compileren, en deze rapporteren volgens de in dit artikel beschreven factureringstoewijzing.

Na uw melding [!DNL CPM] nummer van de vorige kalendermaand; [!DNL Adobe] doet het volgende:

* Maak een factuur op basis van de [!DNL CPM] tarief voor elke geabonneerde gegevensvoer.
* Betaalkosten voor gegevensaanbieders (verkopers) op basis van je berichtgeving [!DNL CPM] gebruik.

>[!IMPORTANT]
>
>Als koper moeten alle gerapporteerde totalen van de indruk waar en nauwkeurig zijn. Als u op de vijfde dag van elke maand geen schattingstotalen rapporteert, moet u totalen voor de niet-aangegeven maand in de volgende maand opnemen.

<br>

## Afbeeldingen toewijzen op voederniveau op basis van de regels voor de handelskwalificatie {#assign-impressions}

De [!UICONTROL Activation] Met de optie use case kunt u eigenschappen gebruiken in de bijbehorende gegevensfeed om segmenten te maken in [Segment Builder](../../../features/segments/segment-builder.md) en wijs die segmenten aan een bestemming toe. Booleaanse operatoren [!UICONTROL AND], [!UICONTROL OR], en [!UICONTROL NOT] laat u de voorwaarden voor eigenschap en segmentkwalificatie plaatsen.

Wanneer u [CPM-gebruik rapporteren op het niveau van gegevensfeed](#feed-level-report), moet u de afbeeldingen proportioneel toewijzen voor elke gegevensinvoer, afhankelijk van de [!DNL Boolean] de exploitanten die in de kwalificatieregels voor de eigenschap worden gebruikt. In de volgende tabel wordt aangegeven hoe u afbeeldingen op de juiste wijze kunt toewijzen door de Booleaanse regel of het type kenmerk.

>[!TIP]
>[CPM-gebruik op segmentniveau rapporteren](#segment-level-report) de gegevensdoorvoerniveaus automatisch door de Audience Manager laten rapporteren.

<table id="table_BF00FE6740D2459DAFA62F2478492586"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Regelkwalificatielogica of -type </th> 
   <th colname="col2" class="entry"> Factureringsverdeling </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> AND</span> </p> </td> 
   <td colname="col2"> <p>Pas 100% van de geleverde beeldtotalen op alle leverancierseigenschappen in een op regels gebaseerd segment toe dat een Booleaanse waarde gebruikt <span class="wintitle"> EN</span> voorwaarde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> OF</span> </p> </td> 
   <td colname="col2"> <p>Pas een gewogen toewijzing van de geleverde beeldtotalen toe op alle leverancierstkenmerken in een op regels gebaseerd segment dat een Booleaanse OF-voorwaarde gebruikt. Gewogen toerekening wordt berekend aan de hand van de volgende formule:</p><p><code>(Trait Population / Segment Population) * Number of Impressions * Cost of CPM</code></p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> NOT</span> </p> </td> 
   <td colname="col2"> <p>Pas 100% van de geleverde beeldtotalen op alle leverancierseigenschappen in een op regels gebaseerd segment toe dat een Booleaanse waarde gebruikt <span class="wintitle"> NOT</span> voorwaarde. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Algoritmische segmenten </p> </td> 
   <td colname="col2"> <p>Pas 100% van de geleverde opmaaktotalen toe op alle providerfeeds in een segment met algoritmische kenmerken. </p> </td> 
  </tr>
 </tbody>
</table>

<br>

## Factureringsvoorbeelden {#billing-examples}

De onderstaande voorbeelden zijn bedoeld om te illustreren hoe [!DNL CPM] de toewijzing van het gebruik gebeurt op het niveau van de gegevenstoevoer.

>[!IMPORTANT]
>We raden u aan [CPM-gebruik op segmentniveau rapporteren](#segment-level-report) in plaats daarvan, om dit proces automatisch te laten doen.

Denk aan het volgende scenario:

![factureringsvoorbeelden](assets/billing-examples.png)

<br>

### Zaak 1: Segmenten met en kwalificatieregels

Dit segment bevat 3 eigenschappen van afzonderlijke gegevensleveranciers. Aangezien segmentkwalificatie is gebaseerd op een [!UICONTROL AND] voorwaarde is dat bezoekers de kenmerken van alle drie de feeds moeten realiseren om in aanmerking te komen voor het segment .

![](assets/billing-segment-and.png)

Met een [!UICONTROL AND] voorwaarde, moet u 100% van de indrukken toewijzen die tijdens de maand aan alle drie gegevensleveranciers worden ontvangen. In de [!UICONTROL Audience Marketplace > Payables] in deze sectie, crediteert u elke provider met 1.000.000 afbeeldingen.

Dit voorbeeld is van toepassing op segmenten die [!DNL Boolean] [!UICONTROL NOT] operatoren of voor segmenten die algoritmische kenmerken bevatten.

<br>

### Zaak 2: Segmenten met OF kwalificatieregels

Dit segment bevat 3 eigenschappen van afzonderlijke gegevensleveranciers. Aangezien segmentkwalificatie is gebaseerd op een [!UICONTROL OR] voorwaarde is dat bezoekers ten minste één van de drie kenmerken moeten realiseren om voor het segment in aanmerking te komen .

We kunnen niet zien welk kenmerk de indruk wekt dat de kwalificatie gebaseerd is op een [!UICONTROL OR] voorwaarde. Dientengevolge, in [!UICONTROL Audience Marketplace > Payables] afdeling u crediteert elke leverancier met een gewogen toerekening van de totale indrukken, op basis van de populatie van trekkers.

![factureringssegment-of](assets/billing-segment-or.png)

<br>

### Zaak 3: Segmenten met Gebruiksscenario&#39;s voor modellering en activering

In dit voorbeeld wordt de attributie beschreven op basis van twee Data Feed-gebruiksgevallen - Modellering en activering. In het voorbeeld bekijken we twee gegevensleveranciers, met de volgende informatie:

![gegevensinvoer](assets/feed-use-cases.png)

In de onderstaande tabel bevat segment X twee kenmerken, T1 en T2, met segmentregel T1 OF T2, waarbij:

* T1 een kenmerk is van gegevensfeed A;
* T2 is een algoritmische eigenschap die is gemodelleerd na derderdekenmerken van Data Feed A en Data Feed B.

Het segment wordt in kaart gebracht aan een bestemming en 1.000.000 beelden zijn ingegaan voor dit segment in een maand, gebruikend [Rapportage op segmentniveau](#segment-level-report).

Van deze 1.000.000 beelden:

* T1 vertegenwoordigt 40% van de segmentpopulatie, wat neerkomt op 400.000 indrukkingen voor Feed A.
* T2 is goed voor 60% van de segmentpopulatie, wat overeenkomt met 600.000 indrukkingen voor Feed A en Feed B.

Op het niveau van de gegevensvoer, is de manier de indrukkingen worden toegewezen:

* Gegevensfeed A ontvangt 600.000 impressies van kenmerk T2 (dat is gebaseerd op kenmerken van gegevens Feed A en gegevensfeed B, zodat beide de indrukken ontvangen) en 400.000 impressies van kenmerk T1 (dat een kenmerk is van gegevensfeed A), in totaal 1.000.000 impressies pressies.
* Gegevensfeed B ontvangt 600.000 impressies van kenmerk T2 (zie bovenstaande toelichting) en 0 impressies van kenmerk T1.

De uitsplitsing in één oogopslag per gegevenstoevoer en gebruikscase is als volgt:

![uitsplitsing naar diervoeder](assets/feed-breakdown-alt.png)

>[!NOTE]
>
>Voor het modelleringsgebruik, zou u CPM gebruik bij activering slechts moeten melden. Als u alleen een model uitvoert maar dit niet activeert, is er geen gebruiksrapportage vereist.

<br>

## Facturerings- en impressietoewijzing voor gegevens met vaste kosten {#billing-flat-fee}

Bij een vaste vergoeding voor de gegevens in de feed wordt u elke maand een vast bedrag aangerekend, ongeacht wanneer het abonnement wordt gestart of hoeveel indrukken u gebruikt. De kosten worden niet geprorgeerd voor gedeeltelijk maandgebruik of intervallen. Net als bij CPM-facturering zal Adobe een factuur genereren en u factureren tegen het maandelijkse, vaste tarief voor uw geabonneerde gegevensfeeds.

Stel bijvoorbeeld dat je bepaalde eigenschappen in een voer in het midden van de maand wilde inschakelen. Je krijgt nog steeds de volledige, maandelijkse factuur, ongeacht wanneer je het abonnement hebt gestart of specifieke aanbiedingen hebt geactiveerd.
