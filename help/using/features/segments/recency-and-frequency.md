---
description: In de Bouwer van het Segment, laten de recentie en de frequentie u bezoekers segmenteren die op acties voorkomen of zich over een bepaald dagelijks interval herhalen.
seo-description: In de Bouwer van het Segment, laten de recentie en de frequentie u bezoekers segmenteren die op acties voorkomen of zich over een bepaald dagelijks interval herhalen.
seo-title: Recente en frequente
solution: Audience Manager
title: Recente en frequente
uuid: faadd18a-bf27-4b73-995e-9809f52f5350
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Recente en frequente {#recency-and-frequency}

Met [!UICONTROL Segment Builder]de frequentie en de frequentie kunt u bezoekers segmenteren op basis van acties die plaatsvinden of herhalen gedurende een ingesteld dagelijks interval.

Audience Manager definieert [!DNL recency] en [!DNL frequency] ziet er als volgt uit:

* **[!UICONTROL Recency]:**Hoe recent een gebruiker heeft bekeken of gekwalificeerd voor een (of meer) eigenschap.
* **[!UICONTROL Frequency]:**De frequentie waarmee een gebruiker een (of meer) eigenschap heeft bekeken of in aanmerking heeft genomen.

[!UICONTROL Recency] en [!UICONTROL Frequency] instellingen helpen u bezoekers te segmenteren op basis van hun werkelijke (of waargenomen) interesse voor een site, sectie of bepaalde creatieve instellingen. Gebruikers die bijvoorbeeld in aanmerking komen voor een segment met hoge eisen inzake recentie/frequentie, hebben wellicht meer belangstelling voor een site of een product dan gebruikers die minder vaak of minder vaak een bezoek brengen.

## Locatie van de instellingen voor recentie en frequentie {#location}

In [!UICONTROL Segment Builder], [!UICONTROL Recency] en de [!UICONTROL Frequency] montages worden gevestigd in de [!UICONTROL Basic View] sectie van het [!UICONTROL Traits] paneel. Klik het klokpictogram om deze controles bloot te stellen.

![](assets/recency_frequency.png)

## Beperkingen en regels {#limitations-rules}

U kunt deze limieten en regels controleren en begrijpen wanneer u de frequentie en frequentie wilt toepassen op kenmerken in uw segmenten.

### Recente

<table id="table_026064124C694D75B7A960457D50170B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limiet of regel </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Minimumwaarde</b> </p> </td> 
   <td colname="col2"> <p>De frequentie moet groter zijn dan 0. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b>Typen sporen</b> </p> </td> 
   <td colname="col2"> <p>U kunt recentiecontroles op regel-gebaseerde en omslageigenschappen slechts toepassen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Treinen van derden</b> </p> </td> 
   <td colname="col2"> <p>U kunt geen recentieregels op individuele derdeattributen of handelsgroepen plaatsen die derdetrekken bevatten. De frequentie en de frequentie zijn alleen van toepassing op uw eigen kenmerken. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Frequentie

<table id="table_EBD621D26C8B4D03933E8C0753C892A7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Limiet of regel </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Treinen van derden</b> </p> </td> 
   <td colname="col2"> <p>U kunt geen frequentieregels instellen voor individuele eigenschappen van derden of groepen van handelsmerken die eigenschappen van derden bevatten. De frequentie en de frequentie zijn alleen van toepassing op uw eigen kenmerken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Typen sporen</b> </p> </td> 
   <td colname="col2"> <p>U kunt frequentiecontroles op regel-gebaseerde en omslageigenschappen slechts toepassen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Recente vereisten</b> </p> </td> 
   <td colname="col2"> <p>U kunt frequentievereisten configureren <i>zonder</i> de noodvereisten te configureren. Stel gewoon een frequentiewaarde in en laat het veld voor recentie leeg. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Regels voor samenvoegen van profielen</b> </p> </td> 
   <td colname="col2"> <p>Zie Frequentie <a href="../../faq/faq-profile-merge.md#trait-freq-device-rules"> overtrekken, Externe apparaatgrafieken en Regels</a>voor het samenvoegen van profielen. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Voorbeelden van recentie {#recency-examples}

Hieronder volgen twee voorbeelden van de werking van recentiepunten, afhankelijk van uw selectie in de gebruikersinterface:

### Een operator gebruiken die kleiner is dan of gelijk is aan (&lt;=)

![Kleiner dan gelijk aan](assets/less-than-equal-to.png)

In dit voorbeeld selecteert u de operator &lt;=, zoals wordt weergegeven in de schermafbeelding. Dit kwalificeert uw gebruiker voor het segment als zij voor om het even welk van de drie eigenschappen minstens drie keer binnen de laatste vijf dagen in aanmerking komen. De tijdlijn hieronder toont de segmentkwalificatie op het moment dat het segment wordt gemaakt, op 1 oktober en tien dagen later.

![Laatste vijf dagen](assets/last-5-days.png)

### Een operator (=>) gebruiken die groter is dan of gelijk is aan

![Groter dan gelijk aan](assets/greater-than-equal-to.png)

In dit voorbeeld selecteert u de operator =>, zoals in de schermafbeelding wordt getoond. Dit kwalificeert uw gebruiker voor het segment als zij voor om het even welk van de drie eigenschappen minstens driemaal in aanmerking komen tussen hun eerste kwalificatie op het platform van de Manager van de Publiek en de besnoeiingstijd vijf dagen geleden. De tijdlijn hieronder toont de segmentkwalificatie op het moment dat het segment wordt gemaakt, op 1 oktober en tien dagen later.

![Eerdere kwalificatie](assets/earlier-qualification.png)


## Voorbeelden van frequentiecortering {#frequency-capping}

De frequentie-begrenzende uitdrukkingen omvatten alle gebruikers het waarvan aantal karakterverwezenlijking onder een gewenste waarde is. Hier volgen enkele voorbeelden van Rechts en Verkeerd:

* Verkeerd - De uitdrukking `frequency([1000T]) <= 5` omvat alle gebruikers die het bezit met identiteitskaart &quot;1000&quot;een maximum van vijf keer hebben gerealiseerd maar omvat ook gebruikers die het bezit niet hebben gerealiseerd. Daarom bevestigt de Manager van de Publiek deze uitdrukking om prestatiesredenen niet, aangezien het teveel gebruikers voor het segment zou kwalificeren.

* Rechts - Als u alle gebruikers wilt omvatten die het bezit met identiteitskaart &quot;1000&quot;een maximum van vijf keer hebben gerealiseerd, voeg een andere voorwaarde aan de uitdrukking toe, om ervoor te zorgen de gebruikers voor het bezit minstens eens hebben gekwalificeerd:  `frequency([1000T]) >= 1  AND  frequency([1000T]) <= 5`

* Rechts - Als u eisen voor recentie/frequentie wilt hebben die kleiner zijn dan een bepaald aantal tijden of dagen, voegt u die eigenschap samen met een `AND` operator. Met behulp van het voorbeeld in het eerste opsommingsteken wordt deze expressie geldig wanneer deze wordt gecombineerd met een ander kenmerk, zoals hier wordt getoond: `frequency([1000T]) <= 5 AND isSiteVisitorTrait`.

* Rechts - Voor het gebruiken van gebruiksgevallen voor het beperken van de advertentiefrequentie kunt u een segmentregel tot stand brengen gelijkend op dit: `(frequency([1000T] <= 2D) >= 5)`. Deze expressie omvat alle gebruikers die de eigenschap met de id &quot;1000&quot; in de afgelopen 2 dagen ten minste vijf keer hebben gerealiseerd. De vastgestelde frequentie die door dit segment naar de advertentieserver met een `NOT` reeks op het segment in de advertentieserver wordt begrensd te verzenden. Deze benadering bereikt betere prestaties [!DNL Audience Manager] terwijl het dienen van het zelfde doel voor frequentiecontrole.

>[!MORELIKETHIS]
>
>* [Besturingselementen voor Segment Builder: Sectie Traits](../../features/segments/segment-builder.md#segment-builder-controls-traits)
>* [Code Syntax used in the Segment Expression Editor](../../features/segments/segment-code-syntax.md)

