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
source-wordcount: '1576'
ht-degree: 0%

---

# Begrijpen [!UICONTROL Look-Alike Modeling] {#about-algorithmic-models}

## Nieuwe gebruikers zoeken met [!UICONTROL Look-Alike Modeling] {#find-new-users}

[!UICONTROL Look-Alike Modeling] helpt u nieuwe, unieke doelgroepen te ontdekken via geautomatiseerde gegevensanalyse. Het proces begint wanneer u een [!UICONTROL trait] of [!UICONTROL segment], een tijdsinterval en eerste en derde partij [!UICONTROL data sources]. Uw keuzen verstrekken de input voor het algoritmische model. Wanneer het analyseproces loopt, zoekt het naar in aanmerking komende gebruikers die op gedeelde kenmerken van de geselecteerde bevolking worden gebaseerd. Na voltooiing zijn deze gegevens beschikbaar in [Trait Builder](../../features/traits/about-trait-builder.md) waar u het kunt gebruiken om eigenschappen tot stand te brengen die op worden gebaseerd [nauwkeurigheid en bereik](../../features/traits/trait-accuracy-reach.md). Bovendien kunt u segmenten maken waarin algoritmische kenmerken worden gecombineerd [!UICONTROL rules-based traits] en voeg andere kwalificatievereisten toe met [!DNL Boolean] expressies en vergelijkingsoperatoren. [!UICONTROL Look-Alike Modeling] biedt u een dynamische manier om waarde uit al uw beschikbare gegevens van het bezit te halen.

## Voordelen {#advantages}

De belangrijkste voordelen van het gebruik [!UICONTROL Look-Alike Modeling] omvatten:

* **Nauwkeurigheid van gegevens:** Het algoritme wordt regelmatig uitgevoerd, waardoor de resultaten actueel en relevant blijven.
* **Automatisering:** U moet geen grote reeks statische regels beheren. Het algoritme zal publiek voor u vinden.
* **Bespaar tijd en verminder uw inspanningen:** Met ons modelleringsproces hoeft u niet te raden wat [!UICONTROL traits]/[!UICONTROL segments] kan tijd besteden aan campagnes om nieuwe doelgroepen te ontdekken. Het model kan dit voor u doen.
* **Betrouwbaarheid:** Modellering werkt met detectie- en kwalificatieprocessen aan de serverzijde die uw eigen gegevens en geselecteerde gegevens van derden evalueren waartoe u toegang hebt. Dit betekent dat u de bezoekers op uw site niet hoeft te zien om ze in aanmerking te laten komen voor een kenmerk.

## Workflow {#workflow}

U beheert modellen in **[!UICONTROL Audience Data > Models]**. Op hoog niveau omvat het workflowproces het volgende:

* Selecteer de basislijngegevens die door het algoritme moeten worden geëvalueerd. Dit omvat een [!UICONTROL trait] of [!UICONTROL segment], tijdbereik, en [!UICONTROL data sources] (uw eigen gegevens en gegevens van derden waartoe u al toegang hebt via [!DNL Audience Manager]). In de workflow voor het maken van modellen kunt u de opdracht [!UICONTROL traits] dat je je model niet wilt beïnvloeden.
* Sla uw model op. Zodra bewaard, loopt het algoritmische evaluatieproces automatisch uit. Het kan echter tot 7 dagen duren voordat dit proces is voltooid. [!DNL Audience Manager] verzendt u een e-mail wanneer het algoritme heeft gebeëindigd en de resultaten beschikbaar voor [!UICONTROL trait] creëren.
* Algoritme maken [!UICONTROL traits] in [!UICONTROL Trait Builder].
* Combineren [!UICONTROL traits] in [!UICONTROL segments] in [!UICONTROL Segment Builder].
* Maken en verzenden [!UICONTROL segment] gegevens naar een [!UICONTROL destination].

## Problemen oplossen {#troubleshooting}

We deactiveren alle [!UICONTROL Look-Alike Model] dat er niet in slaagt gegevens te genereren voor drie opeenvolgende reeksen. U kunt de status van het model niet instellen op actief achteraf. Om ervoor te zorgen dat uw modellen gegevens genereren, raden we u aan modellen te maken van gegevensbronnen met voldoende [!UICONTROL traits] gegevens te verzamelen van.

## Begrijpen [!UICONTROL TraitWeight] {#understanding-traitweight}

[!UICONTROL TraitWeight] is een merkgebonden algoritme dat wordt ontworpen om nieuw te ontdekken [!UICONTROL traits] automatisch. Vergelijken [!UICONTROL trait] gegevens uit uw huidige [!UICONTROL traits] en [!UICONTROL segments] tegen alle andere gegevens van de eerste en derde partij die u tot door hebt toegang [!DNL Audience Manager]. Zie deze sectie voor een beschrijving van de [!UICONTROL TraitWeight] algoritmisch detectieproces.

![](assets/algo_model.png)

De volgende stappen beschrijven de [!UICONTROL TraitWeight] evaluatieproces.

### Stap 1: Een basislijn maken voor [!UICONTROL Trait] Vergelijking

Om een basislijn te bouwen, [!UICONTROL TraitWeight] alle [!UICONTROL traits] geassocieerd met een publiek voor een interval van 30, 60, of 90 dagen. Vervolgens wordt de klasse [!UICONTROL traits] naar gelang van hun frequentie en correlatie. De frequentietelling meet de uniformiteit. Correlatiemaatregelen de waarschijnlijkheid van een [!UICONTROL trait] alleen aanwezig zijn in het basislijnpubliek. [!UICONTROL Traits] die vaak een hoge mate van gemeenschappelijkheid lijken te vertonen, een belangrijk kenmerk dat wordt gebruikt om een gewogen score in te stellen wanneer gecombineerd met [!UICONTROL traits] ontdekt in uw geselecteerde [!UICONTROL data sources].

### Stap 2: Zelfde zoeken [!UICONTROL Traits] in de [!UICONTROL Data Source]

Nadat het een basislijn voor vergelijking bouwt, zoekt het algoritme identiek [!UICONTROL traits] in uw geselecteerde [!UICONTROL data sources]. In deze stap [!UICONTROL TraitWeight] voert een frequentietelling van allen uit ontdekt [!UICONTROL traits] en vergelijkt deze met de basislijn. In tegenstelling tot de basislijn komen echter soms voor [!UICONTROL traits] worden gerangschikt hoger dan de rangschikkingen die vaker voorkomen. Zelden [!UICONTROL traits] naar verluidt een hoge mate van specificiteit vertonen. [!UICONTROL TraitWeight] beoordeelt combinaties van gangbare basislijn [!UICONTROL traits] en soms (zeer specifiek) [!UICONTROL data source] [!UICONTROL traits] als invloedrijker of wenselijker dan [!UICONTROL traits] beide gegevenssets gemeen hebben. In feite erkent ons model deze grote, gemeenschappelijke [!UICONTROL traits] en geen bovenmatige prioriteit toekent aan gegevenssets met hoge correlaties. Zelden [!UICONTROL traits] krijgt hogere prioriteit omdat zij meer waarschijnlijkheid nieuwe, unieke gebruikers vertegenwoordigen dan [!UICONTROL traits] met een hoge mate van uniformiteit over de hele linie.

### Stap 3: Gewicht toewijzen

In deze stap [!UICONTROL TraitWeight] pas ontdekte rangen [!UICONTROL traits] in volgorde van invloed of wenselijkheid. De weegschaal is een percentage dat loopt van 0% tot 100%. [!UICONTROL Traits] gerangschikt naar 100% betekent dat ze meer lijken op het publiek in je basispopulatie. Ook, zwaar gewogen [!UICONTROL traits] zijn waardevol omdat ze nieuwe, unieke gebruikers vertegenwoordigen die zich op dezelfde manier gedragen als uw gevestigde basispubliek. Onthoud, [!UICONTROL TraitWeight] beschouwt [!UICONTROL traits] met een hoge mate van gemeenschappelijkheid in de basislijn en een hoge specificiteit in de vergeleken gegevensbronnen waardevoller zijn dan [!UICONTROL traits] worden gebruikt in elke gegevensset.

### Stap 4: Scoregebruikers

Elke gebruiker in de geselecteerde [!UICONTROL data sources] een gebruikersscore heeft die gelijk is aan de som van alle gewichten van de invloedrijke [!UICONTROL traits] op het profiel van die gebruiker. De scores van de gebruiker worden dan genormaliseerd tussen 0 en 100%.

### Stap 5: Weergeven en werken met resultaten

[!DNL Audience Manager] geeft de gewogen modelresultaten weer in [!UICONTROL Trait Builder]. Wanneer u een [!UICONTROL algorithmic trait], [!UICONTROL Trait Builder] Hiermee kunt u [!UICONTROL traits] op basis van de gewogen score die door het algoritme wordt gegenereerd tijdens een gegevensuitvoering. U kunt een hogere nauwkeurigheid kiezen om alleen gebruikers te kwalificeren die zeer hoge gebruikersscores hebben en daarom zeer gelijkaardig aan het basislijnpubliek, eerder dan de rest van het publiek zijn. Als u een groter publiek (bereik) wilt bereiken, kunt u de nauwkeurigheid verminderen.

### Stap 6: De betekenis van een [!UICONTROL Trait] Alle verwerkingscycli

periodiek, [!UICONTROL TraitWeight] het belang van een [!UICONTROL trait] op basis van de omvang en de verandering van de bevolking van [!UICONTROL trait]. Dit gebeurt als het aantal gebruikers dat hiervoor in aanmerking komt [!UICONTROL trait] neemt toe of daalt in de loop der tijd. Dit gedrag is het duidelijkst zichtbaar in kenmerken die erg groot worden. Stel dat het algoritme het volgende gebruikt [!UICONTROL trait A] voor modellering. Als populatie van [!UICONTROL trait A] stijgingen, [!UICONTROL TraitWeight] herevalueert het belang hiervan [!UICONTROL trait] en kan een lagere score toewijzen of negeren. In dit geval: [!UICONTROL trait A] het is te gebruikelijk of te groot om iets belangrijks over zijn bevolking te zeggen. Na [!UICONTROL TraitWeight] vermindert de waarde van [!UICONTROL trait A] (of negeert het in het model), vermindert de populatie van het algoritmische bezit. De lijst van invloedrijke [!UICONTROL traits] weerspiegelt de ontwikkeling van de basispopulatie. De lijst met invloedrijke [!UICONTROL traits] om te begrijpen waarom deze veranderingen zich voordoen.

Verwante koppelingen:

* [Model Builder](../../features/algorithmic-models/create-model.md)
* [Nauwkeurigheid en bereik](../../features/traits/trait-accuracy-reach.md)

## Plan bijwerken voor [!UICONTROL Look-Alike Models] en [!UICONTROL Traits] {#update-schedule}

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
   <td colname="col2"> <p>Voor nieuw of gekloond [!UICONTROL Look-Alike Models]Het aanmaakproces wordt eenmaal per dag uitgevoerd om: 
     <ul id="ul_97333AC409AF4760A91D90A06050122B"> 
      <li id="li_3A43809F924341FCAC3A85E3825E0F61"> 5 PM EST (november - maart) </li> 
      <li id="li_C07D22AB192D4E0191D9EBF6426EC73D"> 6 PM EDT (maart - november) </li> 
     </ul> </p> <p>Modellen die na de aanmaakdeadline zijn gemaakt of gekloond, worden de volgende dag verwerkt. </p> <p>Als de eerste looppas van een model geen gegevens produceert zal het een tweede keer, de volgende dag in werking stellen. Als de tweede poging ook geen gegevens produceert, zal er een derde poging, de volgende dag zijn. Het model zal ophouden lopend als de derde poging ook geen gegevens produceert. In dit geval deactiveren we het model. Meer informatie in <a href="../../features/algorithmic-models/understanding-models.md#troubleshooting"> Oplossen van problemen met look-Alike modellen</a>. </p> </td>
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

## Modellen-lijstweergave {#models-list-view}

De lijstmening is een centrale werkruimte die u helpt om modellen tot stand te brengen, te herzien en te beheren.

De [!UICONTROL Models] de lijstpagina bevat eigenschappen en hulpmiddelen die u helpen:

* Nieuwe modellen maken.
* Bestaande modellen beheren (bewerken, pauzeren, verwijderen of klonen).
* Zoek naar modellen door naam.
* Maken [!UICONTROL algorithmic traits] een bepaald model te gebruiken.

## Modellen - overzichtsweergave {#models-summary-view}

Op de overzichtspagina worden modeldetails weergegeven, zoals naam, bereik/nauwkeurigheid, verwerkingsgeschiedenis en [!UICONTROL traits] gemaakt van het model. De pagina bevat ook instellingen waarmee u modellen kunt maken en beheren. Klik op een modelnaam in de overzichtslijst om de details weer te geven.

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
   <td colname="col2"> <p>Toont <a href="../../features/traits/trait-accuracy-reach.md"> nauwkeurigheid en bereik</a> gegevens voor de laatste modeluitvoering. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Verwerkingsgeschiedenis model</span> </p> </td> 
   <td colname="col2"> <p>Toont de verwerkingsdatum en de tijd voor de laatste 10 looppas en of de gegevens op die looppas werden geproduceerd. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Influente sporen</span> </p> </td> 
   <td colname="col2"> <p>De <span class="wintitle"> Influente sporen</span> tabel: </p> <p> 
     <ul id="ul_FB15A554CADC40D09F9AC6D384D54ECD"> 
      <li id="li_343E25E8B3584D38B1E2BCB211033DBF"> Vermeldt de bovenste 50 invloedrijke kenmerken die het best worden vertegenwoordigd in de basislijnpopulatie van het model. </li> 
      <li id="li_44957F46C0744A84A987D8F25D93E24E">Hiermee wordt elk kenmerk in volgorde gerangschikt <span class="wintitle"> Relatieve dikte</span> rang. De <span class="wintitle"> Relatieve dikte</span> sorteert pas ontdekte eigenschappen in volgorde van invloed of wenselijkheid. De weegschaal is een percentage dat loopt van 0% tot 100%. Traits gerangschikt dichter bij 100% betekent dat ze meer lijken op het publiek in je basispopulatie. Zie <a href="../../features/algorithmic-models/understanding-models.md#understanding-traitweight"> TraitWeight begrijpen</a>. </li> 
      <li id="li_260151E23B1E484BA06C8494552A04F0">Toont de uniques van 30 dagen en de totale populatie van eigenschappen voor elk kenmerk. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Treits met model</span> </p> </td>
   <td colname="col2"> <p>Toont een lijst van de algoritmische eigenschappen die op het geselecteerde model worden gebaseerd. Klik op de naam van een kenmerk of de handels-id voor meer informatie over de eigenschap. Selecteren <b><span class="uicontrol"> Nieuwe eigenschap maken met model</span></b> om naar het proces voor het maken van algoritmische sporen te gaan. </p> <p>De veranderingen van het sectielabel die op de naam van uw model worden gebaseerd. Stel dat u een model maakt en dit model modelnaam geeft. Wanneer u de overzichtspagina laadt, wordt de naam van deze sectie gewijzigd in <span class="wintitle"> Treedt met model A</span>. </p> </td>
  </tr>
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Bestemmingen ](../../features/destinations/destinations.md)
>* [Eigenschappen ](../../features/traits/trait-details-page.md)
>* [Segmenten ](../../features/segments/segments-purpose.md)

