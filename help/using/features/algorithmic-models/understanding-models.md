---
description: Bouw en beheer de eigenschappen of de segmenten die in blik-gelijkaardige modellering worden gebruikt.
keywords: relative weight, lookalike
seo-description: Bouw en beheer de eigenschappen of de segmenten die in blik-gelijkaardige modellering worden gebruikt.
seo-title: Over look-Alike modellering
solution: Audience Manager
title: Over look-Alike modellering
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1590'
ht-degree: 0%

---


# [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Nieuwe gebruikers zoeken met [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] helpt u nieuwe, unieke doelgroepen te ontdekken via geautomatiseerde gegevensanalyse. Het proces begint wanneer u [!UICONTROL trait] of [!UICONTROL segment], een tijdinterval selecteert, en eerste en derde [!UICONTROL data sources]. Uw keuzen verstrekken de input voor het algoritmische model. Wanneer het analyseproces loopt, zoekt het naar in aanmerking komende gebruikers die op gedeelde kenmerken van de geselecteerde bevolking worden gebaseerd. Na voltooiing, zijn deze gegevens beschikbaar in [Trait Builder](../../features/traits/about-trait-builder.md) waar u het kunt gebruiken om eigenschappen tot stand te brengen die op [nauwkeurigheid en bereik](../../features/traits/trait-accuracy-reach.md) worden gebaseerd. Daarnaast kunt u segmenten samenstellen die algoritmische kenmerken combineren met [!UICONTROL rules-based traits] en andere kwalificatievereisten toevoegen met [!DNL Boolean]-expressies en vergelijkingsoperatoren. [!UICONTROL Look-Alike Modeling] biedt u een dynamische manier om waarde uit al uw beschikbare gegevens van het bezit te halen.

## Voordelen {#advantages}

De belangrijkste voordelen van het gebruik van [!UICONTROL Look-Alike Modeling] zijn:

* **Gegevensnauwkeurigheid:** het algoritme wordt regelmatig uitgevoerd, waardoor de resultaten actueel en relevant blijven.
* **Automatisering:** u moet geen grote reeks statische regels beheren. Het algoritme zal publiek voor u vinden.
* **Bespaar tijd en minder moeite:** met ons modelleringsproces hoeft u niet te raden wat  [!UICONTROL traits]/[!UICONTROL segments] kan werken of tijd te besteden aan campagnes om nieuwe doelgroepen te ontdekken. Het model kan dit voor u doen.
* **Betrouwbaarheid:** Modellering werkt met detectie- en kwalificatieprocessen aan de serverzijde die uw eigen gegevens en geselecteerde gegevens van derden evalueren waartoe u toegang hebt. Dit betekent dat u de bezoekers op uw site niet hoeft te zien om ze in aanmerking te laten komen voor een kenmerk.

## Workflow {#workflow}

U beheert modellen in **[!UICONTROL Audience Data > Models]**. Op hoog niveau omvat het workflowproces het volgende:

* Selecteer de basislijngegevens die door het algoritme moeten worden geëvalueerd. Dit omvat een [!UICONTROL trait] of [!UICONTROL segment], tijdwaaier, en [!UICONTROL data sources] (uw eigen gegevens en derdegegevens u reeds toegang tot door [!DNL Audience Manager] hebt). In het werkschema van de modelverwezenlijking, kunt u [!UICONTROL traits] uitsluiten die u niet met uw model wilt interfereren.
* Sla uw model op. Zodra bewaard, loopt het algoritmische evaluatieproces automatisch uit. Het kan echter tot 7 dagen duren voordat dit proces is voltooid. [!DNL Audience Manager] verzendt u een e-mail wanneer het algoritme heeft gebeëindigd en de resultaten voor  [!UICONTROL trait] verwezenlijking beschikbaar zijn.
* Bouw algoritmisch [!UICONTROL traits] in [!UICONTROL Trait Builder].
* Combineer [!UICONTROL traits] tot [!UICONTROL segments] in [!UICONTROL Segment Builder].
* [!UICONTROL segment] gegevens maken en verzenden naar een [!UICONTROL destination].

## Problemen oplossen {#troubleshooting}

[!UICONTROL Look-Alike Model] die er niet in slagen gegevens te genereren voor drie opeenvolgende uitvoeringen, wordt gedeactiveerd. U kunt de status van het model niet instellen op actief achteraf. Om ervoor te zorgen dat uw modellen gegevens genereren, raden we u aan modellen te maken van gegevensbronnen met voldoende [!UICONTROL traits] om gegevens op te nemen.

## [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] is een merkgebonden algoritme dat wordt ontworpen om nieuw  [!UICONTROL traits] automatisch te ontdekken. De [!UICONTROL trait] gegevens van uw huidige [!UICONTROL traits] en [!UICONTROL segments] tegen alle andere eerste en derdegegevens vergelijkt die u tot door [!DNL Audience Manager] hebt toegang. Zie deze sectie voor een beschrijving van het algoritmische detectieproces [!UICONTROL TraitWeight].

![](assets/algo_model.png)

De volgende stappen beschrijven het [!UICONTROL TraitWeight] evaluatieproces.

### Stap 1: Een basislijn maken voor [!UICONTROL Trait]-vergelijking

Om een basislijn te bouwen, [!UICONTROL TraitWeight] meet al [!UICONTROL traits] verbonden aan een publiek voor een interval van 30, 60, of 90 dagen. Vervolgens wordt [!UICONTROL traits] gerangschikt op basis van hun frequentie en correlatie. De frequentietelling meet de uniformiteit. Correlatie meet de waarschijnlijkheid dat een [!UICONTROL trait] alleen in het basislijnpubliek aanwezig is. [!UICONTROL Traits] vaak wordt gezegd dat ze een hoge mate van gemeenschappelijkheid vertonen , een belangrijk kenmerk dat wordt gebruikt om een gewogen score in te stellen wanneer deze wordt gecombineerd met een kenmerk dat in uw selectie wordt  [!UICONTROL traits] ontdekt  [!UICONTROL data sources].

### Stap 2: Hetzelfde [!UICONTROL Traits] vinden in [!UICONTROL Data Source]

Nadat het een basislijn voor vergelijking bouwt, zoekt het algoritme identieke [!UICONTROL traits] in uw geselecteerde [!UICONTROL data sources]. In deze stap voert [!UICONTROL TraitWeight] een frequentietelling uit van alle ontdekte [!UICONTROL traits] en vergelijkt hen met de basislijn. In tegenstelling tot de basislijn, worden ongewone [!UICONTROL traits] gerangschikt hoger dan die die vaker verschijnen. Zelden [!UICONTROL traits] zouden een hoge mate van specificiteit vertonen. [!UICONTROL TraitWeight] worden combinaties van gemeenschappelijke basislijn  [!UICONTROL traits] en soms (zeer specifiek) beoordeeld  [!UICONTROL data source] [!UICONTROL traits] als invloedrijker of wenselijker dan  [!UICONTROL traits] gemeenschappelijk voor beide gegevenssets. In feite erkent ons model deze grote, gemeenschappelijke [!UICONTROL traits] en wijst geen bovenmatige prioriteit toe aan gegevensreeksen met hoge correlaties. Zeldzame [!UICONTROL traits] krijgt hogere prioriteit omdat zij meer waarschijnlijk nieuwe, unieke gebruikers dan [!UICONTROL traits] met hoge gemeenschappelijk over de hele linie vertegenwoordigen.

### Stap 3: Gewicht toewijzen

In deze stap rangschikt [!UICONTROL TraitWeight] pas ontdekte [!UICONTROL traits] in volgorde van invloed of wenselijkheid. De weegschaal is een percentage dat loopt van 0% tot 100%. [!UICONTROL Traits] gerangschikt naar 100% betekent dat ze meer lijken op het publiek in je basispopulatie. Ook, zijn zwaar gewogen [!UICONTROL traits] waardevol omdat zij nieuwe, unieke gebruikers vertegenwoordigen die zich gelijkaardig aan uw gevestigd, basislijnpubliek kunnen gedragen. [!UICONTROL TraitWeight] beschouwt [!UICONTROL traits] met een hoge mate van gemeenschappelijkheid in de basislijn en hoge specificiteit in de vergeleken gegevensbronnen als waardevoller dan [!UICONTROL traits] gemeenschappelijk in elke gegevensreeks.

### Stap 4: Scoregebruikers

Elke gebruiker in de geselecteerde [!UICONTROL data sources] krijgt een gebruikersscore die gelijk is aan de som van alle gewichten van de invloedrijke [!UICONTROL traits] in het profiel van die gebruiker. De scores van de gebruiker worden dan genormaliseerd tussen 0 en 100%.

### Stap 5: Weergeven en werken met resultaten

[!DNL Audience Manager] geeft de gewogen modelresultaten weer in  [!UICONTROL Trait Builder]. Wanneer u een [!UICONTROL algorithmic trait] wilt bouwen, [!UICONTROL Trait Builder] laat u [!UICONTROL traits] creëren gebaseerd op de gewogen score die door het algoritme tijdens een gegevenslooppas wordt geproduceerd. U kunt een hogere nauwkeurigheid kiezen om alleen gebruikers te kwalificeren die zeer hoge gebruikersscores hebben en daarom zeer gelijkaardig aan het basislijnpubliek, eerder dan de rest van het publiek zijn. Als u een groter publiek (bereik) wilt bereiken, kunt u de nauwkeurigheid verminderen.

### Stap 6: De betekenis van een [!UICONTROL Trait] voor alle verwerkingscycli opnieuw evalueren

Op basis van de omvang en de verandering in de populatie van [!UICONTROL trait] wordt het belang van een [!UICONTROL TraitWeight] periodiek opnieuw beoordeeld. [!UICONTROL trait] Dit gebeurt als het aantal gebruikers dat voor dat [!UICONTROL trait] wordt gekwalificeerd in de loop der tijd toeneemt of afneemt. Dit gedrag is het duidelijkst zichtbaar in kenmerken die erg groot worden. Stel dat het algoritme [!UICONTROL trait A] gebruikt voor modellering. Als de populatie van [!UICONTROL trait A] stijgt, herevalueert [!UICONTROL TraitWeight] het belang van dat [!UICONTROL trait] en kan een lagere score toewijzen of het negeren. In dit geval is [!UICONTROL trait A] te algemeen of te groot om iets belangrijks over zijn bevolking te zeggen. Nadat [!UICONTROL TraitWeight] de waarde van [!UICONTROL trait A] (of het negeert in het model) vermindert, vermindert de bevolking van het algoritmische bezit. De lijst van invloedrijke [!UICONTROL traits] weerspiegelt de evolutie van de basispopulatie. Gebruik de lijst van invloedrijke [!UICONTROL traits] om te begrijpen waarom deze veranderingen voorkomen.

Verwante koppelingen:

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [Nauwkeurigheid en bereik](../../features/traits/trait-accuracy-reach.md)

## Plan voor [!UICONTROL Look-Alike Models] en [!UICONTROL Traits] {#update-schedule} bijwerken

Planning voor het maken en bijwerken van nieuwe of bestaande [!UICONTROL algorithmic models] en [!UICONTROL traits].

### [!UICONTROL Look-Alike Model] Planning maken en bijwerken

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Type activiteit </th>
   <th colname="col2" class="entry"> Beschrijving </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b>Een model maken of klonen</b> </td>
   <td colname="col2"> <p>Voor nieuwe of gekloonde [!UICONTROL look-Alike Models], loopt het aanmaakproces eenmaal per dag bij: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (november - maart) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (maart - november) </li> 
     </ul> </p> <p>Modellen die na de aanmaakdeadline zijn gemaakt of gekloond, worden de volgende dag verwerkt. </p> <p>Als de eerste looppas van een model geen gegevens produceert zal het een tweede keer, de volgende dag in werking stellen. Als de tweede poging ook geen gegevens produceert, zal er een derde poging, de volgende dag zijn. Het model zal ophouden lopend als de derde poging ook geen gegevens produceert. In dit geval deactiveren we het model. Zie meer in <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> het Oplossen van problemen kijkt-als Modellen</a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b>Een model bijwerken</b> </td> 
   <td colname="col2"> <p>Onder ideale omstandigheden lopen bestaande modellen op weekdagen, minstens om de 7 dagen. Als u bijvoorbeeld een model maakt (tegen de deadline) op maandag, wordt de volgende maandag bijgewerkt. </p> <p>Een model wordt opnieuw uitgevoerd als het aan een van de volgende voorwaarden voldoet: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">De laatste uitvoering is mislukt. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Het is gelukt vóór EN het heeft de afgelopen 7 dagen helemaal niet gewerkt EN het model heeft minstens één actief kenmerk eraan gekoppeld. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] Planning maken en bijwerken

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type activiteit </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b>Een overtrek maken</b> </td> 
   <td colname="col2"> <p>Het proces voor het maken van sporen wordt elke dag uitgevoerd, van maandag tot en met vrijdag. Over het algemeen worden nieuwe algoritmische kenmerken binnen 48 uur weergegeven in de gebruikersinterface. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>Een spoor bijwerken</b> </td> 
   <td colname="col2"> <p>Bestaande kenmerken worden ten minste om de 7 dagen bijgewerkt en volgen het schema voor modelupdates. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modellen lijstweergave {#models-list-view}

De lijstmening is een centrale werkruimte die u helpt om modellen tot stand te brengen, te herzien en te beheren.

De lijstpagina [!UICONTROL Models] bevat functies en gereedschappen die u helpen:

* Nieuwe modellen maken.
* Bestaande modellen beheren (bewerken, pauzeren, verwijderen of klonen).
* Zoek naar modellen door naam.
* Maak [!UICONTROL algorithmic traits] met een bepaald model.

## Modellen - overzicht {#models-summary-view}

Op de overzichtspagina worden modeldetails weergegeven, zoals naam, bereik/nauwkeurigheid, verwerkingsgeschiedenis en [!UICONTROL traits] die op basis van het model zijn gemaakt. De pagina bevat ook instellingen waarmee u modellen kunt maken en beheren. Klik op een modelnaam in de overzichtslijst om de details weer te geven.

De overzichtspagina van het model bevat de volgende secties.

<table id="table_14AE8B324115442589E3F993101F72EA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sectie </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr>
   <td colname="col1"> <p> <span class="wintitle"> Basisinformatie</span> </p> </td>
   <td colname="col2"> <p>Deze groep bevat basisinformatie over het model, zoals de naam en het tijdstip waarop het voor het laatst is uitgevoerd. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Model Bereik en nauwkeurigheid</span> </p> </td> 
   <td colname="col2"> <p>Toont <a href="../../features/traits/trait-accuracy-reach.md"> nauwkeurigheid en bereik</a> gegevens voor de laatste modellooppas. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Verwerkingsgeschiedenis model</span> </p> </td> 
   <td colname="col2"> <p>Toont de verwerkingsdatum en de tijd voor de laatste 10 looppas en of de gegevens op die looppas werden geproduceerd. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Influente sporen</span> </p> </td> 
   <td colname="col2"> <p>De tabel <span class="wintitle"> Influential Traits</span>: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Vermeldt de bovenste 50 invloedrijke kenmerken die het best worden vertegenwoordigd in de basislijnpopulatie van het model. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Hiermee wordt elk kenmerk gerangschikt in volgorde van de rangorde <span class="wintitle"> Relatief gewicht</span>. Met <span class="wintitle"> Relatief gewicht</span> sorteert u pas ontdekte kenmerken in volgorde van invloed of wenselijkheid. De weegschaal is een percentage dat loopt van 0% tot 100%. Traits gerangschikt dichter bij 100% betekent dat ze meer lijken op het publiek in je basispopulatie. Zie <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Understanding TraitWeight</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Toont de uniques van 30 dagen en de totale populatie van eigenschappen voor elk kenmerk. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Treits met model</span> </p> </td>
   <td colname="col2"> <p>Toont een lijst van de algoritmische eigenschappen die op het geselecteerde model worden gebaseerd. Klik op de naam van een kenmerk of de handels-id voor meer informatie over de eigenschap. Selecteer <b><span class="uicontrol"> Nieuwe eigenschap maken met model</span></b> om naar het proces voor het maken van algoritmische kenmerken te gaan. </p> <p>De veranderingen van het sectielabel die op de naam van uw model worden gebaseerd. Stel dat u een model maakt en dit model modelnaam geeft. Wanneer u de overzichtspagina laadt, wordt de naam van deze sectie veranderd in <span class="wintitle"> Beelden die Model A</span> gebruiken. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Bestemmingen ](../../features/destinations/destinations.md)
>* [Eigenschappen ](../../features/traits/trait-details-page.md)
>* [Segmenten ](../../features/segments/segments-purpose.md)

