---
description: Bouw en beheer de eigenschappen of de segmenten die in blik-gelijkaardige modellering worden gebruikt.
keywords: relative weight, lookalike
seo-description: Bouw en beheer de eigenschappen of de segmenten die in blik-gelijkaardige modellering worden gebruikt.
seo-title: Over look-Alike modellering
solution: Audience Manager
title: Over look-Alike modellering
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
translation-type: tm+mt
source-git-commit: a6e8db30c54e0629e27b1ee7f189a6c471d2bb6d

---


# Understanding Look-Alike modellering {#about-algorithmic-models}

## Nieuwe gebruikers zoeken met look-Alike modellering {#find-new-users}

[!UICONTROL Look-Alike Modeling] helpt u nieuwe, unieke doelgroepen te ontdekken via geautomatiseerde gegevensanalyse. Het proces begint wanneer u een eigenschap of een segment, een tijdinterval, en eerste en derde gegevensbronnen selecteert. Uw keuzen verstrekken de input voor het algoritmische model. Wanneer het analyseproces loopt, zoekt het naar in aanmerking komende gebruikers die op gedeelde kenmerken van de geselecteerde bevolking worden gebaseerd. Na voltooiing zijn deze gegevens beschikbaar in [Trait Builder](../../features/traits/about-trait-builder.md) , waar u deze kunt gebruiken om kenmerken te maken op basis van [nauwkeurigheid en bereik](../../features/traits/trait-accuracy-reach.md). Daarnaast kunt u segmenten maken die algoritmische kenmerken combineren met op regels gebaseerde kenmerken en andere kwalificatievereisten toevoegen met Booleaanse expressies en vergelijkingsoperatoren. [!UICONTROL Look-Alike Modeling] biedt u een dynamische manier om waarde uit al uw beschikbare gegevens van het bezit te halen.

## Voordelen {#advantages}

De belangrijkste voordelen van het gebruik [!UICONTROL Look-Alike Modeling] zijn:

* **Nauwkeurigheid van gegevens:** Het algoritme wordt regelmatig uitgevoerd, waardoor de resultaten actueel en relevant blijven.
* **Automatisering:** U moet geen grote reeks statische regels beheren. Het algoritme zal publiek voor u vinden.
* **Bespaar tijd en verminder uw inspanningen:** Met ons modelleringsproces hoeft u niet te raden welke traits/segmenten kunnen werken of tijdbronnen aan campagnes kunnen besteden om nieuwe doelgroepen te ontdekken. Het model kan dit voor u doen.
* **Betrouwbaarheid:** Modellering werkt met detectie- en kwalificatieprocessen aan de serverzijde die uw eigen gegevens en geselecteerde gegevens van derden evalueren waartoe u toegang hebt. Dit betekent dat u de bezoekers op uw site niet hoeft te zien om ze in aanmerking te laten komen voor een kenmerk.

## Workflow {#workflow}

U beheert modellen in **[!UICONTROL Audience Data > Models]**. Op hoog niveau omvat het workflowproces het volgende:

* Selecteer de basislijngegevens die door het algoritme moeten worden geëvalueerd. Dit omvat een eigenschap of een segment, tijdwaaier, en gegevensbronnen (uw eigen gegevens en derdegegevens u reeds toegang tot door [!DNL Audience Manager]) hebt. In de workflow voor het maken van modellen kunt u de kenmerken uitsluiten die u niet wilt beïnvloeden in uw model.
* Sla uw model op. Zodra bewaard, loopt het algoritmische evaluatieproces automatisch uit. Het kan echter tot 7 dagen duren voordat dit proces is voltooid. [!DNL Audience Manager] Hiermee stuurt u een e-mail wanneer het algoritme is voltooid en de resultaten beschikbaar zijn voor het maken van de eigenschap.
* Met algoritmische kenmerken inbouwen [!UICONTROL Trait Builder].
* Verhoudingen combineren tot segmenten in [!UICONTROL Segment Builder].
* Creeer en verzend segmentgegevens naar een bestemming.

## Problemen oplossen {#troubleshooting}

Wij deactiveren om het even [!UICONTROL Look-Alike Model] die er niet in slaagt om gegevens voor drie opeenvolgende looppas te produceren. U kunt de status van het model niet instellen op actief achteraf. Om ervoor te zorgen dat uw modellen gegevens genereren, raden we u aan modellen te maken van gegevensbronnen met voldoende kenmerken om gegevens uit te verzamelen.

## TraitWeight begrijpen {#understanding-traitweight}

[!UICONTROL TraitWeight] is een merkgebonden algoritme dat wordt ontworpen om nieuwe eigenschappen automatisch te ontdekken. Het vergelijkt reisgegevens van uw huidige eigenschappen en segmenten met alle andere eerste en derdegegevens die u tot door hebt toegang [!DNL Audience Manager]. Zie deze sectie voor een beschrijving van het [!UICONTROL TraitWeight] algoritmische-detectieproces.

<!-- traitweight.xml -->

![](assets/algo_model.png)

In de volgende stappen wordt het [!UICONTROL TraitWeight] evaluatieproces beschreven.

### Stap 1: Bouw een Basislijn voor Vergelijking van het Beetje

Om een basislijn te bouwen, [!UICONTROL TraitWeight] meet alle eigenschappen verbonden aan een publiek voor een interval van 30, 60, of 90 dagen. Vervolgens worden de kenmerken gerangschikt op basis van hun frequentie en correlatie. De frequentietelling meet de uniformiteit. Correlatie meet de waarschijnlijkheid dat een eigenschap alleen in het basispubliek aanwezig is. Vaak worden traits met een hoge standaardisering genoemd. Dit is een belangrijk kenmerk dat wordt gebruikt om een gewogen score in te stellen in combinatie met kenmerken die worden ontdekt in de geselecteerde gegevensbronnen.

### Stap 2: Dezelfde kenmerken zoeken in de gegevensbron

Nadat het een basislijn voor vergelijking bouwt, zoekt het algoritme identieke eigenschappen in uw geselecteerde gegevensbronnen. In deze stap [!UICONTROL TraitWeight] voert een frequentietelling uit van alle ontdekte kenmerken en vergelijkt deze met de basislijn. In tegenstelling tot de basislijn zijn ongebruikelijke kenmerken echter gerangschikt boven die welke vaker voorkomen. Zeldzame kenmerken zouden een hoge mate van specificiteit vertonen. [!UICONTROL TraitWeight] beschouwt combinaties van gemeenschappelijke basislijnkenmerken en ongewone (zeer specifieke) gegevensbronkenmerken als invloedrijker of wenselijker dan de kenmerken die beide gegevenssets gemeen hebben. In feite erkent ons model deze grote, gemeenschappelijke kenmerken en kent het geen bovenmatige prioriteit toe aan gegevenssets met hoge correlaties. Zeldzame doelen krijgen een hogere prioriteit omdat ze meer kans maken nieuwe, unieke gebruikers te vertegenwoordigen dan tradities met een hoge standaardisering over de hele linie.

### Stap 3: Gewicht toewijzen

In deze stap [!UICONTROL TraitWeight] worden pas ontdekte kenmerken gerangschikt in volgorde van invloed of wenselijkheid. De weegschaal is een percentage dat loopt van 0% tot 100%. Traits gerangschikt dichter bij 100% betekent dat ze meer lijken op het publiek in je basispopulatie. Ook, zijn de zwaar gewogen eigenschappen waardevol omdat zij nieuwe, unieke gebruikers vertegenwoordigen die zich aan uw gevestigd, basislijnpubliek kunnen gedragen. Herinner me, [!UICONTROL TraitWeight] beschouwt de eigenschappen met hoge gemeenschappelijk in de basislijn en hoge specificiteit in de vergeleken gegevensbronnen als waardevoller dan eigenschappen gemeenschappelijk in elke gegevensreeks.

### Stap 4: Scoregebruikers

Elke gebruiker in de geselecteerde gegevensbronnen krijgt een gebruikersscore die gelijk is aan de som van alle gewichten van de invloedrijke kenmerken in het profiel van die gebruiker. De scores van de gebruiker worden dan genormaliseerd tussen 0 en 100%.

### Stap 5: Weergeven en werken met resultaten

Audience Manager geeft de gewogen modelresultaten weer in [!UICONTROL Trait Builder]. Wanneer u een algoritmische eigenschap wilt bouwen, [!UICONTROL Trait Builder] laat u eigenschappen tot stand brengen die op de gewogen score worden gebaseerd door het algoritme tijdens een gegevenslooppas wordt geproduceerd. U kunt een hogere nauwkeurigheid kiezen om alleen gebruikers te kwalificeren die zeer hoge gebruikersscores hebben en daarom zeer gelijkaardig aan het basislijnpubliek, eerder dan de rest van het publiek zijn. Als u een groter publiek (bereik) wilt bereiken, kunt u de nauwkeurigheid verminderen.

### Stap 6: De betekenis van een trein over verwerkingscycli opnieuw evalueren

Periodiek [!UICONTROL TraitWeight] herevalueert het belang van een eigenschap op basis van de omvang en de verandering van de populatie van die eigenschap. Dit gebeurt wanneer het aantal gebruikers dat voor dat kenmerk in aanmerking komt, na verloop van tijd toeneemt of afneemt. Dit gedrag is het duidelijkst zichtbaar in eigenschappen die erg groot worden. Stel dat het algoritme bijvoorbeeld kenmerk A gebruikt voor modellering. Naarmate de populatie van kenmerk A toeneemt, [!UICONTROL TraitWeight] herbeoordeelt u het belang van dat kenmerk en wijst u een lagere score toe of negeert u deze. In dit geval is eigenschap A te algemeen of te groot om iets belangrijks over zijn bevolking te zeggen. Nadat de waarde van Trait A is [!UICONTROL TraitWeight] verminderd (of in het model wordt genegeerd), neemt de populatie van de algoritmische eigenschap af. De lijst van invloedrijke kenmerken weerspiegelt de ontwikkeling van de basispopulatie. Gebruik de lijst van de invloedrijke eigenschappen om te begrijpen waarom deze veranderingen voorkomen.

Verwante koppelingen:

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [Nauwkeurigheid en Bereik](../../features/traits/trait-accuracy-reach.md)

## Plan voor look-Alike modellen en Traits bijwerken {#update-schedule}

Planning voor het maken en bijwerken van nieuwe of bestaande algoritmische modellen en kenmerken.

<!-- c_model_update_schedule.xml -->

### Model maken en plannen bijwerken, vergelijkbaar met vormgeving

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
     </ul> </p> <p>Modellen die na de aanmaakdeadline zijn gemaakt of gekloond, worden de volgende dag verwerkt. </p> <p>Als de eerste looppas van een model geen gegevens produceert zal het een tweede keer, de volgende dag in werking stellen. Als de tweede poging ook geen gegevens produceert, zal er een derde poging, de volgende dag zijn. Het model zal ophouden lopend als de derde poging ook geen gegevens produceert. In dit geval deactiveren we het model. Zie meer in het Oplossen van <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Problemen kijkt-naar Modellen</a>. </p> </td>
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

### Plan voor het maken en bijwerken van trajecten

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

## Modellen-lijstweergave {#models-list-view}

De lijstmening is een centrale werkruimte die u helpt om modellen tot stand te brengen, te herzien en te beheren.

<!-- c_models_list_view.xml -->

De pagina Modellen-lijst bevat functies en gereedschappen die u helpen:

* Nieuwe modellen maken.
* Bestaande modellen beheren (bewerken, pauzeren, verwijderen of klonen).
* Zoek naar modellen door naam.
* Met een bepaald model kunt u algoritmische kenmerken maken.

## Modellen - overzichtsweergave {#models-summary-view}

Op de overzichtspagina worden modeldetails weergegeven, zoals naam, bereik/nauwkeurigheid, verwerkingsgeschiedenis en kenmerken die op basis van het model zijn gemaakt. De pagina bevat ook instellingen waarmee u modellen kunt maken en beheren. Klik op een modelnaam in de overzichtslijst om de details weer te geven.

<!-- c_models_summary.xml -->

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
   <td colname="col2"> <p>Toont <a href="../../features/traits/trait-accuracy-reach.md"> nauwkeurigheid en bereikgegevens</a> voor de laatste modellooppas. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Verwerkingsgeschiedenis model</span> </p> </td> 
   <td colname="col2"> <p>Toont de verwerkingsdatum en de tijd voor de laatste 10 looppas en of de gegevens op die looppas werden geproduceerd. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Influente sporen</span> </p> </td> 
   <td colname="col2"> <p>De tabel <span class="wintitle"> Influential Traits</span> : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Vermeldt de bovenste 50 invloedrijke kenmerken die het best worden vertegenwoordigd in de basislijnpopulatie van het model. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Draait elk kenmerk in volgorde van de <span class="wintitle"> relatieve positie van gewicht</span> . Met <span class="wintitle"> Relatief gewicht</span> sorteert u pas ontdekte kenmerken in volgorde van invloed of wenselijkheid. De weegschaal is een percentage dat loopt van 0% tot 100%. Traits gerangschikt dichter bij 100% betekent dat ze meer lijken op het publiek in je basispopulatie. Zie <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> TraitWeight</a>begrijpen. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Toont de uniques van 30 dagen en de totale populatie van eigenschappen voor elk kenmerk. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Treits met model</span> </p> </td>
   <td colname="col2"> <p>Toont een lijst van de algoritmische eigenschappen die op het geselecteerde model worden gebaseerd. Klik op de naam van een kenmerk of de handels-id voor meer informatie over de eigenschap. Selecteer <b><span class="uicontrol"> Nieuwe eigenschap maken met model</span></b> om naar het maken van de algoritmische eigenschap te gaan. </p> <p>De veranderingen van het sectielabel die op de naam van uw model worden gebaseerd. Stel dat u een model maakt en dit model modelnaam geeft. Wanneer u de overzichtspagina laadt, wordt de naam van deze sectie veranderd in <span class="wintitle"> Traits Gebruikend Model A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Doelen](../../features/destinations/destinations.md)
>* [Treinen](../../features/traits/trait-details-page.md)
>* [Segmenten](../../features/segments/segments-purpose.md)

