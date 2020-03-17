---
description: De metriek van de Verbinding van het profiel verstrekt gegevens over mensen en apparaten die aan uw plaats voor authentiek verklaren. De gegevens en grafieken in de Verbinding van het Profiel werken dynamisch bij aangezien u een fusieregels creeert of wanneer u een bestaande regel van het dashboard van de Regels van de Fusie van het Profiel klikt. Deze cijfers kunnen apparaatgrafieken van de Adobe Experience Cloud Device Co-op of andere apparaatgrafiekbronnen van derden bevatten.
seo-description: De metriek van de Verbinding van het profiel verstrekt gegevens over mensen en apparaten die aan uw plaats voor authentiek verklaren. De gegevens en grafieken in de Verbinding van het Profiel werken dynamisch bij aangezien u een fusieregels creeert of wanneer u een bestaande regel van het dashboard van de Regels van de Fusie van het Profiel klikt. Deze cijfers kunnen apparaatgrafieken van de Adobe Experience Cloud Device Co-op of andere apparaatgrafiekbronnen van derden bevatten.
seo-title: Metriek rapporteren voor regels voor het samenvoegen van profielen
solution: Audience Manager
title: Metriek rapporteren voor regels voor het samenvoegen van profielen
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Metriek rapporteren voor regels voor het samenvoegen van profielen {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] metriek biedt gegevens over personen en apparaten die voor uw site worden geverifieerd. De gegevens en grafieken in [!UICONTROL Profile Merge Rule Reports] worden dynamisch bijgewerkt terwijl u een samenvoegregel maakt of wanneer u op een bestaande regel van het [!UICONTROL Profile Merge Rules] dashboard klikt. Deze meetgegevens kunnen apparaatgrafieken van de grafiekbronnen van het apparaat [!DNL Adobe Experience Cloud Device Co-op] of van andere derden bevatten.

## Regelafmetingen samenvoegen {#merge-rule-metrics}

Hiermee worden geretourneerde gegevens gerapporteerd in staafgrafieken die naast elkaar staan wanneer de samenvoegregels gegevens gebruiken van de [Adobe Experience Cloud Device Co-op](https://marketing.adobe.com/resources/help/en_US/mcdc/) of andere apparaatgrafieken van derden waartoe u toegang hebt [!DNL Audience Manager]. Zo kunt u geverifieerde, gegevens van de eerste partij vergelijken met gegevens van andere apparaten die worden geleverd door de grafiek van een ander apparaat van een andere fabrikant. [!UICONTROL Experience Cloud Device Co-op] Zie Apparaatgrafiek voor informatie over gegevens die door [!UICONTROL Device Co-op]de [component worden geretourneerd: Interne processen en uitvoer](https://marketing.adobe.com/resources/help/en_US/mcdc/mcdc-processes.html). Deze gegevens worden dagelijks bijgewerkt.

<table id="table_A7FB2F9804F84AC8A6DD05C0E6EE7555"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrisch </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Geverifieerde activiteit</span></b> </p> </td> 
   <td colname="col2"> <p>Toont: </p> 
    <ul id="ul_7F7373919A4A49028EF4BF7B28D9F8E9"> 
     <li id="li_FE2F93C496D64ED8928B3E522C9585EA"> <span class="wintitle"> Actieve personen</span>: Het aantal personen dat de afgelopen 60 dagen voor verificatie bij uw site is aangemeld. </li> 
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Kruisapparaat</span>: Het totale aantal <a href="merge-rules-start.md#create-data-source"> Apparaatoverschrijdende IDs</a> die in de <a href="https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html"> Gegevensbron</a> van het geselecteerde <a href="merge-rule-definitions.md"> Voor authentiek verklaarde Profiel</a> voor het leven wordt opgeslagen dat de gegevensbron heeft bestaan. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % actieve personen</span>: Hiermee geeft u <span class="wintitle"> Actieve personen</span> als % weer. </li> 
    </ul> <p> <span class="wintitle"> De voor authentiek verklaarde Activiteit</span> laat u gegevensbronnen door activiteit, volume, en percenten vergelijken. Het kan u helpen een gegevensbron vinden die veel mensen en een hoog percentage actieve gebruikers heeft. Of u vindt mogelijk waarde bij het vergelijken van gegevensbronnen met een hoog percentage actieve gebruikers in vergelijking met de totale omvang van het publiek. Bijvoorbeeld, soms is een gegevensbron met lage totale levenaantallen en hoge activiteit waardevoller dan die met hoge levenresultaten en lage activiteitenaantallen. </p> <p> <p>Opmerking: De <span class="wintitle"> Voor authentiek verklaarde metriek van de Activiteit</span> bevatten slechts de gegevens van de Verbinding <span class="wintitle"></span> van het Profiel. Dit rapport bevat geen <span class="wintitle"> apparaatgrafiekgegevens</span> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Gemiddelde apparaten per persoon</span></b> </p> </td> 
   <td colname="col2"> <p> Hiermee geeft u het gemiddelde aantal apparaten weer dat wordt gebruikt door bezoekers die voor de geselecteerde gegevensbron zijn geverifieerd voor uw site. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Totaal aantal apparaten</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee geeft u het totale aantal apparaten weer dat mensen hebben gebruikt voor verificatie bij uw site voor de geselecteerde gegevensbron. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="wintitle"> Totaal aantal personen</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee wordt het totale aantal personen weergegeven dat deterministisch is geïdentificeerd voor de geselecteerde gegevensbron. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Metrische apparaatgrafiek {#device-graph-metrics}

De [!UICONTROL Merge Rules] rapporten bevatten ook gegevens over het totale aantal personen en apparaten dat uw site heeft bezocht voor de geselecteerde gegevensbron en apparaatgrafiek. Deze metriek keert gegevens terug die op vooraf ingestelde tijdintervallen (de terugblik periode) worden gebaseerd die afhankelijk van de apparatenoptie variëren u wanneer het creëren van een regel selecteert. In de volgende tabel worden deze rapportintervallen voor elk van de opties voor apparaatgrafieken weergegeven.

<table id="table_038983EBC71F4A55BBCA99212AC5DEE6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Optie apparaatgrafiek </th> 
   <th colname="col2" class="entry"> Het Interval van de Terugblik-rug van het rapport </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Profielkoppeling</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_B2FF2341573840549FFB96579F537082"> 
      <li id="li_B37323C2F2434F41B407500AC5C15447">Totaal aantal personen: 60 dagen </li> 
      <li id="li_08D911224A60418BBB3CFB4E70CE73D4">Totaal aantal apparaten: 120 dagen </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Afbeelding van apparaat voor coop</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_64AD1DD89DF64703B70B973A463BA020"> 
      <li id="li_D7D3A3871F434CBFA71BE8929EB41648">Totaal aantal personen: 180 dagen </li> 
      <li id="li_125D387986B2463EB310203CE5857EDA">Totaal aantal apparaten: 180 dagen </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> LiveRamp</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_2772F3AD7E1440789B635794ECDE8DFB"> 
      <li id="li_1432363829D64615B1D349A3722D6268">Totaal aantal personen: 180 dagen </li> 
      <li id="li_D5C0E3CE92524B54BBD36C73A326292B">Totaal aantal apparaten: 180 dagen </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><span class="wintitle"> Tapad</span> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_274529DB58E6442E95C6AD89BECB1362"> 
      <li id="li_67102211A72A4E47AACFE5E369793C17">Totaal aantal personen: 60 dagen </li> 
      <li id="li_3E8F3DA6A7B5487895A626674DA363A5">Totaal aantal apparaten 60 dagen </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Voorbeeldrapporten {#sample-reports}

### Rapport Standaardprofielkoppeling

Een standaardrapport ziet er als volgt uit: [!UICONTROL Profile Link] De regels van de fusie die veelvoudige gegevensbronnen (tot 3, maximum) gebruiken tonen grafieken in afzonderlijke lusjes voor elke gegevensbron. Deze samenvoegregel bevat geen [!UICONTROL Device Co-op] gegevens.

![](assets/profile-link-metrics.png)

### Profielkoppelingsrapport met apparaatgrafiekgegevens

Een [!UICONTROL Profile Link Device Graph] rapport met apparaatgrafiekgegevens uit de grafiek [!UICONTROL Adobe Experience Cloud Device Co-op] of een apparaatgrafiek van derden toont [!UICONTROL Profile Link] en apparaatgrafiekgegevens met staafgrafieken naast elkaar. Door deze grafieken naast elkaar te plaatsen, kunt u de voordelen van het gebruik van de grafieken evalueren [!UICONTROL Experience Cloud Device Co-op] in vergelijking met [!UICONTROL Profile Link] de grafieken zelf. De regels van de fusie die veelvoudige gegevensbronnen (tot 3, maximum) gebruiken tonen grafieken in afzonderlijke lusjes voor elke gegevensbron. Ter herinnering, de [!UICONTROL Authenticated Activity] grafiek en de metriek keren geen gegevens van de [!DNL Adobe] apparatengrafiek of andere, derdeapparatengrafieken terug u tot binnen kunt toegang hebben [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Profielkoppelingsgrafiek {#profile-link-trend}

Naast de andere gegevensvisualisaties, omvatten de [!UICONTROL Profile Link] rapporten een lijngrafiek. De lijngrafiek wordt ontworpen om u tendensen in tijd voor uw profielregels te tonen. Trend-grafieken (en de andere rapporten) zijn beschikbaar wanneer u op een regel van de [!UICONTROL Profile Merge Rules] openingspagina ( **[!UICONTROL Audience Data > Profile Merge Rules]**) klikt. Deze grafieken bevatten apparaatgrafiekgegevens als u lid bent van de [!UICONTROL Device Co-op] of andere apparaatgrafieken van derden waartoe u toegang hebt [!DNL Audience Manager]. Klik op een trendlijn om onderliggende gegevens te zien.

>[!MORELIKETHIS]
>
>* [Veelgestelde vragen over regels voor samenvoegen van profielen](../../faq/faq-profile-merge.md)

