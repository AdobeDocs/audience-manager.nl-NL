---
description: Bouw en beheer de eigenschappen of de segmenten die in blik-gelijkaardige modellering worden gebruikt.
keywords: relatief gewicht, look-kalike
seo-description: Build and manage the traits or segments used in look-alike modeling.
seo-title: About Look-Alike Modeling
solution: Audience Manager
title: Over look-Alike modellering
uuid: 39441e72-5316-453d-9aff-0e0b633aabcd
feature: Algorithmic Models
exl-id: a24b11ce-6087-4095-a6c2-6815e2211ba5
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '1602'
ht-degree: 0%

---

# Werken met [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Nieuwe gebruikers zoeken met [!UICONTROL Look-Alike Modeling] {#find-new-users}

Met [!UICONTROL Look-Alike Modeling] kunt u nieuwe, unieke doelgroepen detecteren via geautomatiseerde gegevensanalyse. Het proces wordt gestart wanneer u een [!UICONTROL trait] of [!UICONTROL segment] , een tijdinterval en een eerste en een derde [!UICONTROL data sources] selecteert. Uw keuzen verstrekken de input voor het algoritmische model. Wanneer het analyseproces loopt, zoekt het naar in aanmerking komende gebruikers die op gedeelde kenmerken van de geselecteerde bevolking worden gebaseerd. Op voltooiing, is dit gegeven beschikbaar in [ Trait Builder ](../../features/traits/about-trait-builder.md) waar u het kunt gebruiken om eigenschappen tot stand te brengen die op [ worden gebaseerd nauwkeurigheid en bereik ](../../features/traits/trait-accuracy-reach.md). Daarnaast kunt u segmenten maken die algoritmische kenmerken combineren met [!UICONTROL rules-based traits] en andere kwalificatievereisten toevoegen met [!DNL Boolean] -expressies en vergelijkingsoperatoren. [!UICONTROL Look-Alike Modeling] biedt u een dynamische manier om waarde te extraheren uit al uw beschikbare gegevens over de eigenschap.

## Voordelen {#advantages}

De belangrijkste voordelen van het gebruik van [!UICONTROL Look-Alike Modeling] zijn:

* **de nauwkeurigheid van Gegevens:** de algoritmelooppas regelmatig, die hulp huidige en relevante resultaten houdt.
* **Automatisering:** u moet geen grote reeks statische regels beheren. Het algoritme zal publiek voor u vinden.
* **sparen tijd en vermindert inspanning:** met ons modelleringsproces moet u niet raden bij wat [!UICONTROL traits] [!UICONTROL segments] kan werken of tijdmiddelen aan campagnes doorbrengen om nieuw publiek te ontdekken. Het model kan dit voor u doen.
* **Betrouwbaarheid:** modellering werkt met server-zijontdekking en kwalificatieprocessen die uw eigen gegevens en geselecteerde derdegegevens evalueren die u toegang tot hebt. Dit betekent dat u de bezoekers op uw site niet hoeft te zien om ze in aanmerking te laten komen voor een kenmerk.

## Workflow {#workflow}

U beheert modellen in **[!UICONTROL Audience Data > Models]** . Op hoog niveau omvat het workflowproces het volgende:

* Selecteer de basislijngegevens die door het algoritme moeten worden geëvalueerd. Dit omvat een [!UICONTROL trait] of [!UICONTROL segment] , een tijdbereik en [!UICONTROL data sources] (uw eigen gegevens en gegevens van derden waartoe u al toegang hebt via [!DNL Audience Manager] ). In de workflow voor het maken van modellen kunt u de [!UICONTROL traits] uitsluiten die u niet wilt beïnvloeden in uw model.
* Sla uw model op. Zodra bewaard, loopt het algoritmische evaluatieproces automatisch uit. Het kan echter tot 7 dagen duren voordat dit proces is voltooid. [!DNL Audience Manager] stuurt u een e-mail wanneer het algoritme is voltooid en de resultaten beschikbaar zijn voor het maken van [!UICONTROL trait] .
* Bouw algoritmisch [!UICONTROL traits] in [!UICONTROL Trait Builder].
* Combineer [!UICONTROL traits] tot [!UICONTROL segments] in [!UICONTROL Segment Builder] .
* [!UICONTROL segment] -gegevens maken en verzenden naar een [!UICONTROL destination] .

## Problemen oplossen {#troubleshooting}

We deactiveren elke [!UICONTROL Look-Alike Model] die er niet in slaagt gegevens te genereren voor drie opeenvolgende uitvoeringen. U kunt de status van het model niet instellen op actief achteraf. Om ervoor te zorgen dat uw modellen gegevens genereren, raden we u aan modellen te maken van gegevensbronnen die voldoende [!UICONTROL traits] bevatten om gegevens van te verzamelen.

## Werken met [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] is een eigen algoritme dat is ontworpen om automatisch nieuwe [!UICONTROL traits] te ontdekken. [!UICONTROL trait] -gegevens van uw huidige [!UICONTROL traits] en [!UICONTROL segments] worden vergeleken met alle andere gegevens van eerste en derde partijen waartoe u toegang hebt via [!DNL Audience Manager] . Zie deze sectie voor een beschrijving van het [!UICONTROL TraitWeight] algoritmische-detectieproces.

![](assets/algo_model.png)

De volgende stappen beschrijven het [!UICONTROL TraitWeight] evaluatieproces.

### Stap 1: Een basislijn maken voor [!UICONTROL Trait] vergelijking

Als u een basislijn wilt maken, meet [!UICONTROL TraitWeight] alle [!UICONTROL traits] die aan een publiek is gekoppeld voor een interval van 30, 60 of 90 dagen. Vervolgens wordt [!UICONTROL traits] gerangschikt op basis van hun frequentie en correlatie. De frequentietelling meet de uniformiteit. Correlatie meet de waarschijnlijkheid dat een [!UICONTROL trait] alleen aanwezig is in het basispubliek. [!UICONTROL Traits] die vaak worden weergegeven, hebben een hoge standaardisering. Dit is een belangrijk kenmerk dat wordt gebruikt om een gewogen score in te stellen in combinatie met [!UICONTROL traits] dat in de geselecteerde selectie wordt ontdekt [!UICONTROL data sources] .

### Stap 2: Hetzelfde zoeken [!UICONTROL Traits] in het dialoogvenster [!UICONTROL Data Source]

Nadat het een basislijn voor vergelijking bouwt, zoekt het algoritme identieke [!UICONTROL traits] in uw geselecteerde [!UICONTROL data sources]. In deze stap voert [!UICONTROL TraitWeight] een frequentietelling uit van alle gevonden [!UICONTROL traits] en vergelijkt ze met de basislijn. In tegenstelling tot de basislijn, worden soms voorkomende [!UICONTROL traits] gerangschikt hoger dan de vaker weergegeven waarden. Zelden [!UICONTROL traits] zouden een hoge mate van specificiteit vertonen. [!UICONTROL TraitWeight] beoordeelt combinaties van gangbare basislijn [!UICONTROL traits] en soms (zeer specifiek) [!UICONTROL data source] [!UICONTROL traits] als invloedrijker of wenselijker dan [!UICONTROL traits] voor beide gegevenssets. In feite erkent ons model deze grote, algemene [!UICONTROL traits] en kent het geen bovenmatige prioriteit toe aan gegevenssets met hoge correlaties. Zelden krijgt [!UICONTROL traits] een hogere prioriteit omdat het waarschijnlijker is dat ze nieuwe, unieke gebruikers vertegenwoordigen dan [!UICONTROL traits] met een hoge algemene standaardisering.

### Stap 3: Gewicht toewijzen

In deze stap rangschikt [!UICONTROL TraitWeight] pas ontdekte waarden [!UICONTROL traits] in volgorde van invloed of wenselijkheid. De weegschaal is een percentage dat loopt van 0% tot 100%. [!UICONTROL Traits] die dichter bij 100% staat, houdt in dat ze meer overeenkomen met het publiek in uw basisbevolking. Bovendien zijn zwaar gewogen [!UICONTROL traits] waardevol omdat ze nieuwe, unieke gebruikers vertegenwoordigen die zich op dezelfde manier gedragen als uw gevestigde, basislijnpubliek. Vergeet niet dat [!UICONTROL TraitWeight] [!UICONTROL traits] met een hoge mate van gemeenschappelijkheid in de basislijn en hoge specificiteit in de vergeleken gegevensbronnen waardevoller vindt dan [!UICONTROL traits] algemeen in elke gegevensset.

### Stap 4: gebruikers scoren

Elke gebruiker in de geselecteerde [!UICONTROL data sources] krijgt een gebruikersscore die gelijk is aan de som van alle gewichten van het invloedrijke [!UICONTROL traits] in het profiel van die gebruiker. De scores van de gebruiker worden dan genormaliseerd tussen 0 en 100%.

### Stap 5: Weergeven en werken met resultaten

[!DNL Audience Manager] geeft de gewogen modelresultaten weer in [!UICONTROL Trait Builder] . Wanneer u een [!UICONTROL algorithmic trait] wilt maken, kunt u met [!UICONTROL Trait Builder] [!UICONTROL traits] een gewogen score maken die tijdens de gegevensuitvoering door het algoritme wordt gegenereerd. U kunt een hogere nauwkeurigheid kiezen om alleen gebruikers te kwalificeren die zeer hoge gebruikersscores hebben en daarom zeer gelijkaardig aan het basislijnpubliek, eerder dan de rest van het publiek zijn. Als u een groter publiek (bereik) wilt bereiken, kunt u de nauwkeurigheid verminderen.

### Stap 6: De significantie van een [!UICONTROL Trait] -bewerking opnieuw evalueren over alle verwerkingscycli

[!UICONTROL TraitWeight] evalueert periodiek het belang van een [!UICONTROL trait] op basis van de grootte en de verandering in de populatie van dat [!UICONTROL trait] . Dit gebeurt wanneer het aantal gebruikers dat voor die [!UICONTROL trait] in aanmerking komt, na verloop van tijd toeneemt of afneemt. Dit gedrag is het duidelijkst zichtbaar in kenmerken die erg groot worden. Stel dat het algoritme [!UICONTROL trait A] gebruikt voor modellering. Naarmate de populatie van [!UICONTROL trait A] toeneemt, evalueert [!UICONTROL TraitWeight] het belang van dat [!UICONTROL trait] en wijst het een lagere score toe of negeert het. In dit geval is [!UICONTROL trait A] te gebruikelijk of te groot om iets belangrijks over zijn bevolking te zeggen. Nadat [!UICONTROL TraitWeight] de waarde van [!UICONTROL trait A] heeft verminderd (of deze in het model negeert), neemt de populatie van de algoritmische eigenschap af. De lijst met invloedrijke factoren [!UICONTROL traits] geeft de ontwikkeling van de basislijnpopulatie weer. Gebruik de lijst van invloedrijke [!UICONTROL traits] om te begrijpen waarom deze veranderingen voorkomen.

Verwante koppelingen:

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [Nauwkeurigheid en Bereik](../../features/traits/trait-accuracy-reach.md)

## Tijdschema bijwerken voor [!UICONTROL Look-Alike Models] en [!UICONTROL Traits] {#update-schedule}

Planning maken en bijwerken voor nieuwe of bestaande [!UICONTROL algorithmic models] en [!UICONTROL traits] .

### [!UICONTROL Look-Alike Model] Plan voor maken en bijwerken

<table id="table_E75A2B334A7F47ED9DFFBD6DF8636641"> 
 <thead>
  <tr>
   <th colname="col1" class="entry"> Type activiteit </th>
   <th colname="col2" class="entry"> Beschrijving </th>
  </tr>
 </thead>
 <tbody>
  <tr> 
   <td colname="col1"> <b> creeer of kloon een Model </b> </td>
   <td colname="col2"> <p>Voor nieuwe of gekloonde [!UICONTROL Look-Alike Models] wordt het aanmaakproces eenmaal per dag uitgevoerd om: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (november - maart) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (maart - november) </li> 
     </ul> </p> <p>Modellen die na de aanmaakdeadline zijn gemaakt of gekloond, worden de volgende dag verwerkt. </p> <p>Als de eerste looppas van een model geen gegevens produceert zal het een tweede keer, de volgende dag in werking stellen. Als de tweede poging ook geen gegevens produceert, zal er een derde poging, de volgende dag zijn. Het model zal ophouden lopend als de derde poging ook geen gegevens produceert. In dit geval deactiveren we het model. Zie meer in <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> het Oplossen van problemen kijkt-als Modellen </a>. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <b> werk een Model </b> bij </td> 
   <td colname="col2"> <p>Onder ideale omstandigheden lopen bestaande modellen op weekdagen, minstens om de 7 dagen. Als u bijvoorbeeld een model maakt (tegen de deadline) op maandag, wordt de volgende maandag bijgewerkt. </p> <p>Een model wordt opnieuw uitgevoerd als het aan een van de volgende voorwaarden voldoet: </p> <p>
     <ul id="ul_7B0442F6E840415B82705C7B7419D079"> 
      <li id="li_27DCB92CE61F4388B5D253C13BD030BE">De laatste uitvoering is mislukt. </li> 
      <li id="li_9887E50D291446AC868A8FCE6295536E">Het is gelukt vóór EN het heeft de afgelopen 7 dagen helemaal niet gewerkt EN het model heeft minstens één actief kenmerk eraan gekoppeld. </li>
     </ul> </p> </td>
  </tr>
 </tbody>
</table>

### [!UICONTROL Look-Alike Trait] Plan voor maken en bijwerken

<table id="table_92A908818C4F4F2287EA56C786CD0BBD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type activiteit </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> creeer een Spoor </b> </td> 
   <td colname="col2"> <p>Het proces voor het maken van sporen wordt elke dag uitgevoerd, van maandag tot vrijdag. Over het algemeen worden nieuwe algoritmische kenmerken binnen 48 uur weergegeven in de gebruikersinterface. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> werk een Spoor </b> bij </td> 
   <td colname="col2"> <p>Bestaande kenmerken worden ten minste om de 7 dagen bijgewerkt en volgen het schema voor modelupdates. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Modellen-lijstweergave {#models-list-view}

De lijstmening is een centrale werkruimte die u helpt om modellen tot stand te brengen, te herzien en te beheren.

De lijstpagina [!UICONTROL Models] bevat functies en gereedschappen die u helpen:

* Nieuwe modellen maken.
* Bestaande modellen beheren (bewerken, pauzeren, verwijderen of klonen).
* Zoek naar modellen door naam.
* Maak [!UICONTROL algorithmic traits] met een bepaald model.

## Modellen - overzichtsweergave {#models-summary-view}

Op de overzichtspagina worden de modeldetails weergegeven, zoals naam, bereik/nauwkeurigheid, verwerkingsgeschiedenis en [!UICONTROL traits] die op basis van het model zijn gemaakt. De pagina bevat ook instellingen waarmee u modellen kunt maken en beheren. Klik op een modelnaam in de overzichtslijst om de details weer te geven.

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
   <td colname="col1"> <p> <span class="wintitle"> Basisinformatie </span> </p> </td>
   <td colname="col2"> <p>Deze groep bevat basisinformatie over het model, zoals de naam en het tijdstip waarop het voor het laatst is uitgevoerd. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Model Reach and Accuracy </span> </p> </td> 
   <td colname="col2"> <p>Toont <a href="../../features/traits/trait-accuracy-reach.md"> nauwkeurigheid en bereik </a> gegevens voor de laatste modellooppas. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Geschiedenis modelverwerking </span> </p> </td> 
   <td colname="col2"> <p>Toont de verwerkingsdatum en de tijd voor de laatste 10 looppas en of de gegevens op die looppas werden geproduceerd. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Influential Traits </span> </p> </td> 
   <td colname="col2"> <p>De tabel <span class="wintitle"> Influential Traits </span> : </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Vermeldt de bovenste 50 invloedrijke kenmerken die het best worden vertegenwoordigd in de basislijnpopulatie van het model. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Elke eigenschap wordt opnieuw gespeld in volgorde van de rang <span class="wintitle"> Relatief gewicht </span> . Met <span class="wintitle"> Relatief gewicht </span> sorteert u pas ontdekte kenmerken in volgorde van invloed of wenselijkheid. De weegschaal is een percentage dat loopt van 0% tot 100%. Traits gerangschikt dichter bij 100% betekent dat ze meer lijken op het publiek in je basispopulatie. Zie <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> Informatie over TraitWeight </a> . </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Toont de uniques van 30 dagen en de totale populatie van eigenschappen voor elk kenmerk. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Traits die model gebruiken </span> </p> </td>
   <td colname="col2"> <p>Toont een lijst van de algoritmische eigenschappen die op het geselecteerde model worden gebaseerd. Klik op de naam van een kenmerk of de handels-id voor meer informatie over de eigenschap. Selecteer <b><span class="uicontrol"> Nieuwe eigenschap maken met model </span></b> om naar het maken van de algoritmische eigenschap te gaan. </p> <p>De veranderingen van het sectielabel die op de naam van uw model worden gebaseerd. Stel dat u een model maakt en dit model modelnaam geeft. Wanneer u de overzichtspagina laadt, wordt de naam van deze sectie veranderd in <span class="wintitle"> Traits Gebruikend Model A </span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Doelen](../../features/destinations/destinations.md)
>* [ Tanden ](../../features/traits/trait-details-page.md)
>* [ Segmenten ](../../features/segments/segments-purpose.md)
