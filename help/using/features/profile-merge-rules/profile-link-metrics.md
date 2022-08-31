---
description: De metriek van de Verbinding van het profiel verstrekt gegevens over mensen en apparaten die aan uw plaats voor authentiek verklaren. De gegevens en grafieken in de Verbinding van het Profiel werken dynamisch bij aangezien u een fusieregels creeert of wanneer u een bestaande regel van het dashboard van de Regels van de Fusie van het Profiel klikt. Deze meetgegevens kunnen apparaatgrafieken van andere apparaatgrafiekbronnen van derden bevatten.
seo-description: Profile Link metrics provide data about people and devices that authenticate to your site. The data and graphs in Profile Link update dynamically as you create a merge rules or when you click an existing rule from the Profile Merge Rules dashboard. These metrics can include device graph from other third-party device graph sources.
seo-title: Report Metrics for Profile Merge Rules
solution: Audience Manager
title: Cijfers rapporteren voor regels voor profielsamenvoeging
uuid: 76a86ff0-4c64-4734-aec0-0a8828942096
feature: Profile Merge
exl-id: 2af59c60-2448-44af-90d2-eccc52f7ff02
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 2%

---

# Cijfers rapporteren voor regels voor profielsamenvoeging {#report-metrics-for-profile-merge-rules}

[!UICONTROL Profile Merge Rule] metriek biedt gegevens over personen en apparaten die voor uw site worden geverifieerd. De gegevens en grafieken in [!UICONTROL Profile Merge Rule Reports] werkt u dynamisch bij terwijl u een samenvoegregel maakt of wanneer u op een bestaande regel klikt in het dialoogvenster [!UICONTROL Profile Merge Rules] dashboard. Deze meetgegevens kunnen apparaatgrafieken van andere apparaatgrafiekbronnen van derden bevatten.

## Regelafmetingen samenvoegen {#merge-rule-metrics}

Hiermee worden geretourneerde gegevens in staafgrafieken naast elkaar gerapporteerd wanneer de samenvoegregels gegevens gebruiken van apparaatgrafieken van derden waartoe u toegang hebt in [!DNL Audience Manager]. Zo kunt u geverifieerde gegevens van de eerste partij vergelijken met gegevens van andere apparaten die worden geleverd door apparaatgrafieken van derden. Deze gegevens worden dagelijks bijgewerkt.

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
     <li id="li_60CFD26EE68B442683C0ED5FED1A79C8"> <span class="wintitle"> Cross-device</span>: Het totale aantal <a href="merge-rules-start.md#create-data-source"> Id's kruisapparaat</a> opgeslagen in het <a href="https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html"> Gegevensbron</a> van de geselecteerde <a href="merge-rule-definitions.md"> Geverifieerd profiel</a> gedurende de levensduur dat de gegevensbron bestaat. </li> 
     <li id="li_F2F07B6A326C4A18B79A0CF2C47D9677"> <span class="wintitle"> % actieve personen</span>: Toont <span class="wintitle"> Actieve personen</span> als %. </li> 
    </ul> <p> <span class="wintitle"> Geverifieerde activiteit</span> Hiermee kunt u gegevensbronnen vergelijken op activiteit, volume en percentage. Het kan u helpen een gegevensbron vinden die veel mensen en een hoog percentage actieve gebruikers heeft. Of u vindt mogelijk waarde bij het vergelijken van gegevensbronnen met een hoog percentage actieve gebruikers in vergelijking met de totale omvang van het publiek. Bijvoorbeeld, soms is een gegevensbron met lage totale levenaantallen en hoge activiteit waardevoller dan die met hoge levenresultaten en lage activiteitenaantallen. </p> <p> <p>Opmerking: De <span class="wintitle"> Geverifieerde activiteit</span> metriek bevatten <span class="wintitle"> Profielkoppeling</span> alleen gegevens. Dit verslag bevat geen <span class="wintitle"> Apparaatgrafiek</span> gegevens. </p> </p> </td> 
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

De [!UICONTROL Merge Rules] in rapporten worden ook gegevens weergegeven over het totale aantal personen en apparaten dat uw site heeft bezocht voor de geselecteerde gegevensbron en apparaatgrafiek. Deze metriek keert gegevens terug die op vooraf ingestelde tijdintervallen (de terugblik periode) worden gebaseerd die afhankelijk van de apparatenoptie variëren u wanneer het creëren van een regel selecteert. In de volgende tabel worden deze rapportintervallen voor elk van de opties voor apparaatgrafieken weergegeven.

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

Een norm [!UICONTROL Profile Link] het rapport ziet als het volgende voorbeeld. De regels van de fusie die veelvoudige gegevensbronnen (tot 3, maximum) gebruiken tonen grafieken in afzonderlijke lusjes voor elke gegevensbron. Deze samenvoegregel omvat niet [!UICONTROL external device graph] gegevens.

![](assets/profile-link-metrics.png)

### Profielkoppelingsrapport met apparaatgrafiekgegevens

A [!UICONTROL Profile Link Device Graph] rapport dat de gegevens van de apparatengrafiek van derdeapparatengrafieken omvat toont [!UICONTROL Profile Link] en apparaatgrafiekgegevens met staafgrafieken naast elkaar. Door deze grafieken naast elkaar te plaatsen, kunt u de voordelen evalueren van het gebruik van externe apparaatgrafieken in vergelijking met [!UICONTROL Profile Link] op zich. De regels van de fusie die veelvoudige gegevensbronnen (tot 3, maximum) gebruiken tonen grafieken in afzonderlijke lusjes voor elke gegevensbron. Ter herinnering: [!UICONTROL Authenticated Activity] de grafiek en de metriek keren geen gegevens van terug [!DNL Adobe] apparaatgrafiek of andere apparaatgrafieken van derden waartoe u toegang hebt in [!DNL Audience Manager].

![](assets/profile-link-graph.png)

## Profielkoppelingsgrafiek {#profile-link-trend}

Naast de andere gegevensvisualisaties, [!UICONTROL Profile Link] rapporten bevatten een lijngrafiek. De lijngrafiek wordt ontworpen om u tendensen in tijd voor uw profielregels te tonen. De grafieken van de trend (en de andere rapporten) zijn beschikbaar wanneer u een regel van klikt [!UICONTROL Profile Merge Rules] landingspagina ( **[!UICONTROL Audience Data > Profile Merge Rules]**). Deze grafieken bevatten apparaatgrafiekgegevens als u lid bent van apparaatafbeeldingen van derden waartoe u toegang hebt in [!DNL Audience Manager]. Klik op een trendlijn om onderliggende gegevens te zien.

>[!MORELIKETHIS]
>
>* [Veelgestelde vragen over regels voor samenvoegen van profielen](../../faq/faq-profile-merge.md)

